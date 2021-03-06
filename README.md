Strut
=======

#### GUI / Authoring Tool for ImpressJS ####

This project intends to create an extensible, maintainable, and clean editor for authoring ImpressJS presentations.
I hope this project can also serve as an example of a browser based rich client as the project matures.

Don't know what ImpressJS is?  Check out the ImpressJS demo presentation: http://bartaz.github.com/impress.js/#/bored
And here is a video of the very first version of Strut: http://www.youtube.com/watch?v=zA5s8wwme44

Strut live preview (Firefox, Chrome and Safari only): http://tantaman.github.com/Strut/web-dist/index.html

### Preview ###

A github hosted preview is available at: http://tantaman.github.com/Strut/web-dist/index.html (Firefox, Chrome and Safari only)

The preview currently points to the development version of Strut.

### Mailing List ###
strut-presentation-editor@googlegroups.com

### Building ###
*Note: You can get pre-built versions of Strut here: https://github.com/tantaman/Strut/downloads*

You'll need CoffeeScript and Handlebars installed in order to build Strut.
* Install CoffeeScript (sudo npm install -g coffee-script)
* Install HandleBars (sudo npm install -g handlebars)
* Install listen (sudo gem install listen)

To build everything in one shot, run: `rake devbuild`

To build and minify everything for a production deployment, run: `rake productionbuild`  (the production build will put its results into web-dist instead of web)

You can compile CoffeeScript whenever there is a change by running `rake coffee[w]`

*A `rake devbuild[w]` which will automatically rebuild on changes is also in the works.*

### Running ###

Strut can run entirely from your local filesystem.  
Just point your browser to `file:///path/to/Strut/web/index.html` to view Strut.

### Contributing ###

Strut uses a Maven directory layout so code and resource will be found in `src/main`

In ```Strut``` there is an object for each major component.  The 
[Slides](https://github.com/tantaman/Strut/blob/master/src/main/coffee/model/presentation/Slide.coffee), 
[SlidePreviews](https://github.com/tantaman/Strut/blob/master/src/main/coffee/ui/editor/transition_editor/TransitionSlideSnapshot.coffee), 
[TransitionEditor](https://github.com/tantaman/Strut/blob/master/src/main/coffee/ui/editor/transition_editor/TransitionEditor.coffee), 
[SlideEditor](https://github.com/tantaman/Strut/blob/master/src/main/coffee/ui/editor/SlideEditor.coffee),
etc. all have their own objects so it's easy to
track down and make changes to a component.  ```Strut``` uses [RequireJS](http://requirejs.org/) to keep source files small and
focused.  [BackboneJS](http://documentcloud.github.com/backbone/) is used for ```Strut's``` data model and serialization as well as for binding events in the 
view layers.  

In addition to having organized code, the [markup for Strut](https://github.com/tantaman/Strut/tree/master/src/main/resources/ui/editor/templates) is also 
split up by component and placed in [HandlebarsJS](http://handlebarsjs.com/) template files. 

Here is the basic layout of the source:

* Presentation Model: src/model/presentation
* Editor UI Layer: src/ui/editor
* Model -> ImpressJS Rendering: src/ui/impress_renderer

templates for UI components are contained in src/ui/COMPONENT_NAME/res/templates
in order to package related markup and backing UI (not model) code into modules.

### Acknowledgements ###

* ImpressJS (of course) https://github.com/bartaz/impress.js/
* BackboneJS http://documentcloud.github.com/backbone/
* CoffeeScript http://coffeescript.org/
* RequireJS http://requirejs.org/
* JQuery http://jquery.com/
* Rake http://rubyforge.org/projects/rake/
* HandlebarsJS http://handlebarsjs.com/
* DustJS http://akdubya.github.com/dustjs/
* Class class http://ejohn.org/blog/simple-javascript-inheritance/
* Impressionist https://github.com/hsivaramx/Impressionist