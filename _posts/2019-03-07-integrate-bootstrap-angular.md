---
layout: post
title: Integrate Bootstrap with Angular
---

Here's a step by step process on how you can install and integrate Bootstrap into your Angular project.

## Installation

Go to your project root (if you're not currently there) and run `npm install bootstrap` which installs the latest Bootstrap version which at the time of this writing is 4.3.1.

If you want to add Bootstrap in your `package.json` dependencies, add the `--save` flag to the command like so: `npm install bootstrap --save`.

If you have to install an older version, just specify it using `npm install <package_name>@<version_number>`, for example, `npm install bootstrap@3.3.7` to install Bootstrap version 3.3.7.

If you're not sure what versions are available out there, you can use `npm view bootstrap versions` which at the time of this writing will show the following:

```
[ '0.0.1',        
  '0.0.2',        
  '3.1.1',        
  '3.2.0',        
  '3.3.0',        
  '3.3.1',        
  '3.3.2',        
  '3.3.4',        
  '3.3.5',        
  '3.3.6',        
  '3.3.7',        
  '3.4.0',        
  '3.4.1',        
  '4.0.0-alpha.2',
  '4.0.0-alpha.3',
  '4.0.0-alpha.4',
  '4.0.0-alpha.5',
  '4.0.0-alpha.6',
  '4.0.0-beta',   
  '4.0.0-beta.2', 
  '4.0.0-beta.3', 
  '4.0.0',        
  '4.1.0',        
  '4.1.1',        
  '4.1.2',        
  '4.1.3',        
  '4.2.1',        
  '4.3.0',        
  '4.3.1' ]
```

## Integration

In your project root, open the `angular.json` file in your code editor and look for the `"styles"` array under the `"architect.build"` object and add `node_modules/bootstrap/dist/css/bootstrap.min.css` like so:

```
"styles": [
  "node_modules/bootstrap/dist/css/bootstrap.min.css"
]
```

Afterwards, run `ng serve` to compile the changes or if `ng serve` is already running, terminate it using `Ctrl + C` or `Cmd + C` if you're on a Mac and run `ng serve` again.

That's basically it! You can now use Bootstrap in your Angular project with all its glory.

---
