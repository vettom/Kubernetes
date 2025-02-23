[<img src="https://vettom-images.s3.eu-west-1.amazonaws.com/logo/vettom-banner.jpg">](https://vettom.pages.dev/)

# Kubernetes for SysAdmins 

## Summary

  Some of my K8 learnings and exam preparation. Anypne preparing for exam, would recoment Udemy cource by Mumshad.
- Samples   : Basic K8 templates, ideal for starter and exam practice
- Vagrant.  : Vagrant Kubernetes environment. (Not sure who wrote it, it works)
- Mycompany : Helm chart2 sample charts with configmaps

# Development Principle
![alt text](https://vettom.github.io/images/dvethos.jpg "Denny Vettom Development ethos ")

# ![alt text](https://vettom.github.io/images/dv-tec-logo-round2cm.png "Denny Vettom  Tech Logo")Exam tips
> Kubectl auto complete `alias k=kubectl; complete -F __start_kubectl`
### Kube Config
- Get current context `k config current-context`
- Set context and namespace `k config set-context newcontext --namespace=newns` 
- View current configuration `k config view`
- Read config from a file `k config view --kubeconfig=/newconf.txt`

### Useful commands
> Make use of --dry-run and -o yaml, sometimes easier to edit yaml and apply it.


**Create simple pod running Nginx**
``` 
k run nginx --image=nginx --restart=Never --dry-run -o yaml 
--restart=Alyays  Creates Deployment
--restart=OnFailure  Creates a Job
```
**Create Deployment with 4 replicas**
``` 
k create deploy deploy1 --image=nginx --dry-run -o yaml 
k scale --replicas=4 deploy/deploy1 
```
**Create Service to expose Deploy1 running port 80, on NodePort=32005**
> NodePort cannot be specified at command prompt, edit Yaml add nodePort then apply. Or use k create and add matching labels for your deployment.
```
k expose deploy deploy1 --name=deploy-service --type=NodePort --port=80 --dry-run -o yaml
```
Edit yaml and add "nodePort=32005" in ports section and apply config.
