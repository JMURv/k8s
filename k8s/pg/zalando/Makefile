srv:
	kubectl apply -f server/conf/operatorconfiguration.crd.yaml
	kubectl apply -f server/conf/pg-conf.yaml
	kubectl apply -f server/operator-service-account-rbac.yaml
	kubectl apply -f server/postgres-operator.yaml
	kubectl apply -f server/api-service.yaml

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

