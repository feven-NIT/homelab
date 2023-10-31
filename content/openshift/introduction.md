# Configure OCP Components

## Overview

In standalone OpenShift, cluster configuration is achieved via cluster-scoped resources in the `config.openshift.io/v1`
API group. Resources such as APIServer, OAuth, and Proxy allow adding additional named certificates to the Kube APIServer, 
adding identity providers, configuring the global proxy, etc. In HyperShift, configuration resources that
impact the control plane need to be specified in the HostedCluster resource instead of inside the guest cluster. The
resources still exist inside the guest cluster, but their source of truth is the HostedCluster and are continuously
reconciled with what is specified in the HostedCluster.
