export NAMESPACE := 04--deployment
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-minimal: # "Apply the minimal Deployment configuration"
	kubectl apply -f Deployment.nginx-minimal.yaml

03-apply-better: # "Apply the better Deployment configuration"
	kubectl apply -f Deployment.nginx-better.yaml

04-rollout-restart: # "Roll the pods in one of the deployments"
	kubectl rollout restart deployment nginx-better
	watch "kubectl get pods"

05-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
