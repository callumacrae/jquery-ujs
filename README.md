Notes on the npm supporting fork
=======================================
We forked from the official version at https://github.com/rails/jquery-ujs to support npm.

* Reasons: [rails/jquery-ujs/issues/423](https://github.com/rails/jquery-ujs/issues/423) and 
  [rails/jquery-ujs/pull/380](https://github.com/rails/jquery-ujs/pull/380)
* We'll do our best to keep the npm version consistent with the version used by jquery-ujs.
* There should be 2 files that differ: Addition of a `package.json` and changes ONLY to the top of the README.md
* For advice on how to use the npm version with Rails and Webpack, see 
  [shakacode/react-webpack-rails-tutorial/pull/88](https://github.com/shakacode/react-webpack-rails-tutorial/pull/88) and 
  [forum article on considerations for jquery with Rails and webpack](http://forum.railsonmaui.com/t/considerations-for-jquery-with-rails-and-webpack/344).
* Publishing to npm:

```bash
   git pull https://github.com/rails/jquery-ujs.git master
   vim package.json # updating version number
   git commit -am 'the version number'
   git push --follow-tags origin master
   npm publish
```

Unobtrusive scripting adapter for jQuery
========================================

This unobtrusive scripting support file is developed for the Ruby on Rails framework, but is not strictly tied to any specific backend. You can drop this into any application to:

- force confirmation dialogs for various actions;
- make non-GET requests from hyperlinks;
- make forms or hyperlinks submit data asynchronously with Ajax;
- have submit buttons become automatically disabled on form submit to prevent double-clicking.

These features are achieved by adding certain ["data" attributes][data] to your HTML markup. In Rails, they are added by the framework's template helpers.

Full [documentation is on the wiki][wiki], including the [list of published Ajax events][events].

Requirements
------------

- [jQuery 1.8.x or higher][jquery];
- HTML5 doctype (optional).

If you don't use HTML5, adding "data" attributes to your HTML4 or XHTML pages might make them fail [W3C markup validation][validator]. However, this shouldn't create any issues for web browsers or other user agents.

Installation using the jquery-rails gem
------------

For automated installation in Rails, use the "jquery-rails" gem. Place this in your Gemfile:

```ruby
gem 'jquery-rails'
```

And run:

```shell
$ bundle install
```

Require both `jquery` and `jquery_ujs` into your application.js manifest.

```javascript
//= require jquery
//= require jquery_ujs
```

Installation using Bower
------------

Run `bower install jquery-ujs --save` to install the jquery-ujs package.

Usage
------------

Require both `jquery` and `jquery-ujs` into your application.js manifest.

```javascript
//= require jquery
//= require jquery-ujs
```

How to run tests
------------

Follow [this wiki](https://github.com/rails/jquery-ujs/wiki/Running-Tests-and-Contributing) to run tests.

## Contributing to jquery-ujs

jquery-ujs is work of many contributors. You're encouraged to submit pull requests, propose
features and discuss issues.

See [CONTRIBUTING](CONTRIBUTING.md).

## License
jquery-ujs is released under the [MIT License](MIT-LICENSE).

[data]: http://www.w3.org/TR/html5/dom.html#embedding-custom-non-visible-data-with-the-data-*-attributes "Embedding custom non-visible data with the data-* attributes"
[wiki]: https://github.com/rails/jquery-ujs/wiki
[events]: https://github.com/rails/jquery-ujs/wiki/ajax
[jquery]: http://docs.jquery.com/Downloading_jQuery
[validator]: http://validator.w3.org/
[csrf]: http://api.rubyonrails.org/classes/ActionController/RequestForgeryProtection.html
[adapter]: https://github.com/rails/jquery-ujs/raw/master/src/rails.js
