# deanlab.github.io
A jekyll based website for DeanLab, a nanoelectronics laboratory out of Columbia University

This will be hosted using github pages.

# Usage

## startup
**Pre-requisites**
Check that ruby is installed

```sh
$ npm ruby -v
```

With a mac, you should be fine.  If ruby is not installed, I would recommend installing rvm, and setting a default version.

then we can 

```sh
$ gem install jekyll
$ gem install bundler
```

clone this repository locally, switch into the repositories directory, and do a 

```sh
$ bundle install
```

this should load all the gems needed to run this Jekyll as there is a Gemfile with the other required gems as part of this repository

We should now be able to fire up Jekyll and see what it all looks like

```sh
$ bundle exec jekyll serve
```

**Making changes and adding content**

The finer points of each collection will be documented below.  When you have made changes, before pushing them back to github, make sure you test that the application compiles everything nicely by starting it with

```sh
$ bundle exec jekyll serve
```

and checking it in a browser.  If all goes well, deploy to github by pushing your changes. At the command line this would look something like

```sh
$ git add -A
$ git commit -m "Added info on work holes"
$ git push origin master
'''


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
