# Presentation Writer  

Markdown Preview Enhanced uses [reveal.js](https://github.com/hakimel/reveal.js) to render beautiful presentations.

[Click here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html) to see the introduction.

![presentation](https://user-images.githubusercontent.com/1908863/26854512-141e87ae-4adc-11e7-8c48-f6e2970338a6.gif)


## Presentation Front-Matter
You can configure your presentation by adding front-matter to your markdown file.   
You need to write your settings under `presentation` section.  
For example:  
```markdown
---
presentation:
  width: 800
  height: 600
---

<!-- slide -->
Your slides goes here...
```   
The presentation above will has size `800x600`

### Settings  
```yaml
---
presentation:
  # The "normal" size of the presentation, aspect ratio will be preserved
  # when the presentation is scaled to fit different resolutions. Can be
  # specified using percentage units.
  width: 960
  height: 700

  # Factor of the display size that should remain empty around the content
  margin: 0.1

  # Bounds for smallest/largest possible scale to apply to content
  minScale: 0.2
  maxScale: 1.5

  # Display controls in the bottom right corner
  controls: true

  # Display a presentation progress bar
  progress: true

  # Display the page number of the current slide
  slideNumber: false

  # Push each slide change to the browser history
  history: false

  # Enable keyboard shortcuts for navigation
  keyboard: true

  # Enable the slide overview mode
  overview: true

  # Vertical centering of slides
  center: true

  # Enables touch navigation on devices with touch input
  touch: true

  # Loop the presentation
  loop: false

  # Change the presentation direction to be RTL
  rtl: false

  # Randomizes the order of slides each time the presentation loads
  shuffle: false

  # Turns fragments on and off globally
  fragments: true

  # Flags if the presentation is running in an embedded mode,
  # i.e. contained within a limited portion of the screen
  embedded: false

  # Flags if we should show a help overlay when the questionmark
  # key is pressed
  help: true

  # Flags if speaker notes should be visible to all viewers
  showNotes: false

  # Number of milliseconds between automatically proceeding to the
  # next slide, disabled when set to 0, this value can be overwritten
  # by using a data-autoslide attribute on your slides
  autoSlide: 0

  # Stop auto-sliding after user input
  autoSlideStoppable: true

  # Enable slide navigation via mouse wheel
  mouseWheel: false

  # Hides the address bar on mobile devices
  hideAddressBar: true

  # Opens links in an iframe preview overlay
  previewLinks: false

  # Transition style
  transition: 'default' # none/fade/slide/convex/concave/zoom

  # Transition speed
  transitionSpeed: 'default' # default/fast/slow

  # Transition style for full page slide backgrounds
  backgroundTransition: 'default' # none/fade/slide/convex/concave/zoom

  # Number of slides away from the current that are visible
  viewDistance: 3

  # Parallax background image
  parallaxBackgroundImage: '' # e.g. "'https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg'"

  # Parallax background size
  parallaxBackgroundSize: '' # CSS syntax, e.g. "2100px 900px"

  # Number of pixels to move the parallax background per slide
  # - Calculated automatically unless specified
  # - Set to 0 to disable movement along an axis
  parallaxBackgroundHorizontal: null
  parallaxBackgroundVertical: null

  # Parallax background image
  parallaxBackgroundImage: '' # e.g. "https://s3.amazonaws.com/hakim-static/reveal-js/reveal-parallax-1.jpg"

  # Parallax background size
  parallaxBackgroundSize: '' # CSS syntax, e.g. "2100px 900px" - currently only pixels are supported (don't use % or auto)

  # Number of pixels to move the parallax background per slide
  # - Calculated automatically unless specified
  # - Set to 0 to disable movement along an axis
  parallaxBackgroundHorizontal: 200
  parallaxBackgroundVertical: 50

  # Enable Speake Notes
  enableSpeakerNotes: false
---
```


## Customize Slide Style
You can add `id` and `class` to a specific slide like this:   
```markdown
<!-- slide id:"my-id" class:"my-class1 my-class2" -->
```

Or if you only want to customize `nth` slide, modify your `less` file like this:   
```less
.markdown-preview-enhanced.markdown-preview-enhanced {
  // ...
  // change the font size of the second slide to 14px
  .preview-slides .slide:nth-child(2),
  &[data-presentation-mode] section:nth-child(2) {
    font-size: 14px; // change font size to 14px;  
  }
}
```

To show a footer image for every slide [#257](https://github.com/shd101wyy/markdown-preview-enhanced/issues/257).   

```less
@footer-img: no-repeat url(assets/footer_logo.png) bottom left;

.preview-slides .slide,
&[data-presentation-mode] {
  .slide-background {
    background: @footer-img;
    background-size: 8%; // I'm using a very large image, so I need to specify a smaller size here
  }
  .slide-background:last-child {
    display: none;
  }
}
```
