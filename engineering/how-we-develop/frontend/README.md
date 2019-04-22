# Frontend

## Zakladne principy 

Dodrziavame standardy a dohody Mobile-first pristup DRY - don’t repeat yourself Snazime sa pisat cisty zrozumitelny kod bez zbytocneho balastu.

K webu pristupujeme komponentarne a rozbijame ho na mensie znovupouzitelne casti Paradny clanok o tom, preco sa divat na kazdy web ako na subor mensich znovupouzitelnych komponentov a ake su tradicne postupy a best practices. Fest so mnou zarezonoval citat 

> Replace "can you build this?" with "can you maintain this without losing your minds?”

a vlastne toto vystihuje ten hlavny dovod, preco to cele riesime ;\) [https://spaceninja.com/2018/09/17/what-is-modular-css](https://spaceninja.com/2018/09/17/what-is-modular-css)

**Konzistentnost v projektoch**   
Ked pridem k starsiemu projektu, pokracujem v standardoch a procesoch, ktore su na nom nastavene! Cize ked sa pri projekte X pouziva odsadzovanie dvoma medzerami a pouzivaju sa WP Coding Standards v PHPcku, tak budem v tom pokracovat a aj ja svoj novy kod odsadzovat rovnako a dodrziavat rovnake standardy \(aj ked na projekte Y pouzivam nieco ine, alebo som zvyknuty na nieco ine\).

**Nazvy premennych, class atd.**   
Snazime sa o co najopisnejsie a najkratsie nazvy. Pozor na mnozne cisla! Priklad: 

```markup
// Bad
<div class="featured-list-items">
    <ul class="featured-list-items__ul">
        <li class="featured-list-items__item">
            <a href="#" class="featured-list-items__item-link">Link</a>
        </li>
    </ul>  
</div>

// Better
<div class="featured-list">
    <ul class="featured-list__items">
        <li class="featured-list__item">
            <a href="#" class="featured-list__item-link">Link</a>    
        </li>
    </ul>  
</div>
```

### 

## Dalsie zrucnosti 

WP-CLI CI, CD - deploy cez nas buddy Serverove zalezitosti - vytvorenie DEV na nasom wodby, atd.

