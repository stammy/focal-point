## Focal Point: Pure HTML/CSS Adaptive Images Framework

Using only HTML/CSS, web authors can specify an image's focal point, which stays as the image's primary focus, while the image's available width changes on responsive webpages. This puts web authors in control of image content for responsive and high-resolution images. Crop and re-size images depending on available width and let CSS to do all of the work, and without any JavaScript.

Many of today's designs are migrating to the [responsive web design technique](http://www.abookapart.com/products/responsive-web-design) coined by [Ethan Marcotte](https://twitter.com/beep). Elements should to be fluid and adjust to the available display, but a wrench is usually thrown into the system when exact pixel dimensions are set for images. The good news is that browsers only _used_ to have poor image downsizing abilities. Today's browsers, however, do a remarkable job of resizing images on the fly, which is one of the primary reasons this framework is now possible.

The __Focal Point Framework__ givens web authors the flexibility of how responsive and hi-res images should be rendered depending on the image. For example, images can use common CSS classnames which allows a standard pattern to be resuabled throughout an entire site, which drastically reduces HTML markup and CSS required. Additionally, each individual image can also be given specific CSS for the general crop/size needed. 

Developers also have control to add and subtract from the framework's CSS as needed. The CSS is minimal in size, __2.8KB compressed (580 bytes gzipped)__, and can be grouped with existing CSS files as to not add any additional HTTP requests. 

Please feel free to contact me: [@adamdbradley](https://twitter.com/adamdbradley)


## 12x12 Grid

An image is represented in a grid of 12x12 units, and you can locate the general focal point of each image using CSS classnames. I use the term "general" focal point because this framework is not built around exact pixels and cropping to strict dimensions. Instead it uses relative positioning to __narrow in on general areas of an image__ in an effort to crop and resize with a simple and quick markup change. If you need to crop, resize and rotate images to exact pixel-perfect dimensions for exact breakpoints then this framework may not be for you.

Web authors can either use default settings to crop and resize images which centers in on the image, or can specify an image's general focal point. By controlling web authoring in markup, this puts content editors in control of how content images render as responsive webpages adjust to the display.
    

## High-Resolution Images, But Smaller Filesizes!

While not required, you can render high-resolution images using a technique from the blog post [Retina Revolution](http://blog.netvlies.nl/design-interactie/retina-revolution/) by Daan Jobsis. Essentially you would serve high-resolution images, but with also high image compression. Amazingly this works great for high-density devices, such as Retina displays, but as the same time, standard resolution devices are not affected by being served large file sizes. The technique is so simple its genius: __"A smaller filesize AND a better quality on both screen types! This is impossible."__ I encourage you to [read his entire post](http://blog.netvlies.nl/design-interactie/retina-revolution/).


## HTML Pattern

Not too scarey right? If you've ever used a _div_ or _img_ element before you should be good to go.

    <div class="focal-point">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## Landscape and Portrait Aspect Ratios

Out of the box all images are considered to be landscape with a 4x3 aspect ratio, and portrait images are generalized to a 3x4 aspect ratio. These ratios are used to help crop images as they are resized. Because of the nature of the CSS _em_ unit and its ability to adapt to its surroundings, it allows the crop and resize to be elastic to the image's original dimensions. While cropping and resizing images, the _em_ unit does not render strict 4x3 or 3x4 ratio images, but instead adjusts relative to the image's dimensions as it resizes. Check out the demos to get a better idea of how they work.


## CSS Framework Classnames

An image is represented in 12x12 units, and you can locate the general focal point of each image using CSS classnames. By not setting a left or right classname, the crop and resize will zoom in to the horizontal center. Likewise, by not setting an up or down classname, the crop and resize will zoom into the vertical center. Basically, __by default it'll zoom into the center of the image__, and the classnames below allow you to crop and resize into a specific point of the image. _Note: X in the classnames represent a number between 1 and 6._

 - __left-X__: Once the breakpoint is hit, the images focal point is X out of 6 units left of the center. _ie: left-1 would move the focal point 1 out of 6 units to the left._
 - __right-X__: Once the breakpoint is hit, the images focal point is X out of 6 units right of the center. _ie: right-6 would move the focal point 6 out of 6 units to the right._
 - __up-X__: Once the breakpoint is hit, the images focal point is X out of 6 units up from the center. _ie: up-3 would move the focal point 3 out of 6 units up._
 - __down-X__: Once the breakpoint is hit, the images focal point is X out of 6 units down from the center. _ie: down-2 would move the focal point 2 out of 6 units down._
 - __portrait__: If it is a portrait image (its height is more than its width) then this classname will help to locate the image's focal point. Once the breakpoint is hit, the image should be cropped with a shape representing an aspect ratio of 3x4 units. By default the 4x3 shape (landscape) is applied and doesn't need to be specified, but this can be overwritten for portrait images. You'll find that landscape will be able to work for most images, and portrait works for the rest. However, any shape needed can be added by the developer for uncommon image dimensions. Also, if you do not need the portrait classname then feel free to cut out the CSS to save yourself a few bytes.

Below is an example of setting the image's focal point 1 out of 6 units to the right of the center, and 2 out of 6 units up from the center:

    <div class="focal-point right-1 up-2">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## See a way to improve this?

Is there a better way to write the HTML/CSS all while keeping it reusable, compact and simple? Submit a pull request or contact me: [@adamdbradley](https://twitter.com/adamdbradley)

__Requirements:__

 - All browsers must be able to at least view the image _(ie: images do not crop and change focal points for IE8 and below, but the image still resizes according to available width. In my book that's still good to go. If a different method doesn't allow the image to load at all in IE8 then that's a no go.)_
 - Only one img request per image
 - Set image breakpoints depending on available CSS width
 - Re-crop and re-size images depending on available CSS width
 - Image web authoring can be assigned to sitewide patterns
 - Each image can also have its own individual crop/resize
 - Keep the CSS file as small as possible
 - Works *without* JavaScript
 - Entirely static and controlled only by HTML/CSS. ie: No requirements for HTTP headers/cookies
 - No DOM manipulation
 - Crawlable by search engines so the image can be indexed and associated to page content
 - Accessible text (ie: alt tag)
 - Printable images
 - Context menu usable when "right-clicking" content images, ie: "Save image as..."


## Other Resources

 - [Responding to the New High-Resolution Web: Considerations for High-Density Displays [slidedeck]](https://dl.dropbox.com/u/75469230/responding-to-the-hi-res-web/index.html)

