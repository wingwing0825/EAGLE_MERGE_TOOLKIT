# 自由合併圖片（Eagle Plugin）

一個俾 Eagle 用嘅拼貼插件，支援手動拖曳排版同智慧分組，將多張圖片快速合併成單一輸出圖。

![Plugin Logo](./logo.png)

## 功能重點

- 支援 `PNG`、`JPEG`、`WebP`
- 手動排版：自訂每行格仔數量，拖曳交換位置
- 智慧分組：按檔名前綴自動分行（可設定每行上限）
- 產生預覽後再輸出
- 可直接匯入 Eagle 指定資料夾
- 可下載到本機
- 可收藏常用資料夾

## 系統需求

- 已安裝 Eagle（桌面版）
- 插件目錄需要包含 `node_modules`（本插件依賴 `sharp`）

## 快速安裝（一般使用者）

如果你已經有打包好的 `.eagleplugin`：

1. 下載 `自由合併圖片.eagleplugin`
2. 在 Eagle 插件管理頁匯入該檔案
3. 完成安裝後，從 Eagle 啟動插件

## 本地開發安裝（開發者）

1. 下載或 clone 呢個 repo
2. 進入專案資料夾後安裝依賴：

```bash
npm install
```

3. 在 Eagle 插件開發模式載入此資料夾
4. 啟動插件測試

## 使用教學

1. 在 Eagle 先選好要拼貼嘅圖片
2. 打開插件，按「重新載入選取」或「追加圖片」
3. 選擇輸出格式（PNG / JPEG / WebP）
4. 選擇排版模式：
   - 手動模式：自行設定每行格仔數量，再拖曳圖片入格
   - 智慧分組：按檔名前綴自動分行，可調整每行上限
5. 可按「產生預覽」確認結果
6. 輸出方式二選一：
   - 「匯入 Eagle」
   - 「存到電腦」

## 打包與上架（GitHub / Eagle）

### 1) 上架前檢查

- `manifest.json`：
  - `id` 必須係 UUID（例如：`117ea974-b0db-48bc-954f-63a3114478f0`）
  - `version` 按版本更新（例如 `1.0.1`）
  - `devTools` 建議設為 `false`
- 確認 `logo.png`、`index.html`、`index.js`、`manifest.json` 完整
- 確認 `node_modules` 已包含（特別係 `sharp`）

### 2) 產生 `.eagleplugin`

用 Eagle 插件打包/匯出功能產生 `.eagleplugin` 檔案，再上傳到 Eagle 插件平台。

> 注意：平台只接受有效插件包，唔好直接上傳未打包資料夾。

### 3) 推上 GitHub 建議內容

- 原始碼（`index.html`、`index.js`、`manifest.json`）
- `README.md`
- 版本變更紀錄（可選：`CHANGELOG.md`）

## 常見問題

### Q1: 上傳平台顯示「插件 ID 格式不正確」

`manifest.json` 嘅 `id` 唔係 UUID。請改成 UUID 後重新打包。

### Q2: 開插件會自動彈出 DevTools

檢查 `manifest.json`：

```json
"devTools": false
```

改完要重新打包插件再安裝。

### Q3: 匯入/輸出失敗

- 確認有先在 Eagle 選圖
- 確認圖片數量同格仔容量合理
- 確認 `node_modules` 已安裝完整

## 隱私說明

- 本插件唔會上傳你嘅圖片到外部伺服器
- 圖片處理在本機完成
- 只會用本機暫存路徑產生輸出檔，再匯入 Eagle 或下載
