# Monitoring Stack

## Installation
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm install monitoring prometheus-community/kube-prometheus-stack \
  --namespace monitoring \
  --set grafana.service.type=NodePort \
  --set grafana.service.nodePort=30300 \
  --set prometheus.service.type=NodePort \
  --set prometheus.service.nodePort=30090

## Access
- Grafana: http://<NODE_IP>:30300
- Prometheus: http://<NODE_IP>:30090
- Login: admin
