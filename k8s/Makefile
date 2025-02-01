master-run:
	kubectl apply -f .pg/master/config-master.yaml
	kubectl apply -f .pg/master/pv-master.yaml
	kubectl apply -f .pg/master/pvc-master.yaml
	kubectl apply -f .pg/master/svc-master.yaml
	kubectl apply -f .pg/master/ss-master.yaml

master-d:
	kubectl delete statefulset pg-master
	kubectl delete svc pg-master

master-dpv:
	kubectl delete pvc pg-master-pvc
	kubectl delete pv pg-master-pv

slave-run:
	kubectl apply -f .pg/slave/config-slave.yaml
	kubectl apply -f .pg/slave/pv-slave.yaml
	kubectl apply -f .pg/slave/pvc-slave.yaml
	kubectl apply -f .pg/slave/svc-slave.yaml
	kubectl apply -f .pg/slave/ss-slave.yaml

slave-d:
	kubectl delete statefulset pg-slave

slave-dpv:
	kubectl delete pvc pg-slave-pvc
	kubectl delete pv pg-slave-pv

kc-run:
	kubectl apply -f ./kc/kc-config.yaml
	kubectl apply -f ./kc/kc-secret.yaml
	kubectl apply -f ./kc/kc-svc.yaml
	kubectl apply -f ./kc/kc-ss.yaml

kc-del:
	kubectl delete statefulset keycloak

kc-del-pv:
	kubectl delete pv kc-pv
	kubectl delete pvc kc-pvc

ispn-run:
	kubectl apply -f ./ispn/ispn-config.yaml
	kubectl apply -f ./ispn/ispn-svc.yaml
	kubectl apply -f ./ispn/ispn-ss.yaml

ispn-del:
	kubectl delete statefulset infinispan

ispn-del-pv:
	kubectl delete pv kc-pv
	kubectl delete pvc kc-pvc