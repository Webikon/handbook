# Templating with Blade

### Why to use templating engine in the first place?

1. Cleaner and more readable code than we have when mixing PHP and HTML.
2. Separation of context. Separation of data logic \(backend\) and views \(frontend\). We can, theoretically, use any CMS or backend with those views.
3. Echo and automatic escaping. `{{}}` -&gt; **better security** 
4. Loops - `$loop` variable can be used inside of loops --&gt; cleaner code \(e.g. no need to use `$i = 0; $i++;` when targeting particular loop item anymore\).
5. Defining main template with sections and inheritance. We can extend only sections we need. -&gt; **DRY**
6. Includes - one of the best functionalities. We can include any partial and pass it some data.
7. Utility directives - we can create our own directives. E.g. `@svg` directive, which outputs inlined SVG HTML and we can also pass it some parameter which can for example change SVG’s main class.

### Blade

1. Don’t have impact on speed. Every template is **compiled** and **cached**.
2. Automatic escaping with `{{ }}`
3. Still possibility to use classic PHP.

#### Defining A layout

```php
@section('content')
    This is default content
@show

@yield('content')
```

Difference between `@yield` and `@section … @show` [https://stackoverflow.com/a/46511300](https://stackoverflow.com/a/46511300)

#### Extending A Layout

```php
@extends('layout.app')

@section('content')
    // Custom code
@endsection

@parent
```

#### Components and slots

We are not using at the moment. Will look into in the future.

#### Displaying Data

```php
{{ 'Escaped string' }}
{!! 'Unescaped string' !!}
```

#### Control Structures

Similar to PHP.

`@isset` checks if variable is set `@empty` checks if variable is empty

Loops and `$loop` variable!

`@hasSection` when we want to display section conditionally \(e.g. it has some wrapper, which should not be displayed when section is empty\)

#### Including Sub-Views

```php
@include('partials.components.search-form')

@includeIf('partials.components.search-form')

@includeWhen($show_search, 'partials.components.search-form')
```

#### @svg directive

In themes, we usually use SVG icons and have directory called `/icons/` where all these icons are located and directive points to this directory. We can use Blade directive `@svg(‘icon_name', 'icon_class')` which outputs inline SVG HTML. All outputed icons have default class `.svg-icon`, additional class can be set by second parameter and it will be prefixed by `.svg-icon-` E.g. when we have **Facebook** icon located in `/icons/facebook.svg` and want it to have additional class `.svg-icon-my-custom-class` we can use directive like this:

```php
<div>
    @svg('facebook', 'my-custom-class')
</div>
```

> **Note!** In Jigsaw, there is this caveat, variable cannot be passed as parameter and we can use only strings as parameters.. E.g. we cannot use `@svg($my_variable)`:

```php
@foreach($icons as $icon_slug)
    // This would not work
    @svg($icon_slug)

    // Instead, we have to use something like this
    @switch($icon_slug)
        @case('facebook')
            @svg('facebook')
            @break
        @case('instagram')
            @svg('instagram')
            @break
    @endswitch
@endforeach
```

I hope to fix it soon in the future.

