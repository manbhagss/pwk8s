**Play With Docker Initialization Commands **

kubeadm init --apiserver-advertise-address $(hostname -i)

kubectl apply -n kube-system -f \
    "https://cloud.weave.works/k8s/net?k8s-version=$(kubectl version | base64 | tr -d '\n')"

curl -L -s https://git.io/vdc53  | sed 's/targetPort: 9090/targetPort: 9090\n  type: LoadBalancer/' | \
    kubectl apply -f -
