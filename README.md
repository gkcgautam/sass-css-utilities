sass-css-utilities - A SASS library for rapid frontend development.
==============

## Intro

The main aim of the library is to speedup up the website development process with the usage of simple utility classes.
The utility classes can be used to modify web page elements in `tablets` and `phones` without needing to make any CSS changes.

It also contains a small set of useful SASS mixins.

## Class names

All of the classes support addition usage in phones and tables through media queries. Just prefix these to the class name: `tab-`, `phn-tab-`, `phn-`

For example, For  modifying the display property of a div in different devices:
  
  <div class="block phn-inline-block">I will chane to inline block when viewed on a phone</div>
  
Similary for changing margin or padding:

  <div class="pad-30 mar-60 tab-pad-20 tab-mar-40 phn-pad-10 phn-mar-20">My margin and padding will change in tablet and phone</div>
  
This is just a simple example. The classes can be used to modifiy even a single property like this:

  <div class="pad-30 mt-60 phn-pv-20 phn-mt-20">My margin and verticla padding will change in phone</div>
  



DOCS COMING SOON!
