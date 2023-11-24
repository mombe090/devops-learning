
#Install Crossplane to the k8s cluster (here we rancher desktop)
add_helm_repo:
	helm repo add \
	crossplane-stable https://charts.crossplane.io/stable
	helm repo update

install:
	helm install crossplane \
    crossplane-stable/crossplane \
    --namespace crossplane-system \
    --create-namespace

check_pods:
	kubectl get pods -n crossplane-system -w

create_secret:
	kubectl create secret \
    generic aws-secret \
    -n crossplane-system \
    --from-file=creds=./credentials.txt

refresh_secret:
	kubectl delete secrets -n crossplane-system aws-secret || true && \
	kubectl create secret \
    generic aws-secret \
    -n crossplane-system \
    --from-file=creds=./credentials.txt 

