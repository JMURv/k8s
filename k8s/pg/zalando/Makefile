srv:
	kubectl apply -f server/conf/operatorconfiguration.crd.yaml # configuration
	kubectl apply -f server/conf/postgresql-operator-default-configuration.yaml # configuration
	kubectl apply -f server/operator-service-account-rbac.yaml # identity and permissions
	kubectl apply -f server/postgres-operator.yaml # deployment
	kubectl apply -f server/api-service.yaml # operator API to be used by UI

srv-run:
	kubectl apply -f server/postgres-cluster.yaml

srv-running:
	kubectl get pod -l name=postgres-operator

srv-p:
	kubectl get pods -l app=pg -L role

srv-s:
	kubectl get svc -l app=pg -L role

ui:
	kubectl apply -f cli/
	kubectl port-forward svc/postgres-operator-ui 8081:80

cli-running:
	kubectl get pod -l name=postgres-operator-ui

