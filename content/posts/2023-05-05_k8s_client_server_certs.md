---
title: "K8s Client and Server certs"
date: 2023-05-05
weight: 10
draft: false
---

Securing a Kubernetes cluster is critical to protecting sensitive data and ensuring the integrity of the system. One of the essential components of securing a Kubernetes cluster is configuring SSL certificates for both client and server authentication. In this blog post, we will discuss the different types of SSL certificates that you need to configure for a Kubernetes cluster.

First, let's start with the basics. SSL certificates are digital certificates that enable secure communication between servers and clients over the internet. SSL certificates use a public key infrastructure (PKI) to verify the identity of the server and client, encrypt data in transit, and ensure that the data exchanged between the two parties is not tampered with or intercepted by malicious third parties.

In a Kubernetes cluster, there are three main types of SSL certificates that need to be configured for secure communication between nodes, services, and clients: cluster-level, node-level, and service-level certificates.

## Cluster-level SSL Certificates:

Cluster-level SSL certificates are used to secure the Kubernetes API server, which is the primary entry point for all communication with the Kubernetes cluster. The API server SSL certificate is used to verify the identity of the API server, encrypt data in transit, and ensure that the data exchanged between the server and clients is not tampered with or intercepted. To configure the API server SSL certificate, you need to create a Kubernetes secret that contains the server certificate, private key, and CA certificate.

## Node-level SSL Certificates:

Node-level SSL certificates are used to secure communication between nodes in the Kubernetes cluster. Each node in the cluster has its own SSL certificate, which is used to authenticate the node and encrypt data in transit. To configure node-level SSL certificates, you need to create a Kubernetes secret that contains the node certificate, private key, and CA certificate.

## Service-level SSL Certificates:

Service-level SSL certificates are used to secure communication between services in the Kubernetes cluster. Each service in the cluster has its own SSL certificate, which is used to authenticate the service and encrypt data in transit. To configure service-level SSL certificates, you need to create a Kubernetes secret that contains the service certificate, private key, and CA certificate.

In addition to these three types of SSL certificates, there are also client certificates that need to be configured for secure communication between clients and the Kubernetes cluster. Client certificates are used to authenticate clients, such as developers or system administrators, and grant them access to the Kubernetes API server. To configure client certificates, you need to create a Kubernetes secret that contains the client certificate, private key, and CA certificate.

## K8s Servers and their associated certs are:
    - etcd server
        - etcdserver.crt
        - etcdserver.key
    - kube-api server
        - apiserver.crt
        - apiserver.key
    - kubelet server
        - kubelet.crt
        - kubelet.key

## K8s Clients and their assoicated certs are:
    - k8s Administrator
        - admin.crt
        - admin.key
    - kube-scheduler
        - scheduler.crt
        - scheduler.key   
    - kube-controller-manager
        - controller-manager.crt
        - controller-manager.key
    - kube-proxy
        - kube-proxy.crt
        - kube-proxy.key
    - kube-api server communicating to etcd server
        - apiserver-kubelet-client.crt
        - apiserver-kubelet-client.key
    - kube-api server communicating to kubelet server
        - apiserver-etcd-client.crt
        - apiserver-etcd-client.key
    - kubelet client
        - kubelet-client.crt
        - kubelet-client.key

## Certificate Authroity certs
    - ca.crt
    - ca.key

In summary, SSL certificates are an essential component of securing a Kubernetes cluster. To configure SSL certificates for a Kubernetes cluster, you need to create cluster-level, node-level, and service-level certificates, as well as client certificates for authentication. Properly configuring SSL certificates ensures that communication between nodes, services, and clients is secure and protected from malicious attacks.