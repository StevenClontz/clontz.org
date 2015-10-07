---
kind: article
title: "Visual Studio 2012 - Setting IIS Express to host site at subdirectory"

created_at: 2014-01-23 10:07

---

UPDATE: This is a terrible way to get this working, as I thankfully discovered.
[See my 2014-02-04 post for details.](/blog/2014/02/04/visual-studio-2012-and-git-slash-bitbucket/)

It took me forever and a day to get this functional, so I wanted to share the 
problem and solution in case it helps someone else out there trying to 
Google their way to solve a similar puzzle.

### Problem

I inherited a ASP.NET website which was hosted at 
`https://www.domain.com/subdirectory/`. The site was coded with absolute 
links throughout of the form `/subdirectory/path/to/resource`. However, when
Visual Studio 2012 spins up IIS Express to host the site locally, the site
is hosted at `http://localhost:port/`. You can see the issue: all the 
references to `/subdirectory/etc` are now broken in the application, which 
makes previewing the site a pain.

<!-- more -->

### Solution

I don't know if there's a more elegant way of solving this problem, but here's
what ended up working for me. I did this through the Visual Studio IDE, but 
it was rather inelegant (I had to pretend to create a new project to get to 
the only dialog box that would allow me to do it). But ultimately, I think 
what it ended up doing was editing a file called `applicationhost.config` 
under the `IISExpress\config\` folder.  Here's the part that's important:

``` xml
<sites>
    <site name="thesite" id="2">
        <application path="/" applicationPool="Clr2IntegratedAppPool">
            <virtualDirectory path="/" physicalPath="C:\path\on\disk\to\site" />
        </application>
        <bindings>
            <binding protocol="http" bindingInformation="*:49673:localhost" />
        </bindings>
    </site>
    <siteDefaults>
        <logFile logFormat="W3C" directory="%IIS_USER_HOME%\Logs" />
        <traceFailedRequestsLogging directory="%IIS_USER_HOME%\TraceLogFiles" enabled="true" maxLogFileSizeKB="1024" />
    </siteDefaults>
    <applicationDefaults applicationPool="Clr4IntegratedAppPool" />
    <virtualDirectoryDefaults allowSubDirConfig="true" />
</sites>
```

When previewing a site in the browser, Visual Studio opens up the file 
assuming it's hosted from the root. So, the solution is to add a second
`virtualDirectory` which mirrors all the files served at the root at the
desired subdirectory, such as `\subdirectory`. Editing the contents of 
`<application>` like so solves the problem:

``` xml
<application path="/" applicationPool="Clr2IntegratedAppPool">
    <virtualDirectory path="/" physicalPath="C:\path\on\disk\to\site" />
    <virtualDirectory path="/subdirectory" physicalPath="C:\path\on\disk\to\site" />
    <!-- note that both physicalPaths are the same! -->
</application>
```

It's a hack, but it works. The more elegant solution would be to allow the 
original virtualDirectory at `\` be eliminated and only host at `\subdirectory`,
however, this messes with Visual Studio's project file in a way that I don't
want to try and fix. I can preview things now, and that's a start!


