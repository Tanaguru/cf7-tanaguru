# CF7 Tanaguru

A fork of the Contact Form 7 WordPress plugin to fix accessibility problems

## Introduction

This repository is the Tanaguru team's version of the WordPress Plugin [Contact Form 7](https://wordpress.org/plugins/contact-form-7/) by Takayuki Miyoshi and modified by Tanaguru team.

CF7 Tanaguru is still in progress as of today (June 2020).

## Who are we? Why this plugin?

Tanaguru is a French-based team of web professionals focused on making the web more accessible. We support our clients' implementation of web accessibility, provide training courses and perform accessibility audits among other things. Moreover, one of our field of actions is to develop accessible websites for our clients.

Forms are an important part when it comes to web accessibility. We have used multiple times the WordPress “Contact Form 7” and “Contact Form 7 Accessible Defaults” to create contact forms.

Yet, we have found room for improvement in terms of web accessibility.

This CF7 Tanaguru plugin aims at correcting and improving the Contact Form 7 plugin by modifying its original source code.

## List of the accessibility fixes

### 1. Main error message or success message handling

In the original Contact Form 7, when there are errors on submitting the form, there are two main message:

- one is visually displayed and inaccessible to screen readers (it's a sentence to tell there are errors): that's a problem because people using screen readers are not all blind people;
- the other is visually hidden and only accessible to screen reader users. This message contains links to anchors in the form. That's a problem because links are accessible through keyboard but not visible at all!

Both main error message or success message have a `role="alert"` attribute but this one is not ready in DOM before dynamically adding the message inside it. So, some screen readers may not read the message.

The main message should be at the top of the form to be logical.

**What we have done:** we decided to move focus on the main message (that must be at the top of the form) in order to be sure that the message will be read by screen readers and so, users are at the right place to go again inside the form to fix their errors.

1. Move the `[response]` short code in our form administration at the top of the form (before writing fields) (**don't forget to do it as a developer**);
1. Remove the `role="alert"` and `aria-hidden="true"` attribute from the main message container that is visible;
1. Add a `tabindex="-1"`attribute on the main message container;
1. Remove the visually hidden message (the one with links inside);
1. On submit, move focus on the main message (error or success).

### 2. Attach individual error message to its field

In the original Contact Form 7, when there are errors on submitting the form, each field in error has a dedicated individual error message below it. These error messages have a `role="alert"` attribute and are not attached to their field so it remains difficult for blind users to access to these messages.

Moreover, these individual messages are visually displayed and inaccessible to screen readers: that's a problem because people using screen readers are not all blind people.

**What we have done:**

1. Remove the `role="alert"` and `aria-hidden="true"` attributes from these messages;
1. Add a unique ID on each individual message;
1. Add an `aria-describedby` attribute on fields which are in error;
1. Attach the `aria-describedby` attribute with the ID of the error message.

### 3. Remove `size` attribute on form fields

A `size` attribute is used on form fields but it's not compliant with accessibility rules. CSS must be used instead in order to fix field size.

## How to contribute?

We try to stay close to the evolving changes of the original plugin. Therefore we have to manually update this repository.

### Cautions

If you have installed the plugin on a website, follow these instructions to make it easier to maintain and update this custom plugin:

* Install the original Contact Form 7 plugin;
* Check that the original plugin is disabled. If not, disable it. This allows us to see in the WordPress back-office when an update is available for the original plugin.

### One branch = one fix

Create a Git branch by fix you want to do. Name this branch following this model: `[version]_name-of-the-fix`.

Example : `5-1-1_error-role-alert`

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

For example, this could look like this (this example is not taken from the original plugin by the way):

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

## How to update CF7 Tanguru plugin from Contact Form 7

Follow these instructions to update the CF7 Tanaguru plugin from the official Contact Form 7:

1. Check that the `master` branch is up to date on your computer;
1. Create a new branch, from the `master` branch, naming `update_[version]` replacing “version” by the new version number of Contact Form 7. Example : `update_5-1-2`
1. Put the new version from the official Contact Form 7 on this branch;
1. Before committing this, compare what you are about to commit and report all CF7 Tanaguru modifications on the new version of Contact Form 7;
1. When everything seems to be OK, commit and push your modifications on your branch `update_[version]`;
1. Go on Github and make a Pull Request to merge your branch `update_[version]` on `master`. Read your Pull Request carefully. If you can, request a review from a colleague to benefit from a fresh eyes looking.
1. Approve the Pull Request.
1. Make a Github Release.
