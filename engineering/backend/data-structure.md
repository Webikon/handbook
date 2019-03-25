---
description: >-
  Basic data structure to easily move data from Jigsaw to Themosis (or any other
  framework).
---

# Data structure

## Project Data Structure

Our goal is to easily move Blade templates filled with dummy data from Jigsaw to WP theme and replace dummy data with dynamic ones.

Jigsaw is using global variable called `$page` [https://jigsaw.tighten.co/docs/site-variables/](https://jigsaw.tighten.co/docs/site-variables/) so we will use it to define dummy data for our pages and templates.   
Then in Themosis, we will create Controllers to pass data where we need them and just slightly adjust variables used in templates. 

All code below is defined in `config.php`.

**Data used on all pages,** we will add as `global_settings`

```php
 'global_settings' => [
    'site_name' => 'My cool website',
    'site_url' => '#',
    'site_logo' => [
        'url' => '',
        'alt' => '',
    ],
    'footer_copyright' => '@2019 Copyright by Webikon',
    'social' => [
        'facebook_url' => '#',
        'instagram_url' => '#',
        'youtube_url' => '#',
        'twitter_url' => '#',
    ],
],
```

E.g. in template, we will get site name like this `$page['global_settings']['site_name']`

**Site menus** will be defined like this:

```php
'main_menu_items' => [
    [
        'title' => 'Domov',
        'url' => '/',
        'target' => '',
        'classes' => 'is-current'
    ],
    [
        'title' => 'About us',
        'url' => '/',
        'target' => '_blank',
        'classes' => '',
    ],
],
```

**Data for particular page or template**, we will use `$template_slug` \(e.g. `front_page` , `blog`, `single_page`, `single_post`, `cart`, `checkout` ...\) as array key. Also notice, that different sections will have its own array of data:

```php
'front_page' => [
    // Sections data should be separated  
    'hero' => [
        'title' => 'This is hero title',
    ],
    'featured_posts' => [
        'section_title' => 'Featured posts',
        // Items should be get from collection
    ]
]
```

So e.g. on Homepage, we will use `$page[‘front_page’][‘hero’][‘title’]` to display hero title. This way, it would be easier for us to convert dummy data to dynamic data. \(another slugs examples can be \)

**Data for custom post types posts** can be added as **Collections** [https://jigsaw.tighten.co/docs/collections-variables-and-functions/](https://jigsaw.tighten.co/docs/collections-variables-and-functions/)   
So if post would have so custom field called `address`, we would add it like this:

```php
'collections' => [
    'posts' => [
        'author' => 'Webikon',
        'address' => '1234 Bratislava, Slovakia',
        'title' => 'Default post title',
        'path' => 'blog/{filename}',
    ],
],
```

>

