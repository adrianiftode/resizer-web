Libs: plusone

# Reference

## Selecting a frame or page

* **frame=x** – Choose which frame of an animated GIF to display.
* **page=x**– Choose which page of a multi-page TIFF document to display.

## Rotation & flipping

* **autorotate=true** Automatically rotates the image based on the EXIF info from the camera. (Requires the [AutoRotate plugin](/plugins/autorotate))
* **sflip=none\|x\|y\|xy** Flips the source image prior to processing (new in V3.1)
* **srotate=0\|90\|180\|270** Rotates the source image prior to processing (only 90 degree intervals) (new in V3.1)
* **rotate=degrees** – Rotates the image any arbitrary angle (occurs after cropping)
* **flip=none\|x\|y\|xy** - Flips the image after everything is done

## Manual cropping

* **crop=(x1,y1,x2,y2)** – Crop the image to the specified rectangle on the source image. You can use negative coordinates to specify bottom-right relative locations.
* **cropxunits** The width the x1 and x2 coordinates are relative to. I.e, use '100' to make x1 and x2 percentages. Useful when you don't know the original image size.
* **cropyunits** The height the y1 and y2 coordinates are relative to. I.e, use '100' to make y1 and y2 percentages. Useful when you don't know the original image size.


## Sizing (and padding, autocropping, carving and stretching)

Please note that width/height/maxwidth/maxheight do NOT include border, margin, or padding widths, and do not include the extra space used by rotation. They constrain the image, not the canvas.

* **maxwidth, maxheight** – fit the image within the specified bounds, preserving aspect ratio.
* **width, height** – force the final width and/or height to certain dimensions. Whitespace will be added if the aspect ratio is different.
* **mode=max\|pad\|crop\|carve\|stretch** - How to handle aspect-ratio conflicts between the image and width+height. 'pad' adds whitespace, 'crop' crops minimally, 'carve' uses seam carving, 'stretch' loses aspect-ratio, stretching the image. 'max' behaves like maxwidth/maxheight. (new in V3.1)
* **anchor=topleft\|topcenter\|topright\|middleleft\|middlecenter\|middleright\|bottomleft\|bottomcenter\|bottomright** How to anchor the image when padding or cropping. (new in V3.1)
* **scale=both\|upscaleonly\|downscaleonly\|upscalecanvas** – By default, images are never upscaled. Use &scale=both to upscale images if they are smaller than width and height
* **zoom=0..infinity** - Scale the image by a multiplier. Useful for mobile devices and situations where you need to retain all the existing width/height/crop settings, but scale the result up or down. Defaults to 1. 0.5 produces a half-size image, 2 produces a double-size image.

## Border, padding, margins and background colors

* **bgcolor=color name \| hex code (6-char).** Sets the background/whitespace color.
* **paddingWidth=px & paddingColor=color\|hex** paddingColor defaults to bgcolor, which defaults to white.
* **borderWidth=px, borderColor=color\|hex**
* **margin=3 or margin=5,5,10,10** Specify a universal margin or left,top,right,bottom widths. (new in V3.1)

## Output format
* **format=jpg\|png\|gif** - The output format to use
* **quality** - Jpeg compression: 0-100 100=best, 90=very good balance, 0=ugly
* **colors=2-255** – Control the palette size of PNG and GIF images. If omitted, PNGs will be 24-bit. ([PrettyGifs plugin](/plugins/prettygifs) required)

## Misc

* **ignoreicc** - true|false. If true, the ICC profile embedded in the source image will be ignored.
* **cache** - always|no|default - Always forces the image to be cached even if it wasn't modified by the resizing module. Doesn't disable caching if it was modified.
* **process** - always|no|default - Always forces the image to be re-encoded even if it wasn't modified. Does not prevent the image from being modified.
* **dpi=90\|300\|600** - The DPI at which the image should be printed. Ignored by all browsers, most operating systems, and most printers.

## [Watermark plugin](/plugins/watermark)

* **watermark** - The name of one or more watermark layers (or layer groups) to render.

## [Image404 plugin](/plugins/image404)

* **404** - The path to the fallback image, or a named preset

## [Gradient plugin](/plugins/gradient)

* **color1,color2** - 6 or 8 digit hex values specifying the start and end gradient colors. 
* **angle** - 0 is horizontal. Degrees to rotate the gradient
* **width/height** - the size of the gradient image

## [PrettyGifs plugin](/plugins/prettygifs)

* **colors** - 2 to 256 (the number of colors to allow in the output image palette). For Gifs and 8-bit PNGs.
* **dither**=true|false|4pass|30|50|79|[percentage] - How much to dither

## [SimpleFilters plugin](/plugins/simplefilters)

* &s.grayscale=true|y|ry|ntsc|bt709|flat  (true, ntsc, and y produce identical results)
* &s.sepia=true
* &s.alpha= 0..1
* &s.brightness=-1..1
* &s.contrast=-1..1
* &s.saturation=-1..1
* &s.invert=true

## [AdvancedFilters plugin](/plugins/advancedfilters)

* &a.blur=radius - Gaussian blur with adjustable radius:
* &a.sharpen=radius - Gaussian sharpen with adjustable radius
* &a.contrast=-1..1
* &a.saturation=-1..1
* &a.brightness=-1..1
* &a.equalize=true - Adjusts contrast, saturation, and brightness with curves based on the histogram. Good for adjusting slightly foggy or dark daytime photos. 
* &a.sepia=true - Sepia effect, slightly different from the one in SimpleFilters
* &a.oilpainting=1..100 -Try `1` for impressionist, `100` for modern art ;)
* &a.removenoise=1-100 - Not a blur effect - designed to remove color noise, 'pepper noise'. Very conservative, doesn't affect edges.

## [DropShadow plugin](/plugins/dropshadow)

* **shadowWidth** - width of the shadow
* **shadowOffset** - (x,y) how to offset the drop shadow
* **shadowColor** - named or hex color of the shadow

## [SpeedOrQuality plugin](/plugins/speedorquality)

* **speed**=0..5 - The amount of quality to sacrifice for speed - each value uses different settings and techniques, and may not support all features.

## [Presets plugin](/plugins/presets)

* **preset**=name1,name2,name3 - A list of preset settings groups to apply. 

## [WhitespaceTrimmer plugin](/plugins/whitespacetrimmer)

* **trim.threshold=80** - The threshold to use for trimming whitespace
* **trim.percentpadding=0.5** - The percentage of padding to restore after trimming

## [WicBuilder](/plugins/wic) & [FreeImageBuilder](/plugins/freeimage)

* **builder=freeimage\|wic** - Enables the FreeImage or Wic pipeline instead of the default GDI pipeline. Special effect plugins not supported.

## [FreeImageDecoder](/plugins/freeimage), [WicDecoder](/plugins/wic)

These act as fallback decoders, but you can tell them to try first by using 

* **decoder=wic\|freeimage**

## [FreeImageEncoder](/plugins/freeimage), [WicEncoder](/plugins/wic)

In addition to jpeg quality and gif/png colors, you can configure the jpeg subsampling for both Wic and FreeImage.

* **subsampling**==444|422|420
