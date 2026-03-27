# 長者時鐘 HK 🕐

> 香港時間顯示、備注欄、提醒事項 — 專為長者設計的大字體網頁應用

**Live Demo:** `https://<你的GitHub用戶名>.github.io/<repo名稱>/`

---

## 功能一覽

| 功能 | 說明 |
|------|------|
| 🕐 香港時間 | 固定 UTC+8，不受裝置時區影響 |
| 📅 日期顯示 | `2026年3月25日 星期三` 格式 |
| 🌅 時段顯示 | 早上 / 下午 / 晚上 |
| ↕️ 分隔條拖動 | 手動調整日期區與時間區的高度比例 |
| 📏 右側滑桿 | 同步控制日期/時間高度比例 |
| ⊡ 自動適配 | 字體溢出時自動縮小至最佳大小（按鈕變紅提示） |
| 📝 備注欄 | 可輸入文字，「大/小」按鈕調節字體，自動限制兩行 |
| 📋 提醒事項 | 新增、編輯、刪除；置頂重複事件（如每日食藥） |
| 🔤 提醒字體 | A- / A+ 四個級別（細/中/大/特大），預設「大」 |
| 💾 本地儲存 | 所有資料存於裝置 `localStorage`，不上傳至伺服器 |
| 📜 全頁滾動 | 上下滾動可瀏覽時鐘、備注、提醒所有區域 |

---

## 部署到 GitHub Pages（免費）

### 第一步 — 建立 Repository

1. 登入 [github.com](https://github.com)
2. 按右上角 **「+」→「New repository」**
3. 填入名稱，例如 `elderly-clock`
4. 設為 **Public**
5. 按 **「Create repository」**

### 第二步 — 上載檔案

1. 在新 repo 頁面按 **「uploading an existing file」**
2. 把以下兩個文件拖入上傳區：
   - `index.html`
   - `README.md`
   - `.github/` 資料夾（含 `workflows/deploy.yml`）
3. 按 **「Commit changes」**

> ⚠️ **注意**：`.github` 是隱藏資料夾，需確認檔案管理員顯示隱藏檔案。

### 第三步 — 啟用 GitHub Pages

1. 進入 repo → 頂部 **「Settings」** 標籤
2. 左側選單點 **「Pages」**
3. **Source** 選 **「GitHub Actions」**
4. 儲存

### 第四步 — 等待部署

- 推送後約 **1 分鐘**自動部署
- 進入 repo → **「Actions」** 標籤查看部署狀態
- 完成後網址為：

```
https://<你的GitHub用戶名>.github.io/<repo名稱>/
```

---

## GitHub Actions 工作流程

`.github/workflows/deploy.yml` 已設定：

```yaml
env:
  FORCE_JAVASCRIPT_ACTIONS_TO_NODE24: true
```

這解決了 Node.js 20 棄用的警告，確保在 2026 年 6 月後仍正常運作。

---

## 本地測試

無需安裝任何軟件，直接在瀏覽器開啟 `index.html` 即可。

```bash
# 或用 Python 啟動本地伺服器
python3 -m http.server 8080
# 然後開啟 http://localhost:8080
```

---

## 資料說明

| localStorage 鍵 | 內容 |
|----------------|------|
| `hk_reminders_v2` | 所有提醒事項（JSON 陣列） |
| `hk_rem_fs_v1` | 提醒字體大小選擇（0-3） |

清除瀏覽器 localStorage 即可重置所有資料。

---

## 瀏覽器支援

Chrome、Safari、Firefox、Edge 最新版本。支援 Android 及 iOS 手機瀏覽器。

---

*為香港長者而設計 ❤️*
