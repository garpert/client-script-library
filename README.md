# client-script-library
Buggered if I can find a way to commit an auto generated client script library to github, so that I can generate a bower package during the service build, inside teamcity.... First world IT problems
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

### Ubuntu users

To use Bower on Ubuntu, you might need to link `nodejs` executable to `node`:

```
sudo ln -s /usr/bin/nodejs /usr/bin/node
```

## Configuration

Bower can be configured using JSON in a `.bowerrc` file. Read over available options at [bower.io/docs/config](http://bower.io/docs/config).


## Support

* [Discord chat](https://discord.gg/0fFM7QF0KpZRh2cY)
* [StackOverflow](http://stackoverflow.com/questions/tagged/bower)
* [Mailinglist](http://groups.google.com/group/twitter-bower) - twitter-bower@googlegroups.com

## Contributing

We welcome [contributions](https://github.com/bower/bower/graphs/contributors) of all kinds from anyone. Please take a moment to review the [guidelines for contributing](CONTRIBUTING.md).

* [Bug reports](https://github.com/bower/bower/wiki/Report-a-Bug)
* [Feature requests](CONTRIBUTING.md#features)
* [Pull requests](CONTRIBUTING.md#pull-requests)


Note that on Windows for tests to pass you need to configure Git before cloning:

```
git config --global core.autocrlf input
```

## License

Copyright (c) 2015 Twitter and [other contributors](https://github.com/bower/bower/graphs/contributors)

Licensed under the MIT License
