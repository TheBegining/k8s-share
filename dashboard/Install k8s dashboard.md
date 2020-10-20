- 安装

    ```
    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
    ```
    > [参考链接](https://kubernetes.io/docs/tasks/access-application-cluster/web-ui-dashboard/)

- 访问
    > kubectl proxy

    > [访问地址](http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy)

- 获取访问token

    1. [创建用户]
        - 创建 Service Account

            > kubectl apply -f ServiceAccount.yml

        - 创建 ClusterRoleBinding

            > kubectl apply -f ClusterRoleBinding.yml

    2. 获取token

        > kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | grep admin-user | awk '{print $1}')
