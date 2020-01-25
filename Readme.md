# Kubernetes for SysAdmins ![alt text](https://vettom.github.io/images/RobinR100px.png "Denny Vettom Logo")

## Summary

  Some of my K8 learnings and exam preparation. Anypne preparing for exam, would recoment Udemy cource by Mumshad.
- Samples   : Basic K8 templates, ideal for starter and exam practice
- Vagrant.  : Vagrant Kubernetes environment. (Not sure who wrote it, it works)
- Mycompany : Helm chart2 sample charts with configmaps



# Exam tips
> Kubectl auto complete `alias k=kubectl; complete -F __start_kubectl`
- Create simple pod running Nginx 
``` k run nginx --image=nginx --restart=Never --dry-run -o yaml ```
- Create Deployment with 2 replicas
``` k create deploy deploy1 --image=nginx --dry-run -o yaml ```