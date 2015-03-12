# What is coming in Python packaging

## Description

In the last 18 months the Python packaging world has seen an explosion of
activity. Learn what improvements are available now and what is on the horizon.

## Audience

Package authors and users.

## Objectives

Provide an overview of the recent past and near-term future of the packaging
world so people know what tools to use and how to use them.

## Abstract

In the last 18 months the Python packaging world has seen an explosion of
activity. Some improvements like SSL certificate verification and pyvenv are
already available, while others are just over the horizon. In this talk you will
learn what the packaging community has been hard at work on and how you can take
advantage of the latest tools and techniques in your Python environments.

## Outline

* Intro (2m)
* Things you might not have heard of (10m)
  * SSL Verification
  * Caching CDN
  * Deprecation of the public mirror network
  * External link handling
  * pyvenv
* Coming soon (10m)
  * Dependency-less pip
  * getpip module
  * wheel package format
  * New package metadata
* Where next? (5m)
  * Warehouse and new upload API
  * requirements.lock
  * Contributing (mailing list, etc)
* Q/A

## Notes

Some topics may get shuffled between headings if they actually happen between
now and April.

* Intro
* Disclaimer, not in chronological or any other order.
* New World Order
  * PyPA
  * BDFL Delegate
* Serving packages
  * HTTPS + HSTS + PFS
  * JSON API
  * Caching CDN
    * Static fall back
  * Deprecation of the public mirror network
    * a-g
    * Mirror authenticity
  * Bandersnatch
  * DevPI
  * Warehouse
* Getting packages
  * SSL verification
  * External link handling
  * dependency_links
  * ensurepip (PEP 453)
  * Wheels
    * pip without setuptools
    * Binary wheels
* Using packages
  * venv
  * Setuptools un-forked
* Making packages
  * Pre-release support
  * Metadata 2.0
  * Twine
  * pypissh removal
  * Packaging User Guide
* Contributing
  * Github issues
  * BitBucket
  * Mailing list
    * Catalog-sig merge
* Thank yous
  * Donald Stufft
  * Nick Coghlan
  * Sponsors

