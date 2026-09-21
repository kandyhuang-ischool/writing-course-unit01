# 12週寫作覺醒——衝刺篇｜單元01 互動教學原型

國中寫作課程「這一次，我是主角／這一次，我當配角」（國中教育會考寫作測驗預試試題）的互動式教學頁面原型。

網頁版：啟用 GitHub Pages 後，網址為 `https://<你的帳號>.github.io/<repo 名稱>/`

## 內容

單一檔案 `index.html`，不需要安裝任何東西、不需要建置流程，直接用瀏覽器開啟即可。課程分為五個步驟：

1. 找到方向：審題・立意・取材
2. 組織結構——對比結構
3. 遣詞造句——用動詞寫心情
4. 範文賞析（完整範文／對比結構解析／用動詞寫心情，三個頁籤）
5. 完成寫作（左欄自動帶出前三個小練習的作答內容供對照）

## 教學影片

四支影片放在 Google Drive，頁面以 iframe 嵌入。每個影片卡上的 `data-video` 屬性決定要播哪一支：

```html
<!-- 填 Drive 檔案 ID -->
<div class="video-card" data-video="1AbCdEfGhIjKlMnOpQrStUvWxYz">

<!-- 或直接貼 Drive 分享連結，會自動轉成 /preview -->
<div class="video-card" data-video="https://drive.google.com/file/d/1AbCd.../view?usp=sharing">

<!-- 之後換成 Cloudflare Stream、Vimeo 等服務，填完整嵌入網址即可 -->
<div class="video-card" data-video="https://customer-xxx.cloudflarestream.com/xxx/iframe">

<!-- 留空則顯示示意佔位框，不嵌入任何影片 -->
<div class="video-card" data-video="">
```

**影片權限**沿用 Google Drive 本身的設定，不需要把影片設為公開。建議設成「僅限特定人員」或「限學校網域」，並勾選「檢視者不能下載、列印、複製」。觀看者必須以有權限的 Google 帳號登入瀏覽器，否則會看到要求存取的畫面。

網頁本身放在 GitHub Pages 上是公開的，但影片檔始終留在 Drive，權限不受影響。

若所在環境以 CSP 擋掉外部內容（例如 Claude Artifact 的預覽頁），頁面會自動把影片區還原成示意佔位框並顯示說明，不會留下無法解釋的黑框。

## 部署到 GitHub Pages

1. 建立一個新的 repository。
2. 上傳 `index.html`（檔名必須是 `index.html`）與本 `README.md`，commit。
3. Settings → Pages → Source 選 **Deploy from a branch**，Branch 選 `main`、資料夾選 `/ (root)`，Save。
4. 約一分鐘後，Pages 設定頁上方會顯示網站網址。

更新內容時重新上傳同名檔案即可，約一分鐘生效（瀏覽器可能需要強制重新整理）。

## 技術備註

- 單一 HTML 檔，CSS／JS 全部內嵌；插圖以 base64 內嵌；字型使用 Google Fonts（Noto Sans TC、Baloo 2）。
- 版面：寬螢幕（≥680px）採左右分割，教材與練習可同時對照；窄螢幕自動改為單欄，頂部步驟列可左右滑動。
- 步驟切換採實體按鈕（頂部步驟列＋每步驟下方的上一步／下一步），切換後畫面會停在步驟列下方。
- 小練習（一）選定「我是主角／我當配角」後，後續練習與寫作任務會自動帶入該題目。
- 離開某個步驟、或切換到其他瀏覽器分頁時，該步驟的影片會自動停止播放（回到該步驟時播放器重新載入，不保留播放進度）。
- 學生填寫的內容僅保存在瀏覽器記憶體中，重新整理頁面即清空；此為原型，尚未串接後端儲存。
