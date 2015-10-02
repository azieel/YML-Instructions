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

### Variables présentes dans les chaines de caractère
Il est possible de rencontrer assez rarement des variables dans les chaines à traduire, elle sont toujours représentés par le schéma %{nom de la variable}

Par exemple vous pouvez rencontrer ce cas dans les fichiers de mysaven:
``` yaml
fr:
    mailer:
        add_candidate:
            welcome: "Bonjour %{username}"
            text02: "Pour compléter votre évaluation, cliquez sur ce lien"
            button_text: "Compléter mon évaluation"
            text03: "Répondre à ce questionnaire ne vous prendra pas plus de dix minutes."
        survey_complete:
            text01: "les résultats de %{username} sont disponibles dans votre tableau de bord Saven."
```
On remarque la variable %{username} à deux reprises, ces variables ne sont pas à traduire et seront remplacé dans l'application par le nom du candidat. L'utilisation de la coloration syntaxique facilite ici le repérage des variables.

### Structures d'aides a ne pas traduire
Parfois certains elements sont présent dans les fichiers mais ne nécessitent pas d'être traduits. Par exemple dans les fichiers homme/femme de resultat se présentent de la manière suivante: 
``` yaml
texts:
    t01:
        text_1:
            tag: p
            class: ""
            text: "Ce n’est pas le monde extérieur qui cause nos comportements ou nos émotions..."
        text_2:
            tag: p
            class: ""
            text: "Dans le texte qui suit, vous allez découvrir comment se positionne ..."
```
Ici les chaines tag: "p" et class: "" ne sont pas a traduire, se sont des aide à l'integration de ces chaines de caratère dans l'application. en règle générale, ce qui ne ressemble pas à du language construit n'est pas à traduire.
Ce sont des cas spécifiques aux textes de résultats pour obtenir une génération de pdf optimale par la suite. La plupart du temps, vous ne rencontrerez pas d'autres cas que ceux là.

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

