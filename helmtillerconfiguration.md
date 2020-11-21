Launch an EC2 Instance

# yum update -y

#curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 > get_helm.sh

#chmod 700 get_helm.sh

#./get_helm.sh -v v2.14.1

Installing Tiller

Create a tiller Serviceaccount in Kubernetes Master

# kubectl -n kube-system create serviceaccount tiller

Bind the tiller serviceaccount to the cluster-admin role in Kubernetes Master:

# kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller

Run 'helm init' in to configure helm

# helm init --service-account tiller

Verify Now on Kubernetes Master Node

# kubectl get pods -n kube-system

# kubectl get deployment -n kube-system
