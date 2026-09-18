# 12週寫作覺醒——衝刺篇｜單元01

國中生寫作自學單元的互動網頁原型，單一 HTML 檔案，開啟即用。

## 檔案說明

| 檔案 | 說明 |
|---|---|
| `index.html` | 網頁本體（HTML / CSS / JS 全部內嵌在同一個檔案） |
| `.gitignore` | 忽略系統暫存檔 |

## 本機預覽

直接用瀏覽器開啟 `index.html` 即可，不需要架站或安裝任何東西。

## 發布到 GitHub Pages

1. 把這個資料夾推上 GitHub（repo 需為 **Public**，免費帳號才能用 Pages）。
2. 進入 repo → **Settings** → 左側 **Pages**。
3. Source 選 **Deploy from a branch**，Branch 選 **main** / 資料夾選 **/ (root)**，按 Save。
4. 等 1～2 分鐘，網址會是：
   `https://<你的帳號>.github.io/<repo 名稱>/`

## 注意事項

- 頁面會從 Google Fonts 載入 `Baloo 2` 與 `Noto Sans TC` 兩套字型，需要連網才會顯示正確字體；離線時會自動退回系統字型，版面不會壞掉。
- 檔名必須是 `index.html`，GitHub Pages 才會自動當作首頁。
- 之後修改內容，只要重新 commit、push，Pages 會在一兩分鐘內自動更新。
