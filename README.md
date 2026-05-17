# 🌱 皮克敏 Flexbox 闖關遊戲

以任天堂手遊「皮克敏 Bloom」為主題的 CSS Flexbox 互動教學遊戲。輸入正確的 CSS 屬性，讓花苗正確排列，就能看到皮克敏從花苗中彈跳出來！

**🔗 線上遊玩：[https://chenkuanhua.github.io/pikmin-flexbox-game/](https://chenkuanhua.github.io/pikmin-flexbox-game/)**

---

## 🎮 遊戲說明

共 5 關，每關練習一個核心 Flexbox 屬性：

| 關卡 | 屬性 | 皮克敏 | 情境 |
|:--|:--|:--|:--|
| 第 1 關 | `display: flex` | 🔴 紅皮克敏 | 讓花苗排成一橫排曬太陽 |
| 第 2 關 | `justify-content: center` | 🟡 黃皮克敏 | 幫花苗移到走道正中間 |
| 第 3 關 | `align-items: center` | 🔵 藍皮克敏 | 讓花苗對齊河道中線 |
| 第 4 關 | `flex-direction: column` | 🟣 紫皮克敏 | 改成直排沿著懸崖排列 |
| 第 5 關 | `flex-wrap: wrap` | 🩷 翅膀皮克敏 | 讓擠出去的花苗自動換行 |

### 玩法
1. 閱讀關卡情境說明
2. 參考上方「目標排列」虛線預覽
3. 在 CSS 輸入框輸入屬性（即時套用）
4. 輸入框變橘色 = 輸入中；變綠色 = 答對 ✅
5. 答對後花苗搖晃彈出皮克敏，飛進底部蒐集區
6. 集滿 20 隻皮克敏通關！

---

## ✨ 功能特色

- **即時驗證**：用 `getComputedStyle()` 偵測 CSS 是否正確，無需按按鈕
- **虛線目標提示**：每個關卡的花苗田顯示正確排列的虛線預覽，降低猜謎感
- **拋物線飛行動畫**：皮克敏沿弧線從花苗飛到底部蒐集區（`requestAnimationFrame`）
- **即時色彩回饋**：輸入中橘框、答對綠框，讓學習狀態一目瞭然
- **Party Bar**：全程固定在畫面底部，蒐集各關皮克敏，動態縮放防破版
- **手機支援**：響應式版面，直向手機自動調整為單欄佈局
- **零依賴**：單一 HTML 檔，無框架、無後端，可直接開啟或投影

---

## 🛠 技術細節

- 純 HTML / CSS / JavaScript，無任何 library
- 圖片以 Base64 嵌入（避免 CDN Hotlink 封鎖）
- CSS 驗證：`getComputedStyle()` 讀取元素計算後的 CSS 值
- 動畫：CSS `@keyframes` + `requestAnimationFrame` 拋物線軌跡
- 版面：CSS Grid（桌機）→ Flexbox `display:contents`（手機）
- Party Bar 皮克敏大小：根據數量動態調整（52px → 28px）

---

## 📚 適用場景

- CSS Flexbox 教學課堂（搭配講義使用）
- 自學 Flexbox 的互動練習
- 前端教學工作坊暖場活動

---

## 授權

圖片版權屬任天堂所有，僅供教育用途展示。  
遊戲程式碼以 MIT License 釋出。
