# CSS

**MUST-READ**   
Jednu z najlepsich best practices prirucku maju 10up, neobsahuje nic extra zlozite a pekne _popisuje_ zakladne praktiky ci uz v jazykoch HTML, CSS, JS, PHP alebo tooloch, ktore pouzivaju. S vacsinou tychto praktik sa stotoznujeme aj my. Odporucam precitat viac krat. [https://10up.github.io/Engineering-Best-Practices/](https://10up.github.io/Engineering-Best-Practices/)

### Struktura suborov 

Podobne ako pri HTML. Strukturujeme SASS subory \(toto suvisi s komponentarnym pristupom\). Tato struktura sa moze projekt od projektu lisit, ale v zasade vsade platia rovnake principy. Pri organizacii CSS vyuzivame kaskadu so zachovanim nizkej specificity \(inspiracia SMACSS, OOCSS alebo Atomic CSS\) normalize, framework CSS zakladne CSS - html tagy, buttony, zoznamy, typografia komponenty sekcie templaty 3rd party kniznice - slick, … utilities

### Frameworky 

#### Foundation 6 

[https://foundation.zurb.com/sites/docs](https://foundation.zurb.com/sites/docs) Na starsich projektoch, momentalne uz nepouzivame.

Na vacsine projektov mame semanticky pristup - cize nepouzivame triedy z frameworku, ale vlastne semanticke nazvy tried a vsetko z F6 v CSSku sa pridavalo pomocou mixinov. [http://blog.chrisdpeters.com/foundation-grid-system-without-meaningless-class-names/](http://blog.chrisdpeters.com/foundation-grid-system-without-meaningless-class-names/)

Na niektorych projektoch sa preslo zo semantickeho pristupu na pouzivanie aj class a helperov z frameworku.

#### Bootstrap 4 

Na novsich projektoch. Vyuzivame triedy z frameworku a tiez dalsie utility triedy v kombinacii s vlastnymi BEM triedami. [https://www.vzhurudolu.cz/prirucka/bootstrap-4-utility](https://www.vzhurudolu.cz/prirucka/bootstrap-4-utility)

### SASS

 [https://sass-guidelin.es/](https://sass-guidelin.es/) Pri vacsine projektov mame config pre SASS linters, takze si treba nastavit editor \(o tomto v inej kapitole\). Nepouzivame @extend.

CSS Guides Ultimatna prirucka s uzitocnymi linkami, kde su vysvetlene viacere principy CSS [https://medium.com/level-up-web/the-ultimate-guide-to-css-103b0f883de3](https://medium.com/level-up-web/the-ultimate-guide-to-css-103b0f883de3) Ako sa naucit do CSS \(popisane vsetky zakladne principy\) [https://www.smashingmagazine.com/2019/01/how-to-learn-css/?utm\_source=CSS-Weekly&utm\_campaign=Issue-346&utm\_medium=email](https://www.smashingmagazine.com/2019/01/how-to-learn-css/?utm_source=CSS-Weekly&utm_campaign=Issue-346&utm_medium=email)

### Naming zaklady 

TODO spisat nejake zakladne pravidla, ako konzistentne nazyvat komponenty, wrappery, stlpce, boxy, jednotlive casti komponentu atd.

### BEM 

V projektoch pouzivame BEM alebo jeho modifikacie. \(napr. HBReavis pouziva podobny princip, ale triedy nepouzivaju \_\_**,** cize namiesto ****`.block__element--modifier` sa pouziva `.block-element--modifier`\)

### Utility triedy 

Na novsich projektoch pouzivame v kombinacii s BEM. Pouzivame hlavne na grid visibility spacing textove helpery



### Useful links

**CSS Guides**  
Ultimatna prirucka s uzitocnymi linkami, kde su vysvetlene viacere principy CSS [https://medium.com/level-up-web/the-ultimate-guide-to-css-103b0f883de3](https://medium.com/level-up-web/the-ultimate-guide-to-css-103b0f883de3)Ako sa naucit do CSS \(popisane vsetky zakladne principy\) [https://www.smashingmagazine.com/2019/01/how-to-learn-css/?utm\_source=CSS-Weekly&utm\_campaign=Issue-346&utm\_medium=email](https://www.smashingmagazine.com/2019/01/how-to-learn-css/?utm_source=CSS-Weekly&utm_campaign=Issue-346&utm_medium=email)

