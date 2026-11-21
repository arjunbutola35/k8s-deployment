# Minikube Helm Demo (App + Deployment + Service + Ingress)

## Quick Start Commands

1. Enable Ingress in Minikube:
   minikube addons enable ingress

2. Build Docker image inside Minikube:
   cd app
   eval $(minikube docker-env)
   docker build -t my-custom-app:1.0.0 .
   cd ..

3. Lint and package the Helm chart:
   helm lint ./my-chart
   helm package ./my-chart

4. Deploy to Minikube:
   helm upgrade --install demo-app ./my-custom-app-0.1.0.tgz --namespace web-apps --create-namespace

5. Verify resources:
   kubectl get deploy,svc,ingress -n web-apps
