# What The GIL Means For Containers

<!-- Make it "Python GIL" for non-Python confs -->

<!-- # Deployment In The Land Of The GIL -->

<!-- # GILd The Lily: Python In Containers -->

## Abstract

The Python Global Interpreter Lock is an eternal monster under the bed of developers, but it doesn't need to be. This talk will teach you how to take the GIL into account when deploying and scaling Python applications in containers: what it means for ops teams, how to design a good Python deployment, and how to ensure it isn't negatively impacting your systems. 

## Description

This talk covers a very basic introduction to the Python Global Interpreter Lock from the point of view of container operations and deployment, along with the knowledge and tools to architect high quality Python application infrastructure. This includes how various application servers interact with the GIL, what problems is causes from an ops-centric point of view, and best practices for running Python applications efficiently and at scale despite the limitations.

## Outline

* Intro
* What Is The GIL (5m)
  * Basics of locking
  * Threads and the GIL
  * IOWAIT
  * C extensions
* Anatomy of a Python Web Server (5m)
  * select()
  * Worker
    * Fork
    * Thread
    * Green
  * Pools and contention
  * Parallels for non-web (e.g. Celery worker)
* Complications (5m)
  * Backpressure and health checks
  * Container OOM tracking
  * Prometheus metrics
    * Big bad global variables
  * Non-IO bound code
  * "Just run more" vs. copy on write utilization
    * gc.freeze()?
  * Default settings gunicorn: a comedy of errors
    * Silent OOMs
    * No internal metrics
* Building For Happiness (5m)
  * Threads threads threads
  * Monitor all the things
  * Embrace your distributed system
  * Threaded web servers
    * Spoiler: Twisted
  * Don't fear the GIL
* Questions (5-10m depending on format)