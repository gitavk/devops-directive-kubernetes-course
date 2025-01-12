export NAMESPACE := 04--statefulset
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-minimal: # "Apply a minimal StatefulSet configuration"
	kubectl apply -f Service.nginx.yaml
	kubectl apply -f Service.nginxs.yaml
	kubectl apply -f StatefulSet.nginx-minimal.yaml

03-delete-minimal: # "Delete the minimal StatefulSet configuration with an init container"
	kubectl delete -f StatefulSet.nginx-minimal.yaml

04-apply-with-init: # "Apply a statefulset configuration with an init container"
	kubectl apply -f Service.nginx.yaml
	kubectl apply -f Service.nginxs.yaml
	kubectl apply -f StatefulSet.nginx-with-init-container.yaml

05-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
