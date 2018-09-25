# Emoji Favicon Webpack Plugin

Leverages [favicon-emoji](https://github.com/albinekb/favicon-emoji) to generate an emoji favicon for your webapp

## Installation

```shell
$ npm install --save-dev emoji-favicon-webpack-plugin
```

## Usage

Add the plugin to your webpack config and pass your emoji of choice to it as an argument. A favicon will be generated and outputted with your bundle.

If you're using [`html-webpack-plugin`](https://github.com/jantimon/html-webpack-plugin), the HTML tags necessary to include your favicon will automatically be added to the `<head>` of your document.

```js
const EmojiFaviconPlugin = require('emoji-favicon-webpack-plugin');
const HtmlPlugin = require('html-webpack-plugin');

module.exports = {
  plugins: [
    new EmojiFaviconPlugin('🦑'),
    new HtmlPlugin() // not required, but really handy
  ]
};
```

## Caveats

MacOS has a pretty awesome and extensive library of emojis built into its [Apple Color Emoji](https://en.wikipedia.org/wiki/Apple_Color_Emoji) typeface, but other operating systems aren't so lucky. If you normally develop on a Mac, you will see different results when you build your app on a Linux or Windows machine.

In order to get consistent results between development and production, you should make sure that you use the same operating system for building in each environment. For example, if you're using Travis CI to build your app, you must specify `osx` as your `os` option in your build config. You may read more about using OS X in Travis [here](https://docs.travis-ci.com/user/reference/osx/).

## Examples

[Transform CSS](https://transform-css.trevorblades.com)