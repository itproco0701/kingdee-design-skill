# KDesign 全域規則與 Design Token 參考

KDesign 的全域規則涵蓋兩大面向：

1. **設計基礎**：色彩、陰影、字體、圖示、動效、插畫、文案、柵格。
2. **設計模式**：消息與回饋、元素狀態、內容截取、國際化。

在前端實作中，KDesign 透過兩層 CSS 變數管理樣式：

- **全域 Token (`--kd-g-*`)**：定義系統級品牌色、語意色、文字色、背景色、邊框、字級與圓角。
- **元件 Token (`--kd-c-<component>-*`)**：各元件內部樣式變數，預設映射到全域 Token，支援細粒度主題客製化。

## 核心色彩 Token

| 類別 | 全域 Token | 預設值 | 用途說明 |
| --- | --- | --- | --- |
| 品牌主題色 | `--kd-g-color-theme` | `#5582f3` | 主要按鈕、選中狀態、品牌強調 |
| 主題淺色變體 | `--kd-g-color-theme-3` | `rgb(227, 238, 255)` | 選中背景、輕量高亮 |
| 進行中狀態 | `--kd-g-color-ongoing` | `#276ff5` | 進行中徽標、處理中狀態指示 |
| 文字連結色 | `--kd-g-color-text-link` | `#0e5fd8` | 超連結、互動操作文字、啟用邊框 |
| 成功狀態 | `--kd-g-color-success` | `#1ba854` | 成功提示、通過狀態 |
| 警告狀態 | `--kd-g-color-warning` | `#ff991c` | 警告提示、待注意狀態 |
| 錯誤狀態 | `--kd-g-color-error` | `#fb2323` | 錯誤校驗、異常與危險操作 |
| 主要文字 | `--kd-g-color-text-primary` | `#212121` | 標題、主要正文內容 |
| 輔助/次要文字 | `--kd-g-color-text-third` | `#999` | 說明文字、輔助資訊、佔位提示 |
| 基礎背景 | `--kd-g-color-background` | `#fff` | 卡片、彈層與內容區底色 |
| 容器背景 | `--kd-g-color-background-contain` | (淺灰容器底色) | 上傳區、容器底色 |
| 強化邊框 | `--kd-g-color-border-strong` | `#d9d9d9` | 輸入框、下拉選單、分割線邊框 |

## 字體與圓角 Token

| 類別 | 全域 Token | 預設值 | 用途說明 |
| --- | --- | --- | --- |
| 標準正文 | `--kd-g-font-size-middle` | `14px` | 企業系統標準表單、正文與按鈕文字 |
| 輔助小字 | `--kd-g-font-size-small` | `12px` | 提示文字 (Tooltip)、徽標、輔助說明 |
| 圓角基準 | `--kd-g-radius-border` | (元件預設圓角) | 提示框、輸入框與基礎容器圓角 |

## 主題客製化方式

在 CSS 中覆寫 `:root` 或特定容器下的 `--kd-g-*` 變數，即可全域切換品牌色與基礎風格；若只需調整單一元件 (例如 Tooltip 或 Badge)，則覆寫對應的 `--kd-c-*` 變數。

```css
:root {
  --kd-g-color-theme: #5582f3;
  --kd-g-color-text-primary: #212121;
  --kd-g-color-border-strong: #d9d9d9;
}
```
