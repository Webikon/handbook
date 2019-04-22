# Linters

Je jedno aky editor kto pouziva, dolezite je, ze dodrzuje pri kodeni standardy, resp. ma nastavene lintery, ktore mu v tom pomahaju.

### **Editorconfig**

[https://editorconfig.org/](https://editorconfig.org/) Toto je plugin do editoru, ktory prestavi default editor nastavenia do stavu, ktore su zadefinovane v konfig subore. Jedna sa hlavne o odsadzovanie \(spaces vs tabs\), end of lines, final newlines a dalsie. Tieto spominane veci su najcastejsim problemom pri spolupraci viacerych ludi a vznikaju sialene git diffy \(jeden clovek pouziva tabs a unixacky end of line, druhy spaces a macovsky end of line, a mame tu problem a nekonzistentnost\).

V teme je to subor `.editorconfig`

### **Linters** 

V projektoch by mali byt vzdy konfiguraky pre zakladne standardy, ktore si lintery natahaju a dokazu nas upozornovat na ich nedorziavanie. Na Blade a Twig templaty nefunguje ziadny autoformatter/autofixer spolahlivo, takze nepouzivat, lebo zvykne celu templatu rozhadzat.

**ESLint** zakladne standardy pre JS moznost pouzit Beautifier alebo nieco podobne na automaticku opravu chyb  
[https://eslint.org/](https://eslint.org/)  
Treba si nainstalovat integraciu tohto lintera do svojho editora.

**SASSLint/SCSSLint** podla projektu, treba hladat  
Na vacsine projektov pouzivame [https://github.com/sasstools/sass-lint](https://github.com/sasstools/sass-lint), ktory pouziva `.sass-lint.yml` konfigurak.  
Treba si nainstalovat integraciu tohto lintera do svojho editora.  


**PHP Codesniffer**  
[https://github.com/squizlabs/PHP\_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)  
****Treba si nainstalovat integraciu tohto lintera do svojho editora.

