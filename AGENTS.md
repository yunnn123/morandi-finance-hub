# AGENTS.md - 大學生莫蘭迪理財知識庫與記帳系統 (Morandi Finance Wiki & Budgeting Hub)

本文件為 AI 開發助手（Coding Agents）的最高指導原則。當使用者要求「新增一篇理財筆記頁面 (`note-XX.html`)」、「擴充知識庫目錄」或「維護記帳工具」時，請嚴格遵守本文件定義之架構、視覺規範與業務邏輯。

---

## 1. 專案目的與定位 (Project Purpose)
本專案結合「結構化理財知識庫（Content Wiki）」與「互動式記帳與預算管理系統（Web App）」，旨在幫助大學生建立正確的預算隔離觀念，並能直接透過站內工具落實日常記帳。
- **無框架靜態架構**：全站採用原生 HTML5、CSS3 與 Vanilla JavaScript，零外部編譯依賴，可直接部署於 GitHub Pages。
- **跨頁面狀態連動**：知識庫首頁與筆記頁面皆可透過唯讀方式讀取瀏覽器 `LocalStorage` 中的帳務狀態，並引導使用者前往 `tool-budget.html` 進行實戰記帳。

---

## 2. 整體視覺風格：莫蘭迪設計系統 (Morandi Design System)
AI 生成任何新頁面時，**嚴禁**使用高飽和度原生色，必須 100% 繼承以下 `:root` CSS 變數與圓角卡片規範：

```css
:root {
  --bg-primary: #F4F1EA;       /* 燕麥奶白：全站背景色 */
  --bg-card: #FFFFFF;          /* 純白：卡片主體背景 */
  --bg-subtle: #EAE6DF;        /* 淺暖灰：次要區塊、膠囊標籤底色 */
  --morandi-green: #8FA395;    /* 莫蘭迪灰綠：主色調、正向指標、儲蓄金庫 */
  --morandi-blue: #8C9DAE;     /* 霧霾藍：悠遊卡模組、知識步驟強調色 */
  --morandi-rose: #C49A9A;     /* 乾燥玫瑰粉：理財痛點提示框、超支警示 */
  --morandi-ochre: #C9B093;    /* 暖駝色：固定支出、精選標籤強調色 */
  --text-main: #4A4845;        /* 深炭灰：主要內文（禁止使用 #000000 死黑） */
  --text-muted: #85817C;       /* 淺灰褐：輔助說明、閱讀時間 */
  --radius-lg: 20px;           /* 大卡片圓角 */
  --radius-md: 12px;           /* 按鈕與內嵌提示框圓角 */
  --shadow-soft: 0 6px 20px rgba(74, 72, 69, 0.06); /* 柔和擴散陰影 */
}
