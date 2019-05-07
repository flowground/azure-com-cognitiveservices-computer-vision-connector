# ![LOGO](logo.png) Computer Vision **flow**ground Connector

## Description

A generated **flow**ground connector for the Computer Vision API (version 1.0).

Generated from: https://api.apis.guru/v2/specs/azure.com/cognitiveservices-ComputerVision/1.0/swagger.json<br/>
Generated at: 2019-05-07T17:37:43+03:00

## API Description

The Computer Vision API provides state-of-the-art algorithms to process images and return information. For example, it can be used to determine if an image contains mature content, or it can be used to find all the faces in an image.  It also has other features like estimating dominant and accent colors, categorizing the content of images, and describing an image with complete English sentences.  Additionally, it can also intelligently generate images thumbnails for displaying large images effectively.

## Authorization

Supported authorization schemes:
- API Key
## Actions

### This operation extracts a rich set of visual features based on the image content. Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.  Within your request, there is an optional parameter to allow you to choose which features to return.  By default, image categories are returned in the response.

#### Input Parameters
* `visualFeatures` - _optional_ - A string indicating what visual feature types to return. Multiple values should be comma-separated. Valid visual feature types include:Categories - categorizes image content according to a taxonomy defined in documentation. Tags - tags the image with a detailed list of words related to the image content. Description - describes the image content with a complete English sentence. Faces - detects if faces are present. If present, generate coordinates, gender and age. ImageType - detects if image is clipart or a line drawing. Color - determines the accent color, dominant color, and whether an image is black&white.Adult - detects if the image is pornographic in nature (depicts nudity or a sex act).  Sexually suggestive content is also detected.
* `details` - _optional_ - A string indicating which domain-specific details to return. Multiple values should be comma-separated. Valid visual feature types include:Celebrities - identifies celebrities if detected in the image.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### This operation generates a description of an image in human readable language with complete sentences.  The description is based on a collection of content tags, which are also returned by the operation. More than one description can be generated for each image.  Descriptions are ordered by their confidence score. All descriptions are in English. Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL.A successful response will be returned in JSON.  If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `maxCandidates` - _optional_ - Maximum number of candidate descriptions to be returned.  The default is 1.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### This operation generates a thumbnail image with the user-specified width and height. By default, the service analyzes the image, identifies the region of interest (ROI), and generates smart cropping coordinates based on the ROI. Smart cropping helps when you specify an aspect ratio that differs from that of the input image. A successful response contains the thumbnail image binary. If the request failed, the response contains an error code and a message to help determine what went wrong.

#### Input Parameters
* `width` - _required_ - Width of the thumbnail. It must be between 1 and 1024. Recommended minimum of 50.
* `height` - _required_ - Height of the thumbnail. It must be between 1 and 1024. Recommended minimum of 50.
* `smartCropping` - _optional_ - Boolean flag for enabling smart cropping.

### This operation returns the list of domain-specific models that are supported by the Computer Vision API.  Currently, the API only supports one domain-specific model: a celebrity recognizer. A successful response will be returned in JSON.  If the request failed, the response will contain an error code and a message to help understand what went wrong.

### This operation recognizes content within an image by applying a domain-specific model.  The list of domain-specific models that are supported by the Computer Vision API can be retrieved using the /models GET request.  Currently, the API only provides a single domain-specific model: celebrities. Two input methods are supported -- (1) Uploading an image or (2) specifying an image URL. A successful response will be returned in JSON.  If the request failed, the response will contain an error code and a message to help understand what went wrong.

#### Input Parameters
* `model` - _required_ - The domain-specific content to recognize.
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### Optical Character Recognition (OCR) detects printed text in an image and extracts the recognized characters into a machine-usable character stream.   Upon success, the OCR results will be returned. Upon failure, the error code together with an error message will be returned. The error code can be one of InvalidImageUrl, InvalidImageFormat, InvalidImageSize, NotSupportedImage,  NotSupportedLanguage, or InternalServerError.

#### Input Parameters
* `detectOrientation` - _required_ - Whether detect the text orientation in the image. With detectOrientation=true the OCR service tries to detect the image orientation and correct it before further processing (e.g. if it's upside-down). 
* `language` - _optional_ - The BCP-47 language code of the text to be detected in the image. The default value is 'unk'
    Possible values: unk, zh-Hans, zh-Hant, cs, da, nl, en, fi, fr, de, el, hu, it, ja, ko, nb, pl, pt, ru, es, sv, tr, ar, ro, sr-Cyrl, sr-Latn, sk.

### Recognize Text operation. When you use the Recognize Text interface, the response contains a field called 'Operation-Location'. The 'Operation-Location' field contains the URL that you must use for your Get Handwritten Text Operation Result operation.

#### Input Parameters
* `detectHandwriting` - _optional_ - If 'true' is specified, handwriting recognition is performed. If this parameter is set to 'false' or is not specified, printed text recognition is performed.

### This operation generates a list of words, or tags, that are relevant to the content of the supplied image. The Computer Vision API can return tags based on objects, living beings, scenery or actions found in images. Unlike categories, tags are not organized according to a hierarchical classification system, but correspond to image content. Tags may contain hints to avoid ambiguity or provide context, for example the tag 'cello' may be accompanied by the hint 'musical instrument'. All tags are in English.

#### Input Parameters
* `language` - _optional_ - The desired language for output generation. If this parameter is not specified, the default value is &quot;en&quot;.Supported languages:en - English, Default. es - Spanish, ja - Japanese, pt - Portuguese, zh - Simplified Chinese.
    Possible values: en, es, ja, pt, zh.

### This interface is used for getting text operation result. The URL to this interface should be retrieved from 'Operation-Location' field returned from Recognize Text interface.

#### Input Parameters
* `operationId` - _required_ - Id of the text operation returned in the response of the 'Recognize Handwritten Text'

## License

**flow**ground :- Telekom iPaaS / azure-com-cognitiveservices-computer-vision-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
