---
description: What should I check before commit to make both me and reviewer less work ;)
---

# Before commit checklist

* [ ] Do I use proper formatting, indenting and keep standards defined in project? [https://handbook.webikon.eu/engineering/style-guides](https://handbook.webikon.eu/engineering/style-guides)
  * PHP \(usually PSR-2\)
  * SASS \(.sass-lint\)
  * Blade/HTML
* [ ] Does ALL my functions have DocBlock comments? \(WP hooks needs only basic comments, not necessarily in DocBlock format\)
* [ ] When I use “magic numbers” or complex functionality, do I have it properly commented? Yeah, I know what this code is doing… but what about when I look at it next month? ;\) [https://handbook.webikon.eu/engineering/standards/documentation](https://handbook.webikon.eu/engineering/standards/documentation)
* [ ] When I copied/pasted some snippet from Stack Overflow \(or other project\), did I properly customised this code to fit this project, added proper comments and/or link to source of this code? Especially when I don’t really know what this code really does… :\)
* [ ] Am I using BEM naming properly?
* [ ] Am I structuring components, sections and templates according to our standards. [https://handbook.webikon.eu/engineering/how-we-develop/frontend/template-structure](https://handbook.webikon.eu/engineering/how-we-develop/frontend/template-structure)
* [ ] Did I do double check for all git diff for this commit for misspellings, forgotten unused code and other mistakes? Yes… Really? Did I? \(Most of small mistakes and “ping-ponging” code from reviewer to developer can be avoided exactly with this.\)
* [ ] Do I use proper commit message? That is imperative sentence, which describes, what is done in this commit. Remember, that I might need to search in those commits in the future... ;\) 

  E.g. `Add Hero component` `Fix styles issues in header` , ….  
  [https://handbook.webikon.eu/engineering/how-we-develop/git/commit-messages](https://handbook.webikon.eu/engineering/how-we-develop/git/commit-messages)

* [ ] Did I properly tested, that my code is really working and doesn't throw any errors or warnings? 

**WP implementation only**

* [ ] Are all strings in templates translatable and in EN, with proper text domain?
  * Note: In WC templates, we can use default WC strings, but don’t forget to use default `woocommerce` text domain as well.
* [ ] Are all strings \(titles and descriptions\) in custom fields/cpt/taxonomies registration translatable? They can be in SK language by default if not defined otherwise.
* [ ] Are all outputted images properly cropped? \(We can use Fly Image Resizer to resize images on the fly.\)  And/or do these images also have responsive sizes if needed? 
* [ ] Do I properly checked if data exists on blocks of code, which don’t have to be always displayed and ? \(so we don’t get `Unidentified index...` warning\)

