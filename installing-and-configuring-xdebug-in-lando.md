# Installing and Configuring XDebug in Lando

The Lando documentation contains [an excellent tutorial](https://docs.devwithlando.io/tutorials/lando-with-vscode.html) on configuring XDebug within Lando and then setting up VSCode properly. Remember that you need to have the following in your `.lando.yml` file:

```yaml
config:
  xdebug: true
```

One other troubleshooting tip: if you've included that line in your config file, and the `launch.json` file is configured properly, and you don't know if XDebug is being turned on or not, you can use `phpinfo()` on a page and check that the `php.ini` file you created is actually being loaded. I used the filename `xdebug.vscode.ini` so I'd be able to differentiate that file from anything else that might be automatically loaded.

