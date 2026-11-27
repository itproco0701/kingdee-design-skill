# Kingdee Design (KDesign) Agent Skill

將金蝶企業級產品設計系統 **KDesign** (https://www.kingdee.design/) 整理為標準 **Agent Skill**，讓 AI Agent 在進行企業級中後台 UI/UX 設計、頁面規劃、視覺規範審查、資料視覺化設計與 React 前端開發時，能夠直接套用 KDesign 的設計原則、Design Token、元件規範與典型頁面模板。

## 專案結構

```text
.
├── README.md
└── skills/
    └── kingdee-design/
        ├── SKILL.md                          # 主技能定義與工作流指令
        └── references/
            ├── design-tokens.md              # 全域規則與 CSS Design Token (--kd-g-*)
            ├── components-and-pages.md       # PC/行動端元件與典型頁面、視覺化規範
            └── dev-resources.md              # 官方套件 (@kdcloudjs/kdesign 等) 與快速上手
```

## 安裝與使用方式

### 方式一：透過 Skills CLI 安裝 (推薦)

若你的 Agent 支援 `skills` CLI，將此儲存庫發佈到 GitHub 後，其他人可直接執行：

```bash
npx skills add <你的GitHub帳號>/<儲存庫名稱> --skill kingdee-design
```

### 方式二：手動複製到各 Agent 技能目錄

將 `skills/kingdee-design/` 資料夾複製到對應工具的 skills 目錄：

- **Claude Code**：`.claude/skills/kingdee-design/` (專案) 或 `~/.claude/skills/kingdee-design/` (全域)
- **Cursor**：`.cursor/skills/kingdee-design/` (專案) 或 `~/.cursor/skills/kingdee-design/` (全域)
- **Gemini CLI**：`.gemini/skills/kingdee-design/` (專案) 或 `~/.gemini/skills/kingdee-design/` (全域)
- **Codex**：`.codex/skills/kingdee-design/` (專案) 或 `~/.codex/skills/kingdee-design/` (全域)

### 方式三：一般聊天型 Agent (Custom GPTs / Gems / Dify / Coze)

1. 將 `skills/kingdee-design/SKILL.md` 的正文貼入系統提示詞 (System Prompt)。
2. 將 `skills/kingdee-design/references/` 底下的三個 `.md` 檔案上傳至知識庫。

## 測試提示詞範例

> 「請用 KDesign 規範幫我設計一個採購訂單表單頁，並提供 `@kdcloudjs/kdesign` 的 React 程式碼骨架與主題 CSS 變數設定。」

## 參考來源

- [KDesign 金蝶設計系統官網](https://www.kingdee.design/)
- [KDesign React 元件庫](https://react.kingdee.design/)
- [KDesign Pro 中後台解決方案](https://pro.kingdee.design/)
- [KDesign Charts 可視化元件庫](https://github.com/kingdee/kd-charts)
