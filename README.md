### Fleet Infra
### Bootstrap Flux với github

```bash
export GITHUB_TOKEN=<your-token>
export GITHUB_USER=<your-username>
export GITHUB_REPOSITORY=<your-repository>
export K8S_CONTEXT=<your-k8s-context>
export CLUSTER_PATH=<cluster-path>
```

Ở đây mình dùng GitHub Personal Account nên thêm flag `--token-auth`:

```bash
flux bootstrap github \
    --token-auth \
    --components-extra=image-reflector-controller,image-automation-controller \
    --context=$K8S_CONTEXT \
    --owner=$GITHUB_USER \
    --repository=$GITHUB_REPOSITORY \
    --branch=main \
    --personal \
    --path=$CLUSTER_PATH
```
