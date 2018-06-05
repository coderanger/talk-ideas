# Kubernetes: The Other Shoe

## Elevator Pitch

Kubernetes has been rapidly gaining steam as a deployment platform and
infrastructure management framework, and has a well-earned reputation as a powerful,
flexible, and useful tool. But as with all new technology, there is always an
"other shoe" that needs dropping. In this talk we'll go over the many steps needed
to get from a basic web application deployed on an out-of-the-box Kubernetes
cluster to a fully production-ready, supportable, maintainable platform.

## Audience

Level: Intermediate

This talk won't cover the very basics on setting up or using Kubernetes, and
does require at least some familiarity with Kubernetes terminology to make sense.
The main target audience is people that have run through a few tutorials, maybe
deployed a small webapp themselves onto Minikube or GKE, and are now trying to
work out how to move Real Production Infrastructure™ into Kubernetes.

I specifically won't cover Kubernetes deployment tools, the baseline expectation
is that the user either already has a relatively vanilla cluster or will be
starting from something like Kops or GKE.

## Abstract

Kubernetes is a hugely powerful platform. It enables all kinds of great tools
and patterns, but at the same time is often quite inscrutable. This is magnified
by the phenomenal pace of improvements. Lots of talks and tutorials get you as
far as a running cluster and some deployed applications, but what then? This
talk covers the proverbial "other shoe dropping", how to take a Kubernetes
cluster from that post-tutorial state to a production-ready, supportable, maintainable
platform. We'll cover topics like how to secure your cluster, set up networking,
provide storage options, ensure visibility into your cluster and applications,
and workflow tools to tie it all together.

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
      * RBAC examples
      * Pod create permissions
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
    * NodeAuthorizer
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
    * external-dns
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
    * InfluxDB (and beyond)
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
  * Autoscaling
    * Pod scaling
    * Node scaling
  * PaaS?
  * Serverless?
* Problems
  * Complexity
    * NIH vs. complexity
  * Keeping up
    * Blog post re-list
  * Next steps
* Conclusion
