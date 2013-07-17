#Preen

A Node.js module to preen unwanted files and packages installed via Bower.

Bower is great but some times it gives you more than you need. These days many packages define paths that are not required in production via the `bower.json` files `ignore` property but even then you may still get more than you need. Preens role is to remove any of those unwanted files/paths.

##A Basic Example
My projects `bower.json` file has jquery as a dependency.
```javascript
{
  "name": "myProject",
  "dependencies": {
    "jquery": "~2.0.3"
  }
}
```
which gives the following folder after running `bower install`  
![](https://raw.github.com/BradDenver/Preen/master/screenshots/basic.png)  
but all I really need for this project is the 4 javascript files.
So I update my `bower.json` to with a preen property as follows
```javascript
{
  "name": "myProject",
  "dependencies": {
    "jquery": "~2.0.3"
  },
  "preen": {
    "jquery": [
      "**.js"
    ]
  }
}
```
and then run `preen` to end up with  
![](https://raw.github.com/BradDenver/Preen/master/screenshots/basic2.png)

##Configuration
an array of minimatch filters

##Options
when running via the command line you can add a preview flag to see a list of all paths and if they will be deleted or kept
`preen --preview`  
![](https://raw.github.com/BradDenver/Preen/master/screenshots/preview.png)  
you can then run `preen` if you are happy to go ahead  
![](https://raw.github.com/BradDenver/Preen/master/screenshots/preview2.png)

##Grunt Task
while preen can be run via the command line it is well suited to running as a grunt task
eg.

##uses
readdirp