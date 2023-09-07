# Pod
- 實際定義或部署時通常不會用 Pod，因為實際使用會必須搭配 Deployment 以及 ReplicaSet 的功能，所以通常會直接寫 Deployment (同時包含 ReplicaSet)。但 Debug 時還是優先從 Pod 這個最小單位找起。
- 指令
  - `kubectl apply -f pod-example.yaml`
  - `kubectl delete -f pod-example.yaml`

## Pod 要建立的資訊
- API group and version
  - apps/v1, cores/v1, etc.
- Resource type (kind):
  - Pod, Deployment, Service, etc.
- Pod name
- Label
- Container name