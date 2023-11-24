install:
	kubectl create namespace argocd
	kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

port_forward:
	kubectl port-forward svc/argocd-server -n argocd 8080:443

gen_password:
	argocd admin initial-password -n argocd