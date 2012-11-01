## Focal Point: Pure HTML/CSS Adaptive Images Framework

Using only HTML/CSS, web authors can specify an image's focal point, which stays as the image's primary focus, even as available CSS width changes for responsive webpages. This puts web authors in control of image content for responsive and high-resolution images. Crop and re-size images depending on available width and let CSS to do all of the work, and without any JavaScript.

The Focal Point Framework givens web authors the flexibility of how responsive and hi-res images should be rendered depending on the image. For example, images can use common CSS classnames which allows a standard pattern to be resuabled throughout an entire site, which drastically reduces HTML markup and CSS required. Additionally, each individual image can also be given specific CSS for the exact crop/size needed.

Developers have control to add and subtract from the framework's CSS as needed, which keeps CSS minimal in size and can be grouped with existing CSS files as to not add any additional HTTP requests. 

Web authors can either use default settings to crop and resize images, or can specify an image's exact crop and size needed. By controlling web authoring in markup, this put content editors in control of how content images display at each breakpoint.
    

## High-Resolution Images, But Smaller Filesizes!

Using a technique from the blog post [Retina Revolution](http://blog.netvlies.nl/design-interactie/retina-revolution/) by Daan Jobsis, we're able serve high-resolution images to high-density displays, such as Retina displays. But as the same time, standard resolution devices are not affected by large file sizes. The technique is so simple its genius: __"A smaller filesize AND a better quality on both screen types! This is impossible."__ I encourage you to [read his entire post](http://blog.netvlies.nl/design-interactie/retina-revolution/).

Because we're entering a responsive web now, and elements need to be fluid and adjust to the available display, setting exact pixel dimensions for images becomes a large challenge. However, it is now in the past that browsers had poor image downsizing abilities. Today browsers now do a remarkable job of resizing images on the fly, which is one of the primary reasons this framework is now possible.


## HTML Pattern

    <div class="focal-point">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## Landscape and Portrait Aspect Ratios

Out of the box all images are considered to be landscape with a 4x3 aspect ratio, and portrait images are generalized to a 3x4 aspect ratio. These ratios are used to help crop images as they are resized. Because of the nature of the CSS _em_ unit and its ability to adapt to its surroundings, it allows the crop and resize to be elastic to the images original dimensions. While cropping and resizing images, the _em_ unit does not render strict 4x3 or 3x4 ratio images, but instead adjust to the image as it resizes. Check out the demos to get a better idea of how they work.


## CSS Framework Classnames

An image is represented in 12x12 units, and you can locate the focal point of each image using the classnames below. By not setting a left or right the crop and resize will zoom in to the center, and not setting a up or down will also zoom into the center. Basically, __by default it'll zoom into the center of the image__, and the classnames below allow you to crop and resize into a specific point of the image. _Note: X in the classnames represent a number between 1 and 6._

 - __left-X__: Once a breakpoint is hit, the images focal point is X out of 6 units left of the center. _ie: left-1 would move the focal point 1 out of 6 units to the left._
 - __right-X__: Once a breakpoint is hit, the images focal point is X out of 6 units right of the center. _ie: right-6 would move the focal point 6 out of 6 units to the right._
 - __up-X__: Once a breakpoint is hit, the images focal point is X out of 6 units up from the center. _ie: up-3 would move the focal point 3 out of 6 units up._
 - __down-X__: Once a breakpoint is hit, the images focal point is X out of 6 units down from the center. _ie: down-2 would move the focal point 2 out of 6 units down._
 - __portrait__: If an image is portrait (its height is more than its width) then this classname will help to locate the image's focal point. Once a breakpoint is hit, the image should be cropped with a shape representing an aspect ratio of 3x4 units. By default the 4x3 shape (landscape) is applied and doesn't need to be specified, but this can be overwritten for portrait images. You'll find that landscape will be able to work for most images, and portrait works for the rest. However, any shape needed can be added by the developer for uncommon image dimensions. Also, if you will not be using the portrait classname at all then feel free to cut out the CSS to save you a few bytes.

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

