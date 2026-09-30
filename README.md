# 盈寓 INYU｜包租代管官方網站

> 讓好房有收益，讓居住有品質。

盈寓 INYU 是一間專注於住宅包租與代管的資產管理品牌。本專案是盈寓的品牌形象網站，使用純 HTML / CSS / JavaScript 製作，**不需要安裝任何套件、不需要後端**，可直接部署到 GitHub Pages。

---

## 網站內容

網站為單頁式設計，透過上方選單切換四個頁面：

| 頁面 | 內容 |
| --- | --- |
| 首頁 | 品牌標語、創造雙贏的居住生態圈、傳統自租 vs 盈寓代管對照表、三大核心優勢 |
| 關於我們 | 品牌介紹、「盈寓」名稱涵義、盈寓生態圈、盈寓標準（居住美學） |
| 服務項目 | 四大標準化服務流程（資產評估、空間升級、高效包租、穩健收益）、方案 A 全效包租、方案 B 輕裝代管 |
| 聯絡我們 | 聯絡資訊、官方 LINE QR Code、線上預約表單 |

**特色**

- 響應式設計，手機、平板、電腦都能正常瀏覽
- 單一 `index.html` 檔案，頁面切換不需重新載入
- 圖片皆為 WebP / PNG，載入速度快
- 配色取自品牌 Logo 的綠色系

---

## 專案結構

```
.
├── index.html          # 網站主檔（所有頁面、樣式、程式都在這個檔案）
├── README.md           # 專案說明
└── img/                # 網站使用的圖片
    ├── logo.png
    ├── 首頁圖.webp
    ├── 首頁左圖.webp
    ├── 首頁右圖.webp
    ├── 首頁中圖.webp
    ├── 關於我們logo圖.png
    ├── 關於我們1圖.webp
    ├── 關於我們2圖.webp
    ├── 關於我們3圖.webp
    ├── 關於我們4圖.webp
    ├── 服務項目1.webp
    ├── 服務項目2.webp
    ├── 服務項目3.webp
    ├── 服務項目4.webp
    └── qrcode.webp
```

> `index.html` 以相對路徑 `./img/...` 讀取圖片，**請務必把 `img` 資料夾與 `index.html` 放在同一層**，否則圖片會無法顯示。

---

## 本機預覽

**方法一：直接開啟**

雙擊 `index.html`，用瀏覽器開啟即可。

**方法二：本機伺服器（較接近正式環境）**

```bash
# 在專案資料夾內執行（需安裝 Python 3）
python -m http.server 8000
```

接著開啟瀏覽器，前往 <http://localhost:8000>。

---

## 部署到 GitHub Pages

### 1. 建立 Repository 並上傳檔案

1. 登入 GitHub，點右上角 **+** → **New repository**。
2. 輸入 Repository 名稱（例如 `inyu-website`），選擇 **Public**，建立。
3. 進入新建立的 Repository，點 **Add file** → **Upload files**。
4. 把 `index.html`、`README.md` 和整個 `img` 資料夾拖曳進去。
5. 往下捲動，按 **Commit changes**。

> 若你習慣使用 Git 指令：
>
> ```bash
> git init
> git add .
> git commit -m "first commit"
> git branch -M main
> git remote add origin https://github.com/<你的帳號>/<Repository 名稱>.git
> git push -u origin main
> ```

### 2. 開啟 GitHub Pages

1. 進入 Repository，點上方 **Settings**。
2. 左側選單點 **Pages**。
3. 在 **Build and deployment** 區塊：
   - **Source** 選擇 **Deploy from a branch**
   - **Branch** 選擇 **main**，資料夾選擇 **/ (root)**
4. 按 **Save**。

### 3. 等待部署完成

等待約 1 到 3 分鐘，重新整理 Pages 設定頁面，上方會出現網站網址：

```
https://<你的帳號>.github.io/<Repository 名稱>/
```

例如帳號為 `inyu`、Repository 為 `inyu-website`，網址就是 `https://inyu.github.io/inyu-website/`。

> 如果 Repository 名稱取為 `<你的帳號>.github.io`，網址會直接是 `https://<你的帳號>.github.io/`。

### 4. 更新網站

之後修改 `index.html` 或圖片，重新上傳（或 `git push`）後，GitHub Pages 會自動重新部署，約 1 到 2 分鐘後生效。

---

## 使用自訂網域（選用）

若要使用 `www.inyu.com.tw`：

1. 在 **Settings → Pages → Custom domain** 填入網域並儲存。
2. 到網域註冊商的 DNS 設定，新增一筆 `CNAME` 紀錄，將 `www` 指向 `<你的帳號>.github.io`。
3. 等 DNS 生效後，勾選 **Enforce HTTPS**。

詳細步驟請參考 [GitHub Pages 官方文件](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)。

---

## 常見問題

**Q：網頁打開了，但圖片沒有顯示？**
GitHub Pages 的檔名**區分大小寫**。請確認 `img` 資料夾內的檔名，與 `index.html` 中寫的完全一致（包含副檔名 `.webp` / `.png`）。另外確認 `img` 資料夾有一起上傳。

**Q：設定好 Pages，打開卻是 404？**
請確認 `index.html` 放在 Repository 的最外層（不是在子資料夾內），且檔名為小寫的 `index.html`。剛設定完也可能需要再等幾分鐘。

**Q：聯絡表單送出後，我收不到資料？**
目前的預約表單只有前端畫面，送出後僅顯示「已收到」訊息，**不會真的寄出資料**（GitHub Pages 是靜態網站，沒有後端）。若要接收表單內容，可以：
- 串接免費表單服務，例如 [Formspree](https://formspree.io/)、[Google 表單](https://www.google.com/forms/about/)
- 或將表單改成導向官方 LINE、電話、Email

**Q：圖片檔名是中文，會有問題嗎？**
GitHub Pages 可以正常讀取中文檔名。若之後發現部分環境出現問題，建議改成英文檔名（例如 `home-hero.webp`），並同步修改 `index.html` 中的路徑。

---

## 修改指南

所有內容都在 `index.html` 中，用文字編輯器（如 VS Code）即可修改。

- **聯絡資訊**：搜尋 `0978-939153`、`contact@inyu.com.tw`，共有「聯絡我們」頁與頁尾兩處。
- **網站配色**：檔案開頭 `<style>` 內的 `:root { ... }` 區塊，可統一調整顏色。
- **替換圖片**：將新圖片放進 `img` 資料夾，檔名保持一致即可直接覆蓋。
- **頁面文字**：搜尋想修改的文字，直接取代。

---

## 聯絡盈寓

- 電話：0978-939153
- 網站：<https://www.inyu.com.tw>
- Email：contact@inyu.com.tw
- 官方 LINE：請見網站「聯絡我們」頁面的 QR Code

---

## 版權聲明

© 2026 盈寓 INYU. All rights reserved.
本專案之品牌名稱、Logo、圖片與文案均屬盈寓所有，未經授權請勿轉載或作商業使用。
