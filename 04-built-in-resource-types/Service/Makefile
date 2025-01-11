export NAMESPACE := 04--service
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  


01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-deployment: # "Apply the Deployment configuration"
	kubectl apply -f Deployment.yaml

03-apply-clusterip-service: # "Apply the ClusterIP Service"
	kubectl apply -f Service.nginx-clusterip.yaml

04-apply-nodeport-service: # "Apply the  NodePort Service"
	kubectl apply -f Service.nginx-nodeport.yaml
	@echo "${RED} 💡 Add a firewall rule to allow inbound traffic for nodeport port!${NC}"

05-apply-loadbalancer-service: # "Apply the  LoadBalancer Service"
	kubectl apply -f Service.nginx-loadbalancer.yaml

06-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
