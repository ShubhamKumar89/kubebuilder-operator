# nginx-operator

Initalize operator:
```bash
operator-sdk init \
  --domain spishu.hashnode.dev \
  --plugins helm
```

Create an API:
```bash
operator-sdk create api \
  --group demo \
  --version v1alpha1 \
  --kind Nginx
```

Install CRD:
```bash
make install
```

Docker image:
```bash
export IMG=shubhamkumar89/nginx-operator:1.2.2
```

Build and push operator docker image:
```bash
make docker-build docker-push IMG=${IMG}
```

Deploy operator:
```bash
make deploy IMG=${IMG}
```

Install Custom Resource:
```bash
kubectl apply -f config/samples/demo_v1alpha1_nginx.yaml
```
