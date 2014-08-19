sass-css-utilities - A SASS library for rapid frontend development.
==============
c
## Intro ##

The main aim of the library is to speedup up the website development process with the usage of simple utility classes.
The utility classes can be used to modify web page elements in `tablets` and `phones` without needing to make any CSS changes.

It also contains a small set of useful SASS mixins.

## Class names ##

All of the CSS classes support usage in phones and tables through media queries. You simply need to add the device category specific prefix to make them device specific. The default prefixes are: `tab-`, `phn-tab-`, `phn-` (These can be changed in config)

For example, For  modifying the display property of a div in different devices:

    <div class="block phn-inline-block">I will change to inline block when viewed on a phone</div>

Similarly for changing margin or padding:

    <div class="pad-30 mar-60 tab-pad-20 tab-mar-40 phn-pad-10 phn-mar-20">My margin and padding will change in tablet and phone</div>

This is just a simple example. The classes can be used to modify even a single property like this:

    <div class="pad-30 mt-60 phn-pv-20 phn-mt-20">My top margin and vertical padding will change in phone</div>

----------
## How to use ##
Just copy the directory to your project and import using:
```
@import "sass-css-utilities/sass-css-utilities";
```

If you want to change configuration, declare the configuration variables before importing the library. (In different file, or on top of import statement. Check style.scss for example)


----------
## Documentation ##

### Utility classes ###

#### Floats ####
 - `fl` : Float left
 - `fr` : Float right
 - `clr` or `clear` : Clear both
 - `cf` or `clearfix` : Clear fix

#### Text Align ####
 - `ta-c` or `align-center` : Text align center
 - `ta-l` or `align-left` : Text align left
 - `ta-r` or `align-right` : Text align right

#### Vertical Align ####
 - `va-top` or `align-top` : Vertical align top
 - `va-middle` or `align-middle` : Vertical align middle
 - `va-bottom` or `align-bottom` : Vertical align bottom
 - `va-baseline` or `align-baseline` : Vertical align baseline

#### Appearance ####
 - `hide` or `hidden` : display:none
 - `invisible` : visibility: hidden
 - `transparent` : opacity 0
 - `opaque` : opacity 1
 - `inline` : display:inline
 - `block` : display:block
 - `inline-block` : display:inline-block, max-width:100%
 - `table` : display: table
 - `table-cell` : display: table-cell
 - `table-row` : display: table-row
 - `border-box` : border-box box model

#### Text Utilities ####
 - `hide-text` : Hides text using text-index technique
 - `ellipsis` : Truncates text with ellipsis
 - `text-break` : word-wrap: break-word
 - `non-selectable` or `disable-text-select` : Disables text selection
 - `uc` or `uppercase` : Transforms text to uppercase
 - `lc` or `lowercase` : Transforms text to lowercase

#### Typography ####
 - `normal` : font-weight: normal
 - `bold` : font-weight: bold
 - `italic` : font-style: italic
 - `line-through` : text-decoration: line-through

#### Color Utilities ####
 - `inherit-color` : color: inherit

#### Position ####
 - `pos-relative` : Relative position
 - `pos-absolute` : Absolute position
 - `pos-fixed` : Fixed position, includes backface-visibility: hidden
 - `pos-static` : Static position

#### Interaction ####
 - `clickable` : cursor:pointer
 - `link` : text-decoration: none, on hover and focus: text-decoration: underline
 - `link-clean` : text-decoration: none for every state
 - `link-block` : display: block, text-decoration: none

----------
### Utility SASS mixins ###

#### Border radius ####
 - `border-radius($radius)`
 - `border-radius-top-left($radius)`
 - `border-radius-top-right($radius)`
 - `border-radius-bottom-left($radius)`
 - `border-radius-bottom-right($radius)`

#### Retina @2x background image ####
 - `bg-image-2x($file, $type, $bg-size:false)` : Example: $file: "trip", $type: "png", $bg-size: "200px 100px" will use trip@2x.png for retina devices.

#### Media queries ####
- `at-least-width($device-width)` : Devices with min width as specified
- `until-width($device-width)` : Devices with max width as specified
- `if-device($device)` : Media query specific to a device. Possible values are `tablet`, `phone-tablet` and `phone`.

Device width config can be updated with these variables:
```
$config-phone-max-width   : 767px;
$config-tablet-min-width  : 768px;
$config-tablet-max-width  : 979px;
$config-desktop-min-width : 980px;
```

#### Example ####
```
@include at-least-width(1600px){
    // a wide screen device with width >= 1600px
}
@include until-width(979px){
    // phones and tablets (width <= 979px)
}
@include if-device(tablet){
    // tablet (min-width 768px and max width 979px)
}
@include if-device(phone-tablet){
    // phone or tablet (max-width 979px)
}
@include if-device(phone){
    // phone (max-width 767px)
}
```

#### Shadow ####
 - `box-shadow($params)`
 - `text-shadow($params)`

Example:
```
.title{
    @include box-shadow(2px 2px 2px 0 #000);
}
```

#### Font size and line height ####
 - `font-size($size, $line_height)` : Converts to rem values + provides px values as fallback.

Line height is optional. Example:
```
.title{
    @include font-size(18,24);
}
```

#### Opacity ####
 - `opacity($opacity)` : Accepts values between 0 and 1. Converts to filter property for IE support.

Example:
```
.thumb{
    @include opacity(0.5);
}
```

#### Disable text selection ####
 - `non-selectable` : Disables ability to select text from the element

Example:
```
.description{
    @include non-selectable;
}
```

#### Hide text ####
 - `hide-text` : Hides text by setting large negative text-indent value with overflow hidden.

Example:
```
.logo{
    @include hide-text;
}
```

#### Inline Block ####
 - `inline-block` : Converts element to inline block. Converts to inline as fallback for older IE browsers which do not support inline-block property.

Example:
```
.name{
    @include inline-block;
}
```

#### Clearfix ####
 - `clearfix` : Clears float using the before and after pseudo classes as table.

Example:
```
.element{
    @include clearfix;
}
```

#### Border Box ####
 - `border-box` : Applies border-box box model to element.

Example:
```
.tile{
    @include border-box;
}
```


----------

### Margin ###
`ma` or `mar-auto` : Auto value for left and right margin. (margin-left:auto; margin-right:auto;)

`ml-a` or `ml-auto`: `auto` value for left margin property

`mr-a` or `mr-auto`: `auto` value for right margin property

#### Auto generated margin classes: ####
Specify values of margins to be generated in variable `$config-margins` and the library will automatically generate different cases based on these. 

    $config-margins: (0 5 10 15 20)

Properties available are (where `X` is one of the values passed in `$config-margins`

`mar-X` : Margin X. Eg: mar-5 is margin: 5px;

`mt-X` : Top Margin. Eg: mt-10 is margin-top: 10px;

`mb-X` : Bottom Margin. Eg: mb-10 is margin-bottom: 10px;

`ml-X` : Left Margin. Eg: ml-10 is margin-left: 10px;

`mr-X` : Right Margin. Eg: mr-10 is margin-right: 10px;

`mv-X` : Vertical Margin. Eg: mv-5 is margin-top: 5px; margin-bottom: 5px;

`mh-X` : Horizontal Margin. Eg: mh-5 is margin-left: 5px; margin-right: 5px;

### Padding ###
Padding classes are also auto generated just like the margin classes.

`pad-X` : Padding X. Eg: pad-5 is padding: 5px;

`pt-X` : Top Padding. Eg: pt-10 is padding-top: 10px;

`pb-X` : Bottom Padding. Eg: pb-10 is padding-bottom: 10px;

`pl-X` : Left Padding. Eg: pl-10 is padding-left: 10px;

`pr-X` : Right Padding. Eg: pr-10 is padding-right: 10px;

`pv-X` : Vertical Padding. Eg: pv-5 is padding-top: 5px; padding-bottom: 5px;

`ph-X` : Horizontal Padding. Eg: ph-5 is padding-left: 5px; padding-right: 5px;

----------

### Tablet and Mobile ###
All of these utility classes can be used with Device prefix technique. For example:

```
<div class="pad-40 align-center phn-pad-20 phn-pt-10 phn-align-left">Content</div>
```
This div will have `40px` padding in desktop and `20px` padding in phones. Additionally we have further changes the top padding to `10px` in phone.
Text align will be `center` in desktop and `left` in phone.

----------
## Configuration ##

### !important in rules ###
By default all of the css properties defined in the utility classes have `!important` attribute to ensure that the classes work as expected by overiding values for the element.
This can be disabled with these variable:
```
$scu-use-important: true; // For all classes. Default value is true
$scu-paddings-use-important: true; // For auto generated paddings
$scu-margins-use-important: true; // For auto generated margins
```

### Prefixes ###
Default Global and device prefixes can be changed with these variables:
```
$scu-prefix:              "";
$scu-prefix-tablet:       "tab-";
$scu-prefix-phone-tablet: "phn-tab-";
$scu-prefix-phone:        "phn-";
```
### Custom values for auto-generated margins and paddings ###
The classes to be generated can be specified in variables `$config-paddings` and `$config-margins`. The default values are:
```
$scu-paddings: (0 5 10 15 20 25 30);
$scu-margins:  (0 5 10 15 20 25 30);
```

You can even specify different values for vertical and horizontal classes. (Global as well as media cases)
Check the `config.scss` file for all other config options and examples.

----------

## NOTE ON USAGE ##
These classes are meant to be used only for making minor changes in elements. Default values should always be specified in the css class or id of the element.

## BUGS AND CONTRIBUTIONS ##
If you have a patch, fork my repo and send me a pull request. Bugs can be reported in Issues section.

## License ##

The MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
