# Kubernetes Simple Config

## DESCRIPTION: 

Full instruction for minikube/kubectl using and orchestrate project. (Django, PostgreSQL)

# Installation Guide 📕:

### Prerequisites 💻

Ensure you have Minikube and kubectl installed on your machine. You can download them from:

- Minikube: [Get Minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Flinux%2Fx86-64%2Fstable%2Fbinary+download) ☸️
- kubectl: [kubectl](https://kubernetes.io/docs/reference/kubectl/) ☸️

### Environment Developing


1. **Clone the repository:** ```git clone https://github.com/excommunicades/kubernetes-simple-config.git```
2. **Build and run minikube:** ```minikube start```
3. **Set ingress addon to minikube:** ```minikube addons enable ingress```
4. **Alias kubectl command for convenient:** ```alias k='kubectl'```
5. **Create all pods/services, ingress, secret:**
```
k apply -f db-secret.yaml - create secret
k apply -f db-pv.yaml - create persistent volume
k apply -f db-pvc.yaml - create persistent volume claim
k apply -f db-deployment.yaml - create postgresql database pod
k apply -f db-service.yaml - create db service
k apply -f django-deployment.yaml - create django-server pod
k apply -f django-service.yaml - create django service
k apply -f ingress.yaml - create ingress
```
6. **Set Up ingress for your local machine:**

Get ```host``` from ```ingress.yaml: <<ingress: spec: rules: host >>```<br>
GET ingress address:
```
k get ingress
```
Set ```ADDRESS``` and ```host``` to ```/etc/hosts```
<br>
example:
```
XXX.XXX.XX.X your_host
```

# Stopping the Services 🚪


**To stop all running cluster, you can use:** ```minikube stop```<br>
**To delete minikube cluster:** ```minikube delete```

# Conclusion

With these config you can easily orchestrate your project :)

## Authors 😎

- **Stepanenko Daniil** - "Kubernetes simple config"