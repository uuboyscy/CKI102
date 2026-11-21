# CKI102

緯育 CKI102 課程資料與授課筆記。

## Gemini Notebook

[CKI102 PyETL 課程逐字稿與資料](https://notebook.google.com/notebook/8210d04a-451e-4b3c-84a9-72976d80302c)

課堂逐字稿與其他上課資料集中於此筆記本，目前設為公開，學生可透過連結查看。逐字稿保留原始語音辨識內容，可能包含錯字或辨識雜訊。

## 課程筆記

### 2026-11-21｜PyETL：爬蟲入門

來源：`tibame cki102 transcript-2026-11-21 01.md`，錄製開始於 09:00:25，最後時間戳為 00:52:49。

- 課程開場介紹資料工程、資料分析、資料科學與 AI 相關工作的不同面向，以及 AI 時代需求拆解、驗證與資料安全的重要性。職涯觀察為講師課堂觀點，不代表所有公司或職位的通則。
- 爬蟲用於自動化擷取網頁資料；課堂介紹瀏覽器與伺服器的請求／回應流程、HTTP GET 與 POST，以及 HTML、JSON 和 XML。
- 課堂介紹 `requests` 發送請求、BeautifulSoup 解析 HTML、Selenium 操作瀏覽器，以及 Pandas 整理表格資料。
- 靜態與動態網頁的擷取方式不同：動態資料可先檢查合法可用的資料介面，必要時再使用瀏覽器自動化。
- 範例構想：整理求職網站職缺資訊，將 Python、AI 等技能關鍵字轉為可分析的欄位。

#### 10:02:31｜HTML 結構與開發者工具

來源：`tibame cki102 transcript-2026-11-21 02.md`；最後時間戳為 00:52:52。原始逐字稿含語音辨識雜訊。

- 以 PTT 頁面觀察 HTML：標籤可巢狀，`<a>` 的 `href` 記錄連結目的地，`<div>` 常用來組織區塊。
- 使用瀏覽器開發者工具的 Elements 與元素選取功能，從畫面找到對應結構，再觀察重複項目的共同標籤與 `class`，定位文章標題及連結。
- `id` 用來識別元素，依 HTML 規範在文件內應唯一；`class` 可以重複。CSS selector 使用 `#` 表示 ID、`.` 表示 class，同一元素可以有多個 class。
- 課堂示範 Copy Selector 與 XPath。兩者都能使用屬性或結構定位；不論選哪一種，都需要測試並留意頁面變動造成的失效。
- 認識 `<head>` 與 `<body>`、圖片 `<img src="…">`、表格 `<table>`、`<thead>`、`<tbody>`、`<tr>` 和 `<th>`。
- 用 VS Code 開啟單一練習資料夾；實際執行程式時仍應確認終端機的工作目錄與 Python 環境設定。

#### 11:02:13｜HTML 表格、表單與 AI 協作

來源：`tibame cki102 transcript-2026-11-21 03.md`；主要逐字稿最後時間戳為 00:57:44，附錄會議筆記另含 00:40:08 時間戳。原始逐字稿保留語音辨識雜訊。

- 在 VS Code 建立 `index.html`，使用 AI 協助產生基本 HTML 結構，再逐步加入表格與 CSS。課堂範例見 [`html_demo/index.html`](html_demo/index.html)。
- 表單用 `<form>`、`<input>` 與按鈕收集資料；`action` 指定送出目標，`method` 指定方法。通常具備 `name` 的表單欄位才會以名稱和值送出；後端如何接收留待 Flask 課程。
- HTML 表單使用 GET 時，欄位通常會放進 URL 的 query string；POST 通常放在 request body。POST 並不自動加密，敏感資料仍需 HTTPS 與適當保護。
- `label for` 可關聯對應的 input，不僅方便點擊，也有助輔助科技辨識；`placeholder` 提示文字不能取代標籤。
- 透過手動貼上、修改和檢視 HTML，理解 coding agent 可協助產生、局部修改與驗證檔案；實際結果仍需人工檢查。
- Git 可保留版本、協助人與 AI 協作；多人或多 Agent 修改同一 repo 時，先確認工作樹並同步最新版本。
- 下個主題預告：透過開發者工具觀察 HTTP 請求、回應、headers 與 cookies／session。HTTP 本身無狀態；session 可以透過 cookie 等機制關聯請求。

> 安全補充：VS Code Workspace Trust 可限制部分工作區功能，但不是完整沙箱；檢查不明專案前應先避免執行程式與啟用不受信任的擴充功能。AI 掃描與雲端編輯器都不能保證安全，也可能涉及資料外傳與隱私風險。
>
> 使用爬蟲時應確認網站授權、服務條款、隱私與合理請求頻率；AI 產生的程式與正規表達式仍需測試驗證。
