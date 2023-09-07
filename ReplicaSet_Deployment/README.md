# ReplicaSet/Deployment
- Deployment 是基於 ReplicaSet 實作成的。
- ReplicaSet 就是一組重複的 Pods 所組成，用來分散運算資源。
- 因為 ReplicaSet 不能做到 Image 替換，但 Deployment 可以，並進一步達成 Rolling update，讓服務在不斷線的情況下滾動升級。
## 注意
- `.spec.selector.matchLabels`和`.spec.template.metadata.labels`必須要相同，否則系統會 reject。且習慣上要跟`.metadata.labels`相同。