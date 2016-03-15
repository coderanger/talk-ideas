# Behind Closed Doors: Managing Passwords in a Dangerous World 

## Description

A modern application has a lot of passwords and keys floating around. Encryption keys, database passwords, and API credentials; often typed in to text files and forgotten. Fortunately a new wave of tools are emerging to help manage, update, and audit these secrets. Come learn how to avoid being the next TechCrunch headline. 

## Abstract

Secrets come in many forms, passwords, keys, tokens. All crucial for the operation of an application, but each dangerous in its own way. In the past, many of us have pasted those secrets in to a text file and moved on, but in a world of config automation and ephemeral microservices these patterns are leaving our data at greater risk than ever before.

New tools, products, and libraries are being released all the time to try to cope with this massive rise in threats, both new and old-but-ignored. This talk will cover the major types of secrets in a normal web application, how to model their security properties, what tools are best for each situation, and how to use them with major web frameworks.

## Outline

* Intros
* Types of secrets
  * Passwords (internal control)
  * Key files (TLS, whole files)
  * Tokens (external control)
  * Other (PCI, etc)
  * Hot vs. cold access
* Properties of a secrets management system
  * Audit trail
  * Least access
  * Integrations
  * Pre-encryption systems
* The usual solutions, and why they are dangerous
* Attack surfaces and threat modelling
  * Code leak
  * Backup leak
  * Directory traversal/transclude
  * RCE
  * Laptop theft
  * Higher power (gov, etc)
* Identity Management
  * Tokens
  * Cloud Systems
  * HSMs
* Tools
  * Text files
  * Chef encrypted bags
  * Ansible Vault
  * Chef Vault
  * Hashicorp Vault
  * KeyWhiz
  * AWS KMS
  * Sneaker
  * Confidant
  * Trousseau
  * Sops
  * Red October
  * Barbican
  * Conjur
* Framework Integration
  * HVAC
  * KeywhizFS
  * Consul Template
  * botocore
