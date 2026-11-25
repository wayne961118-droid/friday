# Daymark｜個人行程與任務

Daymark 是以繁體中文介面的行程與待辦管理網站，可部署至 GitHub Pages。

## 功能

- 建立、編輯、完成及整理待辦事項
- 建立長期目標並查看進度
- 顯示今日到期與逾期提醒
- 使用 Google 帳戶登入 Firebase Authentication
- 透過 Firestore 同步登入者自己的待辦與目標
- 使用 Firebase AI Logic 與 Gemini 提供 AI 小助手

## 專案檔案

- `index.html`：網站介面與功能
- `firebase-config.js`：Firebase Web App 公開設定
- `firestore.rules`：Firestore 使用者資料存取規則
- `firebase.json`、`.firebaserc`：Firebase 專案設定

Firebase Web App 設定會出現在瀏覽器程式中，不要放入服務帳戶私鑰、密碼、存取權杖或其他秘密資料。AI 小助手會把問題與最多 30 筆待辦的標題、期限和完成狀態傳給 Gemini；不要輸入機密內容。

## GitHub Pages 與 Firebase

GitHub Pages 從 `main` 分支根目錄發布。Firebase Authentication 已授權 `wayne961118-droid.github.io` 登入；Firebase App Check 已為 Daymark Web 註冊 Fraud Defense（reCAPTCHA Enterprise），site key 限定此網域並設定在 `firebase-config.js`。本機除錯 token 只供本機測試，不要放入公開程式碼。Firestore 規則限制每位登入者只能讀寫自己的資料。

部署後可用 Google 帳戶登入，確認設定頁顯示雲端同步已開啟。AI 測試時請使用不含個人或機密資料的問題。
