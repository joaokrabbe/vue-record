# vue-record

> custom components for MediaRecorder API

[![NPM version][npm-image]][npm-url] [![Dependency Status][daviddm-image]][daviddm-url]

Checkout the [demo](https://codekraft-studio.github.io/vue-record/) to see it in action.

## Installation

Download the project using your favourite package manager:

```
npm install @codekraft-studio/vue-record
```

Load it inside your project and use it:

```js
import Vue from 'vue'
import VueRecord from '@codekraft-studio/vue-record'

Vue.use(VueRecord)
```

Now you have access to the global defined components, here an example:

```html
<vue-record-audio />
<vue-record-video />
```

## Usage

Use the components in your template with different modes and properties to customize the behavior and the recording output.

#### Modes

The are only two usage modes and can be selected with the __mode__ property:

* __hold__: Hold is the default mode and it means the recording start when the button is clicked or pressed and stops when is released, basically it _record only when holding the button_.
* __press__: Press will start the recording once the button is pressed and it will stop the recording when the button is pressed again, so it will _record until stopped_.

#### Events

* __stream__: The stream event is emitted when the user media device stream is captured and contains the original [MediaStream](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream) object.
* __result__: The result event is emitted once a recording has been completed and contains the [Blob](https://developer.mozilla.org/en-US/docs/Web/API/Blob) data of the recording.

By default it's on __hold__ mode, so the recording start when the button is pressed and stops when the button is released.
But you can change this behaviour using a different mode, the available modes are: `hold` and `press`.

---

## Examples

### Recording Audio

It's simple as adding the component and listening for the __result__ event:

```html
<vue-record-audio @result="onResult" />
```

```js
export default {
  methods: {
    onResult (data) {
      console.log('The blob data:', data);
      console.log('Downloadable audio', window.URL.createObjectURL(data));
    }
  }
}
```

### Recording Video

It's simple as adding the component and listening for the __result__ event:

```html
<vue-record-video @result="onResult" />
```

```js
export default {
  methods: {
    onResult (data) {
      console.log('The blob data:', data);
      console.log('Downloadable audio', window.URL.createObjectURL(data));
    }
  }
}
```

---

## License

[MIT](./LICENSE) © [codekraft-studio](https://github.com/codekraft-studio)


[npm-image]: https://badge.fury.io/js/%40codekraft-studio%2Fvue-record.svg

[npm-url]: https://npmjs.org/package/@codekraft-studio/vue-record

[daviddm-image]: https://david-dm.org/codekraft-studio/vue-record.svg?theme=shields.io

[daviddm-url]: https://david-dm.org/codekraft-studio/vue-record
