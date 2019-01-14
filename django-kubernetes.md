# Forklifting Django: Migrating A Complex Django App To Kubernetes

## Abstract

Everyone is talking about Kubernetes, but migrating existing applications is often easier said than done. This talk will cover the tale of migrating our main Django application to Kubernetes, and all the problems and solutions we ran into along the way.

## Description

Kubernetes has rapidly become an omnipresent tool in the infrastructure world, running everything from the biggest monolith to the slightest microservices. But with power comes complexity, and Kubernetes has never been accused of being too simple or having too few moving pieces. Over about 9 months, we've moved Ridecell's primary Django application from AWS and Ansible to Kubernetes, encountering many pitfalls along the way. This talk will show the approaches we tried, the worst of the issues we encountered, and lay out a path for migrating other Python web applications more effectively!

## Audience

Mostly aimed at people that have a little infrastructure/DevOps experience, who have been looking at Kubernetes and maybe playing with it a bit but are facing down the daunting task of moving major production infrastructure into it. I'll cover some Kubernetes terminology very briefly as I'm talking, but it won't be a Kubernetes 101 talk. I'll be focusing on Django because that's the case I actually had, but most of the talk is applicable to any Python web application.

## Outline

* Intro
* Staring Point
  * Basic app architecture (Django, Celery, Channels)
  * Databases (Postgres, Redis, RabbitMQ)
  * Ansible, Terraform, AWS
  * Things not changing
    * Production DBs
    * Cloudflare
* First Attempt: Static Manifests
  * Upsides
  * Downsides
  * Traefik
  * Cert-manager
* Second Attempt: Helm
  * Upsides
  * Downsides
  * Where Are We Going And Why Am I In This Handbasket
    * Tiller Sadness
* Third Attempt: ridecell-operator
  * CRDs refresher
  * Upsides
  * Downsides
  * Kubebuilder
  * Making your own
    * Basic Spec layout
    * Types of components
* Remaining Sharp Edges
  * Celerybeat
  * Databases
  * Autoscaling?
* Thank You
