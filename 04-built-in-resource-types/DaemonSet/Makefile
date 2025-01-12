export NAMESPACE := 04--daemonset
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-minimal-pod: # "Apply a minimal fluentd pod configuration"
	kubectl apply -f Pod.fluentd-minimal.yaml

03-apply-minimal-daemonset: # "Apply a minimal fluentd daemonset configuration"
	kubectl apply -f DaemonSet.fluentd-minimal.yaml

04-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
