# INSTRUCTION CONCERNANT LES FICHIERS YML

### Présentation
Le yml est un language de balisage, très simple basé sur des documents textes.

### Informations générales et fonctionnement
Les fichiers yml sont constitués de la manière suivante:

``` yaml
fr:
    identifiant1:
        sub_id_level1: "Une chaine de caractères à traduire"
        sub_id_level1: "Une autre chaine de caractères à traduire"
        sub_id_level1:
            sub_id_level2: "Encore une chaine à traduire"
            sub_id_level2: "Encore une chaine à traduire"
            sub_id_level2: 
                sub_id_level3: "Encore une chaine de caractères à traduire"
                sub_id_level3: "Encore une chaine de caractères à traduire"
            sub_id_level2: "Encore une chaine à traduire"
            sub_id_level2: "Encore une chaine à traduire"
        sub_id_level1: "Une chaine de caractères à traduire"
        sub_id_level1: "Une autre chaine de caractères à traduire"
```
Le fichier est donc constitué d'identifiants, qu'il ne faut pas traduire, et les chaines de caractères à traduire.
Il est important de ne pas altérer la structure du fichier ni les identifiant car cela provoquerai un bug dans l'application en effet les traductions ne seront plus accessibles.

Pour information, les traductions sont ensuite récupérées dans le code de l'application de cette manière:

``` erb
    <p><%= t('identifiant1.sub_id_level1.sub_id_level2') %></p>
    #cela donnera comme résultat "Encore une chaine à traduire" si la langue est configuré sur francais
```
D'où l'importance de ne pas altérer la structure du fichier.

### Outils pour faciliter l'utilisation du yaml
Il existe de nombreux editeurs de textes pouvant ouvrir le yml (le bloc note suffit, au final un fichier yml n'est rien d'autre qu'un fichier txt) mais il existe des editeurs permettant de colorer les fichier (comme pour les exemple ci dessus) ce qui rend la lecture et l'utilisation de ce format plus facile.

Je vous conseil sublime text qui est tres leger et facile d'accès. Il est disponible pour window, macosX et linux et reconnaitra automatiquement un fichier yml en utilisant la coloration syntaxique correspondante.

###### Vous pouvez les télécharger à ces adresse:

* [Version WINDOWS](http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%202.0.2%20Setup.exe)
* [Version MAC OSX](http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%202.0.2.dmg)
* [Version LINUX](http://c758482.r82.cf2.rackcdn.com/Sublime%20Text%202.0.2.tar.bz2)
 
###### Plus d'informations sur sublime texte
* [Site web de sublime text](http://www.sublimetext.com/)
 
###### Pour plus de détails ou information, vous pouvez me contacter par mail: j.faure@woolight.com

