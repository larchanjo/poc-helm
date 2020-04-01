# Overview

# Setup

1. Create Service Account

`kubectl -n kube-system create serviceaccount tiller`

`kubectl create clusterrolebinding tiller --clusterrole=cluster-admin --serviceaccount=kube-system:tiller`

2. Install the Helm Tiller

`helm init --service-account tiller`

# Testing

To test that everything is OK, we are going to install the Kibana, to do that, run the command bellow:

`helm install stable/kibana --name kibana`

## Testing Kibana installation

`kubectl port-forward $(kubectl get pod | grep kibana | cut -d ' ' -f 1) 5601:5601`