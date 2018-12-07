---
title: Technologies
permalink: /technologies/
---

## Angular

The Angular IO project can be found at the [Angular.IO](https://angular.io/) website. The guide is at [Angular Guide](https://angular.io/docs/ts/latest/guide/)

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive/pipe/service/class/module`.

## TypeScript

* [Tutorial](https://www.typescriptlang.org/docs/handbook/basic-types.html)
* [See TypeScript in Action](https://www.typescriptlang.org/#download-links)

## Hammer.js

* [getting started](http://hammerjs.github.io/getting-started/)
* [gestures in an angular application](https://blog.angularindepth.com/gestures-in-an-angular-application-dde71804c0d0)
* [hammerjs angular 5 animations](https://angularfirebase.com/lessons/hammerjs-angular-5-animations-for-mobile-gestures-tutorial/)

Disable Firefox Pinch to zoom browser function:

Inside `about:config` change:

* `browser.gesture.pinch.in` to empty string
* `browser.gesture.pinch.in.shift` to empty string
* `browser.gesture.pinch.out` to empty string
* `browser.gesture.pinch.out.shift` to empty string
* `browser.gesture.pinch.threshold` to `-1`

## Web Workers

* [partial image manipulation canvas and webworkers](http://www.smartjava.org/content/partial-image-manipulation-canvas-and-webworkers)
* [parallelize jobs using web workers and threadpool](http://www.smartjava.org/content/html5-easily-parallelize-jobs-using-web-workers-and-threadpool)
* [bl.ocks.org example](https://bl.ocks.org/mbostock/01ab2e85e8727d6529d20391c0fd9a16)
* [using webworkers for safe concurrent javascript](https://blog.logrocket.com/using-webworkers-for-safe-concurrent-javascript-3f33da4eb0b2)
* [webworker with typescript](https://github.com/Qwaz/webworker-with-typescript)
* [typescript webworker](https://github.com/zlepper/typescript-webworker)

````javascript
const workerTask = new WorkerTask(workerPath, (message) => {
    const item = message.data;
    if (item === undefined) { console.log('no item'); return; }
    // don't draw glyphs that lay outside the view
    if (this.helper.checkClipping(item.position)) {
    return;
    }

    this.context.beginPath();
    this.context.moveTo(item.position.x, item.position.y);

    const data = this.getFeaturesForItem(item);

    if (this.itemConfirmsToFilters(item.id, data.features)) {
    // draw highlighted glyph after all other glyphs to render it above all others (independent of selection)
    // necessary to draw a selected and highlighted glyph above other selected glyphs
    if (item.id !== this.configuration.idOfHoveredGlyph ||
        (!this.configuration.showHighlightInNormalMode && !this.configuration.useDragSelection)) {
        this.drawSingleGlyph(item.position, feature, null, false, false, 0);
    }
    } else {
    this.drawSingleGlyph(item.position, feature, 1.0, true, item.id === this.configuration.idOfHoveredGlyph, 0);
    }
}, d);
this.pool.addWorkerTask(workerTask);
````

## File Uploads

* [angular file uploader](https://www.npmjs.com/package/angular-file-uploader)
* [angular material fileupload](https://www.npmjs.com/package/angular-material-fileupload)
* [angular material fileupload github.io](https://nishantmc.github.io/angular-material-fileupload.github.io/index.html)
* [angular material fileupload codepen](https://codepen.io/shepard_one/pen/VKwwVR)
* [uploading files in angular2](https://nehalist.io/uploading-files-in-angular2/)

## Using SASS in Angular Projects

* [SASS Reference Guide](https://sass-lang.com/)
* [BEM Methodology](http://getbem.com/)
* [Using SASS with Angular CLI](https://scotch.io/tutorials/using-sass-with-the-angular-cli)
* [Theming Angular Material](https://material.angular.io/guide/theming-your-components)
* [Pretty Checkboxes](https://lokesh-coder.github.io/pretty-checkbox/)
* [Material Icons Guide](https://google.github.io/material-design-icons/)