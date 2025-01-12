export NAMESPACE := 04--configmap
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-file-like: # "Apply the ConfigMap with file like keys"
	kubectl apply -f ConfigMap.file-like-keys.yaml

03-apply-property-like: # "Apply the ConfigMap with property like keys"
	kubectl apply -f ConfigMap.property-like-keys.yaml

04-apply-pod: # "Apply the ConfigMap with property like keys"
	kubectl apply -f Pod.configmap-example.yaml

05-exec-cat-config: # "Cat /etc/config/conf.yaml within the container"
	kubectl exec configmap-example -c nginx -- cat /etc/config/conf.yml

06-exec-printenv: # "Print the environment variables within the container"
	kubectl exec configmap-example -c nginx -- printenv

07-delete-namespace: # "Delete the namespace to clean up"
	@echo "🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨 "
	kubectl delete -f Namespace.yaml
