# Magento PWA Base Theme

Required base theme for Magento PWA Studio.

⚠️ **This theme contains no UI or presentational code.** Its role is to
configure the Magento 2 layout system to render the Application Shell for a PWA,
and to serve as a common base theme for Magento PWAs that helps Magento to
identify PWA-enabled themes.

## Usage

A Magento PWA Studio theme must use this theme, **Magento/pwa**, as its parent
theme. This works just like current-state Magento themes do: declare the parent
theme in `theme.xml`, and add a dependency `magento-research/theme-module-pwa`
to your `composer.json` file. This theme is published on Packagist, so no
license keys or additional Composer repository configurations are necessary.

## Features

### Layout Simplification

This theme overrides the core page layouts implemented in the `Magento_Theme`
module. Because Magento PWAs don't use traditional Magento layout resolution,
it's most efficient to turn off as much of the layout system as you can. This
theme contains XML config files which disable and remove as much of the layout-
driven UI as possible. Almost all of it can be done in `default.xml`.

### Application Shell Template

This theme overrides the base PHTML template for Magento storefronts:
`root.phtml`. You can customize your application shell by further overriding
this template file and inserting your own markup and server logic.

### Flags PWAs

Magento 2 will provide more and more optimization around "PWA mode" in future
releases. It follows that there ought to be a simple way for the backend to
identify whether a theme is a "PWA theme" or not. In this version of PWA Studio,
server logic will simply examine your theme to see if its `parent` is this theme.

Beyond this, we discourage using theme inheritance for code reuse in the
PWA world.