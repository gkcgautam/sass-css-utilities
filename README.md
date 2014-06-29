sass-css-utilities - A SASS library for rapid frontend development.
==============

## Intro

The main aim of the library is to speedup up the website development process with the usage of simple utility classes.
The utility classes can be used to modify web page elements in `tablets` and `phones` without needing to make any CSS changes.

It also contains a small set of useful SASS mixins.

## Class names

All of the CSS classes support usage in phones and tables through media queries. You simply need to add the device category specific prefix to make them device specific. The default prefixes are: `tab-`, `phn-tab-`, `phn-` (These can be changed in config)

For example, For  modifying the display property of a div in different devices:

    <div class="block phn-inline-block">I will change to inline block when viewed on a phone</div>

Similarly for changing margin or padding:

    <div class="pad-30 mar-60 tab-pad-20 tab-mar-40 phn-pad-10 phn-mar-20">My margin and padding will change in tablet and phone</div>

This is just a simple example. The classes can be used to modify even a single property like this:

    <div class="pad-30 mt-60 phn-pv-20 phn-mt-20">My margin and vertical padding will change in phone</div>



DOCS COMING SOON!
