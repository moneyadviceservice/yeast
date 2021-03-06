Yeast
=====

## Summary

*Yeast contains any MAS CSS that is shared between projects.*

1. Shared SCSS mixins, variables and functions for MAS apps and engines - these do not output any CSS when included in a project.

2. SCSS partials that were originally within the MAS Website (frontend repo). Since we have a need to create standalone MAS branded tools that do not inherit the main MAS Website CSS we have moved the reusable SCSS partials into Yeast to avoid duplicating across projects.

Yeast should be loaded into new projects as a Bower component and then the SCSS partials pulled in to the main project stylesheet.

## Bower

As of 7/11/2016 Yeast is registered with the Bower registry so we can use semantic versioning to reference it as a Bower package, rather than pulling straight from GitHub as we were earlier.

When updating Yeast, update the version in bower.json, and also _create a Git tag_ with the same version:

`git tag -a v1.0.0 -m "Initial tag for Bower"`

This will make the version available in the Bower registry.

Then, update the `bower.json.erb` file in any projects where you need to pull in the latest Yeast. Initially this is being set to pull in the latest 1.x.x version of Yeast. From Frontend:

`"yeast": "^1.0.0",`

## Project structure:

* /lib - SCSS mixins and variables only
* /helpers - Extra mixins and helper classes, originally from MAS Frontend
* /base - default HTML element styling
* /layout - large, common page layout options such as columns, headers, footers
* /components - reusable page modules. At the moment this only includes the Dough Theme folder which is how MAS branding is applied to Dough components. We may find that more files are necessary in this folder


## Projects using Yeast:

* MAS Website (frontend)
* CIA
* RAD
* RAD Consumer
* Universal Credit (in development as of 03/06/2016)
