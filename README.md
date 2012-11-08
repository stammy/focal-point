## Focal Point: Pure HTML/CSS Adaptive Images Framework

A small set of CSS classnames to help keep images cropped on the focal point for responsive designs. Using only HTML/CSS, web authors can specify an image's focal point, which stays as the image's primary focus as the image scales on responsive webpages. This puts [web authors in control of art direction for responsive and high-resolution images](http://blog.cloudfour.com/a-framework-for-discussing-responsive-images-solutions/). Crop and re-size images depending on available width and let CSS to do all of the work, and without any JavaScript. Resize your browser down to as small as it can go when viewing the [demos](http://www.cdnconnect.com/demos/focal-point-full-house).

Many of today's designs are migrating to the [responsive web design technique](http://www.abookapart.com/products/responsive-web-design) coined by [Ethan Marcotte](https://twitter.com/beep). Elements should to be fluid and adjust to the available display, but a wrench is usually thrown into the system when exact pixel dimensions are set for images. The good news is that browsers only _used_ to have poor image downsizing abilities. Today's browsers, however, do a remarkable job of resizing images on the fly, which is one of the primary reasons this small framework is now possible. 

The __Focal Point Framework__ gives web authors the flexibility of how responsive and hi-res images should be rendered depending on the image. For example, images can use common CSS classnames which allows a standard pattern to be resuabled throughout an entire site, which drastically reduces HTML markup and CSS required. Additionally, each individual image can also be given specific CSS for the general crop/size needed. All this without the use of any JavaScript!

Developers also have control to add and subtract from the framework's CSS as needed. The CSS is minimal in size, __2.98KB compressed (723 bytes gzipped)__, and can be grouped with existing CSS files as to not add any additional HTTP requests. 

 - Author: [Adam Bradley](https://twitter.com/adamdbradley) (c) 2012
 - License: MIT/GPLv2

## Demos

Be sure to __adjust your browser window size to as small as it can go__ and __take notice of the image's edges__. As the image's available width changes, __study how the image gets cropped__ as it narrows in on the image's focal point.

 - [Full House](http://www.cdnconnect.com/demos/focal-point-full-house)
 - [A-Team](http://www.cdnconnect.com/demos/focal-point-a-team)
 - [Webster](http://www.cdnconnect.com/demos/focal-point-webster)
 - [Charles in Charge](http://www.cdnconnect.com/demos/focal-point-charles-in-charge)
 - [Dukes of Hazzard](http://www.cdnconnect.com/demos/focal-point-dukes-of-hazzard)
 - [Knight Rider](http://www.cdnconnect.com/demos/focal-point-knight-rider)
 - [Magnum PI](http://www.cdnconnect.com/demos/focal-point-magnum-pi)
 - [My Two Dads](http://www.cdnconnect.com/demos/focal-point-my-two-dads)
 - [Small Wonder](http://www.cdnconnect.com/demos/focal-point-small-wonder)
 - [Alf](http://www.cdnconnect.com/demos/focal-point-alf)
 - [MacGyver](http://www.cdnconnect.com/demos/focal-point-macgyver)


## 12x12 Grid

An image is represented in a grid of 12x12 units (no matter what its natural dimensions are), and you can locate the general focal point of each image using CSS classnames. I use the term "general" focal point because this framework is not built around exact pixels and cropping to strict dimensions. Instead it uses relative positioning to __narrow in on general areas of an image__ in an effort to crop and resize with a simple and quick markup change. If you need to crop, resize and rotate images to exact pixel-perfect dimensions for exact breakpoints widths then this framework [may not be for you](http://css-tricks.com/which-responsive-images-solution-should-you-use/).

Web authors can either use default settings to crop and resize images which centers in on the image, or can specify an image's general focal point. By controlling web authoring in markup, this puts content editors in control of how content images render as responsive webpages adjust to the display.
    

## High-Resolution Images, But Smaller Filesizes!

While not required, you can also render high-resolution images using a technique from the blog post [Retina Revolution](http://blog.netvlies.nl/design-interactie/retina-revolution/) by Daan Jobsis. Essentially you would serve high-resolution images, but the image would also be saved with high compression. Amazingly this works great for high-density devices, such as Retina displays, but as the same time, standard resolution devices are not affected by being served large file sizes. The technique is so simple its genius: __"A smaller filesize AND a better quality on both screen types! This is impossible."__ I encourage you to [read his entire post](http://blog.netvlies.nl/design-interactie/retina-revolution/).


## HTML Pattern

Not too scarey right? If you've ever used a _div_ or _img_ element before you should be good to go.

    <div class="focal-point">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## Landscape and Portrait Aspect Ratios

Out of the box all images are considered to be landscape with a 4x3 aspect ratio, and portrait images are generalized to a 3x4 aspect ratio. These ratios are used to help crop images as they are resized. Because of the nature of the CSS _em_ unit and its ability to adapt to its surroundings, using the _em_ unit allows the crop and resize to be elastic to the image's natural dimensions. While cropping and resizing images, the _em_ unit does not render strict 4x3 or 3x4 ratio images, but instead adjusts relative to the image's natural dimensions. [Check out the demos](http://www.cdnconnect.com/demos/focal-point-full-house) to get a better idea of how they work.


## CSS Framework Classnames

An image is represented in 12x12 units, and you can locate the general focal point of each image using CSS classnames. By not setting a left or right classname, the crop and resize will zoom in to the horizontal center. Likewise, by not setting an up or down classname, the crop and resize will zoom into the vertical center. Basically, __by default it'll zoom into the center of the image__. The classnames below allow you to crop and resize into a general area of the image. _Note: X in the classnames represent a number between 1 and 6._

 - __left-X__: The images focal point is X out of 6 units left of the center. _ie: left-1 would move the focal point 1 out of 6 units to the left._
 - __right-X__: The images focal point is X out of 6 units right of the center. _ie: right-6 would move the focal point 6 out of 6 units to the right._
 - __up-X__: The images focal point is X out of 6 units up from the center. _ie: up-3 would move the focal point 3 out of 6 units up._
 - __down-X__: The images focal point is X out of 6 units down from the center. _ie: down-2 would move the focal point 2 out of 6 units down._
 - __portrait__: If an image has a portrait layout (its height is more than its width) then this classname will help to respect the image's natural aspect ratio while cropping/resizing into the focal point. The image will be cropped with a shape loosly representing an aspect ratio of 3x4 units. By default the 4x3 shape (landscape) is applied and doesn't need to be specified, but this can be overwritten for portrait images. You'll find that landscape will be able to work for most images, and portrait works for the rest. Note that images still crop/resize to the focal point even when not assigning the portrait classname on portrait images, however it doesn't respect the natural aspect ratio as much. Additionally, any shape needed can be added by the developer for uncommon image dimensions. If you do not need the portrait classname then feel free to cut out the CSS to save yourself a few bytes.

Below is an example of setting the image's focal point 1 out of 6 units to the right of the center, and 2 out of 6 units up from the center:

    <div class="focal-point right-1 up-2">
        <div><img src="http://demo.cdnconnect.com/images/hi-res/chrysler-plant.w1020.q20.jpg"></div>
    </div>


## Discussion Points

__Zoom Classnames:__ The standard CSS uses a zoom factor I considered to be general enough for most cases. But some images may want more or less "zooming" depending on the image. There could easily be additional CSS classnames, such as .zoom-2 and .zoom-3, which could set how slow and fast the crop and resize adjusts. The only reason I did not create zoom classnames was to keep the CSS minimal. However, if you have a need for various zoom factors then go for it since it's definately possible.

__Multiple or No Media Queries:__ Same as the zoom classnames, I chose a general breakpoint and only included one media query for common cases. This isn't to say you couldn't have two, five, or even no media queries all. Depending on your use case you could even change zoom factors between each media query. What's included with the standard CSS is general enough for most cases, or at least a good starting point for your own project.

__Browser Support:__ It appears that IE8 and below does not _crop_ the image, but it does resize the image according to its available width. I don't see this as a show stopper what-so-ever. If the worst case scenario is that IE8 users do not get the cropped image on responsive webpages, but instead view images no different that every other image created today, then I'm fine with that. Review the demos in IE8 to see what I mean. (Let's not forget that it's just two _div_'s and an _img_ element). Also, if you come across any other issues, or know of a better way to write the HTML/CSS please let me know.


## See a way to improve this? Contribute / Contact Me

Is there a better/simpler/easier/smaller way to write the HTML/CSS all while keeping it reusable, compact, simple and meets the requirements below? Submit a pull request or contact me: [@adamdbradley](https://twitter.com/adamdbradley)

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
 - [A framework for discussing responsive images solutions [Jason Grigsby]](http://blog.cloudfour.com/a-framework-for-discussing-responsive-images-solutions/)
 - [Foresight.js](https://github.com/adamdbradley/foresight.js): JavaScript plugin that judges device display and network connectivity, then requests the appropriate image. Used by Washington Post's mobile site.
 - [Which responsive images solution should you use? [CSS-Tricks]](http://css-tricks.com/which-responsive-images-solution-should-you-use/)

