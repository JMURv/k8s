master-run:
	kubectl apply -f master/config-master.yaml
	kubectl apply -f master/pvc-master.yaml
	kubectl apply -f master/svc-master.yaml
	kubectl apply -f master/ss-master.yaml

master-d:
	kubectl delete sts pg-master
	kubectl delete svc pg-master

master-dpv:
	kubectl delete pvc pg-master-pvc
	kubectl delete pv pg-master-pv

slave-run:
	kubectl apply -f slave/config-slave.yaml
	kubectl apply -f slave/pvc-slave.yaml
	kubectl apply -f slave/svc-slave.yaml
	kubectl apply -f slave/ss-slave.yaml
	kubectl apply -f slave/pv-slave.yaml

slave-d:
	kubectl delete sts pg-slave

slave-dpv:
	kubectl delete pvc pg-slave-pvc
	kubectl delete pv pg-slave-pv