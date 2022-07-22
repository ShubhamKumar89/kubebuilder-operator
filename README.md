# nginx-operator

## Initalize operator:
```bash
operator-sdk init \
 --domain <domain-name> \
 --plugins <deploy-in>

# e.g. operator-sdk init \
#        --domain www.example.com \
#        --plugins helm */
```

## Create API:
```bash
operator-sdk create api \
  --group <group-name> \
  --version <versison> \
  --kind <type-of-object>
  
# e.g. operator-sdk create api \
#        --group demo \
#        --version v1alpha1 \
#        --kind Nginx */
```

## Install CRD:
```bash
make install
```

## Docker image:
```bash
export IMG=<docker-hub-account-name>/<image-name>:<tag>
# e.g. export IMG=shubhamkumar89/nginx-operator:1.2.2
```

## Build and push operator docker image:
```bash
make docker-build docker-push IMG=${IMG}
```

## Deploy Operator:
```bash
make deploy IMG=${IMG}
```

## Install Custom Resource:
```bash
kubectl apply -f config/samples/<demo-yaml-file>
# e.g. kubectl apply -f config/samples/demo_v1alpha1_nginx.yaml
```
