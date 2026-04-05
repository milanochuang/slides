---
marp: true
theme: default
paginate: true
size: 16:9
nav_exclude: true
style: |
  :root {
    --navy: #0D2B55;
    --blue: #1757A6;
    --orange: #E8711E;
    --light: #F5F7FA;
    --gray: #6B7A8D;
    --white: #FFFFFF;
    --green: #1A8A5A;
    --red: #C0392B;
  }

  section {
    font-family: 'Noto Sans TC', 'PingFang TC', 'Microsoft JhengHei', sans-serif;
    background: var(--white);
    color: var(--navy);
    padding: 48px 60px;
    font-size: 20px;
    line-height: 1.6;
  }

  section.cover {
    background: linear-gradient(135deg, var(--navy) 0%, var(--blue) 100%);
    color: var(--white);
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding: 60px 80px;
  }

  section.cover h1 {
    font-size: 42px;
    font-weight: 800;
    line-height: 1.3;
    margin-bottom: 24px;
    color: var(--white);
    border: none;
  }

  section.cover .subtitle {
    font-size: 22px;
    color: rgba(255,255,255,0.85);
    margin-bottom: 48px;
    font-weight: 400;
  }

  section.cover .meta {
    font-size: 18px;
    color: rgba(255,255,255,0.7);
    border-top: 1px solid rgba(255,255,255,0.3);
    padding-top: 20px;
    width: 100%;
  }

  section.cover .accent-bar {
    width: 64px;
    height: 5px;
    background: var(--orange);
    margin-bottom: 28px;
    border-radius: 3px;
  }

  h1 {
    font-size: 34px;
    font-weight: 800;
    color: var(--navy);
    border-bottom: 3px solid var(--orange);
    padding-bottom: 12px;
    margin-bottom: 28px;
  }

  h2 {
    font-size: 24px;
    font-weight: 700;
    color: var(--blue);
    margin-bottom: 12px;
  }

  h3 {
    font-size: 20px;
    font-weight: 700;
    color: var(--navy);
    margin-bottom: 8px;
  }

  .tag {
    display: inline-block;
    background: var(--orange);
    color: white;
    font-size: 13px;
    font-weight: 700;
    padding: 3px 12px;
    border-radius: 20px;
    letter-spacing: 0.5px;
    margin-bottom: 10px;
  }

  .tag.blue {
    background: var(--blue);
  }

  .tag.green {
    background: var(--green);
  }

  .card {
    background: var(--light);
    border-left: 4px solid var(--orange);
    padding: 16px 20px;
    border-radius: 0 8px 8px 0;
    margin-bottom: 14px;
  }

  .card.blue {
    border-left-color: var(--blue);
  }

  .card.green {
    border-left-color: var(--green);
  }

  .grid-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    margin-top: 12px;
  }

  .grid-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
    margin-top: 12px;
  }

  .metric-box {
    background: var(--navy);
    color: white;
    padding: 18px;
    border-radius: 12px;
    text-align: center;
  }

  .metric-box .num {
    font-size: 38px;
    font-weight: 800;
    color: var(--orange);
  }

  .metric-box .label {
    font-size: 14px;
    color: rgba(255,255,255,0.8);
    margin-top: 4px;
  }

  .pain-box {
    background: #FFF5F5;
    border: 1px solid #FCC;
    border-left: 4px solid var(--red);
    padding: 14px 18px;
    border-radius: 0 8px 8px 0;
    margin-bottom: 12px;
  }

  .pain-box .icon { color: var(--red); font-weight: bold; }

  .arrow {
    text-align: center;
    font-size: 28px;
    color: var(--orange);
    margin: 6px 0;
  }

  .section-header {
    background: linear-gradient(90deg, var(--navy), var(--blue));
    color: white;
    padding: 10px 20px;
    border-radius: 8px;
    font-size: 15px;
    font-weight: 700;
    display: inline-block;
    margin-bottom: 16px;
    letter-spacing: 0.5px;
  }

  .highlight {
    color: var(--orange);
    font-weight: 800;
  }

  .flow-step {
    background: var(--light);
    border: 2px solid var(--blue);
    border-radius: 10px;
    padding: 12px 14px;
    text-align: center;
    font-size: 15px;
    font-weight: 600;
  }

  .flow-arrow {
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 22px;
    color: var(--orange);
  }

  .badge {
    background: #E8F0FB;
    border: 1px solid var(--blue);
    color: var(--blue);
    padding: 4px 14px;
    border-radius: 20px;
    font-size: 14px;
    font-weight: 600;
    display: inline-block;
    margin: 3px 3px;
  }

  section footer {
    font-size: 13px;
    color: var(--gray);
  }

  section[data-marpit-pagination]::after {
    font-size: 14px;
    color: var(--gray);
  }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 17px;
  }

  th {
    background: var(--navy);
    color: white;
    padding: 10px 14px;
    font-weight: 700;
    text-align: left;
  }

  td {
    padding: 9px 14px;
    border-bottom: 1px solid #E0E6EF;
  }

  tr:nth-child(even) td {
    background: var(--light);
  }

  ul {
    padding-left: 22px;
  }

  li {
    margin-bottom: 6px;
  }
---

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="accent-bar"></div>

# 運用生成式 AI<br>提升客戶服務能量及品質

<div class="subtitle">從問答到對話，從被動到主動：<br>以 Agentic RAG 重塑壽險客戶服務體驗</div>

<div class="meta">
2026 富邦人壽金融科技組 MA 甄選 ｜ 莊昊耘 Hao-Yun Chuang
</div>

---

# 目錄

<div class="grid-2" style="margin-top: 20px;">

<div>

<div class="card">
<h3>📊 現況盤點</h3>
富邦人壽 AI 客服已達什麼水準？<br>
<small style="color:var(--gray)">Slide 3–4</small>
</div>

<div class="card blue">
<h3>🔍 缺口分析</h3>
現有方案的三大核心限制<br>
<small style="color:var(--gray)">Slide 5</small>
</div>

<div class="card green">
<h3>💡 三大提案</h3>
Agentic RAG 升級路徑<br>
<small style="color:var(--gray)">Slide 6–11</small>
</div>

</div>

<div>

<div class="card" style="border-left-color: var(--navy)">
<h3>🗺️ 實施 Roadmap</h3>
分階段落地計畫<br>
<small style="color:var(--gray)">Slide 12</small>
</div>

<div class="card" style="border-left-color: var(--gray)">
<h3>📈 效益與合規</h3>
量化效益與風險評估<br>
<small style="color:var(--gray)">Slide 13</small>
</div>

<div class="card" style="border-left-color: var(--orange)">
<h3>🎯 結語</h3>
<small style="color:var(--gray)">Slide 14–15</small>
</div>

</div>
</div>

---

# 富邦人壽 AI 客服現況盤點

<div class="section-header">🏆 業界領先的數位轉型成績</div>

<div class="grid-3" style="margin-bottom: 18px;">
<div class="metric-box">
  <div class="num">120萬+</div>
  <div class="label">AI 職業代碼推薦<br>累計服務保單數</div>
</div>
<div class="metric-box">
  <div class="num">94%</div>
  <div class="label">文字客服機器人<br>回答率</div>
</div>
<div class="metric-box">
  <div class="num">50→25分</div>
  <div class="label">核保智能助理<br>單件作業時間</div>
</div>
</div>

<div class="grid-2">
<div>

**客服場景已落地**
- ✅ 文字客服機器人（24hr，40萬+人次）
- ✅ 數位語音投保（旅平險電話語音）
- ✅ 保單健檢系統（OCR + 大數據）
- ✅ Copilot 強化知識庫整合

</div>
<div>

**內部效能已落地**
- ✅ 核保智能助理（GenAI 病歷摘要）
- ✅ 知識檢索引擎（跨子公司 NLP 搜尋）
- ✅ 智能法遵平台
- ✅ 商品開發 AI 小幫手 / 理賠智慧助理

</div>
</div>

---

# 現況深探：文字客服機器人的架構

<div class="section-header">現有系統能力邊界</div>

<div class="grid-2" style="margin-top: 14px;">
<div>

**運作模式**

```
客戶輸入問題
    ↓
關鍵字 / 意圖比對
    ↓
預設模板回覆 or 跳轉頁面
    ↓
超出範圍 → 轉人工
```

<div style="margin-top: 12px;">
<div class="badge">規則式意圖辨識</div>
<div class="badge">預設 FAQ 模板</div>
<div class="badge">保單資料查詢</div>
<div class="badge">單輪對話為主</div>
</div>

</div>
<div>

**現有能力範圍**

<div class="card" style="margin-bottom: 10px;">
✅ 查詢保障內容、保單帳戶價值<br>
✅ 查詢繳費期限、解約金試算<br>
✅ 查詢業務員聯絡資訊<br>
✅ 旅平險語音投保
</div>

**回答率 94% 的意涵**

> 6% 的問題無法被回答，且<br>
> **能回答的 94% 多為固定格式查詢**，<br>
> 缺乏情境理解與生成能力

</div>
</div>

---

# 現有方案的三大核心缺口

<div class="section-header">🔍 Gap Analysis</div>

<div class="pain-box">
<span class="icon">⚠️ Gap 1：單輪問答，缺乏情境連貫</span><br>
客戶點選已預先建立的「我的重大疾病保障有哪些？」→ 機器人只能回傳保障金額清單。其餘的個人化需求無法結合年齡、已有保單、家庭結構給予<strong>個人化建議</strong>，客戶仍需自行判斷。
</div>

<div class="pain-box">
<span class="icon">⚠️ Gap 2：被動等待，錯失關鍵服務時機</span><br>
現有系統為客戶主動發問才啟動，未能在<strong>保單到期前或理賠後</strong>主動出擊，提供有溫度的個人化關懷。
</div>

<div class="pain-box">
<span class="icon">⚠️ Gap 3：複雜問題直接轉人工，服務斷點明顯</span><br>
當客戶情緒激動（如理賠糾紛）或問題複雜（跨保單比較），系統缺乏<strong>情緒感知</strong>與<strong>智能路由</strong>能力，轉接品質難以保障。
</div>

---

# 三大提案總覽

<div class="grid-3">

<div style="background: #EBF3FF; border-radius: 12px; padding: 20px; text-align: center;">

<div style="font-size: 36px;">🤖</div>

**提案一**

多輪對話<br>RAG 客服升級

<div style="margin-top: 10px; font-size: 14px; color: var(--gray);">
解決 Gap 1<br>情境連貫 × 知識生成
</div>

</div>

<div style="background: #FFF4EB; border-radius: 12px; padding: 20px; text-align: center;">

<div style="font-size: 36px;">💬</div>

**提案二**

主動式個人化<br>保障顧問生成

<div style="margin-top: 10px; font-size: 14px; color: var(--gray);">
解決 Gap 2<br>主動觸達 × 文本生成
</div>

</div>

<div style="background: #EBFAF3; border-radius: 12px; padding: 20px; text-align: center;">

<div style="font-size: 36px;">🎯</div>

**提案三**

情緒感知<br>智慧轉接系統

<div style="margin-top: 10px; font-size: 14px; color: var(--gray);">
解決 Gap 3<br>情緒分類 × 精準轉接
</div>

</div>

</div>

<div class="arrow" style="font-size: 22px; margin-top: 20px; color: var(--navy); font-weight: 700;">
三者整合 → 全方位 AI 客服生態系
</div>

---

# 提案一：多輪對話 RAG 客服升級

<div class="section-header">🤖 Agentic RAG + 多輪意圖追蹤</div>

<div class="grid-2">
<div>

**技術架構**

<div style="background: var(--light); padding: 16px; border-radius: 10px; font-size: 16px;">

```
客戶問：「我的保障夠嗎？」
         ↓
 [意圖分類器] 辨識複合需求
         ↓
 [RAG Retriever] 取回：
 · 個人保單資料
 · 同年齡層保障基準
 · 保險商品知識庫
         ↓
 [LLM Generator] 生成：
 個人化、有根據的建議說明
         ↓
 [對話記憶] 維持多輪上下文
```

</div>

</div>
<div>

**解決了什麼？**

<div class="card">
<strong>情境感知</strong><br>
理解「我想追加醫療險」背後的完整需求脈絡，不再只回傳靜態列表
</div>

<div class="card green">
<strong>知識生成</strong><br>
RAG 結合條款資料庫 + 客戶保單，生成精確、有依據的回答，避免幻覺
</div>

<div class="card blue">
<strong>跨輪記憶</strong><br>
LangGraph 管理對話狀態，實現「這次問的跟上次我提到的健康問題有關嗎？」
</div>

</div>
</div>

---

# 提案一：技術細節與現有升級路徑

<div class="grid-2">
<div>

**核心技術元件**

| 元件 | 技術選型 |
|------|---------|
| 意圖分類 | Fine-tuned BERT (中文) |
| 向量檢索 | 保單條款 Embedding |
| 知識融合 | RAG (LlamaIndex) |
| 對話管理 | LangGraph State Machine |
| 生成模型 | GPT-4o / LLM |
| 護欄機制 | 規則過濾 + RLHF |

</div>
<div>

**與現有系統的升級關係**

<div style="font-size: 16px;">

```
現有：文字客服機器人
 → 關鍵字比對 + FAQ 模板
 → 回答率 94%（固定問題）

升級後：RAG 對話客服
 → 語意理解 + 動態生成
 → 複雜問題自動處理
 → 預估可解決率提升至 98%+
```

</div>

<div class="card green" style="font-size: 16px; margin-top: 10px;">
🔗 <strong>現有 Copilot 知識庫可直接作為 RAG 語料庫</strong>，降低建置成本
</div>

</div>
</div>

---

# 提案二：主動式個人化保障顧問

<div class="section-header">💬 生命事件觸發 × 個人化文本生成</div>

<div class="grid-2">
<div>

**觸發情境（Trigger Events）**

<div class="card" style="font-size: 16px;">🎂 <strong>生日前 30 天</strong>：保障盤點建議生成</div>
<div class="card blue" style="font-size: 16px;">📋 <strong>保單即將到期</strong>：續約方案自動說明</div>
<div class="card green" style="font-size: 16px;">🏥 <strong>理賠申請後</strong>：後續保障缺口分析</div>


</div>
<div>

**生成流程**

```
觸發事件
    ↓
客戶資料 + 保單資料提取
    ↓
個人化 Prompt 建構
（含年齡、保障缺口、偏好）
    ↓
LLM 生成關懷訊息草稿
    ↓
合規過濾 / 業務員審核
    ↓
推播至 APP / LINE / Email
```

<div class="card" style="font-size: 15px; margin-top: 10px;">
💡 業務員可一鍵微調 → 維持<br>「人情溫度」與「AI 效率」的平衡
</div>

</div>
</div>

---

# 提案三：情緒感知智能路由系統

<div class="section-header">🎯 NLP 情緒分類 → 客服品質全面提升</div>

<div class="grid-2">
<div>

**情緒感知分類架構**

<div style="background: var(--light); padding: 16px; border-radius: 10px; font-size: 16px;">

```
客戶輸入文字 / 語音
        ↓
  情緒分類模型
  ┌─────┬──────┬─────┐
  │ 正常   焦慮   憤怒 │
  └──┬──┴──┬───┴──┬──┘
     ↓     ↓      ↓
  繼續  優先排隊  優先轉接
  對話  + 安撫語  資深客服
```

</div>

**後端品質分析**
- 通話逐字稿自動摘要
- 客服應對話術評分
- 常見抱怨主題聚類

</div>
<div>

**為何這很重要？**

<div class="card">
<strong>理賠糾紛場景</strong><br>
偵測到高漲情緒 → 立即轉接資深理賠專員，避免問題升級
</div>

<div class="card blue">
<strong>高齡客戶關懷</strong><br>
偵測到困惑 / 反覆提問 → 調整對話速度，提供電話支援
</div>

<div class="card green">
<strong>管理洞察**</strong><br>
情緒趨勢儀表板 → 識別高投訴商品 / 流程，優先改善
</div>

<div style="font-size: 15px; margin-top: 12px; color: var(--gray);">
技術：Fine-tuned Chinese Sentiment Classifier<br>
訓練語料：金融客服對話 + 遷移學習
</div>

</div>
</div>

---

# 整合架構：全旅程 AI 客服生態系

<div style="text-align: center; margin-top: 16px;">

<div class="grid-3" style="margin-bottom: 12px;">

<div class="flow-step" style="background: #EBF3FF; border-color: var(--blue);">
📲 客戶主動提問<br>
<small>RAG 多輪對話客服</small>
</div>

<div class="flow-step" style="background: #FFF4EB; border-color: var(--orange);">
🔔 主動觸達推播<br>
<small>生命事件 × 個人化生成</small>
</div>

<div class="flow-step" style="background: #EBFAF3; border-color: var(--green);">
💢 情緒感知<br>
<small>分類 × 智慧轉接</small>
</div>

</div>

<div style="font-size: 28px; color: var(--orange); margin: 6px 0;">↓</div>

<div style="background: var(--navy); color: white; padding: 16px 30px; border-radius: 12px; display: inline-block; font-size: 18px; font-weight: 700; margin-bottom: 12px;">
🔗 統一客戶對話記憶 × 保單資料庫 × 合規護欄層
</div>

<div style="font-size: 28px; color: var(--orange); margin: 6px 0;">↓</div>

<div class="grid-3">
<div style="background: var(--light); padding: 12px; border-radius: 8px; font-size: 15px;">
👤 <strong>客戶</strong><br>24hr 無縫體驗
</div>
<div style="background: var(--light); padding: 12px; border-radius: 8px; font-size: 15px;">
🧑‍💼 <strong>業務員</strong><br>AI 輔助，專注在更重要的事情上
</div>
<div style="background: var(--light); padding: 12px; border-radius: 8px; font-size: 15px;">
📊 <strong>管理層</strong><br>即時服務品質洞察
</div>
</div>

</div>

---

# 實施 Roadmap

<div style="margin-top: 16px;">

| 階段 | 時程 | 重點工作 | 預期產出 |
|------|------|----------|----------|
| **Phase 1**<br>基礎建設 |  1–3月 | · 保單條款向量化<br>· RAG 基礎架構建置<br>· 中文情緒分類模型訓練 | RAG Prototype<br>情緒分類器 v1 |
| **Phase 2**<br>核心功能 | 4–6月 | · 多輪對話引擎整合<br>· 生命事件觸發系統<br>· 合規護欄建置 | 內測版上線<br>業務員工具整合 |
| **Phase 3**<br>迭代優化 | 7–9月 | · 用戶反饋收集 & RLHF<br>· 情緒路由上線<br>· 管理儀表板 | 正式對外上線<br>A/B 測試 |
| **Phase 4**<br>規模化 | 10–12月 | · 多管道整合（APP / LINE / Call）<br>· 模型定期再訓練機制 | 全方位效益報告 |

</div>

<div class="card" style="margin-top: 14px; font-size: 16px;">
🔗 <strong>降低風險策略</strong>：Phase 1–2 採 Shadow Mode（AI 建議 + 人工審核），確認品質後逐步放量
</div>

---

# 預期效益 × 風險與合規

<div class="grid-2">
<div>

**📈 量化效益目標**

<div class="metric-box" style="margin-bottom: 10px; background: #1A3A5C;">
  <div class="num" style="font-size: 28px;">94% → 98%+</div>
  <div class="label">客服機器人問題解決率</div>
</div>

<div class="metric-box" style="margin-bottom: 10px; background: #1A3A5C;">
  <div class="num" style="font-size: 28px;">↓ 30%</div>
  <div class="label">人工客服轉接率（估）</div>
</div>

<div class="metric-box" style="background: #1A3A5C;">
  <div class="num" style="font-size: 28px;">↑ NPS</div>
  <div class="label">主動關懷推播 → 客戶滿意度提升</div>
</div>

</div>
<div>

**⚖️ 風險與合規考量**

<div class="pain-box" style="font-size: 16px;">
<strong>金融監管合規</strong><br>
AI 生成內容須符合金管會保險局規範，關鍵保障說明保留人工確認機制
</div>

<div class="pain-box" style="border-left-color: #E8711E; background: #FFF8F0; font-size: 16px;">
<strong>個資保護</strong><br>
RAG 檢索僅在用戶驗證後存取個人保單，符合 PDPA 個資法要求
</div>

<div class="pain-box" style="border-left-color: var(--blue); background: #EBF3FF; font-size: 16px;">
<strong>幻覺（Hallucination）防護</strong><br>
RAG 搭配來源引用 + 規則過濾，確保財務數字生成準確
</div>

</div>
</div>

---

# 為什麼是我？技術背景對應

<div class="section-header">🎓 學術研究 × 工程實作的交叉點</div>

<div class="grid-2">
<div>

**直接對應的技術能力**

<div class="card" style="font-size: 16px;">
🥇 <strong>SemEval 2024 第一名（COPY 準確率）</strong><br>
Fine-tuned BART + 對比學習 → 精確數字生成<br>
→ <span class="highlight">對應金融數字準確性要求</span>
</div>

<div class="card blue" style="font-size: 16px;">
📊 <strong>論文：GPT-4o 零樣本 / 少樣本文本分類</strong><br>
F1: 0.80 → 0.89 → <span class="highlight">情緒分類器訓練基礎</span>
</div>

<div class="card green" style="font-size: 16px;">
🤖 <strong>Droidtown 實習：中文對話系統開發</strong><br>
意圖辨識 × 任務型對話 → <span class="highlight">RAG 客服核心能力</span>
</div>

</div>
<div>

**跨域整合視角**

<div class="card" style="border-left-color: var(--navy); font-size: 16px;">
⚖️ <strong>法律科技黑客松（全國決賽）</strong><br>
帶領電機 × 統計 × 法律跨域團隊<br>
→ 保險科技同樣需要技術 × 法規 × 業務的整合
</div>

<div class="card" style="border-left-color: var(--gray); font-size: 16px;">
🌏 <strong>荷蘭國際學術發表 × 德國交換</strong><br>
跨文化溝通力 + 國際視野<br>
→ 理解不同情境下的使用者需求差異
</div>

<div class="card" style="border-left-color: var(--orange); font-size: 16px;">
📚 <strong>LangChain × LangGraph × RAG</strong><br>
完整 Agentic Workflow 工程能力<br>
→ <span class="highlight">三大提案均可親自實作 Prototype</span>
</div>

</div>
</div>

---

<!-- _class: cover -->
<!-- _paginate: false -->

<div class="accent-bar"></div>

# 從「回答問題」到「理解客戶」

<div class="subtitle">
富邦人壽已有全台最好的 AI 客服基礎建設。<br>
下一步，是讓 AI 真正「懂」每一位保戶。<br><br>
<strong>Agentic RAG × 主動關懷 × 情緒感知</strong><br>
三者整合，實現「AI Everywhere」的真正意涵。
</div>

<div class="meta">
感謝聆聽 ｜ 莊昊耘 Hao-Yun Chuang<br>
milanochuang@gmail.com ｜ milanochuang.github.io
</div>