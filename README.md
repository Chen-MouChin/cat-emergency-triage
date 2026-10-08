# 貓咪急診判斷器

勾選貓咪現在的症狀，立刻知道該「現在就出門、今天就醫、本週預約、還是在家觀察」，並把獸醫會問的資訊整理成一段可以複製的摘要。

- 線上版：https://chen-mouchin.github.io/cat-emergency-triage/
- 原始碼：https://github.com/Chen-MouChin/cat-emergency-triage
- 規格書：[SPEC.md](SPEC.md)
- 單一 `index.html`，CSS 與 JavaScript 內嵌，沒有外部資源，離線可用。

## 怎麼用

1. 打開頁面，勾選你看到的情況。可以複選。
2. 結果區即時顯示顏色與一句話：紅「現在就出門」、橘「今天就醫」、黃「本週預約」、綠「在家觀察」。
3. 第一級時會出現對應的就醫前處置（中毒、骨折、出血、窒息、失溫），分「做」與「不做」。
4. 「就醫前 60 秒」填三個欄位，按「產生摘要」再「複製」，到醫院直接念給獸醫聽。
5. 勾選存在你的瀏覽器裡，重新整理不會消失；「清除全部」一次清掉。

## 開發過程（與 AI 反覆修改的紀錄）

工具：Claude Code（Claude Fable 5.1）。作者負責想法、內容來源、驗收與決策；AI 負責整理規格、寫程式、自我檢查。

1. **想法**：作者原本在做貓健康知識庫（cat-health-tw），裡面有一篇〈貓咪急診判斷與居家急救〉把症狀分四級。作業要做互動網頁，作者決定把這張表做成可以勾的工具，主要交付物就是它。
2. **規格討論**：AI 先提出「症狀勾選 → 取最高等級 → 顯示理由與就醫前處置 → 產生給獸醫的摘要」四段流程，作者確認。規格書列出 29 項症狀、7 項沉默信號、兩個情境開關、10 條驗收條件（見 SPEC.md）。
3. **第一版實作**：單檔 index.html，資料表直接從文章轉成 JavaScript 物件，結果區手機固定在底部、桌機固定在右欄。
4. **自我檢查**：AI 抽出內嵌 JavaScript 做語法檢查，再依驗收條件逐條走一遍。
5. **待補**：手機實測截圖、GitHub Pages 網址、作者實際操作後的修改（會記錄在這一節）。

## 資料來源

- VCA Animal Hospitals, Emergency Care for Cats
- International Cat Care, When to take your cat to the vet
- ASPCA Animal Poison Control, Emergency Procedures；People Foods to Avoid Feeding Your Pets
- FDA, Lovely Lilies and Curious Cats

以上經作者整理為 cat-health-tw 的兩篇文章，再轉成本工具的判斷表。本工具不是診斷，不取代獸醫。

## 授權

程式 MIT。內容為作者整理之衛教摘要，引用時請註明來源。
