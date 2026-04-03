---
marp: true
theme: default
paginate: true
nav_exclude: true
style: |
  section {
    font-family: 'Noto Sans TC', sans-serif;
    font-size: 22px;
    padding: 40px 60px;
  }
  h1 { font-size: 36px; color: #1a1a2e; border-bottom: 3px solid #2333aa; padding-bottom: 8px; }
  h2 { font-size: 28px; color: #16213e; }
  strong { color: #2333aa; }
  ul { line-height: 1.8; }
  .tag {
    display: inline-block;
    background: #e94560;
    color: white;
    border-radius: 4px;
    padding: 2px 10px;
    font-size: 16px;
    margin-right: 6px;
  }
---

# 莊昊耘 Hao-Yun Chuang
## 自我介紹簡報

<br>

📧 milanochuang@gmail.com
🌐 milanochuang.github.io
🎓 國立政治大學 語言學碩士

---

# 關於我

- 計算語言學碩士，核心專長橫跨 **NLP 理論 → LLM 系統開發**
- 曾赴德國杜賓根大學交換（計算語言學），並獲國科會補助赴荷蘭發表學術論文
- 具備從資料爬取、模型微調到 **RAG / AI Agent** 系統整合的完整工程能力
- 相信技術的真正價值，在於能被部署、被衡量、被用來解決真實問題

---

# 技術能力

**LLM & RAG**
LLM Fine-tuning、RAG Pipeline、LangChain / LangGraph / LlamaIndex、Prompt Engineering

**NLP Core**
BERT / BART 微調、NER、POS Tagging、序列標記、CKIP、SpaCy

**後端 & 工程基礎**
Python、FastAPI / Flask / Django、RESTful API、Docker、AWS / GCP

**資料處理**
Scrapy、BeautifulSoup、PostgreSQL、資料清洗 pipeline 設計

---

# 成果①　SemEval-2024 國際競賽

**任務：** 數字感知新聞標題生成（Numeral-Aware Language Generation）

- 以 **BART** 為基底，**自訂對比損失函數（Contrastive Loss）** 進行微調
- 建構 GPT 輔助的數字型態轉換 pipeline 進行資料增強
- **COPY 準確率全球第一（82.17）、整體排名第二**

> 這是我第一次在模型設計的核心假設上做出工程判斷——
> 不只是調參，而是重新設計損失函數。

---

# 成果②　碩士論文：政治語篇 LLM 分類

**任務：** GPT-4o 在情感評價分析（Appraisal Analysis）上的零樣本 / 少樣本評估

- 對 311 則 PTT 政治評論進行 Judgement 子類別標注與分類實驗
- 精確設計 few-shot prompt，**F1 從 0.80 提升至 0.89**
- 建立 Streamlit 儀表板，可視化政治語篇分析結果

> 讓我對 prompt 工程與模型評估形成系統性的認知，
> 而不只是憑直覺調整。

---

# 成果③　法律科技黑客松

**任務：** AI 輔助性侵案判決成案機率分析系統

- 帶領 **電機 × 統計 × 法律** 跨領域四人團隊，身兼 NLP 工程與跨域溝通角色
- 開發爬蟲蒐集判決資料，以規則式 pattern matching 結構化案件特徵
- 建構對話系統，提供以證據條件為基礎的判決機率預測
- **進入全國決賽**

> 讓我理解「跨域合作」的核心不是消除分歧，
> 而是找到所有人都認同的共同目標，再往回設計。

---

# 實務經驗

**研究助理　國立政治大學（2022–2024）**
- Scrapy / BeautifulSoup 建構語料爬取 pipeline
- CKIP + SpaCy 進行 NER、POS tagging，BERT 序列標記模型微調

**課程助教　AI 與數位人文（2022–2023）**
- 設計 Python / NLP 實作模組（Flask、Django）
- 指導 **50+ 名學生** 完成模型調校與專案除錯

**NLP 實習生　卓騰語言科技（2020–2021）**
- 開發中文任務型 LINE 聊天機器人（高鐵票價 / 時刻查詢）
- 意圖辨識、語意解析，對應此職位的 AI Agent Tool-use 概念

---

# 為什麼是這個職位

**技術對齊**
RAG pipeline、LLM 微調、AI Agent 架構——
這些正是我在研究與專案中反覆實作過的核心。

**思維對齊**
我關注的從來不只是「模型能不能跑」，
而是「模型在真實資料上表現如何、如何被衡量、如何迭代」。

**下一步**
我希望在這裡把技術能力真正轉化為可部署、可衡量的系統，
而不只是停留在實驗層次。

---

# 感謝聆聽

<br>

**莊昊耘 Hao-Yun Chuang**

📧 milanochuang@gmail.com
🌐 milanochuang.github.io
💼 linkedin.com/in/milanochuang

<br>

> 期待有機會進一步交流。
