# YoloVer: A Story About Policyfiles

## Abstract

Policyfiles, the latest and greatest *{{Citation needed}}* entry into the Chef
workflow arena. There is a lot of chatter about policies and their related tools,
but few people have taken the plunge and most that do are charging in without
knowing what awaits them on the other side. Together we'll examine what policies
are in Chef, how to use them, and what the downsides can be.

## Outline

* tl;dr
  * New vocabulary
  * Intro to snapshots
  * Push it over there
* A Tour of Policyfile.rb
  * Name
  * Run list(s)
  * Cookbook dependencies
  * Sources
  * Attributes
  * Chef command basics
* The Rough Edges
  * The talking stick problem
  * Graft v host, aka multi-policy issues
  * Environment attributes
  * Base/shared policy
  * Partial updates
* Workflow Overview
  * What is a release process
  * To SemVer or not to SemVer
  * YoloVer workflow
  * Example repository
* Supporting Tools
  * Policyfiles and Test Kitchen
  * Policyfiles and ChefSpec
* How to upgrade
  * Role (cookbook)? conversion
  * Environment (cookbook)? conversion
