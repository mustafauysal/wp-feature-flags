# WP Feature Flags

## The Problem:
 - You don't always have control over when code is deployed when you don't own the hosting
 - Changes have a potential to 500 a site if not managed carefully or if making big changes
 - Features may only need to be enabled or released on a per-site basis
 - Want to be able to reverse a feature or change without having to deploy more code or revert
 - Features can get held up on staging waiting for a final fix or question resolution


## The solution:
Add feature flag interface available in the admin area so that we can enable or disbale large changes when we damn well feel like it. Upon enabling, the feature flag will first verify that the change will not 500 the site and if it fails it should not be allowed through. The interface will be a simple WP list row with one action - turn the flag on or off.


## TODO:
1. Add registration system
1. Add check system
1. Add admin interface
1. Add sandbox so that a change can NEVER 500 a site (AJAX probably?)


## Req's
 - Needs to work with single or multisite - per-site or enable on all sites at once
 - Needs to ensure that a change never 500s a site
 - Needs a method of gracefully expiring the feature flag
 - Namespaced, properly classed, OOP


## Nice-to-haves
 - Groupings of feature flags
 - Multivariate|A/B testing of features


## Registration:
slug, name, description, disabling and enabling callback, activated/deactivated by default


##Limitations:
Doesn't work well with CSS/JS unless there's an extra stylesheet included (not an issue on VIP with concatenated sheets)