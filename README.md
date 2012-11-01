## Focal Point: Pure HTML/CSS Adaptive Images Framework

Using only HTML/CSS, web authors can specify an image's focal point, which stays as the image's primary focus, even as available CSS width changes for responsive webpages. This puts web authors in control of image content for responsive and high-resolution images. Crop and re-size images depending on available width and let CSS to do all of the work, and without any JavaScript.

The Focal Point Framework givens web authors the flexibility of how responsive and hi-res images should be rendered depending on the image. For example, images can use common CSS classnames which allows a standard pattern to be resuabled throughout an entire site, which drastically reduces HTML markup and CSS required. Additionally, each individual image can also be given specific CSS for the exact crop/size needed.

Developers have control to add and subtract from the framework's CSS as needed, which keeps CSS minimal in size and can be grouped with existing CSS files as to not add any additional HTTP requests. An online build tool will be created to make this easier to customize the framework for your project.

Web authors can either use default settings to crop and resize images, or can specify an image's exact crop and size needed. By controlling web authoring in markup, this put content editors in control of how content images display at each breakpoint.
    

## High-Resolution Images, But Smaller Filesizes!

Using a technique from the blog post [Retina Revolution](http://blog.netvlies.nl/design-interactie/retina-revolution/) by Daan Jobsis, we're able serve high-resolution images to high-density displays, such as Retina displays. But as the same time, standard resolution devices are not affected by large file sizes. The technique is so simple its genius: __"A smaller filesize AND a better quality on both screen types! This is impossible."__ I encourage you to [read his entire post](http://blog.netvlies.nl/design-interactie/retina-revolution/).

Because we're entering a responsive web now, and elements need to be fluid and adjust to the available display, setting exact pixel dimensions for images becomes a large challenge. However, it is now in the past that browsers had poor image downsizing abilities. Today browsers now do a remarkable job of resizing images on the fly, which is one of the primary reasons this framework is now possible.


## HTML Pattern

    <div class="focal-point">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## CSS Framework Classnames

 - __left-X__: Once a breakpoint is hit, the images focal point is X out of 6 units left of the center. _ie: left-1 would move the image 1 out of 6 units to the left._
 - __right-X__: Once a breakpoint is hit, the images focal point is X out of 6 units right of the center.
 - __up-X__: Once a breakpoint is hit, the images focal point is X out of 6 units up from the center.
 - __down-X__: Once a breakpoint is hit, the images focal point is X out of 6 units down from the center.
 - __shape-WxH__: Once a breakpoint is hit, the image should be cropped with a shape representing a ratio of X width units by X height units. For example, shape-4x3 and shape-7x5 are common ratios. By default the 4x3 shape is applied and doesn't need to be specified, but this can be overwritten to use a 7x5 ratio by assigning shape-7x5. Additionally, any shape needed can be created by the developer, they are not restricted to what the framework has by default. An online build tool will be created to make this easier.


## See a way to improve this?

Is there a better way to write the HTML/CSS all while keeping it reusable, compact and simple? Submit a pull request or contact me: [@adamdbradley](https://twitter.com/adamdbradley)

__Requirements:__

 - All browsers must be able to view the image, old and new, with and without JS
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
 - Printable images
 - Context menu usable when "right-clicking" content images, ie: "Save image as..."

