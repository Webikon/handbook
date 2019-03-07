# Sage

## Theme Init

Download latest theme from [https://github.com/roots/sage](https://github.com/roots/sage)  
Sage requirement is at least **PHP 7.1.3 !!!**

Download .gitignore for WP - **TODO link**

Add basic mu-plugins as submodules

{% code-tabs %}
{% code-tabs-item title=".gitmodules" %}
```text
[submodule "wp-content/mu-plugins/CPT_Core"]
	path = wp-content/mu-plugins/CPT_Core
	url = https://github.com/WebDevStudios/CPT_Core.git
[submodule "wp-content/mu-plugins/Taxonomy_Core"]
	path = wp-content/mu-plugins/Taxonomy_Core
	url = https://github.com/WebDevStudios/Taxonomy_Core.git
[submodule "wp-content/mu-plugins/acf-codifier"]
	path = wp-content/mu-plugins/acf-codifier
	url = https://github.com/devgeniem/acf-codifier.git

```
{% endcode-tabs-item %}
{% endcode-tabs %}

Copy files from Cacher   
- images cleanup [https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=be121925f4d1b38de187](https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=be121925f4d1b38de187)  
- WP cleanup [https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=dff3df67df933699742a](https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=dff3df67df933699742a)  
- basic rewrites [https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=d2cf84eb197611af56f5](https://app.cacher.io/library/team/552a526d73bb93098d63?snippet=d2cf84eb197611af56f5)  
- tinyMCE customizations  
- simple WP menu

### 

### Common issues

Create project script not running - [https://github.com/roots/sage/issues/1929](https://github.com/roots/sage/issues/1929)

#### Sage and WP Engine

WP Engine doesn't support PHP 7.1.  
So we need to change `composer.json` dependency like this:

```text
"php": ">=7.0",
"illuminate/support": "5.5.40",
"roots/sage-lib": "9.0.0",
```

Also need to change condition for checking PHP version in `functions.php`

