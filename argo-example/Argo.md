- 安装

    > [官网](https://github.com/argoproj/argo)

    ```
    kubectl create namespace argo
    kubectl apply -n argo -f https://raw.githubusercontent.com/argoproj/argo/v2.10.2/manifests/install.yaml
    ```

- 访问Argo Web UI

    ```
    kubectl get pods -n argo
    kubectl port-forward -n argo argo-server-5b897cc58c-glxqv 2746:2746
    ```

- Workflow

    ```
    argo submit hello-world.yml
    ```

- CronWorkflow

    ```
    argo cron create hello-world-cron.yml 
    ```

- Template

    ```
    argo template create hello-world-tpl.yml
    ```
