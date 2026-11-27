---
name: kingdee-design
description: 使用金蝶企業級產品設計系統 KDesign (https://www.kingdee.design/) 進行產品 UI/UX 設計、頁面規劃、視覺規範審查、資料視覺化設計與 React 前端開發。當使用者提及 KDesign、金蝶設計系統、kingdee.design、企業級中後台介面設計、ERP/SaaS 典型頁面 (工作台、列表頁、表單頁、詳情頁、報表頁、異常頁)、@kdcloudjs/kdesign 元件庫或金蝶視覺化圖表規範時使用。
---

# Kingdee Design (KDesign)

這套技能將金蝶企業級產品設計系統 KDesign (https://www.kingdee.design/) 的核心理念、全域設計規則、跨端元件規範、典型頁面模板與前端開發資源結構化，讓 Agent 能在設計評審、原型規劃、資料視覺化與 React 開發任務中輸出一致且符合企業級標準的成果。

## When to Use

- 規劃或設計企業級中後台 (PC 端)、行動辦公 (Mobile 端) 或資料視覺化大屏的介面結構與互動流程。
- 依據 KDesign 視覺規範產出 CSS/Less 樣式、設計 Token 或主題客製化配置。
- 使用 `@kdcloudjs/kdesign` (KDesign React)、KDesign Pro 或 KDesign Charts 撰寫前端程式碼。
- 審查現有企業應用頁面是否符合 KDesign 一致性、可用性與視覺層級規範。

## Steps

### 1. 確認目標平台與使用場景

先判斷使用者的需求屬於哪一個終端與任務類型，避免混用跨端規範：

- **PC 端中後台**：側重高資訊密度、多欄位表單、複雜表格操作、工作台與報表分析。
- **行動端 (Mobile)**：側重單手操作效率、輕量表單錄入、待辦審批與關鍵指標概覽。
- **資料視覺化 (Charts / 大屏)**：側重「可視有效」，降低認知成本，以圖形克制、清晰地表達業務數據。
- **前端工程實作**：優先採用官方 React 元件庫 `@kdcloudjs/kdesign` 與對應圖示庫、圖表皮膚，而非從零手刻基礎元件。

### 2. 套用 KDesign 核心設計原則與原子設計

在規劃任何頁面或元件組合時，以 KDesign 四大設計原則作為決策依據：

- **角色化**：依業務角色 (如財務、主管、營運、一線人員) 組織工作台與操作入口，突出高頻任務與關鍵指標。
- **一致化**：跨模組統一色彩語意、字級層級、元素狀態與消息回饋模式，降低學習成本。
- **高效化**：縮短核心業務路徑，提供清晰的頁頭工具欄、快捷操作與可複用表單/表格模式。
- **愉悦化**：透過克制的陰影、動效、插畫與清晰的引導文案，提升企業級系統的舒適度。

結構拆分遵循 **原子設計 (Atomic Design)** 五層模型：原子 (色彩/字體/圖示/按鈕) -> 分子 (搜尋欄/表單項) -> 有機體 (導覽列/工具欄/資料表格) -> 模板 (典型頁面骨架) -> 介面 (實際業務頁面)。

### 3. 套用全域規則與 Design Token

撰寫樣式、設計系統規範或自訂主題時，一律優先使用 KDesign 全域 CSS 變數 (`--kd-g-*`) 與元件變數 (`--kd-c-*`)，不要硬編碼隨意色值。完整 Token 清單與語意色規則請查閱 `references/design-tokens.md`。

關鍵基準值摘要：

- 主題色 (`--kd-g-color-theme`)：`#5582f3`；進行中/強調藍 (`--kd-g-color-ongoing`)：`#276ff5`；連結色 (`--kd-g-color-text-link`)：`#0e5fd8`。
- 語意狀態色：成功 `#1ba854` (`--kd-g-color-success`)、警告 `#ff991c` (`--kd-g-color-warning`)、錯誤 `#fb2323` (`--kd-g-color-error`)。
- 文字與邊框：主文字 `#212121` (`--kd-g-color-text-primary`)、輔助文字 `#999` (`--kd-g-color-text-third`)、邊框 `#d9d9d9` (`--kd-g-color-border-strong`)。
- 字級基準：常用正文 `14px` (`--kd-g-font-size-middle`)、輔助/標籤字 `12px` (`--kd-g-font-size-small`)。

### 4. 選用典型頁面模板與元件

依業務場景挑選對應的 KDesign 典型頁面與標準元件，詳細清單與佈局結構請查閱 `references/components-and-pages.md`：

- **PC 典型頁面**：工作台、列表頁、表單頁 (含頂部操作工具欄與分區表單錄入區)、詳情頁、報表頁、異常頁。
- **行動端典型頁面**：業務首頁 (聚合工作任務與關鍵指標)、表單頁與各類行動端基礎/導覽/表單元件。
- **資料視覺化**：依數據維度選擇合適圖表 (例如基礎儀表盤維度建議最多 4 個)，確保圖表克制不繁瑣，免去使用者解碼抽象數據的負擔。

### 5. 輸出工程程式碼或設計規格

當使用者需要實作前端程式碼時，請查閱 `references/dev-resources.md` 並遵循以下做法：

- React 專案安裝 `@kdcloudjs/kdesign` 並引入 `@kdcloudjs/kdesign/dist/kdesign.css`。
- 全域語言、方向或主題配置使用 `ConfigProvider`。
- 圖示優先使用 `@kdcloudjs/kdesign-icons` (React) 或 `@kdcloudjs/kdesign-icons-vue` (Vue)。
- 中後台整站腳手架參考 KDesign Pro (基於 KDesign + UmiJS)；資料視覺化圖表參考 KDesign Charts (基於 ECharts 的 KDesign 主題皮膚)。

## Gotchas

- **避免硬編碼樣式覆寫**：直接寫死色值或像素會破壞 KDesign 的主題客製化能力，務必透過 `--kd-g-*` 或 `--kd-c-*` Design Token 覆寫樣式。
- **區分語意色用途**：`#5582f3` 為預設品牌主題色，`#276ff5` 用於進行中狀態，`#0e5fd8` 用於文字連結；切勿混用錯誤紅 (`#fb2323`) 與警告橘 (`#ff991c`)。
- **不超過視覺化維度上限**：在設計儀表盤或大屏圖表時，保持「可視有效」原則，避免在同一圖表堆疊過多維度 (例如基礎儀表盤不超過 4 個維度)。
- **查閱最新元件 API**：若需要特定元件的精細 Props 或最新更新日誌，請引導或檢索官方文件 (`https://react.kingdee.design/` 與 `https://www.kingdee.design/`)，勿憑空編造未確認的 Props 名稱。
