# Blank HTML5 Website Framework

The whole point of this is to abstract things I do over and over again when starting a new web design/development project. This reflects my workflow and may change over time because of that. 

## Production Recommendations

During development I work with multiple CSS files as needed, and multiple JS files for each part of the site or functionality. But when I move to production, I normally put together a build setup that optimizes the code for production.

You should have a build process that combines and minifies the CSS files, and combines and minifies your JS files as well. Remember Modernizr includes the HTML5 shim so you need to keep that in the `head`, but your production ready combined JS should be placed just before the closing `</body>` tag. 

I personally use [YUICompressor](http://developer.yahoo.com/yui/compressor/) for CSS and [Google Closure Compiler](http://code.google.com/closure/compiler/) for JS.

## Included Resources

It includes a few additional items by default:

* [HTML5 Reset Stylesheet](http://html5doctor.com/html-5-reset-stylesheet/) by [Richard Clark](http://richclarkdesign.com/) -- *which was adapted from the Eric Myer's Reset CSS file.*
* [Modernizr](http://modernizr.com) -- Which takes care of adding the HTML5 shim for IE in addition to providing a fantastic way to provide progressive enhancement for new features whose support is still spotty. 
* [jQuery](http://jquery.com) -- A local copy is included for development, then for production simply un-comment the Google CDN link and remove the local `<script>` tag.
  
## File Layout

    .
    ├──index.html
    ├──Readme.md  
    ├── assets/                   
    │    └── css/  
    │    │     └── style.css     # empty css file
    │    ├── fonts/              # empty, for storing web fonts
    │    ├── images/             # empty, for all site images
    │    └── js/
    │    │    ├── main.js        # I almost always need at least one script file, this gets me started
    │    │    └── lib/           # External libraries and plugins should go here
    │    │    │    └── jquery-3.2.1.min.js
    │    └── sass/
    │    │    └── partials/      # all partials that nedded goes here
    │    │    │    └── reset.scss
    │    │    ├── mixins/        # all website's style mixins goes here
    │    │    └── style.scss     # empty sass files
    │    └── views/
    │    │    ├── partials/      # all views partials that nedded goes here, ex: header and │footer
    │    │    ├── mixins/        # all views mixins goes here
    │    │    └── index.pug
