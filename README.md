# Lazy Background Images for Vue
![npm version]()

#### vue-lazy-background-images

A simple Vue component for lazy loading background components.

This component is *only* for background images and does not support anything
other than that.

## Installation

```bash
npm install --save-dev vue-lazy-background-images
```

## Usage

Import the component

```js
import VueLazyBackgroundImages from 'vue-lazy-background-images'
```

Register the component

```js
Vue.component('lazy-background', VueLazyBackgroundImages)
```

And put into your DOM

```html
<lazy-background
  :image-source="backgroundImage"
  loading-image="/img/loading.svg"
  error-image="/img/error.png"
  image-class="cam-viewport"
  background-size="cover"
  :image-success-callback="successCallback"
  :image-error-callback="errorCallback">
</lazy-background>
```

And get this out

```html
<div data-width="640" data-height="360" data-state="loaded" class="cam-viewport loaded" style="background-image: url("http://my-site.com/test-image.png"); background-size: cover"></div>
```

You can see the image-source in the above example is a computed property,
although it doesn't have to be.

The callbacks in the above example are bound to data()

Width and height are for the *image* not the containing div.

## Values

* image-source - The source of the desired image (required)
* loading-image - Path to the loader image (png, svg etc) (required)
* error-image - Path to the error image (required)
* image-class - Any classes you wish to include on the image (optional)
* background-size - CSS background-size value (optional, default is `cover`)
* image-success-callback - Function on success (optional)
* image-error-callback - Function on error (optional)

## Details

#### Knowing state

The component attaches its state as a class, as well as a data- attribute
called `state`

There are 3 states, loading, loaded, and error

There are no events that get emitted, you can access either the classlist or
the dataset to see what state your image is in.

#### Image size

There will be 2x data- attributes on your rendered - `width` and `height` which
is the dimensions of the actual image (not the rendered div)

#### Background size

This is `cover` by default although it can be overridden.

#### Callbacks

You can pass in events to trigger on success and failure. These are completely
optional and are not required for this to work.

#### Notes

Contributions welcome, as long as they are related to background images. Enjoy
the component

