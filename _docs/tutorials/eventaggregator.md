---
title: Event Aggregator Pattern
permalink: /eventaggregator/
description: Tutorial for using the event aggregator pattern in Glyphboard
---

Further Reading:

* [angular 2 cross modules communication eventaggregator](http://abusanad.net/2016/08/20/angular-2-cross-modules-communication-eventaggregator/)
* [Event Aggregator Pattern](https://www.codeproject.com/Articles/812461/Event-Aggregator-Pattern)
* [Event Aggregator](https://martinfowler.com/eaaDev/EventAggregator.html)

This pattern is used to channel events from multiple objects into a single object to simplify registration for clients. While Angular already offers EventEmitters and Data Binding, cross-component communication can be difficult.

Data can be sent as scalar values by adapting the payload type parameter of the event class, for instance, `number`:

````typescript
import { PubSubEvent } from './pub-sub-event';

export class ZoomEvent extends PubSubEvent<number> {
    // No implementation required
    public eventType = 'ZoomEvent';
}
````

This value can be easily read in the event handler:

````typescript
this.eventAggregator.getEvent(ZoomEvent).subscribe(this.onZoom);
.
.
.
private onZoom = (payload: number) => {
    console.log('Zoom is: ' + payload);
}
````

Otherwise, a type or class can be defined for more complex data in the payload:

````typescript
import { PubSubEvent } from './pub-sub-event';
import { RefreshHoverEventData } from './refresh-hover.event.data';

export class RefreshHoverEvent extends PubSubEvent<RefreshHoverEventData> {
    // No implementation required
    public eventType = 'RefreshHoverEvent';
}
````

Here is an example for a payload:

````typescript
export class RefreshHoverEventData {
  private _id;
  private _features;
  private _element;

  constructor(id: number, features: any, element: any) {
    this._id = id;
    this._features = features;
    this._element = element;
  }

  get id() { return this._id; }
  set id(value: number) { this._id = value; }
  get features() { return this._features; }
  set features(value: number) { this._features = value; }
  get element() { return this._element; }
  set element(value: number) { this._element = value; }
}
````

An example how to instantiate the payload and send it with the event:

````typescript
const payload = new RefreshHoverEventData(
  this._idOfHoveredGlyph,
  item.features[this.selectedContext.id],
  item);
this.eventAggregator.getEvent(RefreshHoverEvent).publish(payload);
````

Here is how an event with its payload is consumed:

````typescript
private onRefreshHover = (payload: RefreshHoverEventData) => {
  this.dummyFeatures = payload.features;
  this.drawExampleGlyph();
}

````