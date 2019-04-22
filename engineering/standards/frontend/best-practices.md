---
description: Frontend-specific best practices.
---

# Best Practices

### Perceived Performance <a id="perceived-performance"></a>

Perceived performance is how performant the user perceives the site, as opposed to the technical measurements of performance. While technical performance is important, perceived performance can have a greater effect on the users willingness to stay on the site.

Perceived performance is typically measured as the time it takes for the content to be usable, this may occur before assets have finished rendering \(images, fonts, JavaScript\).

Perceived performance can be improved by

* Using system fonts
* If web fonts are used, initial render ought to use system fonts and switch to the web font once it completes loading \(FOUT\). In recent browsers this can be achieved in CSS using [`font-display: swap`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display) in older browsers the [Font Face Observer](https://fontfaceobserver.com/) JavaScript library can be used.
* Avoid unnecessary jumps.
* As assets load, images, advertisements, video and other embeds, they can cause text content to jump around on the page. Avoid this by using CSS and/or width and height attributes to allow space for this content to fill.
* Lazy load images

### Eliminate Unnecessary Downloads <a id="eliminate-unnecessary-downloads"></a>

Render blocking downloads will have the largest effect on the perceived performance of a web page. Having some blocking requests is unavoidable but they should be kept to a minimum. Google’s Lighthouse documentation [identifies render blocking resources](https://developers.google.com/web/tools/lighthouse/audits/blocking-resources#more-info).

Assets used together should be combined into as few downloads as possible. Each file added to a web page introduces additional overhead – even on HTTP/2.

### Progressive Enhancement <a id="progressive-enhancement"></a>

Progressive enhancement emphasizes core webpage content first. This strategy then progressively adds more nuanced and technically rigorous layers of presentation and features on top of the content as the end-user’s browser/internet connection allow.\*

The order of displaying content:  
First content \(HTML\), then presentation \(CSS\) and after that client-side scripting \([Chocolatey Layers of Progressive Enhancement](https://alistapart.com/article/understandingprogressiveenhancement)\).

The basic render should include content for the lowest end browsers and allow for JavaScript to fail. Additional content \(carousel frames, items behind accordions, etc\) can be loaded and rendered via JavaScript.

### Accessibility <a id="accessibility"></a>

We aim to meet the [WCAG accessibility guidelines](https://webaim.org/standards/wcag/checklist) at level AA.

The most important topics for accessibility are:

* [Semantic, error free HTML5](https://make.wordpress.org/accessibility/handbook/best-practices/markup/semantic-html/)
* All essential functionality can be executed by keyboard only
* All content is available for all users
* A logical order of content in a web page, [tell a story with your HTML](https://rianrietveld.com/2014/11/14/storytelling-html-practical-accessibility/)
* Dynamic changes on a web page are announced
* Good colour contrast between text and background
* Colour alone isn’t used to convey meaning \(for example with error messages\)
* Animation is stoppable by the user

In the Markup Style Guide \(@TODO Add link\) and the [WordPress Accessibility Handbook](https://make.wordpress.org/accessibility/handbook/best-practices/) you’ll find information on how to apply this in your work.

