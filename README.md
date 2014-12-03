Laptop
======

Laptop is a script to set up an OS X laptop for development.

Requirements
------------

We support:

* [OS X Mavericks (10.9)](https://itunes.apple.com/us/app/os-x-mavericks/id675248567)
* [OS X Yosemite (10.10)](https://www.apple.com/osx/)

Older versions may work but aren't regularly tested. Bug reports for older
versions are welcome.

Install
-------

Read, then run the script:

    bash <(curl -s https://raw.githubusercontent.com/bigbam505/laptop/master/mac) 2>&1 | tee ~/laptop.log

Debugging
---------

Your last Laptop run will be saved to `~/laptop.log`. Read through it to see if
you can debug the issue yourself. If not, copy the lines where the script
failed into a [new GitHub Issue](https://github.com/bigbam505/laptop/issues/new) for us. Or, attach the
whole log file as an attachment.

What it sets up
---------------

* [Homebrew] for managing operating system libraries
* [Git] for version control
* [vim] for a lightweight text editor from the console
* [Homebrew Cask] to install mac applications from the command line
* [Virtualbox] to interface with vagrant and docker virtual instances
* [Nvm] for node version managing
* [Slack] for team chat

[Homebrew]: http://brew.sh/

It should take less than 15 minutes to install (depends on your machine).

Laptop can be run multiple times on the same machine safely. It will upgrade
already installed packages and install and activate a new version of ruby (if
one is available).

Make your own customizations
----------------------------

Put your customizations in `~/.laptop.local`. For example, your
`~/.laptop.local` might look like this:

    #!/bin/sh

    brew tap caskroom/cask
    brew install brew-cask

    brew cask install dropbox
    brew cask install google-chrome
    brew cask install rdio

You should write your customizations such that they can be run safely more than
once. See the `mac` script for examples.

Credits
-------

![thoughtbot](http://thoughtbot.com/assets/tm/logo.png)

Laptop is maintained and funded by [thoughtbot, inc](http://thoughtbot.com/community).
The names and logos for thoughtbot are trademarks of thoughtbot, inc.

Thank you, [contributors](https://github.com/thoughtbot/laptop/graphs/contributors)!

Contributing
------------

Edit the `mac` file.

License
-------

Laptop is © 2011-2014 thoughtbot, inc. It is free software, and may be
redistributed under the terms specified in the LICENSE file.
