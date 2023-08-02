# kubernetes-templates
tbd

## Dockerfile (shared-kubectl:1.23)

```
FROM ubuntu:22.10

RUN <<EOR
    apt-get update
    apt-get install -y curl gettext-base
EOR

RUN <<EOR
    curl -LO https://dl.k8s.io/release/v1.23.17/bin/linux/amd64/kubectl
    install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
    kubectl version --client
EOR
```
