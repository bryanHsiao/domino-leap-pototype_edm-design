# DM Studio — 宣傳設計工坊

## 專案概述

一個網頁工具，讓使用者上傳圖片與文字後，即時預覽並匯出專業的宣傳 DM。
適用於課程宣傳、簡章、活動公告等場景。

## 技術方案

- **單一 HTML 檔案**，內嵌 CSS + JS，零框架依賴
- 使用 html2canvas（CDN）實現高解析度 PNG 匯出
- Google Fonts 載入字型

## 設計方向

整合 `nextlevelbuilder/ui-ux-pro-max-skill` 設計系統，以 Notion / Linear 級精緻美感為目標。

- **UI 風格**: Warm neutral 淺色精緻風格（Editorial Refined）
- **色彩系統**: Stone 暖灰中性色調，accent 使用 `#E16A3D`
- **字體配對**:
  - 中文標題：Noto Serif TC（宋體）
  - 西文裝飾：Cormorant Garamond / Fraunces
  - UI 介面：DM Sans + Noto Sans TC
- **UX 遵循**:
  - 觸摸目標 ≥ 44px
  - 過渡動畫 200ms，`prefers-reduced-motion` 支援
  - WCAG AA 對比度
  - 響應式斷點：860px / 1100px

## 功能清單

### 版面配置
- 左側面板：編輯控制區（可折疊段落，Notion 風格）
- 右側面板：即時預覽區 + 範例靈感面板

### 六種 DM 模板

| # | 名稱 | 風格 | 適用場景 |
|---|------|------|----------|
| 1 | 現代簡約 | 白底、粗體 Serif 標題、幾何色塊 | 課程宣傳 |
| 2 | 暗夜霓虹 | 深色漸層 + 霓虹標籤 | 科技活動 |
| 3 | 書院風雅 | 居中排版、Cormorant Garamond、極簡裝飾線 | 藝文展覽 |
| 4 | 商務雙欄 | 左圖右文、專業分欄 | 企業簡章 |
| 5 | 柔彩卡片 | 粉彩背景 + 浮動白卡片 | 社群貼文 |
| 6 | 奢華暗金 | 黑底金線框、高端質感 | VIP / 高階課程 |

### 四種輸出尺寸
- A4 直式（210 × 297 mm）
- 社群正方（1080 × 1080 px）
- 社群橫幅（1200 × 628 px）
- 16:9 寬幅（1920 × 1080 px）

### 編輯功能
- 文字輸入：主標題、副標題、說明文字、CTA 按鈕（即時預覽）
- 圖片來源：本機上傳（拖放 / 點擊）+ URL 載入（支援 Unsplash 等）
- 色彩自訂：主色調 + 背景色選擇器（切換模板自動套用預設色）

### 範例靈感面板
- 位於右側預覽區，不佔編輯空間
- **依模板風格分類**，切換模板時自動更新對應範例
- 每個模板 3 組範例，共 18 組，搭配精選 Unsplash 圖片與專業文案
- 一鍵套用：文字 + 圖片 + 色彩全部填入
- 螢幕 < 1100px 時自動隱藏

### 匯出
- html2canvas 高解析度渲染為 PNG
- 自動以尺寸 + 時間戳命名下載

## 檔案結構

```
index.html          ← 完整應用（單一檔案）
PLAN.md             ← 本計劃檔
.gitignore          ← 排除 .claude/ 等本地設定
.github/workflows/  ← GitHub Pages 自動部署
```

## 部署

- **GitHub**: https://github.com/bryanHsiao/domino-leap-pototype_edm-design
- **GitHub Pages**: https://bryanhsiao.github.io/domino-leap-pototype_edm-design/
- 推送 `main` 分支即自動觸發部署
