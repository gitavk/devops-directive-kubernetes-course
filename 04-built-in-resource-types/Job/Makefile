export NAMESPACE := 04--job
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  


01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-minimal-pod: # "Apply the standalone Pod configuration"
	kubectl apply -f Pod.echo-date-minimal.yaml

03-apply-minimal-job: # "Apply the minimal Job configuration"
	kubectl apply -f Job.echo-date-minimal.yaml

04-apply-better-job: # "Apply the better Job configuration"
	kubectl apply -f Job.echo-date-better.yaml

05-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
