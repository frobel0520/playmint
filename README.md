# Playmint

https://playmint.pages.dev/

打開瀏覽器就能玩的解謎小品入口。每款遊戲都是獨立的 repo 與網站，這裡只放連結，不收納任何遊戲的程式或資料。

| 遊戲 | 網站 | Repo | 語言 |
| --- | --- | --- | --- |
| Tensift（每日分類解謎） | [tensift.pages.dev](https://tensift.pages.dev/) | [tensift](https://github.com/frobel0520/tensift) | English、简体中文、Español |
| 左腳踩右腳：永動機研究所 | [left-foot-right-foot](https://frobel0520.github.io/left-foot-right-foot/) | [left-foot-right-foot](https://github.com/frobel0520/left-foot-right-foot) | 繁體中文 |

兩款遊戲的頁首導覽都有「更多遊戲」連回這裡。

## 共用配色

入口頁的配色、字體與元件樣式沿用 Tensift 的原始主題（米色紙），固定淺色、不跟隨系統深色模式：橫線紙底、Georgia 襯線大標、橘紅大寫小標、1px 墨線框加 24px 圓角與紙膠帶的卡片、橘紅實心主要按鈕。新遊戲接進來時也建議沿用：

| 用途 | 色碼 |
| --- | --- |
| 紙底 `--paper` | `#f3f0e8` |
| 卡片 `--surface` | `#fffcf4` |
| 文字 `--ink` | `#17211d` |
| 重點色 `--accent` | `#df5b3f` |
| 重點文字 `--accent-dark` | `#ad3c26` |

## 部署

單一靜態 `site/index.html`，不需要建置。部署到 Cloudflare Pages 專案 `playmint`：

```bash
npx wrangler pages deploy site --project-name playmint --branch main
```

頁面載入 Harbor 前端腳本（`data-project="playmint"`），維護模式與公告由 Harbor 主控台控制。

## 新增遊戲

在 `site/index.html` 的 `.games` 清單加一個 `<li class="game">`（封面、介紹、節奏、語言、開始玩連結），更新上表，並在該遊戲的導覽加上「更多遊戲」連回 https://playmint.pages.dev/ 。
