# Lazy Background Images for Vue
![npm version]()

#### vue-lazy-background-images

A simple Vue component for lazy loading background components. Only background
images.

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
Vue.component('lazy-background', VueLazyBackgroundImages
)
```

And put into your DOM

```html
<lazy-background
  image-src="http://whatever.com/awesome.png"
</lazy-background>
```

And get this out

```html
<div style="background-image: url(http://whatever.com/awesome.png)"></div>
```

## Values

* image-src - The source of the image

## Customising


#### Notes

Contributions welcome, enjoy the component

