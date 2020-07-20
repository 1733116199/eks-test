1. To create a eks cluster with a mix of public and private subnets (the public ones holds the load balancers and the private ones are used by fargate), type: kubectl create cluster --config-file fargate-profile.yaml
2. To launch an instance of nginx, type: kubectl apply -f nginx.deployment.yaml
3. To attach to the running nginx deployment, type: kubectl exec -it <nginx-pod-name-here> bash
4. To create a load balancer in public subnets to route traffic to nginx, type kubectl apply -f nginx.service.yaml
5. To check load balancer is working, type: kubectl get services -o wide to get the load balancer's public ip, then visit it in a browser