check_if_cluster_ackn:
	linkerd check --pre

install_crds:
	linkerd install --crds | kubectl apply -f -

install_linkderd:
	linkerd install | kubectl apply -f -

check_if_everything_up:
	linkerd check

install_an_default_app:
	curl --proto '=https' --tlsv1.2 -sSfL https://run.linkerd.io/emojivoto.yml \
      | kubectl apply -f -

port_forward:
	kubectl -n emojivoto port-forward svc/web-svc 8088:80

inject_kinkerd:
	kubectl get -n emojivoto deploy -o yaml \
      | linkerd inject - \
      | kubectl apply -f -

