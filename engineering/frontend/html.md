# HTML

Principy: spravne pouzivanie tagov \(co je `<section>`  `<aside>`atd.\) doraz na SEO, headingy a nezabudame na pristupnost

Presli sme od PHP+HTML cez TWIG az po BLADE, ktory pouzivame na novych projektoch. Struktura suborov Tato struktura sa opat projekt od projektu moze lisit. Dodrziavame ale komponentarny pristup a pokial mozno znovupouzitelnost komponentov. Pri novsich projektoch uz mame lepsie zadefinovane co je co :\)

#### Komponenty \(Components\) 

Najmensie znovupouzitelne casti na webe. Moze byt napr. button, ale aj search-form, produktovy teaser alebo vacsi komponent ako hero alebo banner. Komponenty by napr. nemali obsahovat vonkajsie marginy, kvoli lepsej znovupouzitelnosti. Mozeme spravit aj viac variacii rovnakeho komponentu napr. s inymi farbami alebo velkostami.

#### Sekcie \(Sections\) 

Zlozene z komponentov. Moze to byt napr. loop s produktovymi teaserami, header, footer ale aj single post content.

#### Templates 

Zlozene zo sekcii a komponentov. Homepage, Contact template, About us, single post, …

#### SVG 

Na ikonky pouzivame inlinove SVG. \(na niektorych starsich projektoch a Powerlogy su aj ikonkove fonty\). Vyhody mala velkost nestracaju kvalitu ani pri velkych rozliseniach daju sa stylovat cez CSS

#### Blade

 [https://laravel.com/docs/5.7/blade](https://laravel.com/docs/5.7/blade) Templatovaci jazyk, ktory sa pouziva v Laraveli. My sme ho zacali pouzivat so Sage temou. Momentalne aj v Jigsaw a Themosise.

#### Twig

 [https://timber.github.io/docs/getting-started/](https://timber.github.io/docs/getting-started/) [https://twig.symfony.com/doc/2.x/templates.html](https://twig.symfony.com/doc/2.x/templates.html) Templatovaci jazyk, ktory pouziva framework Timber. Pouzivame na niektorych starsich projektoch. Treba ale dat pozor na verziu pouzitu v projekte a verziu oficialnej dokumentacie.

