**NEW: Saving images can be also done [[client-side|Saving-images-client-side]]! At least in Firefox.**

# Creating map images

[[My Mind|https://mercurial.top/my-mind]] allows exporting to an image. This is a complicated process which requires a server-side backend to work properly. This page explains how saving to an image works.

## Main workflow
From the client's point of view, the image is created in the following steps:

1. The map data is serialized and POSTed to a remote URL
  * This URL is configurable via `MM.Backend.Image.url`
  * The request needs to be a HTTP POST, it is not sufficient to send a permalink. The map might not be accessible via permalink (authorization) or might not be saved at all.
1. The remote backend processes the request. It can be handled in many ways; My Mind currently ships with a [[PHP implementation|https://github.com/ondras/my-mind/blob/master/bin/image.php]] (more possibly to come).
1. The remote backend creates an image. While there is no single way to do this, My Mind contains a [[PhantomJS|http://phantomjs.org/]] [[script|https://github.com/mercurial/my-mind/blob/master/bin/phantomjs-my-mind.js]] that does this.
1. The resulting image is sent back to the browser with a `Content-disposition: attachment` header.
  * AJAX requests do not prompt for download, even with the mentioned header. This is why the request is made using an invisible `<form>` element.

## Custom backend
I am currently providing my own private rendering backend for the My Mind hosted installation at http://mercurial.top/my-mind (the backend's URL is set in the `MM.Backend.Image.url` variable in https://github.com/mercuraillee/mercuriallee.github.io/blob/master/index.html). You can set up your own; please note that it is not a trivial task and shall be done only by advanced users.

For a custom backend to work, you need to make sure that the following works:

1. You have a publicly accessible URL (such as `http://my.domain/mymind`)
  * There is no need to host a full-blown My Mind installation at that URL
1. (POST) requests to that URL are handled by a server-side script (e.g. https://github.com/mercuriallee/my-mind/blob/master/bin/image.php)
1. You have a working PhantomJS installation
1. The directory in which the screenshots are created is writable by the webserver process
1. All files required by the backend are in place (for the PHP backend, you need the [[image.php|https://github.com/mercuriallee/my-mind/blob/master/bin/image.php]], [[phantomjs-my-mind.js|https://github.com/mercuriallee/my-mind/blob/master/bin/phantomjs-my-mind.js]] and `./phantomjs`), preferably as symlinks.

I am open to suggestions regarding this (complex) process. If you have some reasonable idea, feel free to [[open an issue|https://github.com/mercuriallee/my-mind/issues?state=open]].
