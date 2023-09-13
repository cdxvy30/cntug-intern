# Service
- Service 可以將多個 Pod (多個應用程式)變成網路服務，且不需修改應用程式即可做到負載平衡。
- Service 的存在主要是為了處理網路，例如每個 Pod 在 K8s 中都會有內網 IP，而這個 IP 是會變動的。
- 舉例來說，當微服務之間要互相存取時，但有其中一個微服務 Pod 的內網 IP 不斷變動時，該如何處理呢？這時 Service 可以幫我們解決這個問題。
- `.spec.selector` 是對應 Pod 的選擇器，符合條件的就會被對應，以 `svc-example.yml` 的範例來說，符合 `app=other` 的 Pod 就會被對應。
- `.spec.type` 有四種型態:
  - `ClusterIP`: 預設方式，僅在 Cluster 內部可存取
  - `NodePort`: 在 WorkerNode 上指定 Port 對應進去 (30000~32767)
  - `LoadBalancer`: 對外開 Load Balancer，通常公有雲才有，私有雲要透過額外的設定才能達到
  - `ExternalName`: 較少用

## 注意

