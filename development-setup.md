# Setting up the development environment

## XDebug and your IDE

[XDebug](http://xdebug.org) is the most commonly used debugger for php. It allows for all the general debugging activities such as breakpoints, step-throughs and even some profiling during runtime. The latter e.g. includes call-stack analyzations and memory allocations.

**Do not be scared its fairly straight forward, I just use too many words.**

### In short

- Locate `xdebug.so`
- Add `php.ini` configuration
- Add browser bookmarklets (PHPStorm)
- Configure your IDE

### Your PHP environment

All the major IDEs support an PHPStorm integration mostly supplied though bookmarklets in the browser to start a session between IDE and browser.

Setting it up is fairly easy but depends on the (W|M)amp stack you have running on your machine. Most of them come with a `xdebug.so` which is nothing more than a PHP extension.
If you're using MAMP on a Mac its somewhere around `/Applications/MAMP/bin/php/php5.4.4/lib/php/extensions/...` but on Windows it should be anywhere in your stack's installation as well.

After you located the extension you would have to find out which configuration file your PHP runtime is loading. Mostly your (M|W)AMP stack gives you the location somewhere in its configuration. Whenever you have the php-binary available in your path (on Mac) or defined as an environment variable (on windows), you can just type `php --ini` in your command prompt and it will show you what *.ini-files it is loading.

That said, up to the next step: changing the `php.ini` to load the `xdebug.so`. Add a section to your ini which looks something like this (if not existent):

```php
[xdebug]
zend_extension="/Applications/MAMP/bin/php/php5.4.4/lib/php/extensions/xdebug.so"
xdebug.remote_host=127.0.0.1
xdebug.remote_enable = 1
```

### PHPStorm specfics

Now, if you are using PHPStorm add a line with `xdebug.idekey = "PHPSTORM"`. Whatever and if you need for other IDEs is something you would have to look up yourself. The same applies for IDE further IDE configuration but that stuff is fairly easy to find and well covered on the interwebs. Before you fiddle with your IDE do not forget to restart your Apache/stack.

Now add the [bookmarks](http://www.jetbrains.com/phpstorm/marklets/) in your browser. These allow you to start/end a session.

Now configure PHPStorm to have a PHP interpreter. Yes, thats the path to your php executable. On Windows the `*.exe` on mac the normal binary under your Mamp folder. If you installed it the good way its even in your path and should just be `/usr/bin` or even `/usr/local/bin`. Now pick XDebug as the debugger and leave the rest as is.

- [Official JetBrains PHPStorm article](http://confluence.jetbrains.com/display/PhpStorm/Zero-configuration+Web+Application+Debugging+with+Xdebug+and+PhpStorm)