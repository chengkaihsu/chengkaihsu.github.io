# 個人網頁 Review 與改版說明

網站：https://chengkaihsu.github.io ／ 日期：2026-08-21

## 一、原版的主要問題

**內容**
1. Publications 區只有三段籠統描述，沒有任何實際論文、期刊、年份或連結——對學術網站來說這是最關鍵的缺口。
2. Research Agenda 與 Current Research Projects 兩區內容幾乎一字不差地重複（四個主題各出現兩次）。
3. 「CV Coming Soon」按鈕指向 `#`，點了沒反應。
4. 頭像是 "KH" 文字佔位符。
5. 聯絡信箱仍是 Berkeley，但職稱已是 ASU。（已改為 `kai.h@asu.edu`）
6. 缺少新進教職通常會有的區塊：News／招生資訊。

**技術 / SEO**
7. 沒有 `<meta name="description">`、Open Graph、canonical、favicon、結構化資料——分享到 LinkedIn/Slack 時不會有預覽卡，Google 也較難正確建立知識面板。
8. CSS 指定 `Inter` 字型但從未載入，實際顯示的是系統字型。
9. 手機版導覽列只是把 6 個連結折行堆疊，沒有漢堡選單；`h1` 在小螢幕字距 -0.085em 擠在一起。
10. 外部連結 `target="_blank"` 沒有 `rel="noopener"`。
11. 沒有 dark mode、沒有 skip-link、`reduced-motion` 等無障礙細節。

## 二、這次做了什麼

- **重新設計**：襯線標題（Source Serif 4）+ Inter 內文，暖米色背景、深青色主色、沙漠橘作強調色（呼應 Arizona）；支援深色模式；桌機/平板/手機三段式 RWD，含漢堡選單。
- **結構整併**：About → Research themes（4 張卡，合併原本重複的兩區）→ Publications → News → Prospective Students → Contact。
- **Publications**：從 ResearchGate / 出版社頁面整理出 **15 篇期刊論文**（2020–2026），每篇附 DOI 或出版社連結、作者、期刊；加上「主題篩選」按鈕（Heat & road safety / Air pollution / Gig-economy riders / Policy & trends）；Nature Cities 那篇標為 Featured。
- **News** 時間軸：5 則（2025-09 至 2026-08）。
- **Prospective Students**：招生說明、歡迎背景、申請管道、來信格式（mailto 自動帶主旨「Prospective student」）。
- **SEO / 技術**：description、OG、canonical、JSON-LD Person、SVG favicon、Google Fonts 正確載入、`rel="noopener"`、skip-link、`scroll-padding-top`、`prefers-reduced-motion`。
- 頭像改為 `<img src="assets/portrait.jpg">`，檔案不存在時自動退回 "KH" 圓形。
- CV 按鈕指向 `assets/Hsu_CV.pdf`。

## 三、請你接手確認的事項（我無法替你決定）

1. **放入照片**：把方形照片存成 `assets/portrait.jpg`（建議 ≥ 800×800）。
2. **放入 CV**：存成 `assets/Hsu_CV.pdf`；若暫時沒有，請先把 hero 區的 CV 按鈕刪掉，不要留死連結。
3. **Email**：已全站改為 `kai.h@asu.edu`。
4. **作者名單**：ResearchGate 對部分論文只顯示你一人，以下幾篇我無法確認完整共同作者，請核對：
   - Unpacking temporal trends in U.S. road injury mortality… (*Cities*, 2026)
   - Micro-mobility users' exposure to PM2.5… (*JCMR*, 2025)
   - Association of nighttime heat with road traffic mortality (*SCS*, 2025)
   - Burning gig, rewarding risk (*AAP*, 2024)
   - Heat-induced risks of road crashes among older motorcyclists (*JTH*, 2024)
   - Reconsidering seasonality… (*TBS*, 2024)
   - Air pollution exposure… central London (*JTH*, 2022) — 這篇我找不到線上連結，目前只列標題。
5. **年份**：我依線上發表日期標記；若你習慣以卷期年份為準（例如 SCS 那篇可能是 2024 vol. / 2025 issue），請自行調整。
6. **招生文字**：Prospective Students 區現在直接導向 SGSUP 的 Faculty Recruiting Doctoral Students 頁面，請記得請學院把你加進該頁名單。
7. **OG 圖片**：`og:image` 指向 `assets/og-image.png`，請放一張 1200×630 的圖（可以就是你的照片加名字），否則分享預覽不會有圖。
8. **News 內容**：請補上我不知道的事項（演講、獲獎、經費）。

## 四、後續可選的改進

- 把 Publications 改由 `publications.json` 或 Jekyll `_data` 產生，之後只要改資料不用改 HTML。
- 每篇論文加一行「一句話重點」或 Altmetric / 媒體報導連結。
- 加入 Teaching 區塊（開課後）。
- 用 GitHub Actions 定期從 ORCID 同步論文清單。
