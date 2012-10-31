Focal Point: Adaptive Images with pure HTML/CSS
===========

Load responsive and high-resolution images using today's HTML/CSS standards and no JavaScript. Crop and re-size images depending on available width allowing CSS to do all of the work.

The focal-point pattern givens web authors the flexibility of how responsive and hi-res images should be rendered depending on the image. For example, each individual image can be given specific CSS for the exact crop/size needed. However, images can also use common CSS classnames which allows a standard pattern to be resuabled throughout an entire site, which reduces HTML markup and CSS required.

See a way to improve this?
===========

Submit a pull request or contact me: [@adamdbradley](https://twitter.com/adamdbradley)

__Requirements:__

 - All browsers must be able to view *at least* the image
 - Only one img tag per image
 - Set image breakpoints depending on available CSS width
 - Re-crop and re-size images depending on available CSS width
 - Images can be assigned follow sitewide CSS
 - Each image can have its own individual CSS
 - Works *without* JavaScript / jQuery
 - Entirely static and controlled only by HTML/CSS. ie: No requirements for HTTP headers/cookies
 - No DOM manipulation
 - No repaints
 - Crawlable by search engines so the image can be indexed and associated to page content
 - Printable images
 - Context menu usable when "right-clicking" content images, ie: "Save image as..."

