# Client-Script-Library
Buggered if I can find a way to commit an auto generated client script library to github, so that I can generate a bower package during the service build, inside teamcity.... First world IT problems


TeamCity.GitHub
===============
Integration of TeamCity and GitHub. Supports TeamCity 7.1 and newer
(https://confluence.jetbrains.com/display/TCD9/Build+Script+Interaction+with+TeamCity)

<img align="right" height="48" src="https://confluence.jetbrains.com/download/attachments/54334539/TeamCity48.png?version=1&modificationDate=1450097890320&api=v2">

About the Plugin
================
The purpose of creating this plugin is to support integration with the [GitHub Change Status API](https://github.com/blog/1227-commit-status-api) in TeamCity, which allows TeamCity to automatically attach build statuses to GitHub pull requests.

The plugin is described in more detail in the following blog posts:
- http://blog.jonnyzzz.name/2012/09/reporting-change-status-to-github.html
- http://blog.jonnyzzz.name/2012/09/github-status-api-in-teamcity-update.html
- http://blog.jonnyzzz.name/2013/04/github-change-status-on-branches.html
 
# Bower - A package manager for the web

> Bower needs resources for its maintenance. Please fill [this form](https://docs.google.com/forms/d/1i-Opb-uPdqUBBZQSbngv3Y3bfolG1gbBvtRLfxMnzRE/viewform?c=0&w=1) if you think you can help.

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

To use the plugin with one of your TeamCity projects, ensure that your VCS root branch specification includes pull requests:

`+:refs/pull/(*/head)` (build number will include `/head`)

or 

`+:refs/pull/(*)/head` (build number will not include `/head`)

**Note:** It is also possible to use `+:refs/pull/(*/merge)`, but not recommended. There is some risk that this spec will cause a feedback loop of builds that will bog down your TeamCity server. [See this bug report](http://youtrack.jetbrains.com/issue/TW-33455) for more information.

Finally, add a new Build Feature to your project's configuration. Choose "Report change status to GitHub" from the list, fill in the necessary info in the dialog, and you should be good to go!

Branches
========<audio controls>
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

### Ubuntu users

To use Bower on Ubuntu, you might need to link `nodejs` executable to `node`:

```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

## Configuration

Bower can be configured using JSON in a `.bowerrc` file. Read over available options at [bower.io/docs/config](http://bower.io/docs/config).


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


```
git config --global core.autocrlf input
```

## License

Copyright (c) 2015 Twitter and [other contributors](https://github.com/bower/bower/graphs/contributors)

Licensed under the MIT License
