# Fields

```php
<?php

use Themosis\Support\Facades\Field;
use Themosis\Support\Facades\Metabox;
use Themosis\Support\Section;

// This is how to make Settings page
$page = Page::make('page-slug', 'Page Title')->set();

$sections[] = new Section('section-slug-name', 'Section Title');
$sections[] = new Section('section-slug-name-2', 'Section Title');
$sections[] = new Section('section-slug-name-3', 'Section Title');

$settings['section-slug-name'] = [
    Field::text('street-address'),
    Field::text('phone'),
    Field::media('theme-logo')
];
$settings['section-slug-name-2'] = [
    Field::text('street-address'),
    Field::text('phone'),
    Field::media('theme-logo')
];
$settings['section-slug-name-3'] = [
    Field::text('street-address'),
    Field::text('phone'),
    Field::media('theme-logo')
];

$page->addSections($sections);
$page->addSettings($settings);

// This is how to make Metabox and all available fields
Metabox::make('basic_metabox', 'post')
    ->add(Field::text('isbn', [
        'label' => 'The field display title. By default it uses the $name.',
        'info' => 'Add a helper text/description to the field.',
        'data' => 'You can define a default value for the field.'
    ]))
    ->add(Field::textarea('textarea_field'))
    ->add(Field::editor('editor_field'))
    ->add(Field::media('media_field'))
    ->add(Field::choice('checkbox_field', [
        'choices' => [
            'none' => 'None',
            'bel'  => 'Belgium',
            'fra'  => 'France',
            'usa'  => 'United States'
        ],
        'multiple' => true,
        'expanded' => true,
    ]))
    ->add(Field::choice('radio_field', [
        'choices' => [
            'none' => 'None',
            'bel'  => 'Belgium',
            'fra'  => 'France',
            'usa'  => 'United States'
        ],
        'multiple' => false,
        'expanded' => true,
    ]))
    ->add(Field::integer('integer_field'))
    ->add(Field::choice('select_field', [
        'choices' => [
            'none' => 'None',
            'bel'  => 'Belgium',
            'fra'  => 'France',
            'usa'  => 'United States'
        ],
    ]))
    ->add(Field::choice('multiple_select_field', [
        'choices' => [
            'none' => 'None',
            'bel'  => 'Belgium',
            'fra'  => 'France',
            'usa'  => 'United States'
        ],
        'multiple' => true,
    ]))
    ->set();

// This is how to make sections (tabs)
Metabox::make('metabox_with_section_fields', 'post')
    ->setTitle('Custom Metabox Title')
    ->add(new Section('general', 'General', [
        Field::text('author'),
        Field::text('publisher')
    ]))
    ->add(new Section('details', 'Details', [
        Field::text('isbn'),
        Field::media('cover'),
    ]))
    ->set();

```

