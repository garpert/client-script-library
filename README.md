

<img align="right" height="48" src="https://confluence.jetbrains.com/download/attachments/54334539/TeamCity48.png?version=1&modificationDate=1450097890320&api=v2">

# TeamCity.GitHub
===============
Integration of TeamCity and GitHub. Supports TeamCity 7.1 and newer [Build Script Interaction with TeamCity](https://confluence.jetbrains.com/display/TCD9/Build+Script+Interaction+with+TeamCity)

# Client-Script-Library
Buggered if I can find a way to commit an auto generated client script library to github, so that I can generate a bower package during the service build, inside teamcity.... First world IT problems

About the Plugin
================
The purpose of creating this plugin is to support integration with the [GitHub Change Status API](https://github.com/blog/1227-commit-status-api) in TeamCity, which allows TeamCity to automatically attach build statuses to GitHub pull requests.

The plugin is described in more detail in the following blog posts:
- http://blog.jonnyzzz.name/2012/09/reporting-change-status-to-github.html
- http://blog.jonnyzzz.name/2012/09/github-status-api-in-teamcity-update.html
- http://blog.jonnyzzz.name/2013/04/github-change-status-on-branches.html
 
Bower - A package manager for the web
=====================================

Bower needs resources for its maintenance. Please fill [this form](https://docs.google.com/forms/d/1i-Opb-uPdqUBBZQSbngv3Y3bfolG1gbBvtRLfxMnzRE/viewform?c=0&w=1) if you think you can help.

[![Build Status](https://travis-ci.org/bower/bower.svg?branch=master)](https://travis-ci.org/bower/bower)
[![Windows Build](https://ci.appveyor.com/api/projects/status/jr6vfra8w84plh2g/branch/master?svg=true)](https://ci.appveyor.com/project/sheerun/bower/history)
[![Coverage Status](https://img.shields.io/coveralls/bower/bower.svg)](https://coveralls.io/r/bower/bower?branch=master)
[![Discord chat](https://img.shields.io/badge/discord-join%20chat%20%E2%86%92-brightgreen.svg?style=flat)](https://discord.gg/0fFM7QF0KpZRh2cY)
[![Issue Stats](http://issuestats.com/github/bower/bower/badge/pr?style=flat)](http://issuestats.com/github/bower/bower)
[![Issue Stats](http://issuestats.com/github/bower/bower/badge/issue?style=flat)](http://issuestats.com/github/bower/bower)

<img align="right" height="300" src="http://bower.io/img/bower-logo.png">


Installation and Configuration
==============================
First, download the [latest build of the plugin](http://teamcity.jetbrains.com/guestAuth/repository/download/bt398/lastest.lastSuccessful/teamcity.github.zip), which is configured for continuous integration on TeamCity [here](http://teamcity.jetbrains.com/viewType.html?buildTypeId=bt398&tab=buildTypeStatusDiv).

**NOTE** Ensure that your download of the `.zip` file is valid - you may be redirected to the login page when using `curl` or `wget`.

Next, put the downloaded `.zip` file into the `<TeamCity Data Directory>/plugins` folder and restart the TeamCity server. You can also upload the .zip directly by clicking "Upload plugin zip" in the Plugins List section of the Administration settings in TeamCity's web interface.

After restarting the server, the plugin should show up as an external plugin in the Plugins List section of the Administration settings.
<ul>
<li><a href="http://prinzhorn.github.io/skrollr/">The "main" example</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/classic.html">"Classic" parallax with different sections and parallax images between the gaps</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/anchors.html">Demonstrating different anchors</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/anchor_target.html">Demonstrating data-anchor-target</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/pausing.html">Pausing the scrolling for a moment to do other animations</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/path.html">Drawing a SVG path</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/circular_motion.html">Using two custom easing functions to create a circular motion</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/bg_constant_speed_less.html">Parallax background with constant speed</a></li>
<li><a href="http://prinzhorn.github.io/skrollr/examples/gradientsmotherfucker.html">gradientsmotherfucker</a></li>
</ul>

To use the plugin with one of your TeamCity projects, ensure that your VCS root branch specification includes pull requests:

`+:refs/pull/(*/head)` (build number will include `/head`)

or 

`+:refs/pull/(*)/head` (build number will not include `/head`)

**Note:** It is also possible to use `+:refs/pull/(*/merge)`, but not recommended. There is some risk that this spec will cause a feedback loop of builds that will bog down your TeamCity server. [See this bug report](http://youtrack.jetbrains.com/issue/TW-33455) for more information.

Finally, add a new Build Feature to your project's configuration. Choose "Report change status to GitHub" from the list, fill in the necessary info in the dialog, and you should be good to go!

Branches
========
<audio controls>
  <source src="http://media.w3.org/2010/07/bunny/04-Death_Becomes_Fur.mp4" type='audio/mp4' />
  <source src="http://media.w3.org/2010/07/bunny/04-Death_Becomes_Fur.oga" type='audio/ogg; codecs=vorbis' />
  <p>Your user agent does not support the HTML5 Audio element.</p>
</audio>
### Windows users

To use Bower on Windows, you must install
[Git for Windows](http://git-for-windows.github.io/) correctly. Be sure to check the
options shown below:

<img src="https://cloud.githubusercontent.com/assets/10702007/10532690/d2e8991a-7386-11e5-9a57-613c7f92e84e.png" width="534" height="418" alt="Git for Windows" />

<img src="https://cloud.githubusercontent.com/assets/10702007/10532694/dbe8857a-7386-11e5-9bd0-367e97644403.png" width="534" height="418" alt="Git for Windows" />

Note that if you use TortoiseGit and if Bower keeps asking for your SSH
password, you should add the following environment variable: `GIT_SSH -
C:\Program Files\TortoiseGit\bin\TortoisePlink.exe`. Adjust the `TortoisePlink`
path if needed.

Ubuntu users

### To use Bower on Ubuntu, 
you might need to link `nodejs` executable to `node`:
```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```
## Bower Configuration

 can be configured using JSON in a `.bowerrc` file. Read over available options at [bower.io/docs/config](http://bower.io/docs/config).


## Support
* [Discord chat](https://discordapp.com/channels/130266017879293952)
* [Discord chat](https://discord.gg/0fFM7QF0KpZRh2cY)
* [StackOverflow](http://stackoverflow.com/questions/tagged/bower)
* [Mailinglist](http://groups.google.com/group/twitter-bower) - twitter-bower@googlegroups.com

## Contributing

We welcome [contributions](https://github.com/bower/bower/graphs/contributors) of all kinds from anyone. Please take a moment to review the [guidelines for contributing](CONTRIBUTING.md).

* [Bug reports](https://github.com/bower/bower/wiki/Report-a-Bug)
* [Feature requests](CONTRIBUTING.md#features)
* [Pull requests](CONTRIBUTING.md#pull-requests)

## NOTE

Note that on Windows for tests to pass you need to configure Git before cloning:
<div class="article js-hide-during-search">

        <h2>Importing a Git repository using the command line</h2>

        <div id="article-platform-nav">
  <ul>
    <li class="platform-mac">
      <a href="#platform-mac" data-platform="mac">
        mac
      </a>
    </li>
    <li class="platform-windows">
      <a href="#platform-windows" data-platform="windows">
        windows
      </a>
    </li>
    <li class="platform-linux">
      <a href="#platform-linux" data-platform="linux">
        linux
      </a>
    </li>
    <li class="platform-all">
      <a href="#platform-all" data-platform="all">
        all
      </a>
    </li>
  </ul>
</div>


        <div class="article-body content-body wikistyle markdown-format">
          <div class="intro">

          

          </div>

          <div class="intro">

<p>If <a href="/articles/importing-from-other-version-control-systems-to-github">GitHub's import tool</a> is not suitable for your purposes, such as if your existing code is hosted on a private network, then we recommend importing using the command line.</p>

</div>

<p>Before you start, make sure you know:</p>

<ul>
<li>Your GitHub user name.</li>
<li>The clone URL for the external repository, such as <code>https://otherhost.com/user/repo.git</code> or <code>git://otherhost.org/user/repo.git</code> (perhaps with a <code>user@</code> in front of the <code>otherhost.org</code> domain name).</li>
</ul>

<div class="alert tip">

<p>For purposes of demonstration, we'll use:</p>

<ul>
<li>An external account named <strong>extuser</strong>
</li>
<li>A GitHub personal user account named <strong>ghuser</strong>
</li>
<li>A GitHub repository named <strong>repo.git</strong>
</li>
</ul>

</div>

<ol>
<li>
<a href="/articles/creating-a-new-repository">Create a new repository on GitHub</a>. You'll import your external Git repository to this new repository.</li>
<li>
<p>On the command line, make a "bare" clone of the repository using the external clone URL. This creates a full copy of the data, but without a working directory for editing files, and ensures a clean, fresh export of all the old data.</p>

<pre class="command-line"><span class="command">git clone --bare https://githost.org/<em>extuser</em>/<em>repo.git</em></span>
<span class="comment"># Makes a bare clone of the external repository in a local directory</span>
</pre>
</li>
<li>
<p>Push the locally cloned repository to GitHub using the "mirror" option, which ensures that all references, such as branches and tags, are copied to the imported repository.</p>

<pre class="command-line"><span class="command">cd *repo.git*</span>
<span class="command">git push --mirror https://github.com/<em>ghuser</em>/<em>repo.git</em></span>
<span class="comment"># Pushes the mirror to the new GitHub repository</span>
</pre>
</li>
<li>
<p>Remove the temporary local repository.</p>

<pre class="command-line"><span class="command">cd ..</span>
<span class="command">rm -rf <em>repo.git</em></span>
</pre>
</li>
</ol>
        </div>

        <div class="support-footer">
          <ul class="article-footer button-nav">
            
              <li><a href="https://github.com/contact" class="minibutton">
                  <span class="octicon octicon-comment-discussion"></span>
                  Contact a human
                </a>
              </li>
            
          </ul>
        </div>
      </div>

```
git config --global core.autocrlf input

<div class="article js-hide-during-search">

        <h2>Importing a Git repository using the command line</h2>

        <div id="article-platform-nav">
  <ul>
    <li class="platform-mac">
      <a href="#platform-mac" data-platform="mac">
        mac
      </a>
    </li>
    <li class="platform-windows">
      <a href="#platform-windows" data-platform="windows">
        windows
      </a>
    </li>
    <li class="platform-linux">
      <a href="#platform-linux" data-platform="linux">
        linux
      </a>
    </li>
    <li class="platform-all">
      <a href="#platform-all" data-platform="all">
        all
      </a>
    </li>
  </ul>
</div>


        <div class="article-body content-body wikistyle markdown-format">
          <div class="intro">

          

          </div>

          <div class="intro">

<p>If <a href="/articles/importing-from-other-version-control-systems-to-github">GitHub's import tool</a> is not suitable for your purposes, such as if your existing code is hosted on a private network, then we recommend importing using the command line.</p>

</div>

<p>Before you start, make sure you know:</p>

<ul>
<li>Your GitHub user name.</li>
<li>The clone URL for the external repository, such as <code>https://otherhost.com/user/repo.git</code> or <code>git://otherhost.org/user/repo.git</code> (perhaps with a <code>user@</code> in front of the <code>otherhost.org</code> domain name).</li>
</ul>

<div class="alert tip">

<p>For purposes of demonstration, we'll use:</p>

<ul>
<li>An external account named <strong>extuser</strong>
</li>
<li>A GitHub personal user account named <strong>ghuser</strong>
</li>
<li>A GitHub repository named <strong>repo.git</strong>
</li>
</ul>

</div>

<ol>
<li>
<a href="/articles/creating-a-new-repository">Create a new repository on GitHub</a>. You'll import your external Git repository to this new repository.</li>
<li>
<p>On the command line, make a "bare" clone of the repository using the external clone URL. This creates a full copy of the data, but without a working directory for editing files, and ensures a clean, fresh export of all the old data.</p>

<pre class="command-line"><span class="command">git clone --bare https://githost.org/<em>extuser</em>/<em>repo.git</em></span>
<span class="comment"># Makes a bare clone of the external repository in a local directory</span>
</pre>
</li>
<li>
<p>Push the locally cloned repository to GitHub using the "mirror" option, which ensures that all references, such as branches and tags, are copied to the imported repository.</p>

<pre class="command-line"><span class="command">cd *repo.git*</span>
<span class="command">git push --mirror https://github.com/<em>ghuser</em>/<em>repo.git</em></span>
<span class="comment"># Pushes the mirror to the new GitHub repository</span>
</pre>
</li>
<li>
<p>Remove the temporary local repository.</p>

<pre class="command-line"><span class="command">cd ..</span>
<span class="command">rm -rf <em>repo.git</em></span>
</pre>
</li>
</ol>
        </div>

        <div class="support-footer">
          <ul class="article-footer button-nav">
            
              <li><a href="https://github.com/contact" class="minibutton">
                  <span class="octicon octicon-comment-discussion"></span>
                  Contact a human
                </a>
              </li>
            
          </ul>
        </div>
      </div>
```

## License

Copyright (c) 2015 Twitter and [other contributors](https://github.com/bower/bower/graphs/contributors)

Licensed under the MIT License
