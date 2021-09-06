### Advanced Cloud Architecture - YCIT 020 at McGill University

## Kyverno

### What is Kyverno?
Kyverno is a policy engine designed for Kubernetes. It runs as an admission controller and can validate, mutate, and generate any configuration data based on customizable policies. It is designed to work nicely with tools you already use like kubectl, kustomize, and Git.

### How to get it started?

<b> Step 1: </b> Install Kyverno using Helm

a) Add the Kyverno Helm repository:

    helm repo add kyverno https://kyverno.github.io/kyverno/

b) Scan the new repository for charts

    helm repo update
    
c) Use Helm 3.2+ to create a Namespace and install Kyverno. Beginning with Kyverno 1.4.2, Kyverno Helm chart v2.0.2, the Kyverno CRDs must be added seperately and before Kyverno is installed.

    helm install kyverno-crds kyverno/kyverno-crds --namespace kyverno --create-namespace

d) Use Kyverno 1.4.2+ to create a customizable Helm release name while installing Kyverno. Before Kyverno 1.4.2, the Helm release name must be Kyverno.

    helm install kyverno kyverno/kyverno --namespace kyverno

<b> Step 2: </b> Once Kyverno is installed you can start applying the different policies. Here is the link: https://kyverno.io/policies/. Here are some of the examples of commands in how to apply the policies.

a) Applying the <b> restrict image registries </b> policy:

    kubectl apply -f https://raw.githubusercontent.com/kyverno/policies/main/best-practices/restrict_image_registries/restrict_image_registries.yaml
    
b) Applying the <b> disallow default namespace </b> policy:

    kubectl apply -f https://raw.githubusercontent.com/kyverno/policies/main/best-practices/disallow_default_namespace/disallow_default_namespace.yaml
    
c) Applying the <b> require drop all </b> policy: 
    
    kubectl apply -f https://raw.githubusercontent.com/kyverno/policies/main/best-practices/require_drop_all/require_drop_all.yaml


<b> Step 3: </b> In order to see the list of policies you have applied, use the following commands:

    kubectl get cpol
    
<b> Step 4: </b> To delete a policy, you can do the following:

    kubectl delete cpol <enter the name of the policy>
    
For example,
    
    kubectl delete cpol restrict-image-registries

<b> Step 5: </b> Finally, if you want to delete your Kyverno installation, you can do the following:

    kubectl delete -f https://raw.githubusercontent.com/kyverno/kyverno/master/definitions/release/install.yaml

## Author

Stanley Tran

## References

#### Documentation on Kyverno
<br> https://kyverno.io/docs/

#### YouTube videos
<br> https://www.youtube.com/watch?v=8fgrjBnxqi0&t=5s 
<br> https://www.youtube.com/watch?v=DREjzfTzNpA

