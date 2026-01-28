# test-reports

Gazai 專案的自動化測試報告系統

## 概述

當 [Gazai-io/gazai](https://github.com/Gazai-io/gazai) 專案的 `develop` 或 `main` 分支有新的 push 時，會自動觸發 GitHub Action 執行 E2E 測試。成功生成的測試報告會自動部署到此 test-reports repository。

## 查看測試結果

訪問 [https://gazai-io.github.io/test-reports/history/](https://gazai-io.github.io/test-reports/history/) 可以查看所有測試結果的歷史記錄。

### 結構說明

- **History 頁面**：展示所有測試執行的歷史記錄
- **Runner 資料夾**：每個編號資料夾（如 `1090/`, `1089/` 等）代表一次測試執行的結果
  - `index.html`：該次測試的詳細報告頁面
  - `test-results.json`：測試結果的 JSON 格式數據
  - `data/`：測試過程中生成的相關數據檔案

## 自動化流程

1. 開發者向 `Gazai-io/gazai` 的 `develop` 或 `main` 分支推送代碼
2. GitHub Action 自動觸發 E2E 測試執行
3. 測試完成後，生成詳細的測試報告
4. 報告自動部署到 `test-reports` repository
5. 可通過 GitHub Pages 查看測試結果

## 注意事項

- 報告會透過 GitHub Actions 排程自動清除：**保留最近 7 天**，並且**至少保留最新 20 次**（避免一週沒跑測試時被清空）。如需保留更久，請及時另存重要結果。
