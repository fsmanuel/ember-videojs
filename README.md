ember-videojs
==============================================================================

Use [VideoJS](https://videojs.com/) HTML5 video player components in your Ember project.

Installation
------------------------------------------------------------------------------

```
ember install ember-videojs
```


Usage
------------------------------------------------------------------------------

```handlebars
{{videojs-player src="https://vjs.zencdn.net/v/oceans.mp4" type="video/mp4" poster="https://vjs.zencdn.net/v/oceans.png"}}
```

### Add multiple sources.

```handlebars
{{video-js sources=sources}}
```

```javascript
this.set("sources", [
  {
    type: "video/mp4",
    src="https://vjs.zencdn.net/v/oceans.mp4"
  },
  {
    type: "video/webm",
    src="https://vjs.zencdn.net/v/oceans.webm"
  },
]);
```

[VideoJS documentation](https://docs.videojs.com/)

### Autoplay

- `autoplay`: true\|false

```handlebars
{{video-js autoplay=true}}
```

### Controls

- `controls`: true\|false

```handlebars
{{video-js controls=true}}
```

### Sizing

- `width`: an integer in pixels (VideoJS doesn't support CSS style sizing)
- `height`: an integer in pixels (VideoJS doesn't support CSS style sizing)
- `fluid`: adds the .vjs-fluid class and will scale to fit the container and content.

```handlebars
{{video-js width=640 height=320}}
{{video-js fluid=true}}
```

### 360 videos and VR

Install the [videojs-vr](https://github.com/videojs/videojs-vr#installation) plugin

- `npm install --save videojs-vr`

Add the import statement to your ember-cli-build.js file.

```
app.import('node_modules/videojs-vr/dist/videojs-vr.min.js');
app.import('node_modules/videojs-vr/dist/videojs-vr.min.js');
```

Add the [vr-projection](https://github.com/videojs/videojs-vr#projection) attribute to your component

- `vr-projection`: '360', 'Sphere', or 'equirectangular'

```handlebars
{{video-js vrProjection="360"}}
```

### Skinning

TBD

### Closed captions and subtitles

Add a text track to your video in the `WebVTT` format.

- `text-track`: [track URL]

```handlebars
{{video-js textTrack="captions-mi.vtt"}}
```

Add multiple tracks or configure the text track options in your component.

```handlebars
{{video-js textTracks=textTracks}}
```

```javascript
this.set("textTracks", [
  {
    kind: "captions",
    label: "Maori",
    language: "mi",
    src="captions-mi.vtt",
    type="text/vtt"
  },
  {
    kind: "captions",
    label: "English",
    language: "en",
    src="captions-en.vtt",
    type="text/vtt"
  }
]);
```

Contributing
------------------------------------------------------------------------------

### Installation

* `git clone <repository-url>`
* `cd ember-videojs`
* `npm install`

### Linting

* `npm run lint:js`
* `npm run lint:js -- --fix`

### Running tests

* `ember test` – Runs the test suite on the current Ember version
* `ember test --server` – Runs the test suite in "watch mode"
* `ember try:each` – Runs the test suite against multiple Ember versions

### Running the dummy application

* `ember serve`
* Visit the dummy application at [http://localhost:4200](http://localhost:4200).

For more information on using ember-cli, visit [https://ember-cli.com/](https://ember-cli.com/).

License
------------------------------------------------------------------------------

This project is licensed under the [MIT License](LICENSE.md).
