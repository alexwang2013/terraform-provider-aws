# EKS Getting Started Guide Configuration

This is the full configuration from https://www.terraform.io/docs/providers/aws/guides/eks-getting-started.html

See that guide for additional information.

NOTE: This full configuration utilizes the [Terraform http provider](https://www.terraform.io/docs/providers/http/index.html) to call out to icanhazip.com to determine your local workstation external IP for easily configuring EC2 Security Group access to the Kubernetes master servers. Feel free to replace this as necessary.



useful link

https://aws.amazon.com/blogs/startups/from-zero-to-eks-with-terraform-and-helm/

https://learn.hashicorp.com/terraform/aws/eks-intro


https://stackoverflow.com/questions/57961162/helm-install-unknown-flag-name

https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nginx-ingress-on-digitalocean-kubernetes-using-helm


Unable to connect to the server: getting credentials: exec: exec: "aws-iam-authenticator": executable file not found in $PATH. try:

$ aws2 eks update-kubeconfig --name terraform-eks-demo --region us-west-2



when helm init --service-account tiller. error Error: unknown flag: --service-account
ignore helm init


terraform output config_map_aws_auth > configmap.yml
kubectl apply -f configmap.yml

kubectl apply -f tiller-user.yaml


helm install my-nginx \
stable/nginx-ingress \
--set rbac.create=true


create deployment
$ kubectl apply -f hello.yml

create ingress
$ kubectl apply -f hello-kubernetes-ingress.yaml


delete
kubectl delete -f hello.yml
kubectl delete -f hello-kubernetes-ingress.yaml

helm del  my-nginx;
terraform destroy
