# Kubernetes: The Other Shoe

## Elevator Pitch

Kubernetes has been rapidly gaining steam as a deployment platform and
infrastructure management tool, and has a well-earned reputation as a powerful,
flexible, and useful tool. But as with all new technology, there is always an
other shoe that needs dropping. In this talk we'll go over the many steps needed
to get from a basic web application deployed on an out-of-the-box Kubernetes
cluster to a fully production-ready, supportable, maintainable platform.

## Audience

Level: Intermediate

This talk won't cover the very basics on setting up or using Kubernetes, and
does require at least some familiarity with Kubernetes terminology to make sense.
The main target audience is people that have run through a few tutorials, maybe
deployed a small webapp themselves onto Minikube or GKE, and are now trying to
work out how to move Real Production Infrastructure™ into Kubernetes.

## Abstract

[todo]

## Outline

* Introductions
* Kubernetes basics
  * (not actually teaching k8s basics)
  * Books, tutorials
  * Docs
  * How to get a cluster
* What is "production-ready"?
  * Security
  * Networking
  * Storage
  * Observability
  * Recovery
  * Workflow
* Security
  * Authentication
    * Passwords/tokens
    * TLS PKI
    * OIDC
    * k8s-oidc-helper
    * Dex
    * dex-k8s-authenticator
    * Kuberos
    * Keycloak
    * Heptio/Authenticator
    * Webhooks
  * Authorization
    * RBAC
      * Namespaces
      * Permissions
      * Roles and Bindings
      * Pod create permissions
      * [probably need more on RBAC]
    * Admission Controllers
      * Defaults
      * Webhooks
      * Initializers
    * Pod Security Policy
      * Privileged
      * MustRunAsNonRoot
      * AllowedHostPaths
      * Seccomp
    * Network Policies (more later)
    * Service Accounts
  * Secrets
    * Kubernetes Secrets
    * Volumes vs. Environment
    * Encryption At Rest
    * Helm & Secrets
    * Etcd Encryption
    * Kubelet Impersonation ☠️
    * Vault
    * kubernetes-vault
    * cert-manager
    * kube2iam [maybe kiam too?]
  * Kubelets
    * TLS
    * Kubelet key rotation
    * [more?]
  * Dashboard
    * Disable?
    * Authentication
  * Vulnerabilities
    * How many copies of OpenSSL?
    * CLAIR
    * Registries
    * Sonobuoy
      * Conformance testing
* Networking
  * CNI
    * CNI Model and Theory
    * To Overlay Or Not To Overlay
    * "kubenet"
    * Flannel (nope)
    * Weave Net
      * Egress policies
    * Calico
    * kube-router
  * Service Discovery
    * Services
    * kube-dns
    * CoreDNS
    * Consul
  * Service Mesh
    * Proxies all the way down
    * kube-proxy and Services
    * Smarter Proxies
    * Ingress
      * Cloud?
      * Nginx
      * Haproxy
      * Others
    * HTTP vs gRPC
    * Envoy
    * Ambassador
    * Traefik
    * Mesh? (show the diagram of tiered -> mesh)
    * Istio
    * Linkerd
    * Conduit
    * Weave Mesh
* Storage
  * Persistent Volumes
    * Cloud?
    * Ceph
    * Rook
  * Databases
    * Cloud? (RDS operator)
    * Operators
    * KubeDB
    * postgres-operator (x2)
    * etcd-operator
    * elasticsearch-operator
* Observability
  * Logs
    * Fluentd
    * Kibana (and ElasticSearch)
    * Logstash
    * Fluentd Bit
    * Splunk?
    * In-band vs out
    * Log performance
    * Sentry (for errors)
  * Metrics
    * Heapster
    * Grafana
    * Prometheus
    * prometheus-operator
    * alertmanager
    * Sensu
  * Tracing
    * Zipkin
    * OpenTracing
    * Jaeger
* Recovery
  * HA Etcd
  * HA apiserver/scheduler
  * HA Tiller?
  * Ark
* Workflow
  * kubectl apply
  * Helm
  * Ksonnet
  * Skaffold
  * Other templating tools
  * Linters
    * [need to figure out which are still maintained]
  * CI/CD
    * Jenkins
    * Concourse
    * GoCD
  * PaaS?
  * Serverless?
* Problems
  * Kubelet Impersonation
  * Complexity
    * NIH vs. complexity
  * Keeping up
    * Blog post re-list
