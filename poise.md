# Poise: Reusable Cookbook Patterns

Writing reusable cookbooks has proven to be one of the biggest challenges to
the growing Chef ecosystem. Poise provides simple but powerful patterns to
make your cookbooks more modular, adaptable, and flexible.

## Abstract

The Chef community has had a troubling relationship with reusable cookbooks.
Many say that they are not worth the much higher complexity compared to
single-environment recipes. Others point to the wealth of existing cookbooks
as a powerful tool to new users. Yet others, including myself, see reusable
cookbooks as the best way to build abstraction layers to tame the growing mass
of tools and services most companies run.

The Poise cookbook provides both an implementation of common patterns for
reusability as well as demonstrations of how to structure a cookbook to be
extended. This talk will lay out the patterns and how to harness them
for your own infrastructure.

## Audience

Experience Chef users or those looking to move up the mastery path. Some
knowledge of Ruby is required, but not too much more than normal Chef.

## Objectives

Teach the audience about the Poise cookbook and how to use it to create
reusable cookbooks.

## Outline

* Intro
* Overview of Cookbook Patterns
  * Wrapper cookbooks
  * Library cookbooks
  * Application cookbooks
  * Role cookbooks
  * Poised cookbooks
* Poise patterns
  * Overall structure
  * Notifying block
  * Include recipe
  * Sub-resources
  * Template attributes
* Designing for Extension
  * Subclassing 101
  * Adding actions
  * Extending actions
  * Using attributes
  * Default recipes
* Q/A

