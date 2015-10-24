# deanlab.github.io
A jekyll based website for DeanLab, a nanoelectronics laboratory out of Columbia University

This will be hosted using github pages.

# Usage

## image handling

There are many spots throughout this site where we use images.  Our prefered method of image handling is via [Cloudinary].  For this to work, in _config.yml we need to set the cloudinar_id to match the cloudinary account we will be using.  A full sized image should be uploaded to cloudinary.  Where an image is to be used, we would then typcially specify the cloudinary image id in the front matter of the document to which it is going to be used.  We can also decide to overide the image and thumbnail options  if we want to change from the defaults

As an alternate, if we are going to use an image stored somewhere else (why?), instead of specifying an imageid, we can specify an imageurl, with the full path to the image you would like to use.

Cloudinary is so nice to use as we don't need to make multiple image sizes for a particular image. Instead we are just going to control the image size through the image_options.  Cloudinary will take care of producing a properly sized image and storing it on a CDN.

## _config.yml

contains the defaults for many of the collections, the cloudinary account needed for our image procesing
title: The Dean Lab
email: tom@codegaucho.com
description: > # this means to ignore newlines until "baseurl:"
This is The Dean Lab, a nanoelectronics laboratory out of Columbia University.
baseurl: "" # the subpath of your site, e.g. /blog/
url: "http://deanlab.github.io" # the base hostname & protocol for your site
twitter_username: codegaucho
github_username:  deanlab
cloudinary_id: codegaucho

## collections

### People

**defaults**

layout: people
image_options: "c_scale,w_320"
thumbnail_options: "c_crop,h_200,w_246"
active_nav: People

**front matter**
name: "Cory R. Dean"
title: "Assistant Professor"
description: "Cory is the fearless leader of the Dean Lab"
imageid: v1381371702/pdjxeo8dxqsvehsjxjoo 
lab: "NWC 704"
office: "CEPSR 916"
phone: "212-854-3189"
email: cory.dean@gmail.com
twitter: codegaucho
facebook: 100006029281065



[Cloudinary]: http://cloudinary.com/