# Swiss Army Django: Small Footprint ETL

## Abstract

A case study of a single-application ETL system to scrape and enrich complex nested data and then expose it via GraphQL and Discord. It will dive into how to use these various async-based libraries together in a small footprint app.

## Description

ETL systems have become commonplace in our world, from tiny personal web scrapers to complex distributed data pipelines. With Django offering a fully async API, new possibilities have opened to simplify the many different microservices into a single Python application that hosts the scrapers, query systems, and administrative interface all in one box. With this comes simplified code and deployment, and many other benefits.

This talk will cover a case study in building this kind of all-in-one ETL system, the components used, and how they all fit together. This includes both API and web scrapers, GraphQL for querying and streaming, and a Discord interface for notifications and control.

## Outline

* Introduction
* Case study: Farm RPG
  * What makes this unique?
  * Kinds of data involved
  * Why? Fun! Also learning
* What is ETL?
  * It’s a web scraper
  * ETL vs ELT
  * A note about “please don’t scrape without permission”
  * The big moving pieces
    * Extractors, scraper cron jobs
    * Transforms, parse HTML or JSON, tweak the data
    * Load, ORM, maybe DRF Serializers
* Why async?
  * Put it all in one box
  * Fewer services, fewer problems
  * Monolith: The reports of my death are greatly exaggerated
  * Background tasks!
    * How to spawn async things from Django
    * Discount cron with task factories
  * When to stick with Celery et al?
    * Crash modeling, what happens on failure
  * Async ORM: how async is async? (hugs to Andrew)
  * Async HTTP clients: httpx
* Deeper into the case study: GraphQL
  * Strawberry
  * django-plus
  * What is GraphQL good for? Game data, nested data, bidirectional data
  * Schema, per app and global
  * Filters
  * Performance? Show some SQL traces
  * Gatsby and friends (offline vs online)
  * Streaming with Channels
* Real time interaction? Discord
  * Or Slack for work stuff
    * Anything asyncio compatible
  * ChatOps?
  * Send summaries out 
  * Chat bot for queries
* Scaling issues and solutions
  * Too much data for one ingest? Sharding 
  * CPU bound? Sync to async or subprocess
  * Slowly swapping out components
  * Transition from processing to control
* Questions
