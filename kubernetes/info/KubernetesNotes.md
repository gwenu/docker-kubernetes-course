Kubernetes Cluster
-----
![Kubernetes cluster](../info/images/kubernetes-cluster.png)


Communication through **Master**

![Kubernetes cluster](../info/images/kubernetes-what-why.png)

![Kubernetes dev vs prod](../info/images/kubernetes-dev-prod.png)

**Kubernetes on local environment**

![Kubernetes local](../info/images/kubernetes-local.png)

```
minikube start
kubectl cluster-info
```

**Config files explained**

```
client-pod.yaml
------
apiVersion: v1
kind: Pod
metadata: 
  name: client-pod
  labels:
    components: web
spec: 
  containers:
    - name: client
      image: poluektova/multi-client
      ports:
        - containerPort: 3000
   
        
        
client-node-port.yaml
------     
apiVersion: v1
kind: Service
metadata: 
  name: client-node-port
spec:
  type: NodePort
  ports:
    - port: 3050
      targetPort: 3000
      nodePort: 31515
  selector:
    component: web
```

![Kubernetes apiVersion](../info/images/kubernetes-api-version.png)

![Kubernetes object types](../info/images/kubernetes-object-types.png)

**Pods** runs one or more closely related container.  
**Services** - (ClusterIP, NodePort(mainly dev purposes), LoadBalancer, Ingress) - sets up networking in a Kubernetes Cluster.  

![Kubernetes simple arch](../info/images/kubernetes-simple-arch.png)

Service linked with Pod by selector (in Service) - labels (in Pod) -> 'component: web'.

**Feed a config file to Kubectl**
```
kubectl apply -f <filename>
```

**Print the status of all running pods/services**
```
kubectl get pods
kubectl get services
```

**Address of VM**
```
minikube ip
```
