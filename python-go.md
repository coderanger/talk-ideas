# What Python Could Learn From Go

## Abstract

Python is awesome, but we can always make it better. Go has been picking up a lot of steam in many communities and has a lot of interesting ideas and techniques that could improve our Python code and Python itself!

## Description

I love Python, but for the past few years I've been working a with Go a lot. While Go is still a long way from Python in my heart, I do have to admit that there are some pretty awesome things about it. In the grand tradition of "good artists copy, great artists steal", I think there are some places we could improve either our Python code or Python itself by taking ideas from Go. This talk will cover Go concepts like type checking, static compilation, error contexts, and code analysis.

## Outline

* Intro
* Why Python (for me)
  * Trac
  * PyGame
  * Community
* Why Go (for me)
  * Kubernetes
  * Strongarm
* The Best Of Python
  * Namespaces
  * Dynamic footguns
  * Ecosystem
* What Could We Learn From Go?
* Type Checking
  * An Intro To Go Types
    * Simple types
    * Pointers
    * Arrays (and Slices)
    * Maps
    * Structs
    * The Big One: Interfaces
      * Interface Compliance
      * Interface{}
    * Casts
    * Current Type vs. Original Type
  * MyPy, etc
  * Gary's Argument For Typing
* Errors
  * I Miss Exceptions
  * errors.Wrapf
  * Stack Trace vs. Context Trace
  * Context Trace in Python
* Deployment
  * Single binary
  * Static compilation
  * Assets
  * FROM scratch
    * Multi-stage builds
  * CLIs
    * Cross-platform builds
* Static Analysis and Tools
  * Gofmt
  * Black!
  * Goimports
  * Go vet (and integration with test)
* Struct Tags
  * Docstrings for fields
  * Standardized parsing
  * JSON, YAML, Protobufs
  * ORM metadata
    * Django v GORM
  * Multiple tools
* Go Generate
  * Code generation, kind of boring in Python
  * Asset management
  * Misc scripting
* Concurrency and Goroutines?
  * Meh, not actually that important in my opinion
* Closing
