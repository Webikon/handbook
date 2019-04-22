---
description: Basic template and file structure for frontend.
---

# Template Structure

We always try to look at the website as set of reusable components. Whole website should of course follow some design guidelines and patterns. We should also try to think how deep should we go when breaking down to components. So sometimes less is better :\) Below is high-level perspective on how this structure should work:

### Components

* Smallest elements which can be reused across the website.
* They should not have styles for external margins, floats, positions and so on, so they can be reusable in different contexts. We can make them more flexible by allowing $classes variable to be passed and used, and also we would avoid creating additional unnecessary HTML wrapper.   In this example, we are including `section-heading` component, setting Title and adding additional classes. 

{% code-tabs %}
{% code-tabs-item title="partials/component/section-heading.blade.php" %}
```php
@php
/**
 * Component for displaying Section Heading.
 *
 * Passable variables:
 *    string $heading_tag
 *    string $title
 *    string $subtitle
 *    string $classes
 */
 
// Set defaults
$heading_tag = $heading_tag ?? 'h1';
@endphp

<div class="section-heading {{ $classes ?? '' }}">
    @if ($title)
        <{{ $heading_tag }} class="section-heading__title"> {{ $title }} </{{ $heading_tag }}>
    @endif

    @if ($subtitle)
        <div class="section-heading__subtitle"> {{ $subtitle }} </div>
    @endif
</div>
```
{% endcode-tabs-item %}
{% endcode-tabs %}

{% code-tabs %}
{% code-tabs-item title="page.blade.php" %}
```php
@include('partials.components.section-heading', [
    'classes' => 'mt-10 mb-20',
    'title' => 'Custom title',
])
```
{% endcode-tabs-item %}
{% endcode-tabs %}

* Components may in some occasions contain other components.

  Examples: **buttons, search form, social buttons, banner or post/product teaser** \(can both contain button\),...

### Sections

* Larger parts of website built from components or other sections. \(TODO: come up with example on section in section\)
* These can have layout/positioning styles, external margins,...
* If we have several different variation of same section, e.g with slightly different column count or different background, we can also allow them to use optional $classes variable as mentioned in **Components**.
* Examples: **posts/products loop, filters section with select inputs, header, footer, sidebar**...

### Templates

* Largest parts of website built from sections.
* These can have layout/positioning styles, external margins,...
* Examples: **homepage, contact template, single post, ...**

### **Layouts**

Basic HTML layout for whole website. We usually use `master.blade.php` as basic layout.  
This layout file includes all sections and components, which are used on every template.  
All **Templates** are extending from this.  
When there are slight changes and some template is displaying something differently, e.g. footer is displayed everywhere except Contact template, we can add simple condition.  
When there are bigger changes in layout which cannot be solved by simple condition \(e.g. on checkout, there is different header, footer and main container have different classes\) we can create another layout, e.g. `checkout.blade.php` and extend some templates from this new one.

## File structure

### Views

In Blade views we have this file structure \(starting with Jigsaw\):  
`_` prefix on folders is used so Jigsaw will know that those folders are only partials. 

```php
/_components // all components as described above
    /_nav // e.g. nav-main
    /_header // e.g. basic head partial, mobile header partials, ...
    /_footer // (optional) footer specific partials 
    hero.blade.php
    teaser-post.blade.php
    ...
/_layouts // all layouts which other pages and templates are extending, 
    master.blade.php // this is basic one
/_sections // all sections as described above
/_woocommerce // all woocommerce overrided templates
// in this root directory, we also have WP pages and templates, which are
// including components and sections
index.blade.php
page.blade.php
```

### Assets

**Javascript**   
We are creating partials for each functionality and using Webpack `@import` to include them in `main.js` .  All partials should have `_` prefix, so we know they are partials :\)  
JS files without prefix are not imported in `main.js` but processed via Laravel Mix as additional separate assets - this is useful when we want to load this JS only on particular template.

**SASS**  
We are creating partials on template structures described above and according to views.  
Woocommerce can be exception and have different naming.  
Also see `main.scss` for more info on how all SASS partials are imported.

> When importing from `node_modules` you can use `~` prefix.  
> E.g. `@import "~slick-carousel/slick/slick";`
>
> See [https://github.com/webpack-contrib/sass-loader\#imports](https://github.com/webpack-contrib/sass-loader#imports)

**Images**  
All SVG icons or some additional static images.



#### Basic Jigsaw file structure:

```php
/_assets // all assets processed by Laravel Mix
   /js
        main.js // this file imports all other partials
        _sliders.js // partial for initializing sliders
        _sticky-header.js // partial
        checkout.js // this should not be imported, but rather processed by Laravel Mix
    /sass
        /base // basics as variables, mixins and CSS framework.
            _bootstrap.scss
            _functions.scss
            _mixins.scss
            _variables.scss
        /components // components as described above
        /global  // styles for global elements, which are used across website
            _accessibility.scss
            _animations.scss
            _buttons.scss
            _fonts.scss
            _forms.scss
            _helpers.scss
            _icons.scss
            _lists.scss
            _media.scss
            _tables.scss
            _typography.scss
            _widgets.scss
            _wp-classes.scss
        /misc // misc styles, like overwriting vendor styles for 3rd party libraries (Slick), etc.
            _slick-custom.scss
        /sections // as described above
        /templates // as described above
        _shame.scss // shameful styles - this might include !importants, hacky overrides, or verbose styles you know can be done differently 
         main.scss // all partials are imported here
/assets // Not processed by Laravel Mix
     /svg // SVG icons
     /images // static images       
```

### Sources:

[https://laravel.com/docs/5.7/blade](https://laravel.com/docs/5.7/blade)   
[http://acmeextension.com/why-use-templating-engine/](http://acmeextension.com/why-use-templating-engine/)

