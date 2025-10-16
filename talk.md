<!-- .slide: data-background="lime" -->
<!-- .slide: data-background="Blue" -->
<!-- .slide: data-background="Yellow" -->
<!-- .slide: data-background="Purple" -->
<!-- .slide: data-background="DarkViolet" -->
<!-- .slide: data-background="Cyan" -->

<!-- .slide: data-background="Blue" -->
# Less JavaScript: HTML alternatives to JavaScript problems

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
- No configureable threshold, but the browser does a good job deciding when to load<!-- .element: class="fragment" -->

<br>
- Just use it!<!-- .element: class="fragment" -->







### CSS Scroll Snap



<!-- .slide: data-background="lime" -->
## This talk is available at

- https://thet.github.io/talk-ploneconf2025-html

- https://github.com/thet/talk-ploneconf2025-html




<!-- .slide: data-background="Purple" data-background-image="./resources/imgs/thats_all_folks.svg" -->




<!-- .slide: data-background="Black" -->
Questions?
