---
extends: _layouts.post
section: content
title: PostCSS Import Fontawesome Fix
date: 2021-04-13
description: How to fix "Your current PostCSS version is 8.x.x, but postcss-import uses 7.x.x" issue with Fontawesome
categories: [laravel, tip, laravel-mix, gotchas]
---

So I recently created a new Laravel application based on the Jetstream starter template; which I highly recommend by the
way if you just want to focus on your application logic and not have to reinvent the authentication proverbial wheel.

I knew I wanted to use Fontawesome for all my icons ([Hero](https://heroicons.com/) and [Feather](https://feathericons.com/)
icons are also great alternatives) but I was having an issue getting it to import into my project with `laravel-mix`
throwing the following error.

```sh
Unknown error from PostCSS plugin. Your current PostCSS version is 8.2.10, but postcss-import uses 7.0.35. Perhaps this is the source of the error below.
ERROR in ./resources/css/app.css
Module build failed (from ./node_modules/mini-css-extract-plugin/dist/loader.js):
ModuleBuildError: Module build failed (from ./node_modules/postcss-loader/dist/cjs.js):
Error: Failed to find '~@fortawesome/fontawesome-pro/css/all.min.css'
  in [
    /Users/<MYUSERNAME>/Projects/Web/<Project>/resources/css
  ]
```

After reading forum posts about changing versions of PostCSS/Import and trying the
[Tailwind PostCSS 7 compatibility build](https://tailwindcss.com/docs/installation#post-css-7-compatibility-build)
it still wasn't working.

I re-read the Fontawesome documentation again (after just skimming it through the first time) and I noticed they were
referencing the JS versions of their scripts over CSS.
```html
<head>
  <!-- Our project just needs Font Awesome solid + brand -->
  <script defer src="/your-path-to-fontawesome/js/brands.js"></script>
  <script defer src="/your-path-to-fontawesome/js/solid.js"></script>
  <script defer src="/your-path-to-fontawesome/js/fontawesome.js"></script>
</head>
<body>
  <i class="fas fa-user"></i> <!-- uses solid style -->
  <i class="fab fa-github-square"></i> <!-- uses brand style -->
</body>
```

So I tried just importing the Fontawesome JS in the `resources/js/app.js` instead of the CSS in `resources/js/app.css`
and the error disappeared.

Below is the working `app.js`.

```js
// js/app.js
import './bootstrap';

import 'alpinejs';

// Import through JS and not CSS.
import '@fortawesome/fontawesome-pro/js/all.min';
```
