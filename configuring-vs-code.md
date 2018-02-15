# Configuring VS Code to use XDebug

In VS Code, go to `Debug > Add Configuration...`. If it asks, create a new PHP configuration.![](/assets/Screen Shot 2018-02-15 at 10.18.52.png)

VS Code will generate a boilerplate file at `.vscode/launch.json`. One of these configuration entries will be labeled `Listen for XDebug`. The default values are fine here, but you'll need to add a line so that the configuration looks like this:

```
{
  "name": "Listen for XDebug",
  "type": "php",
  "request": "launch",
  "port": 9000,
  "pathMappings": {
    "/var/www/[your docroot here]": "${workspaceRoot}"
  }
}
```

Note that you will need to change the key of your `pathMappings` object to match the folder in `/var/www` that is running the site. Also, if you have mapped a subfolder of the repository as your guest docroot \(ie. you set your Vagrant config to load `/path/to/repo/docroot` on your host as `/var/www/remote` on your guest\) you will need to set the value of the `pathMappings` object to `${workspaceRoot}/docroot`.

