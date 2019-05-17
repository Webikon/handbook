---
description: >-
  No matter what editor you use, you should always code according to our
  standards. Linters can help you do it.
---

# Linters

To make it easier to keep an eye on standards, we use **Linters**, tools that are using rules from config files and telling us, if our code is valid.

**Ignoring/excluding**   
If for some reason you don’t want to use linter for particular file or code snippet, each linter has options to ignore or exclude, you just have to search for it ;\)

**Auto fixers**   
There is also possibility to use fixers to fix most of the issues automatically. Anyway, these fixers sometimes fail to fix file properly or don’t do it according to standards in configs \(especially be careful with fixers like Prettier and Beautify\) and have to be fixed manually or not used at all. So ALWAYS make sure to check if file was fixed properly. We also don’t recommend Fix On Save feature, for same reasons as written above.

Also, mostly in older projects, when there are no config files for particular code standards, DON’T use auto fixer and write code to be consistent with what already exists.

**TODO** Make sure all projects have linters as project dependencies.   
**TODO** Add pre-commit hooks for all linters below.

### Editorconfig

[https://editorconfig.org/](https://editorconfig.org/)  
Plugin that will help you to set up your editor basic formatting, indenting, end of lines, etc.   
In project, there should be an `.editorconfig` config file.   
  
All you need to do is activate **Editorconfig** plugin in your editor \(it should be available for every editor\).

### ESLint

[https://github.com/eslint/eslint](https://github.com/eslint/eslint)   
Linter for JS files.   
In project, there should be an `.eslintrc.js` config file.

Make sure, you install it globally `npm install -g eslint`   
Then install and activate **ESLint** plugin in your editor \(it should be available for every editor\).

_On some projects, we also integrate this to our assets building process, so it throws error if something is wrong._   
  
**TODO**: Integrate to Laravel Mix \(Sage already has this\).   
[https://github.com/Rias500/laravel-mix-eslint](https://github.com/Rias500/laravel-mix-eslint)

#### **Autofix JS**

You can use Beautifier.

**TODO** Prettier and its configs.

### SASSLint

[https://github.com/sasstools/sass-lint](https://github.com/sasstools/sass-lint)   
Linter for SASS.   
In project, there should be an `.sass-lint.yml` config file.

Make sure, you install it globally `npm install -g sass-lint`  
Then install and activate **SASS Lint** plugin in your editor \(it should be available for every editor\). Don’t mistake with **SCSS Lint**, it is different linter.

**TODO** Migrate to Stylelint

### PHP Codesniffer

[https://github.com/squizlabs/PHP\_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)   
Linter for PHP.   
In project, there should be an `phpcs.xml` config file.

Make sure, you install it globally, like `composer global require “squizlabs/php_codesniffer=*”` \(different ways to install are here: [https://github.com/squizlabs/PHP\_CodeSniffer\#installation](https://github.com/squizlabs/PHP_CodeSniffer#installation)\). Then install and activate **PHP CodeSniffer** plugin in your editor \(it should be available for every editor\).

_On some projects, we also integrate this in CI or git hooks, so it throws error and won’t allow you to do push or deploy._

**TODO** Integrate to git pre-commit hooks to repo.   
**TODO** Integrate [https://github.com/phpro/grumphp](https://github.com/phpro/grumphp)

#### **Autofix PHP**

Recommended one is **php-cs-fixer \(**[**https://github.com/FriendsOfPHP/PHP-CS-Fixer**](https://github.com/FriendsOfPHP/PHP-CS-Fixer)**\)**.   
When you install plugin below, it should automatically look for `phpcs.xml` or `.php_cs.dist` in project root and apply proper standards.

VSC: [https://marketplace.visualstudio.com/items?itemName=fterrag.vscode-php-cs-fixer](https://marketplace.visualstudio.com/items?itemName=fterrag.vscode-php-cs-fixer)

### HTML/Blade

There is no good way to lint and fix Blade files yet :\(   
**TODO** Test Prettier

