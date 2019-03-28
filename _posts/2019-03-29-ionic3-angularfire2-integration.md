---
layout: post
title: Integrate AngularFire2 with Ionic 3
---

Here’s a step by step process on how to integrate AngularFire2 into an Ionic 3 project.

## Installation

You can create an Ionic 3 project via the Ionic CLI if you don't already have one using the following command:
```
ionic start project_name blank --type=ionic-angular
```

Go to the project root and run the following commands to install AngularFire2 properly:
```
npm install angularfire2 firebase promise-polyfill --save
npm i rxjs@6 rxjs-compat@6 promise-polyfill --save
npm install -g typescript@latest
```

## Integration

Inside the `app.module.ts` file, make the following changes:

Add the following import declarations:
```javascript
import { AngularFireModule } from '@angular/fire';
import { AngularFireDatabaseModule, AngularFireDatabase } from '@angular/fire/database';
import { AngularFireAuthModule } from '@angular/fire/auth';
```

Then add those three to the `imports` array.
```javascript
imports: [
  AngularFireModule.initializeApp(firebaseConfig),
  AngularFireDatabaseModule,
  AngularFireAuthModule
],
```

Under the `AngularFireModule.initializeApp`, you may have noticed that you have to pass the firebase configuration object as an argument that looks something like this:
```javascript
var firebaseConfig = {
  apiKey: "AIzaSyA01NrGxzckRwE6sf_vL3cc7ueGMGXntRA",
  authDomain: "sample-project-825a8.firebaseapp.com",
  databaseURL: "https://sample-project-825a8.firebaseio.com",
  projectId: "sample-project-825a8",
  storageBucket: "sample-project-825a8.appspot.com",
  messagingSenderId: "117752906836"
};
```

Lastly, add the `AngularFireDatabase` to the `providers` array.
```javascript
providers: [
  AngularFireDatabase
]
```

## Usage

Inside a component, add the following to the import declarations:
```javascript
import { AngularFireDatabase } from '@angular/fire/database';
import { Observable } from 'rxjs';
```

You can now use firebase features in your project like so:
```javascript
this.db.list('/messages').push({
  message: "Hello world!"
});

this.db.list('/messages').valueChanges().subscribe((response) => {
  console.log(response);
}, (error) => {
  console.log(error);
});
```