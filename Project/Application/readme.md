# Deploying PHP Guestbook application with MongoDB

## Objectives 

* Start up a MongoDB front end

* Creating Mongo Deployment
	* kubectl apply -f https://k8s.io/examples/application/guestbook/mongo-deployment.yaml
	* Run the following command to view the logs from the MongoDB Deployment: `kubectl logs -f deployment/mongo`
	* -f is watch command and ctrl+C helps with exiting .
* Creating mongodb service
	* Kubernetes seperates deployment from service. Service defines policy to access the Pods.
	* kubectl apply -f https://k8s.io/examples/application/guestbook/mongo-service.yaml
	* kubectl get service
	* kubectl describe service mongo -


* Start up a Guestbook frontend

* Create frontend deployment
	* kubectl apply -f https://k8s.io/examples/application/guestbook/frontend-deployment.yaml
	* kubectl get pods -l app.kubernetes.io/name=guestbook -l app.kubernetes.io/component=frontend
* Create frontend service
	* kubectl apply -f https://k8s.io/examples/application/guestbook/frontend-service.yaml
	* kubectl get pods -l app.kubernetes.io/name=guestbook -l app.kubernetes.io/component=frontend

* Expose and view frontend service.
	* Viewing the Frontend Service via kubectl port-forward
		* kubectl port-forward svc/frontend --address 192.168.172.89 8080:80

**Screenshot**
![port_forwar](https://user-images.githubusercontent.com/57376468/117383264-0664b700-aea6-11eb-9458-52a4071d8d9c.PNG)


* clean up
	* kubectl delete deployment -l app.kubernetes.io/name=mongo
	* kubectl delete service -l app.kubernetes.io/name=mongo
	* kubectl delete deployment -l app.kubernetes.io/name=guestbook
	* kubectl delete service -l app.kubernetes.io/name=guestbook

**Screenshot**
