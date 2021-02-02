
# Abstract

ckeditor5-dll readme solution

The current repo is a fork that creates the ckeditor DLL builds, as described [here](https://ckeditor.com/docs/ckeditor5/latest/builds/guides/development/custom-builds.html "Creating custom builds"), however, with the new [DLL solution](https://github.com/ckeditor/ckeditor5/issues/8517 "Implement DLLs for CKEditor 5 features") being rolled-out by the [ckeditor](https://github.com/ckeditor "CKEditor Ecosystem") team, the implementation is still experimental.

DLL solves the dreaded ['multiple-instances' issue](https://github.com/ckeditor/ckeditor5/issues/667 "Allow adding plugins to a CKEditor 5 build"), as well as provides an improved way of managing the ckeditor plugins integration.


# CKeditor DLL Build
To create your first DLL CKeditor build + basic plugins (see `/src` folder) one has to run through the following commands:

1. ```npm i``` - install all required packages
2. ```npm run build:dll```- building a new ckeditor
   > Note, by default the ```IS_STAND_ALONE``` constant in `ckeditor5/scripts/dll/webpack.config.dll.js` is `TRUE`, that will create the build inside fork's folder structure. 
   
   > When, using the fork  as part of the `djangocms-text-ckeditor` running the ```build:dll``` script will with ```IS_STAND_ALONE``` set to `FALSE` will move the `build` inside the DjangoCMS addon's `/static` folder. NOT REQUIRED.


To make a new `package-lock.json` file run ```npm ci```.

# TODOs
   > 1. Stop basic plugins from failing during build
   > 2. Adjust `ckeditor5/scripts/dll/build-packages-dlls.js` so that instead of moving around the `pacakges`folder, we can use the plugins installed from the `package.json`. 
   
   **NOTE**: this will be fixed by the authors when the branch gets released.