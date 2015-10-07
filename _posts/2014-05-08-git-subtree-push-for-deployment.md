---
title: "`git-subtree` for GitHub Pages deployment"
created_at: 2014-05-08 14:54
kind: article
---

Picking up Yeoman today, and in the process learned a slick trick
for GitHub Pages. A common pattern in both Nanoc and a Yeoman AngularJS
generated project is to have a built version of the site/app within
the project folder, but untracked. Previously, I set up a separate
Git repository within that subfolder in order to push to
`gh-pages` for publishing. But there's a better way.

<!-- more -->

Enter `git subtree`: rather than the process of maintaining a separate
repository for the build folder, Git is able to simply push it using
the existing repository. Here are the steps:

* First, build your project. For nanoc, this is `nanoc compile`
  (or just `nanoc`); for Grunt, this is `grunt build`.

* If your build folder is in `.gitignore`, then remove it. We will track
  changes to the built site alongside your source.

* Add the build folder to the repository with `git add build_folder`,
  replacing `build_folder` with `output`/`dist`/etc. as appropriate.
  Also add the new `.gitignore` with `git add .gitignore`.
  Commit your changes with `git commit -m "Added build folder"`.

* You're ready to deploy to GitHub Pages. Whenever you wish to deploy,
  make sure you've committed your changes to the repository (which should
  now include your build folder). Then it's as simple as:

~~~
    # replace build_folder as appropriate
    git subtree push --prefix build_folder origin gh-pages
~~~

Git pushes the subset of your repository corresponding to your build
folder to the `gh-pages` branch, which is then available at
`http://username.github.io/RepositoryName/`.

Since the subtree push command is rather verbose, I wrote a nanoc command
to handle it for my blog:
<https://github.com/StevenClontz/StevenClontz.com/blob/master/commands/deploy-ghpages.rb>

Credit goes to the Yeoman wiki for showing me the light: 
<https://github.com/yeoman/yeoman/wiki/Deployment>

### Addendum

One caveat here. Since `git subtree push` doesn't have a `--force` option,
you will have trouble on the first push if you have an existing `gh-pages`
branch. You can actually chain git commands together to fix this, thankfully.

    git push origin `git subtree split --prefix build_folder master`:gh-pages --force

Source: <http://stackoverflow.com/a/13403588/1607849>