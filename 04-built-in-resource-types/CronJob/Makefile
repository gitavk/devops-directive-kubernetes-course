export NAMESPACE := 04--cronjob
export GREEN := \e[0;32m
export RED := \e[0;31m
export NC := \e[0m  


01-create-namespace: # "Create a namespace for these examples and set as default"
	kubectl apply -f Namespace.yaml
	kubens ${NAMESPACE}

02-apply-minimal: # "Apply the minimal CronJob configuration"
	kubectl apply -f CronJob.echo-date-minimal.yaml

03-apply-better: # "Apply the better CronJob configuration"
	kubectl apply -f CronJob.echo-date-better.yaml

04-create-job-from-cronjob: # "Manually create a job using a cronjob as the template"
	kubectl create job --from=cronjob/echo-date-better manually-triggered

05-delete-namespace: # "Delete the namespace to clean up"
	@echo "${RED}🚨 Deleting the namespace recursively deletes the resources inside of it! 🚨${NC}"
	kubectl delete -f Namespace.yaml
