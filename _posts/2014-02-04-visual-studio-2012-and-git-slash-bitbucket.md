---
kind: article
title: "Visual Studio 2012 and Git / Bitbucket"

created_at: 2014-02-04 15:43

---

Another write-up for something I'm doing for work. Actually, this one
(incidentally) makes my last post obsolete, since it better solves the 
problem I had in the process of solving the main problem of this post.

This post will outline how I migrated an existing .NET (C#) website project
in Visual Studio 2012 to a version-controlled project powered by Git and
[Bitbucket.org](http://bitbucket.org). As usual, this is mostly for my own
documentation, but perhaps it will help someone searching for a similar 
problem/solution online.

<!-- more -->

The Solution I was dealing with had the website Project files stored in a
separate directory than the Solution itself.  Something like...

```
\project\project.sln   # solution file
\website\Default.aspx  # all website files
```

This is an issue for Git since it wants the entire project stored in the 
same folder. So the first order of business was to create a new Solution 
with all the files in the same folder. Here's how I did it.


### Setting up the new solution for Git

- I used `File > New Project` and 
`Templates > Other Project Types > Visual Studio Solutions` to create a
`Blank Solution`. Let's say I named it `MySolution` and stored it at 
`C:\MySolution\`. Do not check "Add to Source Control" yet.

- I used Windows Explorer to create a subfolder of `MySolution` called 
`mysite`. This was important, because many of the site's links were set up to 
point to `/mysite/foo.jpg`, and by setting up the project in this way the 
development server assumed I wanted the site hosted at 
`http://localhost:(someport)/mysite/`.

- I copied the website files from the existing website project into that 
folder. I'm new to Visual Studio, .NET, etc., but all the important site 
configurations needed were stored in `Web.config` in the Project root.

- I added the `mysite` folder as a Project by right-clicking the Solution and 
choosing `Add > Existing Web Site`. Through the file system, I browsed to the 
`mysite` folder, and clicked Open.

At this point the solution was up and running as needed for local development.
(Barring a few things like getting the SQL Server loaded into the IDE.)
Now it was time to get Visual Studio playing with Git.


### Setting up Git

- I understand that Visual Studio 2013 has Git built-in, but for 2012 I needed
to install a plugin. That was easy.

<http://visualstudiogallery.msdn.microsoft.com/abafc7d6-dcaa-40f4-8a5e-d6724bdb980c>

- To initialize the repository, I clicked the Solution and chose "Add Solution 
to Source Control", selecting "Git" as the source control system.

- From the `Team Explorer` Home, I followed a link to install the third-party 
command prompt tools. Visual Studio's implementation of Git is incomplete,
and even to set up the remote Bitbucket repository I needed to use a few
command line tricks. (Most of the day-to-day stuff is just fine done from
the GUI however.)

- I made my first commit of the project by right-clicking the Solution, and
clicking Commit. Entering the message `initial commit` and clicking Commit 
to confirm got me set up locally to use revision control.


### Working with Bitbucket

- I created a Bitbucket repository to push my existing project to. For 
discussion let's assume my username is `[username]` and the repo was called
`[reponame]`.

- From Team Explorer Home, I clicked "Unsynced Changes". As I said above,
I had to add the remote repository using the terminal. 
"Actions > Open in Command Prompt".

- Only a couple of lines were necessary however:

```
git remote add origin https://bitbucket.org/[username]/[reponame].git
git push -u origin --all
```

I had to enter my Bitbucket username and password, but other than that, I 
was set up! (Typically I prefer SSH over HTTPS in order to avoid 
authentication each time I want to use Git, but I don't know 
how to set that up in a Windows environment yet. The instructions I 
found at first glance implied it was tricky enough to just eschew the issue
altogether for now.)



### Workflow

I'll add a post later on the easiest way to do the initial setup of this 
project by pulling initially from the now-set-up Bitbucket repo once I've 
done it. But let's say that now both my coworker and I have gotten the 
Solution set up under Git revision control with the same Bitbucket remote.
(UPDATE: See below.)

Visual Studio has admittedly made it pretty simple to have us stay synced...
by providing a handy "Sync" button! `VIEW > Team Explorer` followed by 
`Unsynced Commits` brings up the appropriate dialog. By clicking Sync before
starting to work on the site, Git automatically pulls any changes on the 
Bitbucket server and merges them into the project. (Remember, since I haven't
set up SSH, each time the Sync button
is pressed I have to supply my username and password for Bitbucket.)

After changes have been 
made and published, I first have to Commit the changes to the project by 
doing the same process as above. Then, the work can be shared with my coworker 
by clicking Sync again. Git does a pull first to make sure there were no 
changes made on the remote repository while I was working, and then it pushes
my changes to the remote server.



### That's it.

Hopefully this will work well for us! I'll update this post with any changes
or tweaks we made.



### UPDATE: Setting up new solution for existing repo

Last bit: setting up a new solution based on the existing repo was no problem.
Pull up the Command Prompt or Git Bash per your preference and `cd` to the 
folder you want to store the solution in. Then run

```
git clone https://bitbucket.org/[username]/[reponame].git
```

Supplying your Bitbucket username/password will create a folder with your 
solution file and project files. Open it up in Visual Studio and you're 
ready to rock.






