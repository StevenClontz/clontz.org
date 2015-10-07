---
title: Added create_blog command
created_at: 2014-03-11 13:56
kind: article
---

While there were a few options out there for creating a nanoc item 
representing an "article" for use with `Nanoc::Helpers::Blogging`, I
rolled one myself since I had a pretty barebones need:

<!-- more -->

~~~ ruby
name        'create-blog'
usage       'create-blog [name] -d [date]'
aliases     :cb, :create_blog
summary     'creates a blog post item'
description <<-DESC 
Creates /content/_posts/{year}-{month}-{date}-{slug}.md for editing
as a blog post. The slug comes from the given title, and the date
can be optionally provided or derived from the current date.
DESC

flag :h, :help, 'show help for this command' do |value, cmd|
  puts cmd.help
  exit 0
end

opt :c, :created, 'provide created_at datetime', argument: :optional

run do |opts, args, cmd|
  if opts[:created]
    date = opts[:created]
    begin
      created_at = DateTime.parse(date)
    rescue 
      puts "Invalid datetime (#{date})! Using current time instead."
      created_at = DateTime.now
    end
  else
    created_at = DateTime.now
  end
  
  created_date = created_at.strftime("%Y-%m-%d") 
  created_time = created_at.strftime("%Y-%m-%d %H:%M") 

  title = args[0]
  require 'slugify'
  slug = title.slugify
  
  file = "content/_posts/#{created_date}-#{slug}.md"

  puts "Creating new blog post: #{file}"
  open(file, 'w') do |blog|
    blog.puts "---"
    blog.puts "title: #{title}"
    blog.puts "created_at: #{created_time}"
    blog.puts "kind: article"
    blog.puts "---\n\n"
  end
end
~~~

Toss the above into `/commands/create-blog.rb`, install the `slugify` gem,
and run `nanoc create_blog "Hello world"` to try it out.