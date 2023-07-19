---
extends: _layouts.post
section: content
title: Laravel Herd - Laravel development perfected
date: 2023-07-19
description: One click PHP development environment.Zero dependencies. Zero headaches.
categories: [laravel, tip, herd, valet, development, localhost]
---

[LaraconUS](https://twitter.com/hashtag/LaraconUS?src=hashtag_click) 2023 announced some amazing tools including the release of Herd an all-in-one development environment for Laravel with zero dependency and without the need for brew.

If you've used Laravel Valet before, you'll be familiar with the concept of Herd however, Herd is a lot more than just a CLI tool to manage your local development environment. Herd is an
application that will sit neatly in your menu bar and allow you to manage your local development environment with ease.

## Installation

To install Herd, you can download the latest version from the [Laravel Herd website](https://herd.laravel.com). Herd is only available for macOS with no plans to support Windows or Linux.

Once you've downloaded the application, you can install it by dragging the application to your Applications folder.

![Herd Installation](https://i.imgur.com/YRBmXbe.png)

## Migrating from Valet

Herd allows you to seamlessly migrate you existing sites and settings from Valet.

![Herd Migration](https://i.imgur.com/RUILgQu.png)

All your PHP projects placed in the `~/Herd` directory will be automatically detected and available in your browser. Any site previously configured with Valet will be available automatically.

![Herd Sites](https://i.imgur.com/hAeDo9B.png)

![Herd Sites2](https://i.imgur.com/J8aZjZK.png)

## Exposing your local environment

A cool feature of heard is the ability to share your local development environment with the world using [Expose](https://expose.dev/). This is great for testing your application on mobile devices or sharing your work with clients.

## Conclusion

Finally, the Herd application that sits neatly in your menu bar allows you to manage your PHP versions and NGINX configurations with ease. This was a little trickier with Valet and required you to use the terminal as well having to occasionally force PHP version changes by re-linking PHP.
I can easily invision Herd becoming the go-to development environment for Laravel developers on macOS. However, if you're not convinced and you want to stick with Docker give [OrbStack](https://orbstack.dev/) a try. It's much faster than Docker Desktop and has a lot less overhead.



