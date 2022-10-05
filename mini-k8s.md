# Minimum Viable Kubernetes

## Abstract

To Kubernetes or not to Kubernetes, that is the question. While it is frequently used in large and complex situations, many prospective users feel it is therefore too large or complex for their needs. If you're just starting a new project, or even maybe a new startup, should you use Kubernetes? I say yes! Newer tools like K3s which allow building minimalist environments have made it much easier to run in a "I just want some containers" mode. This opens the door to starting on a small Kubernetes setup and being able to slowly grow it over time as your requirements and complexity increase.

## Long Abstract for SCaLE

To Kubernetes or not to Kubernetes, that is the question. While it is frequently used in large and complex situations, many prospective users feel it is therefore too large or complex for their needs. If you're just starting a new project, or even maybe a new startup, should you use Kubernetes? I say yes! Newer tools like K3s which allow building minimalist environments have made it much easier to run in a "I just want some containers" mode. This opens the door to starting on a small Kubernetes setup and being able to slowly grow it over time as your requirements and application complexity increase.

This talk will cover the pros and cons of using a minimalist Kubernetes environment for small applications, how to set one up, and how to use the few bits of Kubernetes we need to get started. This includes how and where to install K3s, setting up a basic webapp and database using Deployments and Services, and how to expand things over time.

## Abstract for PyCon

To Kubernetes or not to Kubernetes, that is the question. While it is frequently used in large and complex situations, many prospective users feel it is therefore too large or complex for a single Flask or FastAPI app. If you're just starting a new project, or even maybe a new startup, should you use Kubernetes? I say yes! Newer tools like K3s which allow building minimalist environments have made it much easier to run in a "I just want some containers" mode. This opens the door to starting on a small Kubernetes setup and being able to slowly grow it over time as your requirements and application complexity increase.

## Description for PyCon

This talk will cover the pros and cons of using a minimalist Kubernetes environment for small applications, how to set one up, and how to use the few bits of Kubernetes we need to get started. This includes how and where to install K3s, setting up a basic Python webapp and database using Deployments and Services, and how to expand things over time.

## Outline

* Intro
* What is Kubernetes
  * Is it all just hype? No
  * Systems as APIs
    * POSIX
    * Salt/Ansible/Chef/Puppet
    * Kubernetes
  * Modular systems
  * Promise theory, convergent systems
* "Should I use Kubernetes?"
  * "Only for big systems" - The standard answer
  * It can be small!
  * Why not X?
    * Docker? Docker on its own is not convergent
    * Compose? Low ecosystem, minimal remote API
    * Ansible? Intermittent convergence vs continuous, self-healing
    * Nomad? Lower ecosystem (but it's good)
    * ECS/Fargate/CloudRun? Expensive, containers are standard but pipeline tools are vendor
    * Lambda/FaaS? Even more lock-in and can limit your architecture
    * Use PaaS/FaaS if you like it and are okay with the downsides, feel free to skip the rest of this talk
  * To containerize or to not containerize
    * CI pipelines
    * Docker build
      * Kaniko, buildah, img
    * Development? I don't
    * Out of scope, assuming yes
  * "Why should I use Kubernetes?"
    * We're going to talk about how go small
    * But obviously Kubernetes does big too
    * Huge ecosystem of tools
      * Want a monitoring system? Install prometheus-stack
      * Need automatic TLS? We've got 5
    * High-level APIs mean things are more modular
    * Smooth growth curve without rebuilding things from scratch
      * Avoid the lift-and-shift
* Baseline persona for this talk
  * Small web app
  * "Maybe I should just get a VPS?"
  * MVP or small product
  * No dedicated ops team
  * Cost sensitive but not shoestring
* tl;dr Use k3s (or possibly k3d)
  * K3s is a mini-sized Kubernetes all in one
    * Friendly fork? Kind of
  * Single binary, run it however you want
  * Curlbash installer for systemd
  * k3d for running under existing Docker
  * Defaults to internal SQLite for single simple single-node
  * Supports Postgres and MySQL (and etcd like K8s)
  * 1 CPU, 512MB (1GB preferred), use whatever server you would use otherwise
    * For this talk we're going to pretend you're getting a single VPS-style server, such as a DO Droplet
  * How to install CCM and CSI
    * The Kubernetes way: run support services inside itself
* "But Kubernetes is still too much for my team to learn"
  * You can ignore 90% of the features
  * Let's go through the 10% you need
  * Workloads: Deployments, Pods
  * Networking: Services, Ingresses
  * That's it. You can add more as you learn and grow but that's it to start
* "How do I get started?"
  * Do what you would do without Kubernetes, but with Kubernetes
  * Does it have Docker install instructions? Follow those
  * Example: Want a Postgres database? Use the `postgres` Docker image
    * This is as good or bad as `apt-get install postgresql-server`
  * You don't need the most complex option, probably
* Workloads: Running stuff
  * Pods: It's a container, that's it
  * They do a million more things but who cares, ignore it all
  * Deployments are multiple identical pods
  * StatefulSets, DaemonSets, important later on but not to start
  * kubectl run
  * YAML Engineering
  * Minimum viable manifests
* Network: Connecting to stuff
  * Inside vs outside network
  * Do you care what a CNI is? NOPE!
  * Services: Internal network name for things
  * Ingresses: HTTP(S) from the outside to the inside
  * What about non-HTTP stuff?
    * Maybe don't, but if you must Service type LoadBalancer
  * Service Mesh? Definitely not
* Storage: Keeping stuff
  * The simple option: hostPath
    * The same as a local process storing locally
  * PVCs: Create cloud disk as needed
    * Requires cloud-specific support
      * What's a CSI?
    * PVC YAML
      * What's a StorageClass?
    * Using it as a volume
  * Object storage: S3, GCS, DO Spaces
    * This is the real answer
    * Even in a fancy Kubernetes setup
    * Integrate in your app code
  * Hosted Database: RDS, Cloud SQL, Citus
    * Great for many reasons
    * But you can run databases on Kubernetes, it's exactly as hard as running them not on Kubernetes
    * Easier with an operator, there's lots of good ones but out of scope for this talk
* What This Leaves Out
  * A lot!
  * All the usual problems of "get a VPS and deploy on it"
    * Multi-server availability
    * Access control
    * Secrets management
    * Alerting
  * A lot of those complex, advanced features are pretty useful
    * But only in specific situations so learn as you go
  * Hosted Kubernetes: GKE, EKS, AKS
    * I've so far not really mentioned these
    * They are good options too!
    * When you are ready to grow beyond 1 server, consider it
    * Beware the overhead
      * Money overhead: control plane etc costs, usually low, but watch out
      * RAM overhead: can be a lot on small servers, 100-200MB
* Questions?

