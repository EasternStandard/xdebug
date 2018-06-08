# Installing and Configuring XDebug in Vagrant

## Installing

XDebug should already be installed with the latest version of the `vagrant-lamp` repo. Ensure you have the most up-to-date copy of the repo and run `vagrant reload --provision devserver` from the `vagrant-lamp` directory.

To manually install XDebug, simple run `sudo apt-get install php-xdebug` from the Vagrant command line.

## Configuring

You will need to make these changes to four separate files:

* `/etc/php/5.6/mods-available/xdebug.ini`
* `/etc/php/7.0/mods-available/xdebug.ini`
* `/etc/php/7.1/mods-available/xdebug.ini`
* `/etc/php/7.2/mods-available/xdebug.ini`

Each of those files should contain the following configuration:

```text
zend_extension=xdebug.so
xdebug.remote_enable=1
xdebug.remote_connect_back=1
xdebug.remote_port=9000
xdebug.max_nesting_level=250
xdebug.remote_autostart=1
xdebug.remote_host=10.0.2.2
xdebug.default_enable=1
xdebug.remote_handler=dbgp
```

Once the changes have been made, run `sudo service apache2 restart` to apply the configuration.

