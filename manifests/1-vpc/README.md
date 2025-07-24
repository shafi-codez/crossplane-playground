kubectl create secret generic aws-creds --from-file=creds=manifests/aws-credentials.txt -n crossplane-system


helm repo add crossplane-stable https://charts.crossplane.io/stable
helm repo update
helm install crossplane \
--namespace crossplane-system \
--create-namespace crossplane-stable/crossplane
kubectl apply -f manifests/1-vpc
kubectl get internetgateway.ec2.aws.upbound.io dev-igw

Output
<img width="1095" height="405" alt="image" src="https://github.com/user-attachments/assets/61d4b5b5-910d-42ca-97bd-2873b0158c0c" />

Verify pods
<img width="1049" height="126" alt="image" src="https://github.com/user-attachments/assets/1929afd9-0ae4-401e-b33e-3e9f8d03abcb" />

Verify CRDS deployed via helm
kubectl get crds | grep crossplane.io

https://help.yeastar.com/en/cloudpbx/deploy/install_ymp_sbc/launch_instances.html


kubectl get vpc.ec2.aws.upbound.io dev-main

private / public routes creation
<img width="943" height="122" alt="image" src="https://github.com/user-attachments/assets/dc09b91e-7c2f-46b4-8266-bdd45a75913f" />

Using Cursor
<img width="694" height="703" alt="image" src="https://github.com/user-attachments/assets/c5eb05da-a93f-43ce-a99d-32bd97e74cf6" />