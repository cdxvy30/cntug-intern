# StatefulSet
- 應用程式分為 Stateless 和 Stateful，如果需要狀態管理的話，在 K8s 中可以撰寫 StatefulSet。有以下幾點可以判斷是否要用到 StatefulSet:
  - 需要穩定和唯一的網路識別（Pod reschedule 後的 Pod name 和 hostname 不變動）
  - 需要穩定的儲存（Pod reschedule 後要取得相同資料，可以使用 Persistent Volume Claim）
  - 部署或 Scale 上有順序的考量（`.spec.podManagementPolicy` 預設 `OrderedReady`，也可以改成 `Parallel`同時產生）
- P.S. 因此如果要用 Pod 組合 MongoDB Cluster 或 MySQL Cluster，StatefulSet 較 Deployment 適合。