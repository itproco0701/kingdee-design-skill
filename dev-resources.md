# KDesign 開發與設計資源指南

## 官方網站與文件入口

- **KDesign 官網 (總入口)**：https://www.kingdee.design/
- **全域規則介紹**：https://www.kingdee.design/rule/guide/introduce
- **KDesign React 元件庫文件**：https://react.kingdee.design/
- **KDesign Pro 中後台解決方案**：https://pro.kingdee.design/
- **KDesign 視覺化規範**：https://www.kingdee.design/charts/guide
- **行動端元件概覽**：https://kingdee.design/mobile/components

## 前端套件與開源儲存庫

| 套件 / 專案 | 用途 | 來源 |
| --- | --- | --- |
| `@kdcloudjs/kdesign` | PC 端企業級 React + TypeScript UI 元件庫 (相容現代瀏覽器與 IE11) | https://github.com/kingdee/kdesign |
| `KDesign Pro` | 基於 KDesign 與 UmiJS 的開箱即用中後台腳手架與典型頁面模板 | https://github.com/kingdee/kdesign-pro |
| `KDesign Charts` (`kd-charts`) | 基於 ECharts 的 KDesign 視覺化圖表皮膚與元件庫 | https://github.com/kingdee/kd-charts |
| `@kdcloudjs/kdesign-icons` | React SVG 圖示庫 | https://github.com/kingdee/kdesign-icons |
| `@kdcloudjs/kdesign-icons-vue` | Vue SVG 圖示庫 | https://github.com/kingdee/kdesign-icons |

## KDesign React 快速上手

### 安裝

```bash
npm install @kdcloudjs/kdesign --save
# 或
yarn add @kdcloudjs/kdesign
```

### 基本引入範例

```tsx
import React from 'react'
import { Button, ConfigProvider } from '@kdcloudjs/kdesign'
import '@kdcloudjs/kdesign/dist/kdesign.css'

export default function App() {
  return (
    <ConfigProvider>
      <Button type="primary">KDesign 按鈕</Button>
    </ConfigProvider>
  )
}
```

### 瀏覽器直接引入 (UMD)

若無打包工具，可從專案 `dist` 目錄或 UNPKG 引入 `kdesign.min.js` 與 `kdesign.min.css`，並透過全域變數 `kdesign` 使用 (例如 `kdesign.Button`)。

## 設計資源

KDesign 官網亦提供設計師與產品經理可直接下載的資源：

- **PC 端**：Sketch 元件庫、Axure 元件庫。
- **行動端**：Sketch 元件庫、Axure 元件庫。
- **通用資源**：圖示資源、插畫資源、視覺標註與低程式碼課程。
