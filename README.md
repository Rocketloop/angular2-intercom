# Angular Intercom

[![npm](https://img.shields.io/npm/v/ng-intercom.svg)](https://www.npmjs.com/package/ng-intercom) [![npm](https://img.shields.io/npm/dm/ng-intercom.svg)](https://www.npmjs.com/ng-intercom) [![Maintenance](https://img.shields.io/maintenance/yes/2017.svg)]()

This is an Intercom wrapper for Angular 2+ with dependency injection for universal applications.

It supports all documented intercom methods.

### BETA VERSION

`master` is now hosting the 1.0.0 beta version of `ng-intercom`. If you need to make changes to the latest stable version, please PR against `0.x.x`. If you need to use the last 0.x version, please run `npm install --save --save-exact ng-intercom@0.2`.

If you find issues with this version, please file an issue as soon as possible so we can take a look at it. We appreciate your cooperation!

### Installation

This package is on NPM, so just run
 ```sh
$ npm install ng-intercom@beta --save
 ```

### Configuration

1. Import `IntercomModule` to `app.module.ts`. The module will automatically include the APP_ID instantiation, so you DO NOT need to copy the install script from Intercom and place it in your `index.html`.

```ts
import { IntercomModule } from 'ng-intercom';

@NgModule({
  imports: [
    ...
    IntercomModule.forRoot({
      app_id: <app_id>
    })
    ...
  ]
})
export class AppModule { }
```

2. Use in your components/directives/whatever you want!

```ts
// App
import { Component, OnInit } from '@angular/core';
import { Intercom } from 'ng-intercom';

@Component({
  selector: 'app',
  template: `...`
})
export class AppComponent implements OnInit {
  constructor(
    public intercom: Intercom
  ){}

  ngOnInit() {
    this.intercom.init({
      app_id: <app_id>,
      // Supports all optional configuration.
      widget: {
        "activator": "#intercom" 
      }
    });
  }
}
```

### Development
To compile, just run `npm run build`. It will compile into the dist directory. 

### Credits
Maintained by [Scott Wyatt](https://github.com/scott-wyatt) and [Wilson Hobbs](https://www.twitter.com/wbhob) in 2017 with contributions from [Florian Reifschneider](https://github.com/flore2003), [Devon Sams](https://www.twitter.com/POS1TRON), and [Humberto Rocha](https://github.com/humrochagf)
