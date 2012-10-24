# Permissions watch dog

### Prerequisities

  * [ruby](http://www.ruby-lang.org/en/downloads/) (tested with v1.9.3)
  * [bundler](http://gembundler.com)

### Installation

    git clone git@github.com:darwin/permdog.git
    cd permdog
    bundle install

### Running

Run it in first terminal session:

    cd permdog
    mkdir -p /tmp/permdog-test/watched-folder
    mkdir -p /tmp/permdog-test/normal-folder
    ./bin/permdog

Test it in second terminal session:

    cd /tmp/permdog-test
    touch normal-folder/test.file
    ls -la normal-folder/test.file
    touch watched-folder/test.file
    ls -la watched-folder/test.file

The second ls should show 0777 rights set on `watched-folder/test.file`. You may check the verbose output in the first terminal session what happened.

Have fun!

## TODO

1. configured via some config file (multiple paths, ignores, latency, etc.)
2. [daemonization](http://daemons.rubyforge.org)
3. installer

#### MIT-style [license](https://raw.github.com/darwin/permdog/master/license.txt)