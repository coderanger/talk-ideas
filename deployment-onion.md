# Application Deployment State of the Onion

An overview of the moving pieces in app deployment currently (ex. chef, puppet, salt, ansible, git, omnibus, compass, less, DB migrations, databases).

## Description

Deploying a moderately complex web application has become quite a challenge over the years. As best-practices have evolved, it has become progressively more time-consuming to keep up with what tools exist and how to use them effectively. This talk will provide an overview of the ecosystem and provide pointers for more information about individual components or problems.

## Audience

People deploying web apps but not very familiar with server operations.

## Objectives

Provide signposts in the rats nest of crazy that is app deployment.

## Abstract

Modern web applications are immensely complex collections of multiple interacting systems. Many new web developers don't have the time to learn all the different pieces and tools, and often their application stability and agility suffer for it. This talk will cover a few of the major groups of tools involved in running an application including databases, web servers, and configuration managers.

## Outline

* Intro (2m)
* Databases (5m)
  * MySQL fragmentation (Maria, etc)
  * Postgres w/ replication, new things
  * Whirlwind tour of NoSQL
  * DB migration strategies
* Web servers (5m)
  * Apache/Nginx
    * No really, mod_wsgi is still awesome
  * Gunicorn
  * uwsgi
  * Twisted
  * Using a CDN for assets
  * PaaS
* Server config (5m)
  * Chef
  * Puppet
  * Salt
  * Ansible
  * 12-factor
* Deploy orchestration and artifacts (5m)
  * Fabric
  * MCollective
  * Git/Hg as deploy sources
  * Omnibus
  * Artifactory
* Q/A
