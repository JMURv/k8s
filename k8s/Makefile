kc-run:
	kubectl apply -f ./kc/kc-config.yaml
	kubectl apply -f ./kc/kc-secret.yaml
	kubectl apply -f ./kc/kc-svc.yaml
	kubectl apply -f ./kc/kc-ss.yaml

kc-d:
	kubectl delete sts keycloak
	kubectl delete svc keycloak

kc-dpv:
	kubectl delete pv kc-pv
	kubectl delete pvc kc-pvc

ispn-run:
	kubectl apply -f ./ispn/ispn-config.yaml
	kubectl apply -f ./ispn/ispn-svc.yaml
	kubectl apply -f ./ispn/ispn-ss.yaml

ispn-d:
	kubectl delete sts infinispan
	kubectl delete svc infinispan-cluster

ispn-dpv:
	kubectl delete pv -l app=infinispan

minio-run:
	kubectl apply -f ./minio/cfg/minio-secret.yaml
	kubectl apply -f ./minio/minio-pvc.yaml
	kubectl apply -f ./minio/minio-svc.yaml
	kubectl apply -f ./minio/minio-deploy.yaml

minio-d:
	kubectl delete deploy minio
	kubectl delete svc minio-svc

minio-dpv:
	kubectl delete pvc minio-pvc
