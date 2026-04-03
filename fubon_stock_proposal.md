---
marp: true
theme: default
paginate: true
nav_exclude: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&family=Inter:wght@400;600;700;800&display=swap');

  * { box-sizing: border-box; }

  section {
    font-family: 'Noto Sans TC', 'Inter', sans-serif;
    background: #F7F9FC;
    color: #1A2340;
    padding: 48px 60px;
    font-size: 15px;
    line-height: 1.6;
  }

  /* ── Cover ── */
  section.cover {
    background: linear-gradient(135deg, #0B2545 0%, #1A4A7A 55%, #0E7490 100%);
    color: #fff;
    padding: 72px 80px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
  section.cover .tag {
    display: inline-block;
    background: rgba(14,116,144,0.5);
    border: 1px solid rgba(14,116,144,0.9);
    border-radius: 6px;
    padding: 5px 16px;
    font-size: 13px;
    font-weight: 700;
    color: #7DD3FC;
    margin-bottom: 28px;
    letter-spacing: 1px;
  }
  section.cover h1 {
    font-size: 44px;
    font-weight: 900;
    line-height: 1.25;
    margin: 0 0 18px;
    color: #fff;
  }
  section.cover p { font-size: 17px; color: rgba(255,255,255,0.7); margin: 0; }
  section.cover .meta {
    margin-top: 44px;
    font-size: 14px;
    color: rgba(255,255,255,0.45);
    border-top: 1px solid rgba(255,255,255,0.15);
    padding-top: 18px;
  }
  section.cover::after { color: rgba(255,255,255,0.3) !important; }

  /* ── Closing ── */
  section.closing {
    background: linear-gradient(135deg, #0B2545 0%, #1A4A7A 60%, #0E7490 100%);
    color: #fff;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  section.closing h1 { color: #fff; font-size: 38px; margin-bottom: 16px; }
  section.closing p { color: rgba(255,255,255,0.68); font-size: 16px; max-width: 560px; margin: 0; }
  section.closing::after { color: rgba(255,255,255,0.3) !important; }

  /* ── Typography ── */
  h1 { font-size: 28px; font-weight: 800; color: #0B2545; margin: 0 0 22px; }
  h2 { font-size: 24px; font-weight: 800; color: #0B2545; margin: 0 0 18px; }
  h3 { font-size: 15px; font-weight: 700; color: #1A4A7A; margin: 0 0 7px; }
  p  { margin: 0 0 10px; }
  ul { padding-left: 20px; margin: 0; }
  li { margin-bottom: 4px; font-size: 13px; }

  /* ── Cards ── */
  .cg { display: grid; gap: 14px; }
  .cg.c2 { grid-template-columns: 1fr 1fr; }
  .cg.c3 { grid-template-columns: 1fr 1fr 1fr; }
  .cg.c4 { grid-template-columns: 1fr 1fr 1fr 1fr; }

  .card {
    background: #fff;
    border-radius: 10px;
    padding: 18px 20px;
    border-left: 4px solid #0E7490;
    box-shadow: 0 2px 10px rgba(11,37,69,0.07);
  }
  .card.blue   { border-left-color: #1A4A7A; }
  .card.teal   { border-left-color: #0E7490; }
  .card.green  { border-left-color: #059669; }
  .card.amber  { border-left-color: #D97706; }
  .card.red    { border-left-color: #DC2626; }
  .card.purple { border-left-color: #7C3AED; }
  .card h3 { font-size: 14px; margin-bottom: 6px; }
  .card p, .card ul { font-size: 13px; color: #374151; margin: 0; }

  /* ── Steps ── */
  .steps { display: flex; gap: 8px; align-items: stretch; }
  .step {
    flex: 1;
    background: #fff;
    border-radius: 9px;
    padding: 14px 12px;
    text-align: center;
    box-shadow: 0 2px 8px rgba(11,37,69,0.07);
    position: relative;
  }
  .step .ico { font-size: 24px; margin-bottom: 6px; }
  .step h3 { font-size: 12px; margin-bottom: 4px; color: #0B2545; }
  .step p  { font-size: 11px; color: #6B7280; margin: 0; }
  .step::after {
    content: '→';
    position: absolute;
    right: -10px;
    top: 50%;
    transform: translateY(-50%);
    color: #94A3B8;
    font-size: 16px;
    z-index: 1;
  }
  .step:last-child::after { display: none; }

  /* ── Highlight bar ── */
  .hbar {
    background: linear-gradient(90deg, #0B2545, #0E7490);
    color: #fff;
    border-radius: 8px;
    padding: 12px 20px;
    font-size: 13px;
    font-weight: 600;
    margin-bottom: 16px;
  }

  /* ── Stat blocks ── */
  .stat {
    text-align: center;
    background: #fff;
    border-radius: 10px;
    padding: 20px 12px;
    box-shadow: 0 2px 10px rgba(11,37,69,0.07);
  }
  .stat .n { font-size: 38px; font-weight: 900; color: #0E7490; line-height: 1; }
  .stat .l { font-size: 12px; color: #6B7280; margin-top: 6px; }

  /* ── Tables ── */
  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 2px 8px rgba(11,37,69,0.07);
  }
  thead tr { background: #0B2545; color: #fff; }
  thead th { padding: 10px 14px; text-align: left; font-size: 12px; font-weight: 600; }
  tbody tr { background: #fff; }
  tbody tr:nth-child(even) { background: #F0F7FF; }
  tbody td { padding: 9px 14px; border-bottom: 1px solid #E5EAF2; font-size: 12.5px; }

  /* ── Code ── */
  pre {
    background: #0F172A;
    border-radius: 8px;
    padding: 16px 20px;
    font-size: 11.5px;
    line-height: 1.55;
    color: #E2E8F0;
    margin: 0;
    overflow: hidden;
  }

  /* ── Badge ── */
  .bdg {
    display: inline-block;
    padding: 2px 10px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
  }
  .bdg.bl { background: #DBEAFE; color: #1D4ED8; }
  .bdg.tl { background: #CFFAFE; color: #0E7490; }
  .bdg.gr { background: #D1FAE5; color: #065F46; }
  .bdg.am { background: #FEF3C7; color: #92400E; }
  .bdg.rd { background: #FEE2E2; color: #991B1B; }

  /* ── Two-col layout ── */
  .cols { display: grid; gap: 20px; }
  .cols.c2 { grid-template-columns: 1fr 1fr; }
  .cols.c5545 { grid-template-columns: 55fr 45fr; }

  /* ── Arch box ── */
  .abox {
    background: #fff;
    border: 1.5px solid #CBD5E1;
    border-radius: 8px;
    padding: 11px 16px;
    font-size: 12.5px;
    margin-bottom: 9px;
  }
  .abox strong { color: #0B2545; font-size: 13px; }

  /* ── TOC list ── */
  .toc { display: grid; grid-template-columns: 1fr 1fr; gap: 10px 40px; margin-top: 16px; }
  .toc-item { display: flex; align-items: baseline; gap: 10px; padding: 8px 0; border-bottom: 1px solid #E5EAF2; font-size: 14px; }
  .toc-num { font-size: 13px; font-weight: 800; color: #0E7490; min-width: 28px; }
---

<!-- _class: cover -->

<div class="tag">FUBON FINANCIAL × LLM SYSTEM DESIGN</div>

# 基於 LLM 的個股<br>理財助理系統設計

**題目二｜技術設計報告**

<div class="meta">
系統架構 ｜ 問題分類 ｜ Prompt 設計 ｜ 資料品質控制 ｜ 用戶體驗 ｜ 五大創新功能<br><br>
2026 富邦證券數據科學組 MA 甄選 ｜ 莊昊耘 Hao-Yun Chuang
</div>

---

# 目錄

<div class="toc">
<div class="toc-item"><span class="toc-num">01</span>核心挑戰與設計目標</div>
<div class="toc-item"><span class="toc-num">02</span>整體系統架構</div>
<div class="toc-item"><span class="toc-num">03</span>用戶問題五大分類</div>
<div class="toc-item"><span class="toc-num">04</span>網路資訊搜尋策略</div>
<div class="toc-item"><span class="toc-num">05</span>Prompt 工程設計</div>
<div class="toc-item"><span class="toc-num">06</span>三層過濾 + Confidence Gating</div>
<div class="toc-item"><span class="toc-num">07</span>數字安全機制</div>
<div class="toc-item"><span class="toc-num">08</span>用戶體驗設計</div>
<div class="toc-item"><span class="toc-num">09</span>合規護欄設計</div>
<div class="toc-item"><span class="toc-num">10</span>創新功能一：Watchlist 推送</div>
<div class="toc-item"><span class="toc-num">11</span>創新功能二：多輪對話記憶</div>
<div class="toc-item"><span class="toc-num">12</span>創新功能三：可信度標籤</div>
<div class="toc-item"><span class="toc-num">13</span>創新功能四：即時事件警報</div>
<div class="toc-item"><span class="toc-num">14</span>創新功能五：個股比較模式</div>
<div class="toc-item"><span class="toc-num">15</span>技術選型建議</div>
<div class="toc-item"><span class="toc-num">16</span>非功能性需求指標</div>
<div class="toc-item"><span class="toc-num">17</span>風險對策與成效指標</div>
<div class="toc-item"><span class="toc-num">18</span>結語</div>
</div>

---

# 01｜核心挑戰與設計目標

<div class="hbar">🎯 讓用戶用自然語言問個股問題，系統自動搜尋、過濾、摘要，並精準呈現重點</div>

<div class="cg c3" style="margin-bottom:14px">
<div class="card blue">
<h3>⚡ 挑戰一：幻覺風險</h3>
<p>LLM 易憑訓練資料產生錯誤數字，在金融領域後果嚴重，需從架構層面根治</p>
</div>
<div class="card amber">
<h3>🕐 挑戰二：資訊時效</h3>
<p>股價、新聞需即時資料，LLM 訓練截止日必然落後，必須接入外部資料源</p>
</div>
<div class="card red">
<h3>⚖️ 挑戰三：金融合規</h3>
<p>不能直接給出「買/賣」建議，需設計明確法遵邊界，避免法律與品牌風險</p>
</div>
</div>

<div class="cg c3">
<div class="card green">
<h3>✅ 目標一：零幻覺數字</h3>
<p>所有關鍵數字 100% 來自結構化 API，LLM 只負責語言包裝，不生成任何數字</p>
</div>
<div class="card teal">
<h3>✅ 目標二：動態搜尋路由</h3>
<p>依問題類型自動選擇最適資料來源，精準與廣度兼顧，Q5 不搜尋節省 latency</p>
</div>
<div class="card purple">
<h3>✅ 目標三：主動情報平台</h3>
<p>從「等用戶問」升級為「主動推送」，Watchlist 推送 + 即時警報 + 個股比較</p>
</div>
</div>

---

# 02｜整體系統架構

<div class="steps" style="margin-bottom:16px">
<div class="step"><div class="ico">💬</div><h3>用戶介面層</h3><p>Web / LINE Bot / App</p></div>
<div class="step"><div class="ico">🔀</div><h3>意圖分類器</h3><p>問題路由至對應搜尋策略</p></div>
<div class="step"><div class="ico">🌐</div><h3>資料擷取層</h3><p>結構化 API + 白名單 + 通用搜尋</p></div>
<div class="step"><div class="ico">🔍</div><h3>三層過濾引擎</h3><p>來源 → 時效 → 內容</p></div>
<div class="step"><div class="ico">🤖</div><h3>LLM 摘要生成</h3><p>Grounded Generation</p></div>
<div class="step"><div class="ico">📤</div><h3>後處理輸出</h3><p>合規聲明 + 記憶寫回</p></div>
</div>

<div class="abox">
<strong>🏛️ 結構化資料層</strong>｜TWSE 開放資料 ｜ Yahoo Finance ｜ Alpha Vantage ｜ 公開資訊觀測站（MOPS）<br>
<span style="color:#0E7490;font-size:12px">→ Q1 即時行情、Q2 財務基本面的主力來源，數字直接注入 Prompt，不經 LLM 生成</span>
</div>
<div class="abox">
<strong>📰 白名單新聞層</strong>｜MoneyDJ ｜ 鉅亨網 ｜ 工商時報 ｜ 經濟日報 ｜ 臺灣證券交易所<br>
<span style="color:#0E7490;font-size:12px">→ Q3 新聞事件的主力來源，品質穩定可控；通用搜尋（Google/Bing）僅作補充用途</span>
</div>
<div class="abox" style="margin-bottom:0">
<strong>⚙️ 核心設計原則</strong>：Q5 知識型問題直接 LLM 作答（不觸發搜尋），節省 latency 與 API 費用；品質不足觸發 Confidence Gating 拒答，不讓 LLM 硬答
</div>

---

# 03｜用戶問題五大分類體系

<table>
<thead>
<tr><th>類別</th><th>名稱</th><th>典型問題範例</th><th>時效需求</th><th>搜尋策略</th><th>LLM 角色</th></tr>
</thead>
<tbody>
<tr><td><span class="bdg bl">Q1</span></td><td>即時行情類</td><td>台積電現在多少？今天大盤漲幾點？</td><td>秒 / 分鐘</td><td>結構化 API</td><td>語言包裝</td></tr>
<tr><td><span class="bdg tl">Q2</span></td><td>財務基本面類</td><td>聯發科 ROE 趨勢？負債比有風險嗎？</td><td>季 / 年</td><td>財報 API + MOPS</td><td>詮釋比較</td></tr>
<tr><td><span class="bdg gr">Q3</span></td><td>新聞事件類</td><td>鴻海最近有什麼消息？AI 概念股為何漲？</td><td>天</td><td>白名單新聞搜尋</td><td>摘要整合</td></tr>
<tr><td><span class="bdg am">Q4</span></td><td>分析師觀點類</td><td>外資目標價多少？市場怎麼看半導體？</td><td>週</td><td>通用搜尋（標可信度）</td><td>觀點彙整</td></tr>
<tr><td><span class="bdg rd">Q5</span></td><td>知識教育類</td><td>本益比怎麼算？什麼是殖利率？</td><td>無時效</td><td><strong>不搜尋</strong></td><td>直接作答</td></tr>
</tbody>
</table>

<div class="hbar" style="margin-top:16px;font-size:13px">
⚡ <strong>複合型問題拆解</strong>：「台積電現在本益比貴嗎？」= Q1（即時股價 API）+ Q2（最新 EPS API）+ Q5（本益比公式 LLM 直答）→ 三路並行，系統自動整合計算後輸出
</div>

---

# 04｜網路資訊搜尋策略

<table style="margin-bottom:14px">
<thead>
<tr><th>方案</th><th>做法</th><th>優點</th><th>缺點</th><th>適用類別</th></tr>
</thead>
<tbody>
<tr><td><strong>A. 通用搜尋 API</strong></td><td>Google / Bing / Serper</td><td>覆蓋廣、即時性高</td><td>雜訊多、SEO 農場混入</td><td>Q3/Q4 補充</td></tr>
<tr><td><strong>B. 金融結構化 API</strong></td><td>Yahoo Finance、TWSE、TEJ</td><td>精準、無幻覺風險</td><td>覆蓋有限、費用較高</td><td>Q1/Q2 主力</td></tr>
<tr><td><strong>C. 白名單爬蟲</strong></td><td>固定爬取可信財經媒體</td><td>品質穩定、合規性高</td><td>靈活性低、需維護名單</td><td>Q3 主力</td></tr>
<tr><td><strong>✅ D. 混合動態路由</strong></td><td>依問題類型自動選擇 A+B+C</td><td>精準與廣度兼顧</td><td>架構較複雜</td><td><strong>全類別最佳</strong></td></tr>
</tbody>
</table>

<div class="cols c2">
<div class="card green">
<h3>🏛️ 可信來源白名單</h3>
<ul>
<li>⭐⭐⭐⭐⭐ 公開資訊觀測站（MOPS）</li>
<li>⭐⭐⭐⭐⭐ 臺灣證券交易所（TWSE）</li>
<li>⭐⭐⭐⭐ MoneyDJ ｜ 鉅亨網</li>
<li>⭐⭐⭐⭐ 工商時報 ｜ 經濟日報</li>
</ul>
</div>
<div class="card teal">
<h3>⚡ 動態路由核心邏輯</h3>
<ul>
<li>Q5 → <strong>不搜尋</strong>，直接 LLM 作答</li>
<li>Q1/Q2 → <strong>結構化 API 優先</strong></li>
<li>Q3 → <strong>白名單主力</strong> + 通用補充</li>
<li>品質不足 → 觸發 <strong>Confidence Gating</strong></li>
</ul>
</div>
</div>

---

# 05｜Prompt 工程設計

<div class="cols c2">
<div>

**System Prompt 四大設定**

<div class="card blue" style="margin-bottom:10px">
<h3>🔒 ① Grounded Anchoring</h3>
<p>「只根據以下提供的資料作答，禁止使用訓練資料中的舊數字」</p>
</div>
<div class="card amber" style="margin-bottom:10px">
<h3>📎 ② Source Attribution</h3>
<p>「每個關鍵數據必須標記來源名稱與資料日期，無來源則不輸出」</p>
</div>
<div class="card red" style="margin-bottom:10px">
<h3>🚫 ③ Explicit Refusal Permission</h3>
<p>「若搜尋資料不足，直接說明找不到，不得硬性給出答案」</p>
</div>
<div class="card green">
<h3>🎭 ④ Fact vs Opinion Separation</h3>
<p>「觀點/預測必須加引號並標明來源，與事實陳述明確區分」</p>
</div>

</div>
<div>

**標準化輸出格式**

```
📌 一句話結論（≤ 30 字）
━━━━━━━━━━━━━━━━━━━━━

📋 重點摘要（最多 3 條）
• [重點] ── 來源：XX｜日期：XX
• [重點] ── 來源：XX｜日期：XX

📰 資料來源清單
⚠️  注意事項（矛盾/不確定說明）

---
本資訊僅供參考，不構成投資建議。
```

<div class="card purple" style="margin-top:10px">
<h3>🔑 最關鍵設計</h3>
<p>數字類資料由 API 取得後直接注入 Prompt，LLM 只做「語言包裝」，從架構層消除數字幻覺</p>
</div>

</div>
</div>

---

# 06｜三層過濾引擎 + Confidence Gating

<div class="steps" style="margin-bottom:14px">
<div class="step" style="flex:1.1">
<div class="ico">🏛️</div>
<h3>Layer 1 來源層</h3>
<p>白名單驗證 + 可信度評分<br>✓ 白名單 → 通過<br>△ 主流媒體 → 降權<br>✗ 論壇 / SEO農場 → 排除</p>
</div>
<div class="step" style="flex:1.1">
<div class="ico">🕐</div>
<h3>Layer 2 時效層</h3>
<p>依問題類別設定門檻<br>Q1 行情：> 15 分鐘過期<br>Q2 財務：> 1 季標舊<br>Q3 新聞：> 7 天降權</p>
</div>
<div class="step" style="flex:1.1">
<div class="ico">🧠</div>
<h3>Layer 3 內容層</h3>
<p>LLM 語義分析<br>相似度 > 0.85 → 去重<br>數字矛盾 → 標記說明<br>廣告內容 → 排除</p>
</div>
<div class="step" style="flex:1.3">
<div class="ico">🛡️</div>
<h3>Confidence Gating</h3>
<p>三維評分<br>時效性（40%）<br>來源可信度（35%）<br>主題覆蓋度（25%）</p>
</div>
</div>

<div class="cols c2">
<div class="card green">
<h3>📊 過濾效果</h3>
<p>原始 15～20 篇 → Layer 1 留 8～12 篇 → Layer 2 留 5～8 篇 → Layer 3 精煉至 <strong>3～5 個高品質核心片段</strong> 進入 LLM</p>
</div>
<div class="card red">
<h3>⚠️ Gating 拒答範例</h3>
<p>「目前找不到足夠可靠的相關資訊，建議直接查閱公開資訊觀測站（mops.twse.com.tw）或洽詢專業理財顧問」</p>
</div>
</div>

---

# 07｜數字安全機制

<div class="hbar">🔐 任何出現在最終回應中的數字，都必須可追溯至 API 或原始引文，禁止 LLM 自行生成</div>

<table style="margin-bottom:14px">
<thead>
<tr><th>資料類型</th><th>取得方式</th><th>LLM 的角色</th><th>安全等級</th></tr>
</thead>
<tbody>
<tr><td>股價、成交量、漲跌幅</td><td>TWSE 即時 API</td><td>語言包裝，數字不可修改</td><td>🟢 最高</td></tr>
<tr><td>EPS、ROE、負債比</td><td>財報 API + MOPS</td><td>語言包裝 + 比較詮釋</td><td>🟢 最高</td></tr>
<tr><td>新聞中引用的數字</td><td>直接引用原文片段</td><td>附來源，不得重新計算</td><td>🟡 高</td></tr>
<tr><td>預測 / 目標價</td><td>引用分析師說法原文</td><td>加引號，標明為「觀點」</td><td>🟡 高</td></tr>
<tr><td>計算衍生數字（如本益比）</td><td>API 數字由系統自動計算</td><td>呈現結果，說明計算公式</td><td>🟢 最高</td></tr>
</tbody>
</table>

<div class="cg c2">
<div class="card red">
<h3>🚫 絕對禁止行為</h3>
<p>LLM 根據語境「推算」股價 ｜ 根據舊新聞「估計」最新財報數字 ｜ 自行合成搜尋結果中從未出現的數字</p>
</div>
<div class="card teal">
<h3>✅ Q1 行情類安全流程</h3>
<p>TWSE API 取得 → 時間戳注入 → 數字直貼 Prompt → LLM 僅包裝語句 → 輸出含時間戳的行情回應</p>
</div>
</div>

---

# 08｜用戶體驗設計

<div class="cols c2">
<div>

**三段式回應結構**

<div class="card blue" style="margin-bottom:10px">
<h3>① 結論前置（≤ 30 字）</h3>
<p>符合金融用戶「快速決策」閱讀習慣，先給結論再展開細節</p>
</div>
<div class="card teal" style="margin-bottom:10px">
<h3>② 條列式重點（2～3 條）</h3>
<p>手機介面友善，每條附來源與日期，掃描效率高，清楚可追溯</p>
</div>
<div class="card green">
<h3>③ 來源 + 注意事項</h3>
<p>建立信任感；資訊有矛盾時在此說明，培養用戶判斷力</p>
</div>

</div>
<div>

**問題改寫（Query Clarification）**

<div class="hbar" style="font-size:12px;margin-bottom:10px">提問模糊時主動引導，提升搜尋精準度</div>

```
用戶：「聯電怎麼樣？」

系統：您好！請問您想了解
     聯電（2303）的哪方面？

① 📈 最新股價與行情
② 📰 近期重要新聞
③ 📊 財務狀況（EPS、ROE）
④ 🎯 法人 / 分析師觀點

請選擇或直接輸入問題 😊
```

</div>
</div>

---

# 09｜合規護欄設計

<div class="hbar">⚖️ 金融法遵紅線：不得給出明確「買入 / 賣出」指示；所有回應強制附加免責聲明</div>

<div class="cg c3" style="margin-bottom:14px">
<div class="card red">
<h3>❌ 禁止做的事</h3>
<p>「建議買入」「不建議現在追高」等明確方向性指示，直接觸犯金融法規</p>
</div>
<div class="card green">
<h3>✅ 正確做法</h3>
<p>整理多空論點並陳，不做傾向性判斷，由用戶自行權衡後決策</p>
</div>
<div class="card teal">
<h3>📋 輸出格式</h3>
<p>多方觀點（標來源）+ 空方觀點（標來源）+ 建議諮詢專業顧問</p>
</div>
</div>

<div class="cols c2" style="margin-bottom:12px">
<div class="abox">
<strong>📈 多方觀點</strong><br>
• AI 需求強勁，CoWoS 封裝產能滿載（工商時報）<br>
• 外資連續買超，目標價調升至 1,200 元（MoneyDJ）
</div>
<div class="abox">
<strong>📉 空方觀點</strong><br>
• 地緣政治風險仍存，熊本廠成本超支疑慮（經濟日報）<br>
• 本益比相對歷史均值偏高（財報 API 計算）
</div>
</div>

<div style="background:#FEF2F2;border-radius:8px;padding:10px 16px;font-size:12.5px;color:#7F1D1D">
⚠️ 投資決策涉及個人風險承受度與財務狀況，本資訊僅供參考，不構成任何投資建議。建議諮詢專業理財顧問後再行決策。
</div>

---

# 10｜創新功能一：Watchlist 每日情報推送

<div class="hbar">從「等用戶來問」→「主動送情報」，從 Chatbot 升級為個人化投資情報站</div>

<div class="cols c2">
<div>

<div class="card blue" style="margin-bottom:10px">
<h3>⏰ 每日 07:00（盤前）</h3>
<p>批次查詢所有用戶 Watchlist（最多 20 檔個股），過濾過去 24 小時重大新聞與公告</p>
</div>
<div class="card teal" style="margin-bottom:10px">
<h3>🤖 LLM 快速摘要</h3>
<p>每檔個股限 2～3 條重點，確保推播訊息精簡可讀，不造成資訊焦慮</p>
</div>
<div class="card green">
<h3>📤 LINE 即時推播</h3>
<p>透過 LINE Messaging API 推送，「您追蹤的 3 檔個股昨日有新消息」</p>
</div>

</div>
<div>

```
━━━━━━━━━━━━━━━━━━━━━━
📊 昨日追蹤個股快報
━━━━━━━━━━━━━━━━━━━━━━

🟢 台積電（2330）
   法說會將於下周舉行
   外資預期上調財測
   來源：MoneyDJ｜昨日 15:32

🔴 鴻海（2317）
   子公司宣布新一輪回購計畫
   來源：工商時報｜昨日 09:15

[查看完整摘要]  [管理追蹤清單]
━━━━━━━━━━━━━━━━━━━━━━
```

</div>
</div>

---

# 11｜創新功能二：多輪對話脈絡記憶

<div class="hbar">Entity Tracking + Session Memory，讓用戶自然追問，無需重複說明股票名稱</div>

<div class="cols c2">
<div>

```
用戶：「台積電最近的消息呢？」
系統：[提供台積電近期新聞摘要]
     ← 記憶：當前主體 = 台積電

用戶：「那它的競爭對手呢？」
     ↑ 解析「它」= 台積電
系統：查詢三星半導體、英特爾
     提供對比摘要

用戶：「外資怎麼看這兩家？」
     ↑「這兩家」= 台積電 + 三星
系統：外資觀點比較分析
```

</div>
<div>

<div class="card blue" style="margin-bottom:10px">
<h3>📝 Session Context 壓縮</h3>
<p>每輪對話摘要存入 Redis，控制 Token 數量，避免 context 無限膨脹</p>
</div>
<div class="card teal" style="margin-bottom:10px">
<h3>🏷️ Entity Tracking</h3>
<p>追蹤對話中提到的股票代號、產業名稱，支援代詞解析（它、這家、這兩家）</p>
</div>
<div class="card green">
<h3>⏱ Session TTL</h3>
<p>30 分鐘無互動自動重置，防止跨主題的錯誤脈絡繼承</p>
</div>

</div>
</div>

---

# 12｜創新功能三：資訊可信度標籤

<div class="hbar">「授人以魚不如授人以漁」── 讓用戶看見資訊來源，培養獨立判斷力而非依賴 AI</div>

<div class="cols c2">
<div>

<div class="card green" style="margin-bottom:10px">
<h3>🏛️ 官方資料</h3>
<p>TWSE、MOPS 等政府機構，最高可信度，數字可直接採信</p>
</div>
<div class="card blue" style="margin-bottom:10px">
<h3>📰 主流媒體</h3>
<p>白名單財經媒體，高可信度，經過編輯審核</p>
</div>
<div class="card amber" style="margin-bottom:10px">
<h3>🌐 網路資訊</h3>
<p>通用搜尋補充，中等可信度，建議用戶自行驗證</p>
</div>
<div class="card red">
<h3>⚠️ 資料較舊</h3>
<p>超過時效門檻，提醒用戶資訊可能已有變化</p>
</div>

</div>
<div>

```
📋 重點摘要

• 台積電 Q1 法說會將於 4/17 舉行
  [🏛️ 官方｜MOPS｜2026-04-01]

• 外資預期上調 2026 年獲利預測
  [📰 主流｜工商時報｜2026-04-02]

• 分析師預測年底突破 1,500 元
  [🌐 網路｜財經部落格｜2026-03-28]
  ⚠️ 建議自行查證此觀點
```

<div class="card purple" style="margin-top:12px">
<h3>💡 設計理念</h3>
<p>資訊透明比隱藏來源能建立更深層信任，也降低 AI 幻覺造成的損失風險</p>
</div>

</div>
</div>

---

# 13｜創新功能四：重大事件即時警報

<div class="hbar">Watchlist 個股觸發特定條件時，即時推播（不等每日報告），讓用戶第一時間掌握</div>

<div class="cols c2">
<div>

**觸發條件**

| 事件類型        | 觸發門檻            |
| --------------- | ------------------- |
| 股價單日漲跌    | > ±7%（接近漲跌停） |
| MOPS 重大訊息   | 任何新重訊公告      |
| 法說會 / 股東會 | 新增公告即觸發      |
| 大額外資買賣超  | > 5,000 張單日      |

<div class="card teal" style="margin-top:12px">
<h3>🔧 技術實現</h3>
<p>MOPS API polling 每 5 分鐘 + 股價偵測每分鐘 → 觸發後 LLM 快速摘要 → LINE 推播，目標延遲 < 3 分鐘</p>
</div>

</div>
<div>

```
🚨 即時警報
━━━━━━━━━━━━━━━━━━━━
您追蹤的個股有重大異動！

台積電（2330）
現價：+6.8% ↑ 接近漲停

觸發原因：MOPS 重大訊息更新
「宣布與 NVIDIA 深化
  CoWoS 合作協議」

━━━━━━━━━━━━━━━━━━━━
[查看完整新聞摘要]
[查看今日行情]
```

</div>
</div>

---

# 14｜創新功能五：個股比較模式

<div class="hbar">支援同時比較 2～3 檔個股，結構化表格呈現，滿足「選股比較」的高頻使用需求</div>

**用戶輸入：「幫我比較台積電和聯發科」**

<table style="margin-bottom:12px">
<thead><tr><th>指標</th><th>台積電（2330）</th><th>聯發科（2454）</th><th>資料來源</th></tr></thead>
<tbody>
<tr><td>現價</td><td>980 元</td><td>1,250 元</td><td>TWSE 即時 API</td></tr>
<tr><td>本益比</td><td>22x</td><td>18x</td><td>系統自動計算</td></tr>
<tr><td>EPS（最新季）</td><td>11.2 元</td><td>15.8 元</td><td>財報 API</td></tr>
<tr><td>股息殖利率</td><td>1.8%</td><td>3.2%</td><td>財報 API</td></tr>
<tr><td>外資持股比例</td><td>72%</td><td>55%</td><td>TWSE API</td></tr>
</tbody>
</table>

<div class="cols c2">
<div class="card blue">
<h3>📰 台積電近期重點</h3>
<p>CoWoS 產能持續滿載，法說會將公布 Q2 展望（工商時報）</p>
</div>
<div class="card teal">
<h3>📰 聯發科近期重點</h3>
<p>Dimensity 旗艦晶片出貨量創新高，AI 手機滲透率提升（經濟日報）</p>
</div>
</div>

---

# 15｜技術選型建議

<table>
<thead><tr><th>層級</th><th>建議技術</th><th>選擇理由</th></tr></thead>
<tbody>
<tr><td><strong>LLM 核心</strong></td><td>GPT-4o / Claude 3.5 Sonnet</td><td>繁體中文理解強、函數調用穩定、幻覺率低</td></tr>
<tr><td><strong>Embedding</strong></td><td>text-embedding-3-small</td><td>語義去重用途，成本低、效能足夠</td></tr>
<tr><td><strong>向量搜尋</strong></td><td>FAISS / Qdrant</td><td>Layer 3 語義去重，快速相似度比對</td></tr>
<tr><td><strong>Web 搜尋 API</strong></td><td>Serper API / Bing Search API</td><td>結構化輸出、穩定、支援日期篩選</td></tr>
<tr><td><strong>金融資料 API</strong></td><td>TWSE 開放資料 + Yahoo Finance</td><td>台股必備、免費或低成本</td></tr>
<tr><td><strong>後端框架</strong></td><td>FastAPI（Python）</td><td>非同步支援、LLM 整合生態豐富</td></tr>
<tr><td><strong>Session 管理</strong></td><td>Redis</td><td>輕量、高速、TTL 自動清除</td></tr>
<tr><td><strong>排程任務</strong></td><td>Celery + Redis</td><td>Watchlist 每日批次推送任務</td></tr>
<tr><td><strong>推播管道</strong></td><td>LINE Messaging API</td><td>台灣用戶習慣、即時推播支援完整</td></tr>
</tbody>
</table>

---

# 16｜非功能性需求指標

<div class="cg c4" style="margin-bottom:18px">
<div class="stat"><div class="n">< 5s</div><div class="l">P95 回應延遲<br>（含搜尋 + 摘要）</div></div>
<div class="stat"><div class="n">100%</div><div class="l">數字資料來自 API<br>非 LLM 生成</div></div>
<div class="stat"><div class="n">30min</div><div class="l">相同問題快取時效<br>Redis Query Hash</div></div>
<div class="stat"><div class="n">99.5%</div><div class="l">系統可用性目標<br>含 Fallback 機制</div></div>
</div>

<div class="cg c3">
<div class="card blue">
<h3>⚡ 效能優化策略</h3>
<ul>
<li>非同步並行搜尋（asyncio）</li>
<li>Q5 問題不搜尋直接回答</li>
<li>熱門問題 Redis 快取</li>
<li>Watchlist 批次處理</li>
</ul>
</div>
<div class="card green">
<h3>🛡️ 可靠性設計</h3>
<ul>
<li>金融 API 失敗 → 降級白名單爬蟲</li>
<li>白名單失敗 → Confidence Gating</li>
<li>LLM 超時 → Retry with backoff</li>
<li>各服務健康檢查監控</li>
</ul>
</div>
<div class="card teal">
<h3>📊 可觀測性指標</h3>
<ul>
<li>各類別問題佔比統計</li>
<li>Confidence Gating 觸發率</li>
<li>來源使用分佈追蹤</li>
<li>用戶滿意度回饋收集</li>
</ul>
</div>
</div>

---

# 17｜風險對策與設計成效

<div class="cols c2">
<div>

**主要風險與對策**

| 風險           | 對策                              |
| -------------- | --------------------------------- |
| LLM 數字幻覺   | 數字全由 API 提供，LLM 禁止生成   |
| 新聞可信度不足 | 白名單 + 多來源交叉驗證 + 標籤    |
| 金融合規違規   | 合規護欄強制 + 免責聲明自動附加   |
| 搜尋 API 費用  | Q5 不搜尋 + Redis 快取 + 費用告警 |
| 即時資料延遲   | 時間戳強制標示 + 時效門檻警示     |

</div>
<div>

**設計成效摘要**

<div class="card green" style="margin-bottom:9px">
<h3>✅ 幻覺防護</h3>
<p>Grounded Generation + 數字 API 注入，從架構層切斷幻覺路徑</p>
</div>
<div class="card blue" style="margin-bottom:9px">
<h3>✅ 動態路由效益</h3>
<p>Q5 問題（約 15～20%）跳過搜尋，顯著降低延遲與費用</p>
</div>
<div class="card teal">
<h3>✅ 被動 → 主動平台</h3>
<p>Watchlist 推送 + 即時警報，從問答工具升級為情報服務</p>
</div>

</div>
</div>

---

<!-- _class: closing -->

# 謝謝聆聽

**基於 LLM 的個股理財助理系統設計**

<p>
以「零幻覺數字」、「動態搜尋路由」、「三層品質過濾」為核心技術基礎，<br>結合五項創新功能，將系統從問答工具升級為主動個人化情報平台。
</p>

<div class="cg c3" style="margin-top:36px;max-width:640px">
<div class="stat" style="background:rgba(255,255,255,0.12);border-radius:12px">
<div class="n" style="color:#7DD3FC;font-size:30px">5 類</div>
<div class="l" style="color:rgba(255,255,255,0.6)">問題分類體系</div>
</div>
<div class="stat" style="background:rgba(255,255,255,0.12);border-radius:12px">
<div class="n" style="color:#7DD3FC;font-size:30px">3 層</div>
<div class="l" style="color:rgba(255,255,255,0.6)">資料過濾引擎</div>
</div>
<div class="stat" style="background:rgba(255,255,255,0.12);border-radius:12px">
<div class="n" style="color:#7DD3FC;font-size:30px">5 項</div>
<div class="l" style="color:rgba(255,255,255,0.6)">創新功能設計</div>
</div>
</div>
