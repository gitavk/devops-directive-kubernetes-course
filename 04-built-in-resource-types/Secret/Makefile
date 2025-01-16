export NAMESPACE := 04--secret
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  

01-create-namespace: # desc: "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-secret-string-data: # desc: "Apply Secret using stringData field"
	kubectl apply -f Secret.string-data.yaml

03-base64-encode: # desc: "Base64 encode a string"
	@echo "${RED}🚨 Be careful using 'echo' for this purpose since it includes a newline by default${NC}"
	printf "bar" | base64

04-get-value: # desc: "Get secret value"
	kubectl get secret string-data -o yaml | yq '.data.foo'

05-get-and-decode-value: # desc: "Get secret value"
		- kubectl get secret string-data -o yaml | yq '.data.foo' | base64 -d

06-apply-secret-base64-data: # desc: "Apply secret using base64 encoded data"
		- kubectl apply -f Secret.base64-data.yaml

07-create-dockerconfigjson: # desc: "Create a Docker registry secret"
	kubectl create secret docker-registry dockerconfigjson \
		--docker-email=foo@bar.com \
		--docker-username=username \
		--docker-password=password \
		--docker-server=https://index.docker.io/v1/

08-apply-dockerconfigjson: # desc: "Apply a Docker registry secret configuration"
	kubectl apply -f Secret.dockerconfigjson.yaml

09-apply-pod: # desc: "Apply the ConfigMap with property like keys"
	kubectl apply -f Pod.secret-example.yaml

10-exec-printenv: # desc: "Print the environment variables within the container"
	kubectl exec secret-example -c nginx -- printenv

11-exec-cat-config: # desc: "Cat /etc/config/conf.yaml within the container"
	kubectl exec secret-example -c nginx -- cat /etc/config/foo

12-delete-namespace: # desc: "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
