---
marp: true
theme: default
paginate: true
size: 16:9
style: |
  :root {
    --teal:        #0F6E56;
    --teal-mid:    #1D9E75;
    --teal-light:  #E1F5EE;
    --teal-dark:   #085041;
    --purple:      #3C3489;
    --purple-light:#EEEDFE;
    --purple-dark: #26215C;
    --amber:       #633806;
    --amber-light: #FAEEDA;
    --amber-dark:  #412402;
    --coral-light: #FAECE7;
    --coral:       #712B13;
    --text:        #1a1a1a;
    --muted:       #6b6b6b;
    --faint:       #aaaaaa;
    --border:      #e8e8e4;
    --surface:     #f7f7f5;
    --white:       #ffffff;
  }
  section {
    font-family: 'Noto Sans TC', 'PingFang TC', 'Microsoft JhengHei', sans-serif;
    background: var(--white);
    color: var(--text);
    padding: 48px 60px;
    font-size: 16px;
    line-height: 1.75;
  }
  section::after { font-size: 12px; color: var(--faint); }
  h1 { font-size: 34px; font-weight: 600; line-height: 1.2; margin-bottom: 0.2em; }
  h2 {
    font-size: 24px; font-weight: 600; color: var(--text);
    border-bottom: 2.5px solid var(--teal-mid);
    padding-bottom: 0.3em; margin-bottom: 0.65em;
  }
  h3 { font-size: 16px; font-weight: 600; color: var(--teal); margin-bottom: 0.25em; }
  p  { margin: 0.35em 0; }
  ul { margin: 0.25em 0 0.25em 1.1em; }
  li { margin: 0.2em 0; font-size: 15px; }
  strong { font-weight: 600; }
  code {
    font-family: 'JetBrains Mono', monospace;
    background: var(--surface); border-radius: 4px;
    padding: 1px 6px; font-size: 13px; color: var(--teal-dark);
  }
  table { width: 100%; border-collapse: collapse; font-size: 14px; margin-top: 10px; }
  th { background: var(--teal-mid); color: white; padding: 9px 14px; text-align: left; font-weight: 600; }
  td { padding: 8px 14px; border-bottom: 1px solid var(--border); vertical-align: top; }
  tr:nth-child(even) td { background: var(--surface); }

  /* layout */
  .two-col   { display: grid; grid-template-columns: 1fr 1fr;         gap: 18px; margin-top: 14px; }
  .three-col { display: grid; grid-template-columns: 1fr 1fr 1fr;     gap: 14px; margin-top: 14px; }
  .four-col  { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 12px; margin-top: 14px; }
  .col { display: flex; flex-direction: column; gap: 10px; }

  /* tags */
  .tag { display: inline-block; font-size: 12px; font-weight: 600; padding: 3px 11px; border-radius: 20px; margin-right: 5px; }
  .t-teal   { background: var(--teal-light);  color: var(--teal);   }
  .t-purple { background: var(--purple-light); color: var(--purple); }
  .t-amber  { background: var(--amber-light);  color: var(--amber);  }
  .t-coral  { background: var(--coral-light);  color: var(--coral);  }
  .t-gray   { background: #f0f0ed; color: #555; }

  /* cards */
  .card { background: var(--surface); border-radius: 10px; padding: 14px 16px; font-size: 14px; line-height: 1.65; }
  .card-teal   { border-left: 4px solid var(--teal-mid); border-radius: 0 10px 10px 0; }
  .card-purple { border-left: 4px solid var(--purple);   border-radius: 0 10px 10px 0; }
  .card-amber  { border-left: 4px solid #BA7517;         border-radius: 0 10px 10px 0; }
  .card-coral  { border-left: 4px solid #D85A30;         border-radius: 0 10px 10px 0; }

  /* quote */
  .quote {
    background: var(--teal-light); border-left: 5px solid var(--teal-mid);
    border-radius: 0 12px 12px 0; padding: 18px 22px; margin: 12px 0;
    font-size: 17px; line-height: 1.8; color: var(--teal-dark);
  }

  /* metrics */
  .metric-row { display: flex; gap: 12px; margin: 12px 0; }
  .metric { flex: 1; background: var(--surface); border-radius: 10px; padding: 14px; text-align: center; }
  .mval  { display: block; font-size: 26px; font-weight: 700; color: var(--teal);  line-height: 1.2; }
  .mlbl  { display: block; font-size: 12px; color: var(--muted); margin-top: 4px;  line-height: 1.4; }

  /* pain boxes */
  .pain { background: var(--surface); border-radius: 10px; border-top: 3px solid; padding: 13px 14px; }
  .pain-title { font-size: 14px; font-weight: 600; color: var(--text); margin-bottom: 5px; }

  /* chat bubbles */
  .bq {
    background: #f0f0ed; border-radius: 10px 10px 10px 0;
    padding: 8px 13px; font-size: 13px; color: #333;
    display: inline-block; max-width: 90%; margin-bottom: 5px;
  }
  .ba {
    background: var(--teal-light); border-radius: 10px 10px 0 10px;
    padding: 9px 13px; font-size: 13px; color: var(--teal-dark); display: block; line-height: 1.65;
  }
  .ba-purple {
    background: var(--purple-light); color: var(--purple-dark);
    border-radius: 10px 10px 0 10px;
    padding: 9px 13px; font-size: 13px; display: block; line-height: 1.65;
  }
  .ba-amber {
    background: var(--amber-light); color: var(--amber-dark);
    border-radius: 10px 10px 0 10px;
    padding: 9px 13px; font-size: 13px; display: block; line-height: 1.65;
  }
  .ba-follow {
    background: #d4edda; color: #1a5c2a; border-left: 3px solid #28a745;
    border-radius: 0 10px 10px 0; padding: 7px 13px;
    font-size: 12px; display: block; line-height: 1.6; margin-top: 5px;
  }

  /* flow */
  .flow { display: flex; align-items: center; gap: 6px; flex-wrap: wrap; margin: 8px 0; }
  .fstep    { background: var(--surface); border: 1px solid var(--border); border-radius: 8px; padding: 5px 12px; font-size: 13px; font-weight: 500; white-space: nowrap; }
  .fstep-hi { background: var(--teal-light); color: var(--teal); border-color: var(--teal-mid); }
  .farrow   { color: var(--faint); font-size: 16px; }

  /* before/after compare */
  .vs-row { display: flex; gap: 0; margin: 10px 0; }
  .vs-left  { flex: 1; background: #fff3f0; border-radius: 10px 0 0 10px; padding: 12px 16px; font-size: 13px; line-height: 1.65; }
  .vs-right { flex: 1; background: var(--teal-light); border-radius: 0 10px 10px 0; padding: 12px 16px; font-size: 13px; line-height: 1.65; color: var(--teal-dark); }
  .vs-label { font-size: 11px; font-weight: 700; letter-spacing: 0.05em; margin-bottom: 6px; }

  /* layer pill */
  .lp { display: inline-block; font-size: 11px; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; padding: 2px 10px; border-radius: 20px; margin-bottom: 6px; }
  .lp-teal   { background: var(--teal-mid); color: white; }
  .lp-purple { background: var(--purple);   color: white; }
  .lp-amber  { background: #BA7517;         color: white; }

  /* misc */
  .accent-bar { width: 44px; height: 4px; background: var(--teal-mid); border-radius: 2px; margin: 14px 0; }
  .pg-label   { font-size: 11px; font-weight: 700; letter-spacing: 0.1em; color: var(--teal); text-transform: uppercase; margin-bottom: 8px; }
  .footnote   { font-size: 12px; color: var(--muted); margin-top: 10px; font-style: italic; }
  .check      { color: var(--teal-mid); font-weight: 700; }
  .step-num   { display: inline-flex; align-items: center; justify-content: center; width: 22px; height: 22px; border-radius: 50%; background: var(--teal-mid); color: white; font-size: 12px; font-weight: 700; margin-right: 6px; flex-shrink: 0; }
  .divider    { border: none; border-top: 1px solid var(--border); margin: 14px 0; }
  .section-chip {
    display: inline-block; font-size: 12px; font-weight: 700;
    padding: 4px 14px; border-radius: 20px; margin-bottom: 12px;
  }
  .chip-status   { background: #e8f4fd; color: #185FA5; }
  .chip-pain     { background: #fdecea; color: #9b2c2c; }
  .chip-solution { background: var(--teal-light); color: var(--teal); }
  .chip-system   { background: var(--purple-light); color: var(--purple); }
  .chip-conclude { background: var(--amber-light); color: var(--amber); }
---

<!-- ══════════════════════════════════
     01｜封面
══════════════════════════════════ -->

# 正向力量探索助理

<div class="accent-bar"></div>

<div style="font-size: 20px; font-weight: 600; color: var(--teal-mid); margin-bottom: 10px;">
以 RAG × 人文關懷，打造富邦金控年報智慧對話系統
</div>

<div style="font-size: 15px; color: var(--muted); line-height: 1.8; max-width: 700px;">
以 2024 年富邦金控股東會年報為知識核心，從現狀調查出發，精確定義三類使用者的痛點，設計融合三層人文關懷的 RAG 系統，讓年報從「被動存在的文件」成為「主動回應需求的對話助理」。
</div>

<div style="margin-top: 28px; display: flex; gap: 8px; flex-wrap: wrap;">
  <span class="tag t-teal">大語言模型運用</span>
  <span class="tag t-purple">RAG 系統設計</span>
  <span class="tag t-amber">人文關懷</span>
  <span class="tag t-coral">金融業落地場景</span>
</div>

<div style="position: absolute; bottom: 48px; left: 60px; font-size: 13px; color: var(--muted);">
  <strong>敘事流程：</strong>
  <span style="color:#185FA5;">現狀調查</span> →
  <span style="color:#9b2c2c;">痛點定義</span> →
  <span style="color:var(--teal);">解決方案</span> →
  <span style="color:var(--purple);">系統構造</span> →
  <span style="color:var(--amber);">結論</span>
</div>
<div style="position: absolute; bottom: 48px; right: 60px; font-size: 12px; color: var(--faint);">富邦金控數據科學組 MA 甄選 ｜ 莊昊耘 Hao-Yun Chuang</div>

---

<!-- ══════════════════════════════════
     02｜現狀調查①：公益規模
══════════════════════════════════ -->

<div class="section-chip chip-status">現狀調查 01 / 02</div>

## 富邦的公益投入有多大？

<div class="metric-row">
  <div class="metric"><span class="mval">4.98億</span><span class="mlbl">2024 年捐贈總額<br>年報第 217 頁</span></div>
  <div class="metric"><span class="mval">177,915</span><span class="mlbl">助學計畫受惠學生<br>年報第 222 頁</span></div>
  <div class="metric"><span class="mval">9.8萬棵</span><span class="mlbl">Run For Green 累積植樹<br>年報第 222 頁</span></div>
  <div class="metric"><span class="mval">138,021</span><span class="mlbl">急難救助受惠個案<br>年報第 222 頁</span></div>
</div>

<div class="two-col" style="margin-top: 6px;">
<div>

**公益體系結構**（來源：§4.13，第215–224頁）

- **富邦慈善基金會**：弱勢扶助、急難救助、助學
- **富邦文教基金會**：兒少教育、媒體素養、青少年發聲
- **富邦藝術基金會**：藝文推廣、美術館經營
- **台北富邦銀行基金會**：長者身心健康、身障藝術
- **上海富邦華一公益基金會**：婦女長者、偏遠扶貧

</div>
<div>

**2024 年捐贈結構**

| 捐贈目的 | 金額 | 比例 |
|---------|------|------|
| 五家基金會活動費 | 296,780,000 元 | 59.59% |
| 對公益團體捐贈 | 201,225,819 元 | 40.41% |
| **合計** | **498,005,819 元** | **100%** |

<div class="footnote">資料來源：年報第 223–224 頁，§4.13（捐贈執行情形）</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     03｜現狀調查②：年報溝通現狀
══════════════════════════════════ -->

<div class="section-chip chip-status">現狀調查 02 / 02</div>

## 年報作為溝通媒介的現狀

<div class="two-col">
<div>

**年報的結構現實**

<div class="card card-teal" style="margin-bottom: 8px; font-size: 13px;">
  <strong>272 頁、A4 尺寸</strong><br>
  公益資訊集中於 §4.13（第215–224頁），佔全書不到 4%，但含有最多對外溝通價值的內容。
</div>

<div class="card" style="font-size: 13px; margin-bottom: 8px;">
  <strong>主要閱讀對象</strong>：法人投資人、法遵人員、監管機構——並非一般大眾、NGO 或媒體記者。
</div>

<div class="card" style="font-size: 13px;">
  <strong>現有溝通管道</strong>：年報 PDF 下載、官網 ESG 頁面（靜態）、IR 部門人工回覆——沒有互動式入口。
</div>

</div>
<div>

**誰需要年報裡的資訊，但現在找不到？**

<div class="pain" style="border-top-color: #D85A30; margin-bottom: 8px;">
  <div class="pain-title">NGO / 公益團體</div>
  <div style="font-size: 13px; color: var(--muted);">想找企業合作，不知道富邦支持哪些議題、哪個基金會對口、門檻是什麼。</div>
</div>
<div class="pain" style="border-top-color: #7F77DD; margin-bottom: 8px;">
  <div class="pain-title">媒體記者 / ESG 分析師</div>
  <div style="font-size: 13px; color: var(--muted);">截稿壓力下需要精確數字與出處，但 IR 信箱回覆慢、年報翻找費時。</div>
</div>
<div class="pain" style="border-top-color: #BA7517;">
  <div class="pain-title">一般消費者 / 潛在客戶</div>
  <div style="font-size: 13px; color: var(--muted);">對銀行社會形象有興趣，但不可能讀 272 頁年報，資訊與他們之間有高牆。</div>
</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     04｜痛點①：三類使用者的痛
══════════════════════════════════ -->

<div class="section-chip chip-pain">痛點定義 01 / 02</div>

## 三類使用者，三種不同的痛

<div class="three-col">

<div class="col">
  <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 8px;">
    <span class="tag t-teal">NGO / 公益團體</span>
  </div>
  <div class="pain" style="border-top-color: #1D9E75; flex: 1;">
    <div class="pain-title">合作門檻不透明</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">不知道找哪個基金會、怎麼談、有沒有規模門檻，只能靠人脈打聽或寫冷門信等 1–2 週。</div>
  </div>
  <div class="pain" style="border-top-color: #1D9E75;">
    <div class="pain-title">資訊分散無整合入口</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">五個基金會各自官網，議題重疊、格式不一，難以評估契合度。</div>
  </div>
</div>

<div class="col">
  <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 8px;">
    <span class="tag t-purple">媒體 / 分析師</span>
  </div>
  <div class="pain" style="border-top-color: #7F77DD; flex: 1;">
    <div class="pain-title">引用無出處是法遵風險</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">媒體若引用不準確的 ESG 數字，IR 部門須花時間澄清，甚至影響國際評等。</div>
  </div>
  <div class="pain" style="border-top-color: #7F77DD;">
    <div class="pain-title">截稿壓力 vs 人工翻找</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">記者無法等待 IR 回覆，往往略過精確數字或依賴二手資料，傳播失真。</div>
  </div>
</div>

<div class="col">
  <div style="display: flex; align-items: center; gap: 8px; margin-bottom: 8px;">
    <span class="tag t-amber">消費者 / 大眾</span>
  </div>
  <div class="pain" style="border-top-color: #BA7517; flex: 1;">
    <div class="pain-title">數字有重量，但沒有溫度</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">「498,005,819 元」是精確數字，但對一般人是抽象的，「陪伴 13 萬個家庭」才有情感重量。</div>
  </div>
  <div class="pain" style="border-top-color: #BA7517;">
    <div class="pain-title">品牌精神難具體感受</div>
    <div style="font-size: 13px; color: var(--muted); line-height: 1.6;">「正向力量 成就可能」停留在口號層，需要具體故事承載，消費者才能真正感受。</div>
  </div>
</div>

</div>

---

<!-- ══════════════════════════════════
     05｜痛點②：年報 PDF 技術痛點
══════════════════════════════════ -->

<div class="section-chip chip-pain">痛點定義 02 / 02</div>

## 年報 PDF 本身的技術痛點

<div class="card card-teal" style="margin-bottom: 16px; font-size: 14px;">
  <strong>核心問題：</strong>年報不是純文字文件，是高度結構化的排版文件。傳統「直接 pdftotext → 切 chunk」在這份年報上會失敗，產生三類具體問題。
</div>

<div class="three-col">
<div class="col">
  <div class="lp lp-teal">技術痛點 01</div>
  <div style="font-weight: 600; font-size: 15px; margin-bottom: 6px;">CID 字體編碼異常</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    Adobe InDesign 輸出的 PDF 存在 <strong>Adobe-CNS1</strong> 字體映射問題，<code>pdftotext</code> 提取出現 <code>(cid:3712)</code> 亂碼，無法直接使用。
  </div>
  <div style="font-size: 12px; color: var(--muted); margin-top: 6px;">影響範圍：年報多頁內文，包含部分公益章節</div>
</div>

<div class="col">
  <div class="lp lp-purple">技術痛點 02</div>
  <div style="font-weight: 600; font-size: 15px; margin-bottom: 6px;">表格數字語境依賴</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    「177,915」單獨出現毫無意義，必須與「用愛心做朋友助學活動受惠學生人次」綁定，固定長度 chunking 會切斷這個對應關係。
  </div>
  <div style="font-size: 12px; color: var(--muted); margin-top: 6px;">影響範圍：第 217、222–224 頁捐贈明細表</div>
</div>

<div class="col">
  <div class="lp lp-amber">技術痛點 03</div>
  <div style="font-weight: 600; font-size: 15px; margin-bottom: 6px;">章節跨頁結構</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    §4.13 企業責任橫跨第 215–224 頁，中間夾雜員工訓練表格，固定 size chunking 會混淆語意邊界，讓「教育推廣」和「員工福利」混入同一個 chunk。
  </div>
  <div style="font-size: 12px; color: var(--muted); margin-top: 6px;">影響範圍：整個公益章節（10頁）</div>
</div>
</div>

<div class="footnote" style="margin-top: 14px;">以上三項均為實際解析 2024 富邦金控年報 PDF 所得的觀察，非理論推演。</div>

---

<!-- ══════════════════════════════════
     06｜解決方案：系統定位
══════════════════════════════════ -->

<div class="section-chip chip-solution">解決方案 01 / 02</div>

## 「正向力量探索助理」：設計原則

<div class="quote" style="font-size: 16px; margin-bottom: 18px;">
「技術可以讓答案<strong>準確</strong>，但人文關懷讓答案<strong>有用</strong>。<br>我們希望系統不只知道年報說了什麼，還知道對話那端的人需要什麼。」
</div>

<div class="three-col">

<div class="col">
  <div style="font-size: 13px; font-weight: 700; color: var(--muted); margin-bottom: 6px;">設計原則 01</div>
  <div style="font-size: 15px; font-weight: 600; margin-bottom: 8px;">讓資訊可被找到</div>
  <div class="card card-teal" style="font-size: 13px; line-height: 1.65;">
    以 RAG 讓年報成為可對話的知識庫，任何人一句話就能問到，不需讀 272 頁。答案附頁碼，數字可驗證。
  </div>
</div>

<div class="col">
  <div style="font-size: 13px; font-weight: 700; color: var(--muted); margin-bottom: 6px;">設計原則 02</div>
  <div style="font-size: 15px; font-weight: 600; margin-bottom: 8px;">讓答案對使用者有意義</div>
  <div class="card card-purple" style="font-size: 13px; line-height: 1.65;">
    同一套知識庫，對 NGO 說具體、對記者說嚴謹、對消費者說故事。身份不同，答案的語氣與格式不同。
  </div>
</div>

<div class="col">
  <div style="font-size: 13px; font-weight: 700; color: var(--muted); margin-bottom: 6px;">設計原則 03</div>
  <div style="font-size: 15px; font-weight: 600; margin-bottom: 8px;">讓對話有人的溫度</div>
  <div class="card card-amber" style="font-size: 13px; line-height: 1.65;">
    感知使用者問題背後的隱性需求，主動追問一次，而不是只把資料丟出去就結束對話。
  </div>
</div>

</div>

---

<!-- ══════════════════════════════════
     07｜解決方案：三層人文關懷概覽
══════════════════════════════════ -->

<div class="section-chip chip-solution">解決方案 02 / 02</div>

## 三層人文關懷設計：概覽

<table>
<tr>
  <th>層次</th>
  <th>設計名稱</th>
  <th>解決的痛點</th>
  <th>技術實作</th>
  <th>觸發時機</th>
</tr>
<tr>
  <td><span class="lp lp-teal" style="font-size:11px;">Layer 1</span></td>
  <td><strong>語氣設計</strong></td>
  <td>數字有重量但無溫度<br>品牌精神難具體感受</td>
  <td>System Prompt 改寫<br>數字轉主詞句型</td>
  <td>所有回答均啟動</td>
</tr>
<tr>
  <td><span class="lp lp-purple" style="font-size:11px;">Layer 2</span></td>
  <td><strong>對象感知路由</strong></td>
  <td>同一問題對不同人答案需求不同<br>使用者身份不明確</td>
  <td>對話開場身份確認<br>三套 Prompt 模板切換</td>
  <td>對話開始時觸發</td>
</tr>
<tr>
  <td><span class="lp lp-amber" style="font-size:11px;">Layer 3</span></td>
  <td><strong>意圖探測追問</strong></td>
  <td>問題背後有未說出口的需求<br>系統只回答表面問題</td>
  <td>Prompt 指令：判斷隱性需求<br>主動追問一次，且只一次</td>
  <td>LLM 判斷需要時觸發</td>
</tr>
</table>

<div class="card" style="margin-top: 14px; font-size: 13px;">
  <strong>整體設計邏輯：</strong>三層相互獨立，可依場景選擇啟用組合。Layer 1 改 Prompt 即可；Layer 2 需對話狀態管理；Layer 3 需 LLM 推理支撐。所有層次共用同一個知識庫，無需維護三套系統。
</div>

---

<!-- ══════════════════════════════════
     08｜系統構造①：技術 Pipeline
══════════════════════════════════ -->

<div class="section-chip chip-system">系統構造 01 / 05</div>

## 技術架構：從 PDF 到有溫度的答案

<div class="flow" style="margin-bottom: 18px;">
  <span class="fstep">PDF 解析</span><span class="farrow">→</span>
  <span class="fstep">Semantic Chunking</span><span class="farrow">→</span>
  <span class="fstep">Embedding</span><span class="farrow">→</span>
  <span class="fstep">Hybrid 檢索</span><span class="farrow">→</span>
  <span class="fstep">Reranking</span><span class="farrow">→</span>
  <span class="fstep fstep-hi">人文關懷 Prompt</span><span class="farrow">→</span>
  <span class="fstep fstep-hi">附頁碼輸出</span>
</div>

<div class="two-col">
<div class="col">

<div class="card" style="font-size: 13px;">
  <strong>解析層</strong>（對應技術痛點 01、02）<br>
  <code>pdfplumber</code> 表格完整提取，保留行列對應關係<br>
  <code>pdftoppm</code> 對 CID 字體頁面進行 rasterize，以視覺方式解析
</div>

<div class="card" style="font-size: 13px;">
  <strong>Chunking</strong>（對應技術痛點 03）<br>
  以 §H1/H2 標題為語意邊界，表格整體保留為單一 chunk<br>
  每個 chunk 攜帶 Metadata：<code>章節名稱 + 頁碼 + 所屬基金會</code>
</div>

<div class="card" style="font-size: 13px;">
  <strong>檢索</strong><br>
  Embedding：<code>text-embedding-3-small</code>，向量庫：<code>ChromaDB</code><br>
  <strong>Hybrid Search</strong>（向量 + BM25），Cross-Encoder Reranking
</div>

</div>
<div class="col">

<div class="card card-purple" style="font-size: 13px;">
  <strong>生成層</strong><br>
  模型：GPT-4o / Claude Sonnet<br>
  Prompt 結構：<br>
  　① 角色設定（Layer 2 路由決定）<br>
  　② 語氣規則（Layer 1 常駐）<br>
  　③ 意圖追問指令（Layer 3 條件觸發）<br>
  　④ 來源引用強制規則<br>
  　⑤ 幻覺防護規則
</div>

<div class="card card-amber" style="font-size: 13px;">
  <strong>輸出格式</strong><br>
  答案本文 + 「依據年報第 X 頁，§X.X 節」+ 數字錨點驗證標記（若為數字題）
</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     09｜系統構造②：Layer 1 語氣設計
══════════════════════════════════ -->

<div class="section-chip chip-system">系統構造 02 / 05</div>

## Layer 1 語氣設計 × 解決「感知斷層」

<div style="margin-bottom: 10px;">
  <span class="tag t-teal">痛點對應</span>
  <span style="font-size: 14px; color: var(--muted);">數字有重量但沒有溫度 ／ 品牌精神「正向力量」難以具體感受</span>
</div>

**Before → After：同樣的數字，不同的重量**

<div class="vs-row" style="margin-bottom: 14px;">
  <div class="vs-left">
    <div class="vs-label" style="color:#9b2c2c;">✗ 一般 RAG 輸出</div>
    急難救助投入 4,371 萬元，受惠個案 138,021 人次。（第222頁）
  </div>
  <div class="vs-right">
    <div class="vs-label" style="color:var(--teal);">✓ Layer 1 語氣設計後</div>
    富邦 2024 年透過急難救助，<strong>陪伴了 13 萬個正在度過難關的家庭</strong>，累計投入 4,371 萬元。如果你想進一步了解特定議題的支援方式，我可以幫你找更多。（依據年報第 222 頁）
  </div>
</div>

**Prompt 規則（三條核心）**

<div class="three-col" style="margin-top: 0;">
  <div class="card" style="font-size: 13px;">
    <strong>數字給主詞</strong><br>
    「138,021 人次」→「13 萬個家庭」<br>
    人次是統計，家庭是存在的人
  </div>
  <div class="card" style="font-size: 13px;">
    <strong>答案有邀請</strong><br>
    不停留在陳述事實，結尾引導下一步，讓對話有機會繼續
  </div>
  <div class="card" style="font-size: 13px;">
    <strong>措辭帶精神</strong><br>
    選用「陪伴」而非「服務」，細微差異傳遞「正向力量」品牌精神
  </div>
</div>

---

<!-- ══════════════════════════════════
     10｜系統構造③：Layer 2 對象感知
══════════════════════════════════ -->

<div class="section-chip chip-system">系統構造 03 / 05</div>

## Layer 2 對象感知路由 × 解決「對象模糊」

<div style="margin-bottom: 10px;">
  <span class="tag t-purple">痛點對應</span>
  <span style="font-size: 14px; color: var(--muted);">同一個問題，NGO、記者、消費者各自需要完全不同格式的答案</span>
</div>

**對話開場設計**

<div style="margin: 10px 0 14px;">
  <div class="bq">您好，我是富邦正向力量助理。請問您今天是想了解<strong>合作機會</strong>、<strong>查詢相關數據</strong>，還是<strong>認識富邦在做的事</strong>？</div>
</div>

<div class="three-col">
  <div style="background: var(--teal-light); border-radius: 10px; padding: 14px;">
    <div style="font-size: 11px; font-weight: 700; color: var(--teal); margin-bottom: 6px;">選 A｜合作機會</div>
    <div style="font-size: 13px; font-weight: 600; margin-bottom: 6px;">引導行動型 Prompt</div>
    <div style="font-size: 12px; color: var(--teal-dark); line-height: 1.65;">
      優先輸出：計畫名稱 + 歷年規模 + 聯絡窗口引導<br>
      語氣：具體、有行動指引<br>
      Layer 3：詢問合作方向
    </div>
  </div>
  <div style="background: var(--purple-light); border-radius: 10px; padding: 14px;">
    <div style="font-size: 11px; font-weight: 700; color: var(--purple); margin-bottom: 6px;">選 B｜查詢數據</div>
    <div style="font-size: 13px; font-weight: 600; margin-bottom: 6px;">嚴謹引用型 Prompt</div>
    <div style="font-size: 12px; color: var(--purple-dark); line-height: 1.65;">
      優先輸出：精確數字 + 頁碼 + 可引用格式<br>
      語氣：嚴謹、不加溫暖修辭<br>
      Layer 3：通常不觸發
    </div>
  </div>
  <div style="background: var(--amber-light); border-radius: 10px; padding: 14px;">
    <div style="font-size: 11px; font-weight: 700; color: var(--amber); margin-bottom: 6px;">選 C｜認識富邦</div>
    <div style="font-size: 13px; font-weight: 600; margin-bottom: 6px;">故事敘述型 Prompt</div>
    <div style="font-size: 12px; color: var(--amber-dark); line-height: 1.65;">
      優先輸出：故事化敘述 + 感知數字 + 品牌精神連結<br>
      語氣：溫暖、有畫面感<br>
      Layer 3：引導深入感興趣的方向
    </div>
  </div>
</div>

---

<!-- ══════════════════════════════════
     11｜系統構造④：Layer 3 意圖探測
══════════════════════════════════ -->

<div class="section-chip chip-system">系統構造 04 / 05</div>

## Layer 3 意圖探測 × 解決「需求未被說出口」

<div style="margin-bottom: 10px;">
  <span class="tag t-coral">痛點對應</span>
  <span style="font-size: 14px; color: var(--muted);">有些問題的表面是一件事，背後其實是另一個更重要的問題</span>
</div>

<div class="two-col">
<div>

**Prompt 核心指令**

<div class="card card-amber" style="font-size: 13px; line-height: 1.7; margin-bottom: 10px;">
回答使用者問題後，判斷此問題是否存在<strong>未說出口的需求</strong>（如尋找資源、尋求合作、個人情境）。若判斷有，主動追問一次釐清——<strong>且只問一次，不過度介入</strong>。若判斷無，以邀請語結尾即可。
</div>

**判斷邏輯範例**

| 問法 | 推測隱性需求 | 追問設計 |
|------|------------|---------|
| 「有在幫助老人嗎？」 | 可能在為家人找資源 | 詢問：為長者本人 or 照顧者？ |
| 「支持環保嗎？」 | 可能想合作 | 詢問：了解還是尋求合作機會？ |
| 「偏鄉教育有什麼？」 | 可能是 NGO 或教師 | 詢問：哪個年齡層 / 縣市？ |

</div>
<div>

**示範對話：意圖探測啟動**

<div style="margin-top: 4px;">
  <div class="bq">「富邦有在幫助老人嗎？」</div>
  <div class="ba" style="margin-bottom: 5px;">
    有的。台北富邦銀行基金會長期投入長者身心健康，2024 年舉辦「富邦甲子盃」桌球及圍棋大賽、「富邦銀髮音樂陪伴計畫」，並特別為照顧者設計喘息之旅活動。（依據年報第 223 頁，§4.13.3）
  </div>
  <div class="ba-follow">↳ 請問你是在為某位長者尋找參與活動的機會，還是想了解與富邦合作推廣長者服務的可能性？我可以幫你找更符合需求的資訊。</div>
</div>

<div class="card" style="margin-top: 12px; font-size: 13px;">
  <strong>設計邊界：</strong>追問語氣是邀請，不是詢問。若使用者不回應追問，系統不再追問，保持對話自然不強迫。
</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     12｜系統構造⑤：幻覺防護
══════════════════════════════════ -->

<div class="section-chip chip-system">系統構造 05 / 05</div>

## 幻覺防護 × 解決「數字可信度」

<div style="margin-bottom: 10px;">
  <span class="tag t-purple">痛點對應</span>
  <span style="font-size: 14px; color: var(--muted);">媒體引用無出處是法遵風險 ／ 數字一旦錯誤對銀行品牌造成傷害</span>
</div>

<div class="two-col">
<div>

**三層防護機制**

<div class="card card-teal" style="margin-bottom: 8px; font-size: 13px;">
  <span class="step-num">1</span><strong>Prompt 約束層</strong><br>
  「僅使用 context 中的資訊回答。找不到時，回答：根據現有年報資料，無法回答此問題。」禁止補充訓練知識。
</div>

<div class="card card-purple" style="margin-bottom: 8px; font-size: 13px;">
  <span class="step-num">2</span><strong>數字錨點驗證</strong><br>
  答案中出現的所有數字，在原始 PDF 對應頁碼做字串比對。若數字在被引用頁面找不到，標記「需人工確認」。
</div>

<div class="card card-amber" style="font-size: 13px;">
  <span class="step-num">3</span><strong>來源頁碼強制輸出</strong><br>
  每則答案末尾強制附上「依據年報第 X 頁，§X.X 節」，讓引用者有據可查，人工複核成本最小化。
</div>

</div>
<div>

**Accuracy 評估框架**

<table>
<tr><th>題型</th><th>評估方式</th><th>標準</th></tr>
<tr><td>數字類</td><td>Exact Match</td><td>精確符合 or ±5%</td></tr>
<tr><td>敘述類</td><td>Semantic Similarity</td><td>cosine ≥ 0.85</td></tr>
<tr><td>複合類</td><td>分開計算</td><td>分別報告</td></tr>
</table>

<div class="card" style="margin-top: 12px; font-size: 13px;">
  <strong>為什麼分開報告？</strong><br>
  數字題與敘述題的失敗模式完全不同。用單一 Accuracy 會讓「答對故事、答錯數字」的情況被遮蓋。最危險的幻覺不是答錯，是<strong>答得自信但來源不存在</strong>——數字錨點驗證專門對付這個。
</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     13｜場景驗證①：NGO 媒合
══════════════════════════════════ -->

<div class="section-chip chip-system">場景驗證 01 / 03</div>

## 場景一：NGO 公益合作媒合

<div style="margin-bottom: 10px;">
  <span class="tag t-teal">Layer 2 路由 A</span>
  <span class="tag t-teal">Layer 3 意圖追問</span>
  <span class="tag t-teal">幻覺防護啟動</span>
</div>

<div class="two-col">
<div>

**使用者痛點回顧**
- 不知道哪個基金會對口
- 合作門檻不透明，只能靠人脈
- 平均等待 IR 回覆 1–2 週

**系統如何回應這些痛**

<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">1</span>
  <div style="font-size: 13px;">Layer 2 偵測「合作機會」身份，切換至引導行動型 Prompt</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">2</span>
  <div style="font-size: 13px;">Layer 1 將「177,915 人次」轉化為「177,915 位學生」，讓對話有人的感覺</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">3</span>
  <div style="font-size: 13px;">Layer 3 探測到可能有合作需求，追問一次釐清學生年齡層</div>
</div>

<div class="footnote">✓ 落地價值：降低 IR/PR 人工接洽成本，讓 5 億公益資源找到更多對口夥伴</div>

</div>
<div>

**完整對話**

<div class="bq">「我們是偏鄉教育 NPO，想找企業合作，富邦有相關計畫嗎？」</div>
<div class="ba">
富邦文教基金會深耕兒少教育逾 30 年，旗下「好正學堂」專門媒合社企與 NPO，採不同場域的親身體驗，引發年輕世代對永續議題的關注。2024 年助學捐款達 1 億元，陪伴了 177,915 位學生。（依據年報第 222 頁，§4.13.1）
</div>
<div class="ba-follow">↳ 請問你們的計畫主要面向哪個年齡層的學生？這樣我可以幫你找更對口的合作窗口。</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     14｜場景驗證②：ESG 數字查詢
══════════════════════════════════ -->

<div class="section-chip chip-system">場景驗證 02 / 03</div>

## 場景二：ESG 數字即時查詢

<div style="margin-bottom: 10px;">
  <span class="tag t-purple">Layer 2 路由 B</span>
  <span class="tag t-purple">幻覺防護全啟動</span>
  <span class="tag t-purple">Layer 1 嚴謹模式</span>
</div>

<div class="two-col">
<div>

**使用者痛點回顧**
- 截稿壓力下需要精確數字 + 出處
- 引用錯誤是媒體與銀行雙方的風險
- IR 回覆慢，記者往往略過精確數字

**系統如何回應這些痛**

<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">1</span>
  <div style="font-size: 13px;">Layer 2 偵測「查詢數據」身份，切換至嚴謹引用型 Prompt，不加溫暖修辭</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">2</span>
  <div style="font-size: 13px;">幻覺防護：數字錨點驗證確認每個數字均存在於被引用頁面</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">3</span>
  <div style="font-size: 13px;">強制輸出頁碼，記者可直接寫「依富邦年報第 222 頁」，引用有據</div>
</div>

<div class="footnote">✓ 落地價值：支援 DJSI、MSCI 評等資料提交；媒體引用有頁碼，降低公關風險</div>

</div>
<div>

**完整對話**

<div class="bq">「富邦 2024 年弱勢關懷投入多少？有哪些具體計畫？」</div>
<div class="ba-purple">
2024 年弱勢關懷支出明細：<br>
・急難救助專案：投入 4,371 萬元，受惠個案 138,021 人次<br>
・用愛心做朋友助學：捐款 106,749,000 元，受惠 177,915 人次<br>
・愛心志工社：6,405 名志工，服務時數 22,792 小時<br>
全年捐贈總額：498,005,819 元<br>
（依據年報第 222–223 頁，§4.13.3 節）
</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     15｜場景驗證③：品牌溝通
══════════════════════════════════ -->

<div class="section-chip chip-system">場景驗證 03 / 03</div>

## 場景三：品牌形象大眾溝通

<div style="margin-bottom: 10px;">
  <span class="tag t-amber">Layer 2 路由 C</span>
  <span class="tag t-amber">Layer 1 全力發揮</span>
  <span class="tag t-amber">Layer 3 引導深入</span>
</div>

<div class="two-col">
<div>

**使用者痛點回顧**
- 「4.98億」對一般人是抽象數字
- 「正向力量 成就可能」停留在口號
- 消費者不可能讀 272 頁年報

**系統如何回應這些痛**

<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">1</span>
  <div style="font-size: 13px;">Layer 2 切換至故事敘述型 Prompt，數字背後說人，不說統計</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">2</span>
  <div style="font-size: 13px;">Layer 1：「9.8 萬棵樹」加上「長在全台 8 個縣市」，數字有了地理感</div>
</div>
<div style="display: flex; gap: 6px; align-items: flex-start; margin: 8px 0;">
  <span class="step-num">3</span>
  <div style="font-size: 13px;">Layer 3 追問消費者最有共鳴的方向，引導深入了解</div>
</div>

<div class="footnote">✓ 落地價值：讓年報數字成為品牌情感素材，可整合至官網、LINE Bot、Fubon+ App</div>

</div>
<div>

**完整對話**

<div class="bq">「富邦除了是銀行，還做了什麼對社會有意義的事？」</div>
<div class="ba-amber">
富邦每年贊助四大馬拉松，跑者每跑 40 公里，富邦就在台灣土地上種下一棵樹——截至 2024 年，這些樹已有 9.8 萬棵，長在全台 8 個縣市。<br><br>
同一年，富邦慈善基金會陪伴了 13 萬個正在度過困難的家庭，也幫助了將近 18 萬名學生繼續就學的機會。<br><br>
這就是「正向力量 成就可能」——不是口號，是每一棵樹、每一個孩子。（依據年報第 222 頁）
</div>
<div class="ba-follow">↳ 你對哪個方向最有共鳴？環境、教育，還是弱勢關懷？</div>

</div>
</div>

---

<!-- ══════════════════════════════════
     16｜結論
══════════════════════════════════ -->

<div class="section-chip chip-conclude">結論</div>

## 痛點 × 解法對照，以及落地路徑

<div style="margin-bottom: 14px;">

| 痛點 | 對應使用者 | 系統解法 | 核心技術 |
|------|----------|---------|---------|
| 合作門檻不透明 | NGO | Layer 2 路由 A + Layer 3 追問 | 身份路由 + 意圖探測 |
| 引用無出處 | 媒體 / 分析師 | 幻覺防護三層 + 頁碼強制輸出 | 數字錨點驗證 |
| 數字缺乏溫度 | 消費者 | Layer 1 語氣設計 | System Prompt 改寫 |
| CID 字體亂碼 | （技術） | pdftoppm 視覺解析 | PDF rasterize |
| 表格語境切斷 | （技術） | pdfplumber 整行保留 | Table-aware extraction |
| 章節跨頁混淆 | （技術） | 標題邊界 Semantic Chunking | Metadata + 標題切割 |

</div>

<div class="two-col">
<div>
<div class="card card-teal" style="font-size: 13px;">
  <strong>短期</strong>：嵌入富邦官網 ESG 頁面，作為「正向力量探索助理」對外入口
</div>
<div class="card card-purple" style="font-size: 13px; margin-top: 8px;">
  <strong>中期</strong>：整合至 LINE Bot / Fubon+ 行動銀行，擴大觸及至消費者日常
</div>
</div>
<div>
<div class="quote" style="font-size: 14px; margin: 0;">
「富邦的公益投入不缺數字，缺的是讓對的人在對的時機，用對的方式找到這些數字的入口。這套系統，就是那個入口。」
</div>
</div>
</div>

---

<!-- ══════════════════════════════════
     17｜英文摘要
══════════════════════════════════ -->

# Fubon Annual Report RAG System
## *Accurate Answers with Human Warmth*

<div class="accent-bar"></div>

**Problem** — Fubon's 2024 Annual Report (272 pages) contains NT$498M in charitable contributions, 177,915 student beneficiaries, and 98,000 trees planted. Yet NGOs can't find collaboration partners, journalists can't cite reliable data under deadline, and consumers can't feel the human impact behind the numbers.

**Solution** — A RAG system with three-layer humanistic care design, turning a passive PDF into an interactive knowledge assistant.

| Layer | Design | Solves |
|-------|--------|--------|
| Layer 1 | Tone Design — numbers become subject-led sentences | "Statistics without warmth" |
| Layer 2 | Identity Routing — 3 Prompt templates for NGO / media / public | "One answer doesn't fit all" |
| Layer 3 | Intent Detection — one proactive follow-up question | "Unstated needs go unmet" |

**Technical Stack** — `pdfplumber` table extraction + `pdftoppm` for CID font pages + Semantic Chunking by heading boundary + Hybrid Search (vector + BM25) + Cross-Encoder Reranking + three-layer hallucination defense (Prompt constraint / numeric anchor validation / mandatory page citation).

**Core Thesis** — Technology makes answers accurate. Humanistic care makes them meaningful. The system knows not just what the annual report says, but what the person on the other end of the conversation needs.