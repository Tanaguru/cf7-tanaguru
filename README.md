# CF7 Tanaguru

## Introduction

This repository is the Tanaguru team's version of the [WordPress Plugin Contact Form 7](https://wordpress.org/plugins/contact-form-7/) by Takayuki Miyoshi.

CF7 Tanaguru is still in progress as of today (January 2019).

## Who are we ? Why this plugin ?
Tanaguru is a French-based team of web professionals focused on making the web more accessible. We support our clients' implementation of web accessibility, provide training courses and perform accessibility audits among other things. What's more, one of our field of actions is to develop accessible websites for our clients. 

Forms are an important part when it comes to web accessibility. We have used multiple times the WordPress Contact Form 7 and Contact Form 7 Accessible Defaults to create contact forms. 

Yet, we have found room for improvement in terms of web accessibility. 

This Contact Form 7 Tanaguru plugin aims at correcting and improving the original plugin.

## How to make changes

We try to stay close to the evolving changes of the original plugin. Therefore we have to manually update this repository. 

### Using specific comment tags
To make it easier to merge changes with new updates, we document our changes in the code. Make sure to wrap the section of code you've changed with the following comment tags :

```
/**
* #cf7-tng-start
* Describe quickly the changes made
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

// if (links) {
//    links.setAttribute('role', 'button')
// }

/* #cf7-tng-end */
```
