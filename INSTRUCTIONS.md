# Instructions

## Update Ingress Domain
```bash
export INGRESS_DOMAIN=apps.terasky.demo
find . \( -type d -name .git -prune \) -o -type f -print0 | xargs -0 sed -i "s/tap-lab\.terasky\.demo/$INGRESS_DOMAIN/g"
```

## Create Pre Reqs
```bash
kubectl apply -f namespace.yaml
kubectl apply -f pipelines.yaml
kubectl apply -f tls-trust.yaml
kubectl apply -f redis.yaml
```

## Install SCG Operator
```bash
tanzu package install scg \
  --namespace tap-install \
  --package spring-cloud-gateway.tanzu.vmware.com \
  --version 2.0.0-tap.3
```
## Patch SCG Operator
```bash
kctrl package installed pause \
  --package-install scg \
  --namespace tap-install \
  --yes

kubectl apply -f scg-operator-tls-trust.yaml
```

## Deploy App SSO Auth Server and Config
```bash
kubectl apply -f appsso.yaml
```

## Deploy Workloads
```bash
kubectl apply -f workload.yaml
```

## Deploy SCG instance and config
```bash
kubectl apply -f tls-service-bindings.yaml
kubectl apply -f scg-config.yaml
```

## Expose App externally
```bash
kubectl apply -f ingress.yaml
```