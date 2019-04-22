# Workflows

### Ako robime projekty 

Pristupy, akymi sme robili/robime a na akych su postavane nase projekty.   
V skratke:

* upravena underscores tema, v templatoch mix PHP+HTML, gulp 
* Timber framework, upravena underscores, twig templates, gulp 
* Sage tema, blade templates, webpack 
* Jigsaw a Themosis 
* Alternativa su este projekty postavene na page builderoch.

### 1.Old school 

Projekty: HB Reavis, Synergie, ... Upravena undescores tema Foundation 5 alebo 6 V templatoch sa mixuje PHP + HTML, cize datova struktura s frontendom. Gulp ako buildovaci nastroj.

### 2.Timber + twig 

Projekty: Habitat, Across, ... [https://timber.github.io/docs/getting-started/](https://timber.github.io/docs/getting-started/) [https://twig.symfony.com/doc/2.x/templates.html](https://twig.symfony.com/doc/2.x/templates.html) 

V podstate zaciatok nasej cesty za oddelenim FE a BE - MVC pristup :\)   
Timber je framework, ktory poskytuje lepsiu pracu s datami vo WP a umoznuje oddelit datovu vrstvu od frontendu \(views\). Tiez ma kopec uzitocnych funkcii na vsetko, WP\_Queries, Taxonomies, Menus, obrazky, atd. Chyba tu ale praca s controllermi a nie je to uplne MVC pristup. Tiez nasa implementacia a praca s datami nebola moc DRY.   
Ako templatovaci jazyk Timber pouziva twig.   
Ako temu sme pouzivali underscores upravenu pre Timber a twig.   
Foundation 5 alebo 6.   
Gulp stale ako buildovaci nastroj.

### 3.Sage + Blade 

Projekty: Powerlogy, Hashtag, Maminerecepty [https://github.com/roots/sage](https://github.com/roots/sage)   
Velky krok vpred po technologickej stranke co sa tyka pristupu k tvoreni temy.   
Vylepsenie MVC pristupu. Kompletne oddelenie FE a BE. Controllers - praca s datami, moznost jednoducho passovat data to jednotlivych templatov/views.   
Views - toto je v podstate to, co sa zobrazuje na frontende, v nich by sa mali pripravene data uz len zobrazovat.  
Blade ako templatovaci jazyk.   
Switch z gulpu na webpack.

### 4.Jigsaw, Themosis + Blade 

Najnovsi pristup. [https://jigsaw.tighten.co/](https://jigsaw.tighten.co/)   
Jigsaw sluzi na pripravenie statickych blade templatov.

[https://framework.themosis.com/](https://framework.themosis.com/)   
Themosisom prechadzame na sposob tvorby webovej aplikacie velmi podobny Laravelu. Cela struktura aplikacie je uplne ina ako ma WP. Cela datova struktura a backend je ako keby v roote aplikacie, vo WP teme je len cisto frontend \(views\).

Buildovanie assetov pomocou Laravel Mix.

