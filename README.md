# bgvideo
Add background video to WordPress posts

Forked from https://github.com/pommiegranit/bgvideo

The original version has developed some compatibility issues with mobile, particularly more recent versions of iOS.

The __`<source>`__ tag is unnecessary since the web has coalesced around the mp4 video format. This version of the bgvideo plugin removes the __`<source>`__ child element and instead uses a src attribute on the __`<video>`__ tag itself. CSS hooks like IDs and classes remain untouched, so the plugin will function the same as before.

The autoplay, loop, and muted attributes are rendered with their full boolean values (e.g., autoplay="true"), and an attribute for playsinline has also been added.

So instead of rendering the bgvideo html like this:

```html
<div class="bgvideo-wrapper">
  <video id="bgVideo" preload="none" muted="" autoplay="" loop="" class="bgvideo">
    <source src="https://domain.com/urlforvideo.mp4" type="video/mp4">
  </video>
</div>
```

It now looks like this:

```html
<div class="bgvideo-wrapper">
  <video id="bgVideo" type="video/mp4" src="https://domain.com/urlforvideo.mp4" poster="https://domain.com/urlforposter.jpg" muted="true" autoplay="true" loop="true" playsinline="true" class="bgvideo"></video>
</div>
```

To use the plugin in a manner that ensures compatibility with iOS on small screens, simply add a shortcode within the WordPress content editor, like so:

[bgvideo mp4="https://domain.com/urlforvideo.mp4" poster="https://domain.com/urlforposter.jpg" autoplay muted loop playsinline]
