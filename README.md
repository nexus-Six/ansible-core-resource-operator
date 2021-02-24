Watch and React to Core OpenShift/Kubernetes Resources Changes in your Operator  
=========

A sample Ansible Operator for OpenShift that watches a core ressource (Secret) and triggers a Playbook.

To build ( with Podman ) and deploy on OpenShift :

Change "/example/" for your Quay repository in deploy/operator.yaml and the following commands 

```
$ operator-sdk build --image-builder=podman quay.io/example/ansible-secrets-operator:v0.0.1

$ podman push quay.io/example/ansible-secrets-operator:v0.0.1

$ oc create -f deploy/service_account.yaml
$ oc create -f deploy/role.yaml
$ oc create -f deploy/role_binding.yaml
$ oc create -f deploy/operator.yaml
```

