# K8s 操作指令
## Namespace
- Namespace 的概念重要在於可以將一個 Cluster 內的資源分割成不同組別，例如切割成開發環境 Development 和產品環境 Production。
```
kubectl create namespace development
kubectl create namespace production

kubectl delete namespace development

kubectl get namespace
```
- 上述指令中的 `namespace` 也可以縮寫為 `ns`。
- 這裡要注意有些 Resource 不吃 Namespace，例如: Persistent Volume, StorageClass 和 Node 等是無法在 Cluster 層級用 Namespace 做區隔。
- 在寫 Resource 的 YAML 檔時，可在 `.metadata.namespace` 指定命名空間，而 `kubectl apply` 時指定的命名空間如果和 YAML 檔中的 `namespace` 不同，K8s 會拒絕該 `apply` 的請求。

## Reference
- 