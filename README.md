# 👋 vue-horizontal-list-autoscroll 🕶

<h3 align="center">
  <img alt="Version" src="https://img.shields.io/badge/version-1.1.5-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/MiKr13/S3-Bucket-Download/#README" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
  <a href="#" target="_blank">
    <img alt="License: MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
  </a>
  <a href="https://www.npmjs.com/package/vue-horizontal-list-autoscroll" target="_blank">
    <img alt="NPM Downloads" src="https://img.shields.io/npm/dw/vue-horizontal-list-autoscroll">                                       
  </a>
  <a href="https://twitter.com/mikr1306" target="_blank">
    <img alt="Twitter: mikr1306" src="https://img.shields.io/twitter/follow/mikr1306.svg?style=social" />
  </a>
  <a href="https://github.com/mikr13" target="_blank">
    <img alt="GitHub followers" src="https://img.shields.io/github/followers/mikr13?style=social">                                       
  </a>
</h3>

A pure vue horizontal list implementation with minimal dependencies, ssr support, mobile friendly, touch friendly and responsive now with auto scroll

This project is built on top of [vue-horizontal-list](https://github.com/fuxingloh/vue-horizontal-list), huge shout out to [Fuxing Loh](https://github.com/fuxingloh) for laying the groundwork, every other option and configuration available there is valid here also before version (1.1.5).

## Demo

[All Examples](https://mikr13.github.io/vue-horizontal-list-autoscroll/)

## Installation

```sh
npm i vue-horizontal-list-autoscroll
# or
yarn add vue-horizontal-list-autoscroll
```

## Basic usage

```vue
<vue-horizontal-list-autoscroll-autoscroll :items="items" :options="{responsive: [{end: 576, size: 1}, {start: 576, end: 768, size: 2},{size: 3}], autoscroll:{ enabled: true, returnToStart: true }}">
  <template v-slot:default="{item}">
    <div class="item">
      <h5>{{item.title}}</h5>
      <p>{{item.content}}</p>
    </div>
  </template>
</vue-horizontal-list-autoscroll>
```

## Features

* Lightweight implementation with 1 dependencies.
* SSR supported
* Mobile touch screen friendly
* Invisible scroll bar for consistent Windows and MacOS browsing experience.
* Autoscroll feature with return to start feature
* Snap to the nearest item in the horizontal-list when scrolling.
* Windowed & Full-screen mode
  * The windowed mode will respect the container and not show overflowing item
  * Full-screen mode will show overflowing item, best result for small screen
* Dynamic responsive breakpoint configuration
* Navigation control will show up dynamically for larger screen
* Touch screen friendly
* Minimal config setup
* Custom prev & next icons support
* Tested on chrome, edge and safari
* [Examples](https://github.com/mikr13/vue-horizontal-list-autoscroll/tree/master/examples)

## Options

```js
const options = {
  item: {
    // css class to inject into each individual item
    class: '',
    // padding between each item
    padding: 12 
  },
  autoscroll: {
    // auto scroll feature enabled or not
    enabled: true,
    // if enabled, the interval in seconds, by default 10 seconds
    interval: 15,
    // if enabled, the list will autoscroll to beginning of the list once it reaches the end i.e. all list items are scrolled
    returnToStart: true
  }
  list: {
    // css class for the parent of item
    class: '', 
    // maximum width of the list it can extend to before switching to windowed mode, basically think of the bootstrap container max-width
    // windowed is used to toggle between full-screen mode and container mode
    windowed: 1200,
    // padding of the list, if container < windowed what is the left-right padding of the list
    // during full-screen mode the padding will added to left & right to centralise the item
    padding: 24
  },
  responsive: [
    // responsive breakpoints to calculate how many items to show in the list at each width interval
    // it will always fall back to these:
    {end: 576, size: 1},
    {start: 576, end: 768, size: 2},
    {start: 768, end: 992, size: 3},
    {start: 992, end: 1200, size: 4},
    {start: 1200, size: 5}
  ],
  navigation: {
    // when to show navigation
    start: 992,
    color: '#000'
  }
} 
```

## Examples

### Basic Responsive Usage

* Width between 0 - 576, show 1

* Width between 576 - 768, show 2

* Width catch all, show 3

## Contributing
For any question or feature request please feel free to create an [issue](https://github.com/MiKr13/vue-horizontal-list-autoscroll/issues/new) or [pull request](https://github.com/MiKr13/vue-horizontal-list-autoscroll/pulls).
