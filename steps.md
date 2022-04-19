eksctl create iamserviceaccount \
  --cluster=analytics-k8s2 \
  --namespace=kube-system \
  --name=aws-load-balancer-controller \
  --role-name "EKSLBControllerRoleK8S2" \
  --attach-policy-arn=arn:aws:iam::009349951012:policy/AlbIAMLoadBalancerCtlPolicyK8S2 \
  --approve

kubectl annotate serviceaccount -n kube-system aws-load-balancer-controller \
    eks.amazonaws.com/sts-regional-endpoints=true

create an ecr and enable the pull?
  