kind-01-generate-config:
	REPLACE_WITH_ABSOLUTE_PATH=${PWD} envsubst < kind-config.yaml.TEMPLATE > kind-config.yaml

kind-02-create-cluster:
	kind create cluster --config kind-config.yaml

kind-03-delete-cluster:
	kind delete cluster
