---
description: >-
  This section describes a basic set of rules for translating WordPress
  projects.
---

# Translations

In general we follow the rules below.

* **wp-content/languages** folder
  * is **NEVER kept in repository** and should be present in the **git ignore** list
  * always contains files added/updated using the Update feature in WordPress administration or WP CLI
* translations of our **custom themes and plugins** are kept in repository with the theme or plugin
* we use **Loco translate** to translate strings in **3rd party** plugins and themes \(these are kept under wp-content/languages/loco\)

