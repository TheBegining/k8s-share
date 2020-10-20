ENV=dev
kubectl kustomize ./overlays/${ENV} | argo template create -n ${ENV} -
argo template delete -n ${ENV} hello-world-tpl