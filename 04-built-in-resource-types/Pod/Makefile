export NAMESPACE := 04--pod
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace:
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-wrong-way-create:
	@echo "${RED}PLEASE DO NOT DO THIS${NC}"
	kubectl run --image=nginx:1.26.0 -n ${NAMESPACE} created-the-wrong-way

03-minimal-apply: # "Apply the minimal pod configuration"
	kubectl apply -n ${NAMESPACE} -f Pod.nginx-minimal.yaml

04-minimal-port-forward: # "Port forward minimal"
	kubectl port-forward -n ${NAMESPACE} nginx-minimal 8080:80

05-better-apply: # "Apply the better pod configuration"
	kubectl apply -n ${NAMESPACE} -f Pod.nginx-better.yaml

06-better-port-forward: # "Port forward to the better pod configuration"
	kubectl port-forward -n ${NAMESPACE} nginx-better 8080:8080

07-delete-namespace: 
	@echo "${RED} Deleting the namespace recursively deletes the resources inside of it!${NC}"
	kubectl delete -f Namespace.yaml
