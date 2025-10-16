<!-- .slide: data-background="lime" -->
<!-- .slide: data-background="Blue" -->
<!-- .slide: data-background="Yellow" -->
<!-- .slide: data-background="Purple" -->
<!-- .slide: data-background="DarkViolet" -->
<!-- .slide: data-background="Cyan" -->

<!-- .slide: data-background="Blue" -->
# Less JavaScript

HTML alternatives to JavaScript problems

<br>
<a href="https://thet.github.io/talk-ploneconf2025-html">
  https://thet.github.io/talk-ploneconf2025-html
</a>

<footer>
    Johannes Raggam<br>
    <a href="https://www.syslab.com/">syslab.com GmbH</a><br>
    @ Plone Conference 2025
</footer><!-- .element: class="footnote mt-8" -->




<!-- .slide: data-background="lime" -->
## About

Some HTML and CSS features can make comples JavaScript unnecessary.



<!-- .slide: data-background="lime" -->
## Why should you care?

- Performance<!-- .element: class="fragment" --> 
- Accessibility<!-- .element: class="fragment" -->
- Maintainability, Developer experience, ...<!-- .element: class="fragment" -->


<!-- .slide: data-background="lime" -->
## Limitations

- Browser support<!-- .element: class="fragment" --> 
- Design constraints<!-- .element: class="fragment" --> 
- Feature constraints<!-- .element: class="fragment" --> 




<!-- .slide: data-background="Yellow" -->
## Quick wins


<!-- .slide: data-background="Yellow" -->
### lazy image loading

```html [1-4|2]
<img src="image.jpg"
     loading="lazy"
     alt="..."
>
```

- Only for images and iframes<!-- .element: class="fragment" -->
- <span>
    🤔
    No configureable threshold,
    <br>
    <small>but the browser does a good job deciding when to load</small>
  </span><!-- .element: class="fragment" -->
- Just use it!<!-- .element: class="fragment" -->


<!-- .slide: data-background="Yellow" -->
### date, time, datetime-local

```html [1-4|2]
<input type="datetime-local"
       name="appointment"
       value="2025-05-30T13:45"
/>
```

<input type="datetime-local"
       name="appointment"
       value="2025-05-30T13:45"
/><!-- .element: class="fragment medium" -->

- Excellent mobile support<!-- .element: class="fragment" -->
- Text input possible<!-- .element: class="fragment" -->
- <span>
  😐
  i18n support depending on browser
  <br>
  <small>Ref: <a href="https://github.com/plone/mockup/issues/1328">plone/mockup#1328</a></small>
  <br>
  <small>Ref: <a href="https://github.com/Patternslib/Patterns/pull/1172">Patternslib/Patterns#1172</a></small>
  </span>
  <!-- .element: class="fragment" -->


<!-- .slide: data-background="Yellow" -->
### audio, video

```html [1-11|2-7|3,6|8-10]
<audio controls>
  <source src="audio.mp3"
          type="audio/mpeg"
  />
  <source src="audio.wav"
          type="audio/wav"
  />
  <!-- Fallback for browsers that don't support the audio element -->
  <a href="audio.mp3">mp3 download</a>
  <a href="audio.wav">wav download</a>
</audio>
```

<audio controls>
  <source src="https://upload.wikimedia.org/wikipedia/commons/2/24/Bourne_woods_Birdsong_and_rain_2020-06-17_0742.mp3"
          type="audio/mpeg"
  />
</audio>

<br>
Multiple source formats, browser chooses


<!-- .slide: data-background="Yellow" -->
```html [1-11|2-7|3,6|8-10]
<video controls>
  <source src="video.ogv"
          type="video/ogg"
  />
  <source src="video.webm"
          type="video/webm"
  />
  <!-- Fallback for browsers that don't support the video element -->
  <a href="video.ogv">ogg download</a>
  <a href="video.webm">webm download</a>
</video>
```

<video controls>
  <source src="https://upload.wikimedia.org/wikipedia/commons/7/79/Big_Buck_Bunny_small.ogv"
          type="video/ogg"
  />
  <source src="https://upload.wikimedia.org/wikipedia/commons/3/37/Big_Buck_Bunny_with_VTT_acid_test.webm"
          type="video/webm"
  />
  <!-- Fallback for browsers that don't support the video element -->
  <a href="https://upload.wikimedia.org/wikipedia/commons/7/79/Big_Buck_Bunny_small.ogv">ogg download</a>
  <a href="https://upload.wikimedia.org/wikipedia/commons/3/37/Big_Buck_Bunny_with_VTT_acid_test.webm">webm download</a>
</video>


<!-- .slide: data-background="Yellow" -->
audio / video with WaveSurfer.js

```html
<script src="https://cdn.jsdelivr.net/npm/@patternslib/patternslib@9.10.4-alpha.0/dist/bundle.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@patternslib/pat-wavesurfer@1.0.0-alpha.0/dist/remote.min.js"></script>

<audio class="pat-wavesurfer"
       controls
       data-pat-wavesurfer="
            plugins: hover, loop, minimap, zoom;
       "
>
  <source src="audio.mp3" type="audio/mpeg"/>
</audio>
```
<audio class="pat-wavesurfer" controls data-pat-wavesurfer="plugins: hover, loop, minimap, zoom;">
  <source src="https://upload.wikimedia.org/wikipedia/commons/2/24/Bourne_woods_Birdsong_and_rain_2020-06-17_0742.mp3"
          type="audio/mpeg"
  />
  Your browser does not support the audio element.
</audio>




<!-- .slide: data-background="Cyan" -->
## The details/summary element

```html
<details>
  <summary>More info</summary>
  <p>This is additional information that can be shown or hidden by clicking the summary.</p>
</details>
```

<details>
  <summary>More info</summary>
  <p>This is additional information that can be shown or hidden by clicking the summary.</p>
</details>


<!-- .slide: data-background="Cyan" -->
```html [1-13|2,9|3]
<details
    name="info"
    open
>
  <summary>Summary A</summary>
  <p>Text A</p>
</details>
<details
    name="info"
>
  <summary>Summary B</summary>
  <p>Text B</p>
</details>
```

<div>
  <details
      name="info"
      open
  >
    <summary>Summary A</summary>
    <small>Text A</small>
  </details>
  <details
      name="info"
  >
    <summary>Summary B</summary>
    <small>Text B</small>
  </details>
</div><!-- .element: class="fragment" -->


<!-- .slide: data-background="Cyan" -->
## Usages

- Accordions<!-- .element: class="fragment" -->
- Responsive/Mobile Menu<!-- .element: class="fragment" -->
- Plone toolbar<!-- .element: class="fragment" -->
- Form tabbing<!-- .element: class="fragment" -->

- <span>😐 Limited styling options<br><small>open/close transition</small></span><!-- .element: class="fragment" -->


<!-- .slide: data-background="Cyan" -->
## Demos

- https://classic.demo.plone.org/@@resourceregistry-controlpanel
- https://sfd.at
- https://codepen.io/thetetet/pen/azbmwWE




<!-- .slide: data-background="Blue" -->
## Slider / Carousel

```html
<ul class="slider">
  <li>Slide 1</li>
  <li>Slide 2</li>
  <li>Slide 3</li>
  <li>Slide 4</li>
</ul>

<style>
  .slider {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    scroll-behavior: smooth;
    scrollbar-width: none;
  }
  .slider li {
    flex: 0 0 100%;
    scroll-snap-align: start;
    list-style: none;
  }
</style>
```


<!-- .slide: data-background="Blue" -->
<ul class="slider">
  <li>Slide 1</li>
  <li>Slide 2</li>
  <li>Slide 3</li>
  <li>Slide 4</li>
</ul>

<style>
  .slider {
    display: flex !important;
    overflow-x: auto !important;
    scroll-snap-type: x mandatory !important;
    scroll-behavior: smooth !important;
  }
  .slider li {
    flex: 0 0 100% !important;
    scroll-snap-align: start !important;
    list-style: none !important;
  }
</style>


<!-- .slide: data-background="Blue" -->
### CSS scroll buttons (experimental)

https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-button

```html
<style>
  .slider {
    anchor-name: --my-carousel;
  }
  .slider::scroll-button(*) {
    position: absolute;
    position-anchor: --my-carousel;
    align-self: anchor-center;
    border: 0;
    font-size: 2rem;
    background: none;
    color: black;
    opacity: 0.7;
    cursor: pointer;
  }
  .slider::scroll-button(left) {
    content: "◄";
    right: calc(anchor(left) - 45px);
  }
  .slider::scroll-button(right) {
    content: "►";
    left: calc(anchor(right) - 45px);
  }
  .slider::scroll-button(*):hover,
  .slider::scroll-button(*):focus {
    opacity: 1;
  }
  .slider::scroll-button(*):active {
    translate: 1px 1px;
  }
  .slider::scroll-button(*):disabled {
    opacity: 0.2;
    cursor: unset;
  }
</style>
```


<!-- .slide: data-background="Blue" -->

<ul class="slider2">
  <li>Slide 1</li>
  <li>Slide 2</li>
  <li>Slide 3</li>
  <li>Slide 4</li>
</ul>

<style>
  .slider2 {
    display: flex !important;
    overflow-x: auto !important;
    scroll-snap-type: x mandatory !important;
    scroll-behavior: smooth !important;
    scrollbar-width: none !important;
    anchor-name: --my-carousel;
  }
  .slider2 li {
    flex: 0 0 100% !important;
    scroll-snap-align: start !important;
    list-style: none !important;
  }

  .slider2::scroll-button(*) {
    position: absolute;
    position-anchor: --my-carousel;
    align-self: anchor-center;
    border: 0;
    font-size: 2rem;
    background: none;
    color: black;
    opacity: 0.7;
    cursor: pointer;
  }
  .slider2::scroll-button(left) {
    content: "◄";
    right: calc(anchor(left) - 45px);
  }
  .slider2::scroll-button(right) {
    content: "►";
    left: calc(anchor(right) - 45px);
  }
  .slider2::scroll-button(*):hover,
  .slider2::scroll-button(*):focus {
    opacity: 1;
  }
  .slider2::scroll-button(*):active {
    translate: 1px 1px;
  }
  .slider2::scroll-button(*):disabled {
    opacity: 0.2;
    cursor: unset;
  }
</style>


<!-- .slide: data-background="Blue" -->
### With scroll-markers

https://developer.mozilla.org/en-US/docs/Web/CSS/::scroll-marker
```html
<style>
  .slider3 {
    scroll-marker-group: after;
  }
  .slider3 li::scroll-marker {
    content: "";
    border: 1px solid green;
    border-radius: 50%;
    height: 1em;
    width: 1em;
  }
  ::scroll-marker-group {
    display: flex;
    gap: 0.4em;
    place-content: center;
  }
  ::scroll-marker:target-current {
    background: green;
  }
</style>
```


<!-- .slide: data-background="Blue" -->
<ul class="slider3">
  <li>Slide 1</li>
  <li>Slide 2</li>
  <li>Slide 3</li>
  <li>Slide 4</li>
</ul>

<style>
  .slider3 {
    display: flex !important;
    overflow-x: auto !important;
    scroll-snap-type: x mandatory !important;
    scroll-behavior: smooth !important;
    scrollbar-width: none !important;
    anchor-name: --my-carousel;
  }
  .slider3 li {
    flex: 0 0 100% !important;
    scroll-snap-align: start !important;
    list-style: none !important;
  }

  .slider3::scroll-button(*) {
    position: absolute;
    position-anchor: --my-carousel;
    align-self: anchor-center;
    border: 0;
    font-size: 2rem;
    background: none;
    color: black;
    opacity: 0.7;
    cursor: pointer;
  }
  .slider3::scroll-button(left) {
    content: "◄";
    right: calc(anchor(left) - 45px);
  }
  .slider3::scroll-button(right) {
    content: "►";
    left: calc(anchor(right) - 45px);
  }
  .slider3::scroll-button(*):hover,
  .slider3::scroll-button(*):focus {
    opacity: 1;
  }
  .slider3::scroll-button(*):active {
    translate: 1px 1px;
  }
  .slider3::scroll-button(*):disabled {
    opacity: 0.2;
    cursor: unset;
  }

  .slider3 {
    scroll-marker-group: after;
  }
  .slider3 li::scroll-marker {
    content: "";
    border: 1px solid green;
    border-radius: 50%;
    height: 1em;
    width: 1em;
  }
  ::scroll-marker-group {
    display: flex;
    gap: 0.4em;
    place-content: center;
  }
  ::scroll-marker:target-current {
    background: green;
  }
</style>



<!-- .slide: data-background="Blue" -->
### Demos

https://topos.orf.at/marina-abramovic-albertina-modern100

http://localhost:4000/page_m_lead_text.html

http://localhost:5173/




<!-- .slide: data-background="Purple" -->
## form validation

```html
<form>
  <input name="title"
         required
  />
</form>

<style>
  input:invalid {
    border: 2px solid red;
  }
  input:valid {
    border: 2px solid green;
  }
</style>
```

<form>
  <input name="title"
         required
         class="medium"
  />
</form>

<style>
  input:invalid {
    border: 4px solid red;
  }
  input:valid {
    border: 4px solid green;
  }
</style>


<!-- .slide: data-background="Purple" -->
https://patternslib.com/demos/validation

- Uses Web API form validation
- CSS :invalid/:valid selectors
- Adds more validation rules (dependencies on other fields, checkboxes, ...)
- Custom error messages




<!-- .slide: data-background="Purple" -->
## Dialogs

https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/dialog




<!-- .slide: data-background="Purple" -->
## future: masonry

https://www.smashingmagazine.com/native-css-masonry-layout-css-grid/
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout
https://drafts.csswg.org/css-grid-3/#masonry-switch




<!-- .slide: data-background="Purple" -->
## future: maps

https://maps4html.org/




<!-- .slide: data-background="lime" -->
## This talk is available at

- https://thet.github.io/talk-ploneconf2025-html

- https://github.com/thet/talk-ploneconf2025-html




<!-- .slide: data-background="Purple" data-background-image="./resources/imgs/thats_all_folks.svg" -->




<!-- .slide: data-background="Black" -->
Questions?
