# Columnar output
$ kubectl get services                          # List all services in the namespace
$ kubectl get pods --all-namespaces             # List all pods in all namespaces
$ kubectl get pods -o wide                      # List all pods in the namespace, with more details

# Verbose output
$ kubectl get nodes                             # Get All Nodes
$ kubectl describe nodes <node-name>
$ kubectl get pods                              # Get All Pods
$ kubectl describe pods <pod-name>
$ kubectl describe pods/<pod-name>              # Equivalent to previous

# List Services Sorted by Name
$ kubectl get services --sort-by=.metadata.name

# List pods Sorted by Restart Count
$ kubectl get pods --sort-by=.status.containerStatuses[0].restartCount

# Get ExternalIPs of all nodes
$ kubectl get nodes -o jsonpath='{.items[*].status.addresses[?(@.type=ExternalIP)].address}'

#Logs
kubectl logs my-pod -c my-container( kubectl logs knote-5f6d8d9995-mgq2d -c containerd://e4c88734d9eff11e3f4b84411c920ac61367b8455d906917f23ef457be8c0eb6)

#Container
kubectl get pod <pod-name> -o jsonpath='{.spec.containers[*].name}' #Get List of all container
kubectl logs my-pod -c my-container  #Get log of container inside pod
