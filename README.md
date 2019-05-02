# CF7 Tanaguru

* [Accéder à la version française](#cf7-tng-fr)
* [Go to English version](#cf7-tng-en)

# <h1 id="cf7-tng-fr">CF7 Tanaguru ReadMe - Version française</h1>

## Introduction

Ce répertoire Github héberge le [Plugin WordPress Contact Form 7](https://wordpress.org/plugins/contact-form-7/), crée par Takayuki Miyoshi et modifié par l'équipe Tanaguru.

En janvier 2019, CF7 Tanaguru reste en cours d'évolution.

## Qui sommes-nous ? Pourquoi ce plugin ?

Tanaguru est une équipe française de professionnels du web ayant pour objectif de rendre le web plus accessible. Nous accompagnons nos clients dans l'intégration de l'accessibilité numérique dans leurs organisations, nous délivrons des formations et nous faisons des audits d'accessibilité entre autres. De plus, un de nos domaines d'action se trouve être le développement de sites accessibles pour nos clients.

Les formulaires sont des composants importants et sensibles concernant l'accessibilité numérique. Plusieurs fois nous avons utilisé le plugin WordPress Contact Form 7 et Contact Form 7 Accessible Defaults pour créer des formulaires.

Pourtant, nous avons trouvé à nos formulaires une marge de progression concernant leur accessibilité.

Ce plugin CF7 Tanaguru a pour but de corriger et améliorer le plugin Contact Form 7 en partant du code source original.

## Comment contribuer ?

Nous essayons de rester au plus près des évolutions du plugin original, c'est pourquoi nous devons tenir à jour ce répertoire manuellement.

### Précautions

Si vous avez installé le plugin sur un site, respectez les consignes suivantes afin de faciliter la maintenance et la mise à jour de ce plugin personnalisé : 
* Installez le plugin original Contact Form 7
* Vérifier que le plugin original est désactivé. Si ce n'est pas le cas, désactivez-le.
    * Ceci nous permet de voir dans le back office de WordPress lorsqu'une mise à jour est disponible pour le plugin original.
* Les formulaires de contact doivent bien être créés lorsque CF7 Tanaguru est activé **et** Contact Form 7 est désactivé. Les formulaires seront alors reliés à CF7 Tanaguru (c'est-à-dire que si on désactive CF7 Tanaguru, il n'y aura plus de formulaires).

### Utiliser des commentaires spécifiques
Pour faciliter la fusion des modifications avec les mises à jour du plugin, nous documentons nos changements dans le code. Assuez-vous d'encadrer les portions de code que vous avez changé avec les blocs de commentaires suivants :

```
/**
* #cf7-tng-start
* Décrivez brièvement en anglais les changements effectués
*/

// code

/* #cf7-tng-end */
```

### Commenter le code original

Si jamais vous souhaitez retirer tout un morceau de code (par exemple, un bloc conditionnel (if/else), une fonction entière etc.), commentez le code original et dans le bloc de commentaire `#cf7-tng-start`, expliquez brièvement *pourquoi* ceci a été retiré, surtout si cela a un lien avec l'accessibilité.

Par exemple, ceci pourrait ressembler à ce qui suit (cet exemple n'a pas été pris du plugin original) :

```
/**
* #cf7-tng-start
* Remove role="button" : if button is needed
* use <button> tags instead of <a> tags.
*/

// if (link) {
//    link.setAttribute('role', 'button')
// }

/* #cf7-tng-end */
```

***

# <h1 id="cf7-tng-en">CF7 Tanaguru ReadMe - English version</h1>

## Introduction

This repository is the Tanaguru team's version of the [WordPress Plugin Contact Form 7](https://wordpress.org/plugins/contact-form-7/) by Takayuki Miyoshi.

CF7 Tanaguru is still in progress as of today (January 2019).

## Who are we ? Why this plugin ?
Tanaguru is a French-based team of web professionals focused on making the web more accessible. We support our clients' implementation of web accessibility, provide training courses and perform accessibility audits among other things. What's more, one of our field of actions is to develop accessible websites for our clients. 

Forms are an important part when it comes to web accessibility. We have used multiple times the WordPress Contact Form 7 and Contact Form 7 Accessible Defaults to create contact forms. 

Yet, we have found room for improvement in terms of web accessibility. 

This CF7 Tanaguru plugin aims at correcting and improving the Contact Form 7 plugin by modifying its original source code.

## How to make changes ?

We try to stay close to the evolving changes of the original plugin. Therefore we have to manually update this repository. 

### Cautions

If you have installed the plugin on a website, follow these instructions to make it easier to maintain and update this custom plugin: 
* Install the original Contact Form 7 plugin
* Check that the original plugin is disabled. If not, disable it.
    * This allows us to see in the WordPress back office when an update is available for the original plugin.
* Contact forms must be created when CF7 Tanaguru is activated **and** Contact Form 7 is disabled. The forms will then be linked to CF7 Tanaguru (i.e. if you disable CF7 Tanaguru, there will be no more forms).

### Using specific comment tags
To make it easier to merge changes with new updates, we document our changes in the code. Make sure to wrap the section of code you've changed with the following comment tags :

```
/**
* #cf7-tng-start
* Describe quickly in English the changes made
*/

// code

/* #cf7-tng-end */
```

### Commenting original code

If you ever want to remove a whole chunk of code (ie. if statement, a whole function, etc.), comment the original code and in the `#cf7-tng-start` comment tag, quickly explain *why* this has been removed, especially if it has to do with web accessibility.

For example, this could look like this (this example is not taken from the original plugin by the way) :

```
/**
* #cf7-tng-start
* Remove role="button" : if button is needed
* use <button> tags instead of <a> tags.
*/

// if (link) {
//    link.setAttribute('role', 'button')
// }

/* #cf7-tng-end */
```
