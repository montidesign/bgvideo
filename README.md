# bgvideo
Add background video to WordPress posts

Forked from https://github.com/pommiegranit/bgvideo

The original version has developed some compatibility issues with mobile, particularly more recent versions of iOS.

The source tag is unnecessary since the web has coalesced around the mp4 video format. This version of the bgvideo plugin removes the source child element and instead uses a src attribute on the <video> tag itself. CSS hooks like IDs and classes remain untouched, so the plugin will function the same as before.

The autoplay, looped, and muted attributes are rendered with their full boolean values (e.g., autoplay="true"), and an attribute for playsinline has also been added.

To use the plugin in a manner that ensure compatibility with iOS on small screens, simply add a shortcode to your content, like so:

[bgvideo mp4="https://domain.com/urlforvideo.mp4" poster="https://domain.com/urlforposter.jpg" autoplay muted loop playsinline]
