export NAMESPACE := 04--replicaset
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-minimal-apply: # "Apply the minimal ReplicaSet configuration"
	kubectl apply -f ReplicaSet.nginx-minimal.yaml

03-better-apply: # "Apply the improved ReplicaSet configuration"
	kubectl apply -f ReplicaSet.nginx-better.yaml

04-delete-pods: #	"Delete all the pods! (they will be automatically recreated)"
	kubectl delete pods --all
	watch "kubectl get pods"

05-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED} Deleting the namespace recursively deletes the resources inside of it! ${NC}"
	kubectl delete -f Namespace.yaml
