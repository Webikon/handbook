---
description: Guidelines specifically for the output in the DOM.
---

# Markup

Follow the regular [WordPress HTML style guide](https://make.wordpress.org/core/handbook/best-practices/coding-standards/html/) and the [WordPress Accessibility Best Practices](https://make.wordpress.org/accessibility/handbook/best-practices/) with the additions listed below.

Generating a semantic DOM is important. Then HTML elements have true meaning and devices like browsers and assistive technology know how to interact with them natively. Even when writing a dynamically generated DOM \(such as with React\), be mindful of what you’re actually outputting.

We aim to meet the [WCAG accessibility guidelines](https://www.w3.org/WAI/) at level AA.

This markup guide is additional to [10up Best Practices on Markup](https://10up.github.io/Engineering-Best-Practices/markup/). So please read them thoroughly as well.

The [Accessibility Testing Guide](https://engineering.hmn.md/guides/testing/accessibility/) explains how to test for valid Markup.

### Semantics <a id="semantics"></a>

* Use semantic HTML5 elements, don’t compose the HTML using mainly \(meaningless\) divs and spans
* Use an `<a>` for change of location
* Use a `<button>` to invoke an action

```markup
// Bad:
<div style="big-heading">News</div>

// Good:
<h1>News</h1>
```

```markup
// Bad:
<a href="#" id="js-some-action">Open</a>

// Good:
<button id="js-some-action">Open</button>
```

### screen-reader-text class <a id="screen-reader-text-class"></a>

This class is used to hide content from screen but not from screen readers and search engines.  
[The CSS class screen-reader-text](https://make.wordpress.org/accessibility/handbook/best-practices/markup/the-css-class-screen-reader-text/) explains why and how and gives the most recent CSS properties used for WordPress core.

On some projects, where we use Bootstrap, this class is called `.sr-only` .

### Title attribute <a id="title-attribute"></a>

#### Title attribute on iframes <a id="title-attribute-on-iframes"></a>

Give iframes a unique title attribute describing the content of the iframe.

```text
<iframe title="Your title" src="your-url"></iframe>
```

#### Title attribute on links <a id="title-attribute-on-links"></a>

Don’t use a title attribute on links. The support is so different per device that it can’t be trusted to be consistent.

```markup
// Bad:
<a href="your-url" title="Your title"></a>

// Good:
<a href="your-url">Your title</a>
```

If you don’t want to show the link text, use the `.screen-reader-text` class to hide it from vision:

```markup
<a href="your-url"><span class="screen-reader-text">Your title</span></a>
```

### ARIA <a id="aria"></a>

WAI-ARIA stands for “Web Accessibility Initiative – Accessible Rich Internet Applications”. It is a set of attributes to help enhance the semantics of a web site or web application to help assistive technologies, such as screen readers for the blind, make sense of certain things that are not native to HTML.

> First rule of ARIA: don’t use ARIA.

A pure semantic HTML5 solution without ARIA is always preferred. This way all devices interacting with the web page or app understand the meaning of this element.

```markup
// Bad:
<div role="button" tabindex="0">text</div>

// Redundant:
<button role="button">text</button>

// Good:
<button>text</button>
```

ARIA can be useful for announcing dynamic or toggled content.

* W3C Specs and examples on [Using ARIA](https://w3c.github.io/using-aria/)
* [ARIA Widgets Code Library](https://dequeuniversity.com/resources/)

