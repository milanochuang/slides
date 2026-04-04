---
marp: true
theme: default
paginate: true
size: 16:9
nav_exclude: true
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
    padding: 46px 58px;
    font-size: 15.5px;
    line-height: 1.75;
  }
  section::after { font-size: 12px; color: var(--faint); }
  h1 { font-size: 33px; font-weight: 600; line-height: 1.2; margin-bottom: 0.2em; }
  h2 {
    font-size: 23px; font-weight: 600; color: var(--text);
    border-bottom: 2.5px solid var(--teal-mid);
    padding-bottom: 0.28em; margin-bottom: 0.6em;
  }
  h3 { font-size: 15px; font-weight: 600; color: var(--teal); margin-bottom: 0.2em; }
  p  { margin: 0.3em 0; }
  ul { margin: 0.2em 0 0.2em 1.1em; }
  li { margin: 0.18em 0; font-size: 14px; }
  strong { font-weight: 600; }
  code {
    font-family: 'JetBrains Mono', monospace;
    background: var(--surface); border-radius: 4px;
    padding: 1px 5px; font-size: 12.5px; color: var(--teal-dark);
  }
  table { width: 100%; border-collapse: collapse; font-size: 13.5px; margin-top: 8px; }
  th { background: var(--teal-mid); color: white; padding: 8px 13px; text-align: left; font-weight: 600; }
  td { padding: 7px 13px; border-bottom: 1px solid var(--border); vertical-align: top; }
  tr:nth-child(even) td { background: var(--surface); }

  .two-col   { display: grid; grid-template-columns: 1fr 1fr;         gap: 16px; margin-top: 12px; }
  .three-col { display: grid; grid-template-columns: 1fr 1fr 1fr;     gap: 13px; margin-top: 12px; }
  .four-col  { display: grid; grid-template-columns: 1fr 1fr 1fr 1fr; gap: 11px; margin-top: 12px; }
  .col { display: flex; flex-direction: column; gap: 8px; }

  .tag { display: inline-block; font-size: 11.5px; font-weight: 600; padding: 2px 10px; border-radius: 20px; margin-right: 4px; }
  .t-teal   { background: var(--teal-light);  color: var(--teal);   }
  .t-purple { background: var(--purple-light); color: var(--purple); }
  .t-amber  { background: var(--amber-light);  color: var(--amber);  }
  .t-coral  { background: var(--coral-light);  color: var(--coral);  }
  .t-gray   { background: #f0f0ed; color: #555; }

  .card { background: var(--surface); border-radius: 9px; padding: 12px 15px; font-size: 13.5px; line-height: 1.65; }
  .card-teal   { border-left: 4px solid var(--teal-mid); border-radius: 0 9px 9px 0; }
  .card-purple { border-left: 4px solid var(--purple);   border-radius: 0 9px 9px 0; }
  .card-amber  { border-left: 4px solid #BA7517;         border-radius: 0 9px 9px 0; }
  .card-coral  { border-left: 4px solid #D85A30;         border-radius: 0 9px 9px 0; }

  .quote {
    background: var(--teal-light); border-left: 5px solid var(--teal-mid);
    border-radius: 0 11px 11px 0; padding: 15px 20px; margin: 10px 0;
    font-size: 16px; line-height: 1.8; color: var(--teal-dark);
  }

  .metric-row { display: flex; gap: 11px; margin: 11px 0; }
  .metric { flex: 1; background: var(--surface); border-radius: 9px; padding: 13px; text-align: center; }
  .mval { display: block; font-size: 25px; font-weight: 700; color: var(--teal); line-height: 1.2; }
  .mlbl { display: block; font-size: 11.5px; color: var(--muted); margin-top: 3px; line-height: 1.4; }

  .pain { background: var(--surface); border-radius: 9px; border-top: 3px solid; padding: 11px 13px; }
  .pain-title { font-size: 13.5px; font-weight: 600; color: var(--text); margin-bottom: 4px; }

  .bq {
    background: #f0f0ed; border-radius: 9px 9px 9px 0;
    padding: 7px 12px; font-size: 13px; color: #333;
    display: inline-block; max-width: 90%; margin-bottom: 5px;
  }
  .ba {
    background: var(--teal-light); border-radius: 9px 9px 0 9px;
    padding: 8px 12px; font-size: 13px; color: var(--teal-dark); display: block; line-height: 1.65;
  }
  .ba-purple {
    background: var(--purple-light); color: var(--purple-dark);
    border-radius: 9px 9px 0 9px;
    padding: 8px 12px; font-size: 13px; display: block; line-height: 1.65;
  }
  .ba-amber {
    background: var(--amber-light); color: var(--amber-dark);
    border-radius: 9px 9px 0 9px;
    padding: 8px 12px; font-size: 13px; display: block; line-height: 1.65;
  }
  .ba-follow {
    background: #d4edda; color: #1a5c2a; border-left: 3px solid #28a745;
    border-radius: 0 9px 9px 0; padding: 6px 12px;
    font-size: 12px; display: block; line-height: 1.6; margin-top: 4px;
  }

  .flow { display: flex; align-items: center; gap: 5px; flex-wrap: wrap; margin: 7px 0; }
  .fstep    { background: var(--surface); border: 1px solid var(--border); border-radius: 7px; padding: 4px 11px; font-size: 12.5px; font-weight: 500; white-space: nowrap; }
  .fstep-hi { background: var(--teal-light); color: var(--teal); border-color: var(--teal-mid); }
  .farrow   { color: var(--faint); font-size: 15px; }

  .vs-row { display: flex; gap: 0; margin: 9px 0; }
  .vs-left  { flex: 1; background: #fff3f0; border-radius: 9px 0 0 9px; padding: 11px 15px; font-size: 13px; line-height: 1.65; }
  .vs-right { flex: 1; background: var(--teal-light); border-radius: 0 9px 9px 0; padding: 11px 15px; font-size: 13px; line-height: 1.65; color: var(--teal-dark); }
  .vs-label { font-size: 11px; font-weight: 700; letter-spacing: 0.05em; margin-bottom: 5px; }

  .lp { display: inline-block; font-size: 10.5px; font-weight: 700; letter-spacing: 0.08em; text-transform: uppercase; padding: 2px 9px; border-radius: 20px; margin-bottom: 5px; }
  .lp-teal   { background: var(--teal-mid); color: white; }
  .lp-purple { background: var(--purple);   color: white; }
  .lp-amber  { background: #BA7517;         color: white; }

  .accent-bar { width: 42px; height: 4px; background: var(--teal-mid); border-radius: 2px; margin: 12px 0; }
  .pg-label   { font-size: 10.5px; font-weight: 700; letter-spacing: 0.1em; color: var(--teal); text-transform: uppercase; margin-bottom: 7px; }
  .footnote   { font-size: 11.5px; color: var(--muted); margin-top: 9px; font-style: italic; }
  .check      { color: var(--teal-mid); font-weight: 700; }
  .step-num   { display: inline-flex; align-items: center; justify-content: center; width: 20px; height: 20px; border-radius: 50%; background: var(--teal-mid); color: white; font-size: 11px; font-weight: 700; margin-right: 5px; flex-shrink: 0; }
  .divider    { border: none; border-top: 1px solid var(--border); margin: 12px 0; }

  .chip { display: inline-block; font-size: 11.5px; font-weight: 700; padding: 3px 13px; border-radius: 20px; margin-bottom: 10px; }
  .chip-status   { background: #e8f4fd; color: #185FA5; }
  .chip-pain     { background: #fdecea; color: #9b2c2c; }
  .chip-solution { background: var(--teal-light); color: var(--teal); }
  .chip-system   { background: var(--purple-light); color: var(--purple); }
  .chip-conclude { background: var(--amber-light); color: var(--amber); }
---

<!-- ══════════════════════════════ 01 封面 ══════════════════════════════ -->

# 富邦年報 AI 助理，讓富邦與社會共榮

<div class="accent-bar"></div>

<div style="font-size: 19px; font-weight: 600; color: var(--teal-mid); margin-bottom: 10px;">
以 RAG × 人文關懷，打造富邦金控年報智慧對話系統
</div>

<div style="font-size: 14.5px; color: var(--muted); line-height: 1.8; max-width: 700px;">
以 2024 年富邦金控股東會年報為知識核心，從現狀調查出發，精確定義三類使用者的痛點，設計融合三層人文關懷的 RAG 系統，讓年報從「被動存在的文件」成為「主動回應需求的對話助理」。
</div>

<div style="margin-top: 26px; display: flex; gap: 7px; flex-wrap: wrap;">
  <span class="tag t-teal">大語言模型運用</span>
  <span class="tag t-purple">RAG 系統設計</span>
  <span class="tag t-amber">人文關懷設計</span>
  <span class="tag t-coral">金融業落地場景</span>
</div>

<div style="position: absolute; bottom: 46px; left: 58px; font-size: 13px; color: var(--muted);">
  <strong>敘事流程：</strong>
  <span style="color:#185FA5;">現狀調查</span> →
  <span style="color:#9b2c2c;">痛點定義</span> →
  <span style="color:var(--teal);">解決方案</span> →
  <span style="color:var(--purple);">系統構造</span> →
  <span style="color:var(--amber);">結論</span>
</div>
<div style="position: absolute; bottom: 46px; right: 58px; font-size: 11.5px; color: var(--faint);">富邦金控數據科學組 MA 甄選 ｜ 莊昊耘 Hao-Yun Chuang</div>

---

<!-- ══════════════════════════════ 02 現狀調查（合併） ══════════════════════════════ -->

<div class="chip chip-status">現狀調查</div>

## 富邦的公益規模，與年報的溝通現狀

<div class="metric-row">
  <div class="metric"><span class="mval">4.98億</span><span class="mlbl">2024 捐贈總額<br>第 217 頁</span></div>
  <div class="metric"><span class="mval">177,915</span><span class="mlbl">助學受惠學生<br>第 222 頁</span></div>
  <div class="metric"><span class="mval">9.8萬棵</span><span class="mlbl">Run For Green 植樹<br>第 222 頁</span></div>
  <div class="metric"><span class="mval">138,021</span><span class="mlbl">急難救助個案<br>第 222 頁</span></div>
</div>

<div class="two-col" style="margin-top: 8px;">
<div>

**年報結構現實**
- 272 頁，公益資訊僅集中於 §4.13（第215–224頁），佔全書不到 4%
- 主要閱讀對象為法人投資人與法遵人員，格式以揭露為主
- 現有溝通管道：PDF 下載、靜態官網、IR 人工回覆

</div>
<div>

**誰需要這些資訊，卻找不到入口？**

<div class="pain" style="border-top-color: #1D9E75; margin-bottom: 7px;">
  <div class="pain-title">NGO / 公益團體</div>
  <div style="font-size: 12.5px; color: var(--muted);">想找企業合作，五個基金會各自官網，無整合入口，合作門檻完全不透明。</div>
</div>
<div class="pain" style="border-top-color: #7F77DD; margin-bottom: 7px;">
  <div class="pain-title">媒體記者 / ESG 分析師</div>
  <div style="font-size: 12.5px; color: var(--muted);">截稿壓力下需要精確數字與出處，IR 回覆慢，往往略過準確數字。</div>
</div>
<div class="pain" style="border-top-color: #BA7517;">
  <div class="pain-title">一般消費者 / 潛在客戶</div>
  <div style="font-size: 12.5px; color: var(--muted);">對銀行社會形象有興趣，但 272 頁年報與他們之間存在高牆。</div>
</div>

</div>
</div>

---

<!-- ══════════════════════════════ 03 痛點①：三類使用者 ══════════════════════════════ -->

<div class="chip chip-pain">痛點定義 01 / 02</div>

## 三類使用者，三種不同的痛

<div class="three-col">

<div class="col">
  <div style="margin-bottom: 6px;"><span class="tag t-teal">NGO / 公益團體</span></div>
  <div class="pain" style="border-top-color: #1D9E75;">
    <div class="pain-title">合作門檻不透明</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">哪個基金會對口、怎麼談、有沒有規模門檻——只能靠人脈打聽或寄冷門信等 1–2 週。</div>
  </div>
  <div class="pain" style="border-top-color: #1D9E75;">
    <div class="pain-title">資訊分散無整合入口</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">五個基金會各自官網，議題重疊、格式各異，難以評估契合度。</div>
  </div>
</div>

<div class="col">
  <div style="margin-bottom: 6px;"><span class="tag t-purple">媒體 / 分析師</span></div>
  <div class="pain" style="border-top-color: #7F77DD;">
    <div class="pain-title">引用無出處是法遵風險</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">媒體引用不準確的 ESG 數字，IR 部門須澄清，嚴重時影響 DJSI、MSCI 等國際評等。</div>
  </div>
  <div class="pain" style="border-top-color: #7F77DD;">
    <div class="pain-title">截稿壓力 vs 人工翻找</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">記者無法等 IR 回覆，往往略過精確數字，改用二手資料，傳播失真。</div>
  </div>
</div>

<div class="col">
  <div style="margin-bottom: 6px;"><span class="tag t-amber">消費者 / 大眾</span></div>
  <div class="pain" style="border-top-color: #BA7517;">
    <div class="pain-title">數字有重量，卻缺感知</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">「498,005,819 元」精確，但抽象；「陪伴 13 萬個家庭」才有情感重量。年報語言與大眾之間有距離。</div>
  </div>
  <div class="pain" style="border-top-color: #BA7517;">
    <div class="pain-title">品牌精神難具體感受</div>
    <div style="font-size: 12.5px; color: var(--muted); line-height: 1.6;">「正向力量 成就可能」需要具體故事承載，消費者才能真正感受到它的存在。</div>
  </div>
</div>

</div>

---

<!-- ══════════════════════════════ 04 痛點②：PDF 技術痛點 ══════════════════════════════ -->

<div class="chip chip-pain">痛點定義 02 / 02</div>

## 年報 PDF 本身的技術痛點

<div class="card card-teal" style="margin-bottom: 14px; font-size: 13.5px;">
  年報為 Adobe InDesign 排版輸出的高度結構化文件。直接使用 <code>pdftotext → 固定長度 chunking</code> 的標準做法，在這份年報上會產生三類具體失敗，以下均為實際解析所得，非理論推演。
</div>

<div class="three-col">
<div class="col">
  <div class="lp lp-teal">技術痛點 01</div>
  <div style="font-weight: 600; font-size: 14px; margin-bottom: 5px;">CID 字體編碼異常</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    Adobe-CNS1 字體映射問題導致 <code>pdftotext</code> 輸出 <code>(cid:3712)</code> 等亂碼，無法直接用於向量化。影響年報多頁內文，含部分公益章節。
  </div>
</div>

<div class="col">
  <div class="lp lp-purple">技術痛點 02</div>
  <div style="font-weight: 600; font-size: 14px; margin-bottom: 5px;">表格數字語境依賴</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    「177,915」單獨出現毫無意義，必須與「用愛心做朋友助學活動受惠學生人次」綁定。固定長度 chunking 會切斷此對應關係。影響第 217、222–224 頁捐贈明細表。
  </div>
</div>

<div class="col">
  <div class="lp lp-amber">技術痛點 03</div>
  <div style="font-weight: 600; font-size: 14px; margin-bottom: 5px;">章節跨頁結構</div>
  <div class="card" style="font-size: 13px; line-height: 1.7;">
    §4.13 企業責任橫跨第 215–224 頁，中間夾雜員工訓練表格，固定 size chunking 會混淆語意邊界，令「教育推廣」與「員工福利」同入一個 chunk。
  </div>
</div>
</div>

---

<!-- ══════════════════════════════ 05 解決方案（合併） ══════════════════════════════ -->

<div class="chip chip-solution">解決方案</div>

## 「正向力量探索助理」：設計原則與三層關懷

<div class="quote" style="font-size: 15px; margin-bottom: 14px;">
「技術讓答案準確，人文關懷讓答案有用。系統要知道年報說了什麼，也要知道對話那端的人需要什麼。」
</div>

<div class="three-col" style="margin-top: 0;">

<div class="col">
  <div class="lp lp-teal">Layer 1</div>
  <div style="font-size: 14px; font-weight: 600; margin-bottom: 5px;">語氣設計</div>
  <div style="font-size: 12.5px; color: var(--muted); margin-bottom: 6px;">解決：數字缺乏溫度 ／ 品牌精神難感受</div>
  <div class="card card-teal" style="font-size: 12.5px; line-height: 1.65;">
    System Prompt 改寫，數字轉主詞句型，答案末尾加邀請語，措辭傳遞「正向力量」精神。所有回答均啟動。
  </div>
</div>

<div class="col">
  <div class="lp lp-purple">Layer 2</div>
  <div style="font-size: 14px; font-weight: 600; margin-bottom: 5px;">對象感知路由</div>
  <div style="font-size: 12.5px; color: var(--muted); margin-bottom: 6px;">解決：同一問題對不同身份需不同答案</div>
  <div class="card card-purple" style="font-size: 12.5px; line-height: 1.65;">
    對話開場身份確認，切換三套 Prompt 模板：引導行動型（NGO）／ 嚴謹引用型（媒體）／ 故事敘述型（消費者）。
  </div>
</div>

<div class="col">
  <div class="lp lp-amber">Layer 3</div>
  <div style="font-size: 14px; font-weight: 600; margin-bottom: 5px;">意圖探測追問</div>
  <div style="font-size: 12.5px; color: var(--muted); margin-bottom: 6px;">解決：問題背後有未說出口的需求</div>
  <div class="card card-amber" style="font-size: 12.5px; line-height: 1.65;">
    Prompt 指令：回答後判斷是否有隱性需求。若有，主動追問一次——只一次，語氣為邀請而非詢問。
  </div>
</div>

</div>

---

<!-- ══════════════════════════════ 06 系統構造①：Pipeline + 幻覺防護 ══════════════════════════════ -->

<div class="chip chip-system">系統構造 01 / 04</div>

## 技術架構與幻覺防護

<div class="flow" style="margin-bottom: 14px;">
  <span class="fstep">PDF 解析</span><span class="farrow">→</span>
  <span class="fstep">Semantic Chunking</span><span class="farrow">→</span>
  <span class="fstep">Hybrid 檢索</span><span class="farrow">→</span>
  <span class="fstep">Reranking</span><span class="farrow">→</span>
  <span class="fstep fstep-hi">人文關懷 Prompt</span><span class="farrow">→</span>
  <span class="fstep fstep-hi">附頁碼輸出 + 數字驗證</span>
</div>

<div class="two-col">
<div>

**解析與檢索層**（對應三項技術痛點）

<div class="card" style="font-size: 13px; margin-bottom: 7px;">
  <code>pdftoppm</code> 對 CID 字體頁面 rasterize，視覺解析取代文字提取（對應痛點 01）
</div>
<div class="card" style="font-size: 13px; margin-bottom: 7px;">
  <code>pdfplumber</code> 表格整行提取，保留數字與標籤的對應關係（對應痛點 02）
</div>
<div class="card" style="font-size: 13px;">
  以標題層級為語意邊界切割 chunk，每個 chunk 攜帶 <code>章節 + 頁碼</code> Metadata（對應痛點 03）<br>
  Hybrid Search（向量 + BM25）+ Cross-Encoder Reranking
</div>

</div>
<div>

**幻覺防護三層**（對應「引用無出處」痛點）

<div class="card card-teal" style="font-size: 13px; margin-bottom: 7px;">
  <span class="step-num">1</span><strong>Prompt 約束</strong>：僅使用 context 回答，找不到時明確告知無法回答
</div>
<div class="card card-purple" style="font-size: 13px; margin-bottom: 7px;">
  <span class="step-num">2</span><strong>數字錨點驗證</strong>：答案中所有數字回頭比對原始 PDF 對應頁面，若字串不存在則標記「需人工確認」
</div>
<div class="card card-amber" style="font-size: 13px;">
  <span class="step-num">3</span><strong>頁碼強制輸出</strong>：每則答案末尾附「依據年報第 X 頁，§X.X 節」，讓引用者有據可查
</div>

<div class="footnote">Accuracy 評估：數字題 Exact Match ／ 敘述題 Semantic Similarity（cosine ≥ 0.85）分開報告</div>

</div>
</div>

---

<!-- ══════════════════════════════ 07 系統構造②：Layer 1 語氣設計 ══════════════════════════════ -->

<div class="chip chip-system">系統構造 02 / 04</div>

## Layer 1 語氣設計 × 解決「感知斷層」

<div style="margin-bottom: 10px;">
  <span class="tag t-teal">痛點對應</span>
  <span style="font-size: 13.5px; color: var(--muted);">數字有重量但缺乏感知 ／ 品牌精神「正向力量」難以具體傳遞</span>
</div>

**同樣的數字，說法不同，重量完全不同**

<div class="vs-row" style="margin-bottom: 13px;">
  <div class="vs-left">
    <div class="vs-label" style="color:#9b2c2c;">一般 RAG 輸出</div>
    急難救助投入 4,371 萬元，受惠個案 138,021 人次。（第222頁）
  </div>
  <div class="vs-right">
    <div class="vs-label" style="color:var(--teal);">Layer 1 語氣設計後</div>
    富邦 2024 年透過急難救助，<strong>陪伴了 13 萬個正在度過難關的家庭</strong>，累計投入 4,371 萬元。如果你想進一步了解特定議題的支援方式，我可以幫你找更多。（依據年報第 222 頁）
  </div>
</div>

**Prompt 三條核心規則**

<div class="three-col" style="margin-top: 0;">
  <div class="card" style="font-size: 13px;">
    <strong>數字給主詞</strong><br>
    「138,021 人次」→「13 萬個家庭」<br>
    人次是統計數字，家庭是真實存在的人
  </div>
  <div class="card" style="font-size: 13px;">
    <strong>答案有邀請</strong><br>
    不停留在陳述事實，結尾引導下一步行動，讓對話有繼續的空間
  </div>
  <div class="card" style="font-size: 13px;">
    <strong>措辭傳精神</strong><br>
    選用「陪伴」而非「服務」，細微差異傳遞「正向力量」的品牌態度
  </div>
</div>

---

<!-- ══════════════════════════════ 08 系統構造③：Layer 2 路由 ══════════════════════════════ -->

<div class="chip chip-system">系統構造 03 / 04</div>

## Layer 2 對象感知路由 × 解決「對象模糊」

<div style="margin-bottom: 10px;">
  <span class="tag t-purple">痛點對應</span>
  <span style="font-size: 13.5px; color: var(--muted);">NGO、媒體、消費者問同一個問題，需要完全不同格式的答案</span>
</div>

**對話開場設計**

<div style="margin: 8px 0 12px;">
  <div class="bq">您好，我是富邦正向力量助理。請問您今天是想了解<strong>合作機會</strong>、<strong>查詢相關數據</strong>，還是<strong>認識富邦在做的事</strong>？</div>
</div>

<div class="three-col">
  <div style="background: var(--teal-light); border-radius: 9px; padding: 13px;">
    <div style="font-size: 10.5px; font-weight: 700; color: var(--teal); margin-bottom: 5px;">選 A｜合作機會</div>
    <div style="font-size: 13.5px; font-weight: 600; margin-bottom: 5px;">引導行動型 Prompt</div>
    <div style="font-size: 12px; color: var(--teal-dark); line-height: 1.65;">
      輸出：計畫名稱 + 歷年規模 + 聯絡窗口<br>
      語氣：具體，有行動指引<br>
      Layer 3：詢問合作方向
    </div>
  </div>
  <div style="background: var(--purple-light); border-radius: 9px; padding: 13px;">
    <div style="font-size: 10.5px; font-weight: 700; color: var(--purple); margin-bottom: 5px;">選 B｜查詢數據</div>
    <div style="font-size: 13.5px; font-weight: 600; margin-bottom: 5px;">嚴謹引用型 Prompt</div>
    <div style="font-size: 12px; color: var(--purple-dark); line-height: 1.65;">
      輸出：精確數字 + 頁碼 + 可引用格式<br>
      語氣：嚴謹，不加溫暖修辭<br>
      Layer 3：通常不觸發
    </div>
  </div>
  <div style="background: var(--amber-light); border-radius: 9px; padding: 13px;">
    <div style="font-size: 10.5px; font-weight: 700; color: var(--amber); margin-bottom: 5px;">選 C｜認識富邦</div>
    <div style="font-size: 13.5px; font-weight: 600; margin-bottom: 5px;">故事敘述型 Prompt</div>
    <div style="font-size: 12px; color: var(--amber-dark); line-height: 1.65;">
      輸出：故事化敘述 + 感知數字 + 品牌精神<br>
      語氣：溫暖，有畫面感<br>
      Layer 3：引導深入感興趣方向
    </div>
  </div>
</div>

<div class="footnote" style="margin-top: 10px;">同一個知識庫，三種 Prompt 模板，技術成本低，使用者體驗差異顯著。</div>

---

<!-- ══════════════════════════════ 09 系統構造④：Layer 3 意圖探測 ══════════════════════════════ -->

<div class="chip chip-system">系統構造 04 / 04</div>

## Layer 3 意圖探測 × 解決「需求未被說出口」

<div style="margin-bottom: 10px;">
  <span class="tag t-coral">痛點對應</span>
  <span style="font-size: 13.5px; color: var(--muted);">問題的表面是一件事，背後往往是另一個更重要的問題</span>
</div>

<div class="two-col">
<div>

**Prompt 核心指令**

<div class="card card-amber" style="font-size: 13px; line-height: 1.7; margin-bottom: 10px;">
回答使用者問題後，判斷此問題是否存在<strong>未說出口的需求</strong>。若判斷有，主動追問一次釐清——<strong>只一次</strong>，語氣為邀請。若判斷無，以邀請語結尾即可。
</div>

**觸發邏輯範例**

| 問法 | 推測隱性需求 | 追問設計 |
|------|------------|---------|
| 「有在幫助老人嗎？」 | 為家人找資源 | 長者本人 or 照顧者？ |
| 「支持環保嗎？」 | 尋求合作 | 了解 or 合作機會？ |
| 「偏鄉教育有什麼？」 | NGO 或教師 | 哪個年齡層 / 縣市？ |

</div>
<div>

**示範對話**

<div class="bq">「富邦有在幫助老人嗎？」</div>
<div class="ba" style="margin-bottom: 5px;">
  有的。台北富邦銀行基金會長期投入長者身心健康，2024 年舉辦「富邦甲子盃」桌球及圍棋大賽、「富邦銀髮音樂陪伴計畫」，並為照顧者設計喘息之旅活動。（依據年報第 223 頁，§4.13.3）
</div>
<div class="ba-follow">↳ 請問你是在為某位長者尋找參與活動的機會，還是想了解與富邦合作推廣長者服務的可能性？我可以幫你找更符合需求的資訊。</div>

<div class="card" style="margin-top: 10px; font-size: 13px;">
  <strong>設計邊界：</strong>若使用者不回應追問，系統不再追問，對話保持自然。
</div>

</div>
</div>

---

<!-- ══════════════════════════════ 10 場景驗證①：NGO ══════════════════════════════ -->

<div class="chip chip-system">場景驗證 01 / 03</div>

## 場景一：NGO 公益合作媒合

<div style="margin-bottom: 9px;">
  <span class="tag t-teal">Layer 2 路由 A</span>
  <span class="tag t-teal">Layer 3 意圖追問</span>
  <span class="tag t-teal">幻覺防護啟動</span>
</div>

<div class="two-col">
<div>

**使用者痛點**
- 哪個基金會對口、門檻是什麼，全靠人脈
- 平均等待 IR 回覆 1–2 週

**系統回應邏輯**

<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">1</span>
  <div style="font-size:13px;">Layer 2 偵測「合作機會」，切換至引導行動型 Prompt</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">2</span>
  <div style="font-size:13px;">Layer 1 將「177,915 人次」轉為「177,915 位學生」，對話有人的感覺</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">3</span>
  <div style="font-size:13px;">Layer 3 探測到合作需求，追問一次釐清學生年齡層</div>
</div>

<div class="footnote">✓ 降低 IR/PR 人工接洽成本，讓 5 億公益資源找到更多對口夥伴</div>

</div>
<div>

<div class="bq">「我們是偏鄉教育 NPO，想找企業合作，富邦有相關計畫嗎？」</div>
<div class="ba">
  富邦文教基金會深耕兒少教育逾 30 年，旗下「好正學堂」專門媒合社企與 NPO，透過不同場域的親身體驗，引發年輕世代對永續議題的關注與行動。2024 年助學捐款達 1 億元，陪伴了 177,915 位學生。（依據年報第 222 頁，§4.13.1）
</div>
<div class="ba-follow">↳ 請問你們的計畫主要面向哪個年齡層的學生？這樣我可以幫你找更對口的合作窗口。</div>

</div>
</div>

---

<!-- ══════════════════════════════ 11 場景驗證②：ESG ══════════════════════════════ -->

<div class="chip chip-system">場景驗證 02 / 03</div>

## 場景二：ESG 數字即時查詢

<div style="margin-bottom: 9px;">
  <span class="tag t-purple">Layer 2 路由 B</span>
  <span class="tag t-purple">幻覺防護全啟動</span>
  <span class="tag t-purple">Layer 1 嚴謹模式</span>
</div>

<div class="two-col">
<div>

**使用者痛點**
- 截稿壓力下需要精確數字 + 出處
- 引用錯誤是媒體與銀行雙方的法遵風險

**系統回應邏輯**

<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">1</span>
  <div style="font-size:13px;">Layer 2 偵測「查詢數據」，切換至嚴謹引用型 Prompt，省略溫暖修辭</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">2</span>
  <div style="font-size:13px;">數字錨點驗證確認每個數字均存在於被引用頁面</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">3</span>
  <div style="font-size:13px;">強制輸出頁碼，記者可直接寫「依富邦年報第 222 頁」，引用有依據</div>
</div>

<div class="footnote">✓ 支援 DJSI、MSCI 評等資料提交；媒體引用有頁碼，降低公關風險</div>

</div>
<div>

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

<!-- ══════════════════════════════ 12 場景驗證③：品牌 ══════════════════════════════ -->

<div class="chip chip-system">場景驗證 03 / 03</div>

## 場景三：品牌形象大眾溝通

<div style="margin-bottom: 9px;">
  <span class="tag t-amber">Layer 2 路由 C</span>
  <span class="tag t-amber">Layer 1 全力發揮</span>
  <span class="tag t-amber">Layer 3 引導深入</span>
</div>

<div class="two-col">
<div>

**使用者痛點**
- 「4.98億」對一般人是抽象數字
- 消費者無法讀 272 頁年報，資訊形同不存在

**系統回應邏輯**

<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">1</span>
  <div style="font-size:13px;">Layer 2 切換至故事敘述型 Prompt，數字背後說人，說地方</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">2</span>
  <div style="font-size:13px;">Layer 1：「9.8 萬棵樹」加上「長在全台 8 個縣市」，數字有了地理感</div>
</div>
<div style="display:flex; gap:5px; align-items:flex-start; margin: 7px 0;">
  <span class="step-num">3</span>
  <div style="font-size:13px;">Layer 3 追問消費者最有共鳴的方向，引導深入了解</div>
</div>

<div class="footnote">✓ 年報數字成為品牌情感素材，可整合至官網、LINE Bot、Fubon+ App</div>

</div>
<div>

<div class="bq">「富邦除了是銀行，還做了什麼對社會有意義的事？」</div>
<div class="ba-amber">
  富邦每年贊助四大馬拉松，跑者每跑 40 公里，富邦就在台灣土地上種下一棵樹——截至 2024 年，這些樹已有 9.8 萬棵，長在全台 8 個縣市。<br><br>
  同一年，富邦慈善基金會陪伴了 13 萬個正在度過困難的家庭，也幫助了將近 18 萬名學生繼續就學。<br><br>
  這就是「正向力量 成就可能」——每一棵樹、每一個孩子，都是真實的行動。（依據年報第 222 頁）
</div>
<div class="ba-follow">↳ 你對哪個方向最有共鳴？環境、教育，還是弱勢關懷？</div>

</div>
</div>

---

<!-- ══════════════════════════════ 13 三場景整合對照 ══════════════════════════════ -->

<div class="chip chip-system">場景整合</div>

## 同一套系統，感知身份，給出對的答案

<div class="quote" style="font-size: 14.5px; margin-bottom: 14px;">
同一個知識庫，系統根據「你是誰、你需要什麼、你問題背後的問題是什麼」給出不同的答案。三層關懷共用一套技術底層，無需維護三套系統。
</div>

<table>
<tr>
  <th>維度</th>
  <th>場景一：NGO</th>
  <th>場景二：媒體 / 分析師</th>
  <th>場景三：消費者</th>
</tr>
<tr>
  <td><strong>Layer 1 語氣</strong></td>
  <td>具體 + 引導行動</td>
  <td>嚴謹 + 無修辭</td>
  <td>溫暖 + 故事性</td>
</tr>
<tr>
  <td><strong>Layer 2 路由</strong></td>
  <td>引導行動型模板</td>
  <td>嚴謹引用型模板</td>
  <td>故事敘述型模板</td>
</tr>
<tr>
  <td><strong>Layer 3 追問</strong></td>
  <td>釐清合作方向</td>
  <td>通常不觸發</td>
  <td>引導深入興趣</td>
</tr>
<tr>
  <td><strong>數字呈現</strong></td>
  <td>規模感 + 聯絡入口</td>
  <td>精確值 + 頁碼</td>
  <td>故事化 + 情感重量</td>
</tr>
<tr>
  <td><strong>解決的核心痛點</strong></td>
  <td>合作門檻不透明</td>
  <td>引用無出處風險</td>
  <td>數字缺乏感知</td>
</tr>
</table>

---

<!-- ══════════════════════════════ 14 結論 ══════════════════════════════ -->

<div class="chip chip-conclude">結論</div>

## 痛點 × 解法對照，以及落地路徑

<table style="margin-bottom: 14px;">
<tr>
  <th>痛點</th>
  <th>對應使用者</th>
  <th>系統解法</th>
  <th>核心機制</th>
</tr>
<tr><td>合作門檻不透明</td><td>NGO</td><td>Layer 2 路由 A + Layer 3 追問</td><td>身份路由 + 意圖探測</td></tr>
<tr><td>引用無出處</td><td>媒體 / 分析師</td><td>幻覺防護三層 + 頁碼強制輸出</td><td>數字錨點驗證</td></tr>
<tr><td>數字缺乏感知</td><td>消費者</td><td>Layer 1 語氣設計</td><td>System Prompt 改寫</td></tr>
<tr><td>CID 字體亂碼</td><td>（技術）</td><td>pdftoppm 視覺解析</td><td>Rasterize + 視覺提取</td></tr>
<tr><td>表格語境切斷</td><td>（技術）</td><td>pdfplumber 整行保留</td><td>Table-aware extraction</td></tr>
<tr><td>章節跨頁混淆</td><td>（技術）</td><td>標題邊界 Semantic Chunking</td><td>Metadata + 標題切割</td></tr>
</table>

<div class="two-col">
<div>
  <div class="card card-teal" style="font-size: 13px; margin-bottom: 7px;"><strong>短期：</strong>嵌入富邦官網 ESG 頁面，作為「正向力量探索助理」對外入口</div>
  <div class="card card-purple" style="font-size: 13px;"><strong>中期：</strong>整合至 LINE Bot / Fubon+ 行動銀行，擴大觸及至消費者日常</div>
</div>
<div>
  <div class="quote" style="font-size: 14px; margin: 0; padding: 14px 18px;">
    「富邦的公益投入不缺數字，缺的是讓對的人在對的時機，以對的方式找到這些數字的入口。這套系統，就是那個入口。」
  </div>
</div>
</div>

---

<!-- ══════════════════════════════ 15 英文摘要 ══════════════════════════════ -->

# Fubon Annual Report RAG System
## *Accurate Answers with Human Warmth*

<div class="accent-bar"></div>

**Problem** — Fubon's 2024 Annual Report (272 pages) contains NT$498M in charitable contributions, 177,915 student beneficiaries, and 98,000 trees planted across Taiwan. Yet NGOs cannot find collaboration partners, journalists cannot cite reliable data under deadline pressure, and consumers cannot feel the human impact behind the numbers.

**Solution** — A RAG system with three-layer humanistic care design, turning a passive PDF into a responsive knowledge assistant.

| Layer | Design | Solves |
|-------|--------|--------|
| Layer 1 | Tone Design — numbers become subject-led sentences | Statistics without emotional resonance |
| Layer 2 | Identity Routing — 3 Prompt templates for NGO / media / public | One answer format cannot serve all users |
| Layer 3 | Intent Detection — one proactive follow-up question | Unstated needs go unaddressed |

**Technical Stack** — `pdfplumber` table extraction + `pdftoppm` for CID font pages + Semantic Chunking by heading boundary + Hybrid Search (vector + BM25) + Cross-Encoder Reranking + three-layer hallucination defense (Prompt constraint / numeric anchor string validation / mandatory page citation).

**Core Thesis** — Technology makes answers accurate. Humanistic care makes them meaningful.