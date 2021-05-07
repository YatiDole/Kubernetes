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

**Screenshot**
![kubectl_get_nodes](https://user-images.githubusercontent.com/57376468/117506311-ff43b480-af4a-11eb-85ea-07b342db3d21.PNG)

* Start up a Guestbook frontend

* Create frontend deployment
	* kubectl apply -f https://k8s.io/examples/application/guestbook/frontend-deployment.yaml
	* kubectl get pods -l app.kubernetes.io/name=guestbook -l app.kubernetes.io/component=frontend
* Create frontend service
	* kubectl apply -f https://k8s.io/examples/application/guestbook/frontend-service.yaml
	* kubectl get pods -l app.kubernetes.io/name=guestbook -l app.kubernetes.io/component=frontend

**Screenshot**
![frontend_get_pods](https://user-images.githubusercontent.com/57376468/117506448-39ad5180-af4b-11eb-8b31-c25cb052180e.PNG)

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
![cleanup_getpods](https://user-images.githubusercontent.com/57376468/117506783-c9530000-af4b-11eb-9169-000bdc33bc9c.PNG)

**Screenshot of Browser**
![final_screenshot](https://user-images.githubusercontent.com/57376468/117506786-ca842d00-af4b-11eb-9c93-ab5a2cb1e0c8.PNG)
