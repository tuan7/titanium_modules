# Ti.ImageFactory Module

## Description

This module provides a set of image transformation functions.

## Getting Started

View the [Using Titanium Modules](http://docs.appcelerator.com/titanium/latest/#!/guide/Using_Titanium_Modules) document for instructions on getting
started with using this module in your application.

## Accessing the Ti.ImageFactory Module

To access this module from JavaScript, you would do the following:

	var ImageFactory = require('ti.imagefactory');

## Functions

### imageWithAlpha

Creates a new image by creating a copy of the given image, adding an alpha channel if it doesn't already have one.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * Currently there are no properties for this method -- specify an empty dictionary

### imageWithTransparentBorder

Creates a new image by creating a copy of the given image, adding a transparent border of the given size around its edges. The size of the image will be expanded by the specified border size.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * borderSize[int]: The size of the border (default: 1)

### imageWithRoundedCorner

Creates a new image by creating a copy of the given image with rounded corners.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
   * borderSize[int]: The size of the border (default: 1)
   * cornerRadius[int]: The radius of the corner edges (default: 0)

### imageAsThumbnail

Creates a new image by creating a copy of the given image that is squared to the thumbnail size.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * size[int]: The size of the thumbnail (default: 48)
    * borderSize[int]: The size of the border (default: 1)
    * cornerRadius[int]: The radius of the corner edges (default:0)
    * quality[int]: The interpolation quality. One of the following constants (default: imagefactory.QUALITY\_HIGH)
        * imagefactory.QUALITY\_DEFAULT
        * imagefactory.QUALITY\_NONE
        * imagefactory.QUALITY\_LOW
        * imagefactory.QUALITY\_MEDIUM
        * imagefactory.QUALITY\_HIGH

### imageAsResized

Creates a new image by creating a copy of the given image that is rescaled to the specified size.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * width[int]: The width of the new image (default: image width)
    * height[int]: The height of the new image (default: image height)
    * quality[int]: The interpolation quality. One of the following constants (default: imagefactory.QUALITY\_HIGH)
        * imagefactory.QUALITY\_DEFAULT
        * imagefactory.QUALITY\_NONE
        * imagefactory.QUALITY\_LOW
        * imagefactory.QUALITY\_MEDIUM
        * imagefactory.QUALITY\_HIGH
    * hires[boolean]: Create a hires image (for Retina displays only)

### imageAsCropped

Creates a new image by creating a copy of the given image that is cropped to the specified bounds.

#### Arguments

* Image blob[blob]: Image to transform
* Options[dictionary]: A dictionary specifying the options for the transformation
    * width[int]: The width of the new image (default: image width)
    * height[int]: The height of the new image (default: image height)
    * x[int]: The x-coordinate of the upper-left corner of the bounds (default: image center - width / 2)
    * y[int]: The y-coordinate of the upper-left corner of the bounds (default: image center - height / 2)

### imageTransform

Creates a new image by applying a sequence of transformations to the image.

#### Arguments

* Image blob[blob]: Image to transform
* Transform[dictionary]: A sequence of transform specifications. Transforms are listed as additional parameters to the function and are applied in the order specified. Each transform is a dictionary with the options described above for each transform along with an additional 'type' property included with each dictionary of transform options.
    * type[int]: The identifier of the transform to apply. One of the following constants
        * imagefactory.TRANSFORM\_CROP
        * imagefactory.TRANSFORM\_RESIZE
        * imagefactory.TRANSFORM\_THUMBNAIL
        * imagefactory.TRANSFORM\_ROUNDEDCORNER
        * imagefactory.TRANSFORM\_TRANSPARENTBORDER
        * imagefactory.TRANSFORM\_ALPHA
    * options as described in the above transforms

### compress

Creates a new image by creating a copy of the given image and applying the specified compression quality.

#### Arguments

* Image blob[blob]: Image to compress
* Compression Quality[float]; The quality of the resulting JPEG image, expressed as a value from 0.0 to 1.0. The value 0.0 represents the maximum compression (or lowest quality) while the value 1.0 represents the least compression (or best quality). (default: 1.0)

## Usage

See example.

## Author

Jeff English

## Module History

View the [change log](changelog.html) for this module.

## Feedback and Support

Please direct all questions, feedback, and concerns to [info@appcelerator.com](mailto:info@appcelerator.com?subject=iOS%20ImageFactory%20Module).

## License
Copyright(c) 2011-2013 by Appcelerator, Inc. All Rights Reserved. Please see the LICENSE file included in the distribution for further details.
