# Job/CronJob
- Job 代表只有一次性的工作，例如 GitLab 升級檢查時會做 Pre-check 的工作，因為有規定版本升級步驟。
- CronJob 則是定期工作，可用場景例如 Application 本身會產生 Caches 需要定期清理、檢查 dependencies 的版本等。