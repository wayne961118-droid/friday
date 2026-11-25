# Daymark｜個人行程與任務

Daymark 是以繁體中文介面的個人行程與待辦管理網站，使用純 HTML、CSS 與 JavaScript，可部署至 GitHub Pages。

## 功能

- 建立、編輯、完成及整理待辦事項
- 建立長期目標並查看完成進度
- 顯示今日到期與逾期提醒
- 使用 Google 帳戶登入 Firebase Authentication
- 透過 Firestore 同步登入者自己的待辦與目標
- 使用 Firebase AI Logic 與 Gemini 提供 AI 小幫手

## 檔案

- `index.html`：網站介面與功能
- `firebase-config.js`：Firebase Web App 公開設定
- `firestore.rules`：Firestore 使用者資料存取規則
- `firebase.json`、`.firebaserc`：Firebase 專案設定

Firebase Web App 設定會出現在瀏覽器程式中，不應放入服務帳戶私鑰、Channel Secret、密碼、存取權杖或其他秘密資料。AI 小幫手會在送出前說明會傳送的待辦欄位與資料使用情況。

## GitHub Pages 與 Firebase

本專案使用根目錄中的 `index.html`，可由 GitHub Pages 從 `main` 分支的根目錄發布。發布後，需在 Firebase Authentication 的授權網域加入 GitHub Pages 網域；在 Firebase App Check 為正式網站設定 reCAPTCHA Enterprise site key，並將 site key 設定到 `firebase-config.js` 的 `appCheckSiteKey`。本機除錯 token 只供本機測試，不要寫入公開程式碼。

Firestore 規則限制每位登入者只能讀寫自己的資料。部署或修改規則後，應確認未登入時無法存取雲端資料，登入後可以同步與登出。
