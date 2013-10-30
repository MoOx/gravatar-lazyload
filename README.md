# Gravatar Lazyload

> Gravatar script that allow you to (lazy) load some gravatars on your webpage without using `<img>`.

_No javascript dependency. Less than 1Kb compressed + gzipped_

You just need to include `gravatar.js` script, and add a `data-email` or `data-email-md5` attribute on elements having `gravatar`, `gravatar-before` or `gravatar-after` class.
This elements will be or have`:before`/`:after` pseudo elements with the gravatar in it.

Gravatar are added after `window.load` fired (to make a sort of lazy load).

## TODO

+ lazyload when the gravatar will appear on the viewport, not just after window.load.

## Installation

*Remember you need to include all scripts added to your page (using your own solution: simple `<script>`s, or using you favorite assets manager - grunt.js, require.js...)*

**Note: MD5.js is optional (not needed if you directly use data-email-md5 attribute - *recommanded method*).**

## Usage

Include `gravatar.js` in your page and optionally `lib/md5.js` & two polyfills (`addEventListener` + `getElementsByClassName`) if you want old browsers support.
Note that I advise you [aight.js](https://github.com/shawnbot/aight) to find  nice polyfills in it, instead of the polyfills I gave.

To trigger the JavaScript you need to add a classname to the element. You can use `gravatar`, `gravatar-before` or `gravatar-after` depending on where you want the Gravatar to be added.

That's it.

## Options

If you want to change default options, you can just create (before including the `gravatar.js` script) the javascript object `gravatarOptions`.
Here are default values:

```js
var gravatarOptions = {
    size: 48, // can be from 1 to 512
    rating: 'PG', // Gravatar rating values: G | PG | R | X - see Gravatar doc for more info
    defaultImage: ''; // Default Gravatar url if the user don't have one. Can be an url or a Gravatar value like 404 | mm | identicon | monsterid | wavatar
    propertyUsed: 'background-image', // Can be `background-image`, `background`, or `content` since the value is an `url(…)`
    addDimensions: true, //  true or false (add width & height). Usefull if you use background property. In this case, remember to add content: "";
    pseudoDisplay: 'inline-block', // CSS display property used for pseudo elements. Can be `block` or `inline-block` (inline is not advised...) or `null
}
```

*Note: `gravatar` class is incompatible with `propertyUsed: 'content'` since this property is only for pseudo elements.*

**Alternatively, you can specify some options for each element with html attributes, using `data-gravatar-size`, `data-gravatar-rating`, `data-gravatar-defaultImage`**

## Credits

Based on [an original idea](http://darcyclarke.me/development/quick-tip-get-gravatar-images-from-emails-with-javascript/) of [@darcyclarke](https://github.com/darcyclarke) & [@chriscoyier](https://github.com/chriscoyier)

## License

Released under [MIT Licence](http://moox.mit-license.org/)


[![Bitdeli Badge](https://d2weczhvl823v0.cloudfront.net/MoOx/gravatar-lazyload/trend.png)](https://bitdeli.com/free "Bitdeli Badge")

