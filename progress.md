# 開發歷程

> 人機協作紀錄｜2026-05-16 ~ 2026-05-17

## 起點

正在學習 CSS Flexbox，老師用「製作一款 Flex 遊戲」的方式讓學生練習屬性，而不是死背語法。靈感來自皮克敏 Bloom 的花苗孵化機制——「CSS 打對了才能解鎖角色彈跳」，把正確答案和遊戲回饋直接連結。

## 開發過程

**V1（基礎架構）**：5 關 HTML 骨架、`getComputedStyle()` 即時驗證、提示系統。

**V2（UX 大幅改版）**：從上下捲動改為左右雙欄 Grid；從 Pikipedia 找到各顏色真實花苗 PNG；移除「檢查」按鈕，改為 `input` 事件即時偵測自動過關；加彩帶動畫。

**V3（皮克敏 Bloom 風格）**：每株花苗依序搖晃彈出一隻皮克敏，蒐集在底部固定 Party Bar；全部 UI 參考截圖改版成 Bloom 風格（白色大圓角卡片、暗色編輯器）；皮克敏從花苗沿拋物線弧度飛到 Party Bar（`getBoundingClientRect()` + `sin(t·π)` 弧線）。

**Base64 嵌入**：發現其他使用者圖片破圖（Fandom CDN 擋 Hotlink），改從 `pikmin.wiki.gallery` 下載全部 10 張圖片轉 Base64 嵌入 HTML。

**手機版**：用 `display:contents` 讓 `.left` / `.right` 子元素直接排入 flex 容器，CSS `order` 重排順序；Party Bar 改 `position:sticky`；Pikmin 飛行時自動 `scrollIntoView`。

## Bug 修復

- 紫色皮克敏圖片下載到 HTML 錯誤頁面（`<!DOCTYPE html>`），重新從 Pikmin Bloom 條目取得正確 URL 修正
- 第 4 關直排花苗超出花苗田：花苗從 80px 縮為 68px，手機 Stage 高度加大至 280px
- 新增虛線 Ghost 目標層，答對後淡出；`position:relative` 確保花苗圖層在虛線上方
- 第 5 關桌機 Ghost 與花苗重疊：`#c5` 加 `max-width:340px` 讓種子真正溢出，Ghost 同步限寬顯示換行預覽
- Party Bar 超過 20 隻皮克敏破版：動態縮放（52px → 28px）
- 輸入框即時色彩回饋：輸入中橘色框、答對綠色框

## 結果

- 單一 `index.html`，可直接用瀏覽器開啟
- 5 關互動練習 + 20 隻皮克敏蒐集動畫
- 手機、桌機皆可遊玩
- 公開於 GitHub Pages：https://chenkuanhua.github.io/pikmin-flexbox-game/
