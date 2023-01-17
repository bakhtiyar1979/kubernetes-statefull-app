Statefull app in K8S

1. Statefull means Persistent volume is created and in case pod goes down data will be persisted/kept 
2. Get Storageclass --> kubectl get sc/storageclass/storageclasses 
3. kubectl create secret generic mysql-pass --from-literal=password=eks-orchsky-mysql-pw --namespace statefull
4. kubectl get secret --namespace statefull
5. kubectl patch storageclass orchsky -p  '{"metadata": {"annotations":{"storageclass.kubernetes.io/is-default-class":"true"}}}' -n statefull