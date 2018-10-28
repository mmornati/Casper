# Casper

[![Greenkeeper badge](https://badges.greenkeeper.io/mmornati/Casper.svg)](https://greenkeeper.io/)

The default theme for [Ghost](http://github.com/tryghost/ghost/). This is the latest development version of Casper. If you're just looking to download the latest release, head over to the [releases](https://github.com/TryGhost/Casper/releases) page.

&nbsp;

![screenshot-desktop](https://user-images.githubusercontent.com/120485/27221326-1e31d326-5280-11e7-866d-82d550a7683b.jpg)

&nbsp;

# First time using a Ghost theme?

Ghost uses a simple templating language called [Handlebars](http://handlebarsjs.com/) for its themes.

We've documented our default theme pretty heavily so that it should be fairly easy to work out what's going on just by reading the code and the comments. Once you feel comfortable with how everything works, we also have full [theme API documentation](https://themes.ghost.org) which explains every possible Handlebars helper and template.

**The main files are:**

- `default.hbs` - The main template file
- `index.hbs` - Used for the home page
- `post.hbs` - Used for individual posts
- `page.hbs` - Used for individual pages
- `tag.hbs` - Used for tag archives
- `author.hbs` - Used for author archives

One really neat trick is that you can also create custom one-off templates just by adding the slug of a page to a template file. For example:

- `page-about.hbs` - Custom template for the `/about/` page
- `tag-news.hbs` - Custom template for `/tag/news/` archive
- `author-ali.hbs` - Custom template for `/author/ali/` archive


# Development

Casper styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
$ yarn install
$ yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
$ yarn zip
```

# PostCSS Features Used

- Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
- Variables - Simple pure CSS variables
- [Color Function](https://github.com/postcss/postcss-color-function)


# SVG Icons

Casper uses inline SVG icons, included via Handlebars partials. You can find all icons inside `/partials/icons`. To use an icon just include the name of the relevant file, eg. To include the SVG icon in `/partials/icons/rss.hbs` - use `{{> "icons/rss"}}`.

You can add your own SVG icons in the same manner.

## Configuration
This theme comes with a default ***favicon*** generated with [Real Favicon Generator](http://realfavicongenerator.net). If you want to add your *favicon* you can generate your own (with [Real Favicon Generator](http://realfavicongenerator.net)) and place downloaded files inside the ***assets/img/favicons*** Odin directory.

***Disqus*** comments, ***Google Analytics*** and ***CookieBar*** are disabled by default, but they are easily configurable with *Blog Header Code Injection* inside your Ghost Admin Area.

```html
<script>
// to enable Google Analytics
var ga_id = 'YOUR-UA-ID_HERE';

// to enable Disqus
var disqus_shortname = 'YOUR_DISQUS_SHORTNAME'

//to Enable the cookiebar (http://www.primebox.co.uk/projects/jquery-cookiebar/)
var cookieBarSettings = {
    message: 'We use cookies to track usage and preferences',
	acceptButton: true,
	acceptText: 'I Understand'
};
//List of available CookieBar Settings
// message: 'We use cookies to track usage and preferences',
// acceptButton: true,
// acceptText: 'I Understand',
// acceptFunction: null,
// declineButton: false,
// declineText: 'Disable Cookies',
// declineFunction: null,
// policyButton: true,
// policyText: 'Privacy Policy',
// policyURL: '/privacy-policy/',
// autoEnable: true,
// acceptOnContinue: false,
// acceptOnScroll: false,
// acceptAnyClick: false,
// expireDays: 365,
// renewOnVisit: false,
// forceShow: false,
// effect: 'slide',
// element: 'body',
// append: false,
// fixed: false,
// bottom: false,
// zindex: '',
// domain: 'www.example.com',
// referrer: 'www.example.com'

</script>
```


# Copyright & License

Copyright (c) 2013-2018 Ghost Foundation - Released under the [MIT license](LICENSE).
