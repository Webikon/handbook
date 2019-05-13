---
description: What should I check to make both me and reviewer less work ;)
---

# Before commit checklist

* [ ] Do I use proper formatting, indenting and keep standards?
  * PHP \(usually PSR-2\)
  * SASS \(.sass-lint\)
  * Blade/HTML
* [ ] Does ALL my functions have DocBlock comments? \(WP hooks needs only basic comments, not necessarily in DocBlock format\)
* [ ] When I use “magic numbers” or complex functionality, do I have it properly commented? Yeah, I know what this code is doing… but what about when I look at it next month? ;\)
* [ ] When I copied/pasted some snippet from Stack Overflow \(or other project\), did I properly customised this code to fit this project, added proper comments and/or link to source of this code? Especially when I don’t really know what this code really does… :\)
* [ ] Am I using BEM naming properly?
* [ ] Did I do double check for all git diff for this commit for misspellings, forgotten unused code and other mistakes? Yes… Really? Did I? \(Most of small mistakes and “pingponging” code from reviewer to dev can be avoided exactly with this.\)
* [ ] Do I use proper commit message? That is imperative sentence, which describes, what is done in this commit. Remember, that I might need to search in those commits in the future... ;\) 

  E.g. `Add Hero component` `Fix styles issues in header` , ….

**WP implementation only**

* [ ] Are all strings in templates translatable and in EN, with proper text domain?
  * Note: In WC templates, we can use default WC strings, but don’t forget to use default `woocommerce` text domain as well.
* [ ] Are all strings \(titles and descriptions\) in custom fields/cpt/taxonomies registration translatable? They can be in SK language by default if not defined otherwise.
* [ ] Are all outputted images properly cropped? \(We can use Fly Image Resizer to resize images on the fly.\)  And/or do these images also have responsive sizes if needed? 
* [ ] Do I properly checked if data exists on blocks of code, which don’t have to be always displayed and ? \(so we don’t get `Unidentified index...` warning\)

