---
marp: true
theme: uncover
html: true
---

<!-- _class: lead -->

<!-- Good afternoon everyone. Today, I will present my research, My study focuses on how we can use large language model from the perspective of evaluative language to understand public opinion in online political discussions — specifically, how people evaluate political parties on PTT. -->

#### Political Comment Opinion Analysis and Applications of Large Language Models: A Case Study of Social Media Comments on Taiwan's 2024 Presidential Election

<div style="position: absolute; bottom: 30px; left: 100px; font-size: 0.8em; text-align: left;">

Hao-Yun Chuang  
Graduate Institute of Linguistics, NCCU  
18 November 2025

</div>

---

<!--_paginate: true-->
## Online political comment
- 「貪污腐化的Ａ黨」→ political comment
- As an cognitive shortcut
→ people tend to evaluate political party (Gastil, 2014)
- Characteristics
  - Immediacy and rapid dissemination
  - Anonymity and grassroot nature
  - Diversity and large scale

---

<!--_paginate: true-->
### Deeper understanding of the comment
- Most research in NLP mostly limit at polarity.
- Evaluative dimensions may be overlooked.
- More fine-grained categories of evaluations is needed.
- It help understand how political party's image is constructed and challenged

---

<!--_paginate: true-->
### Appraisal framework (White, 2005)

- Derives from Systemic Functional Linguistics
- Analyzes how language conveys attitudes and evaluations in communication


---

<!--_paginate: true-->
## <span style="font-variant:small-caps;">judgement</span> & subcategories
<div style="transform: scale(1);">

<table style="width: 100%; text-align: center; border-collapse: collapse; font-size: 32px;">
  <tr style="background-color: #44A6D4; color: white;">
    <th>Subcategory</th>
    <th>What it Evaluates</th>
    <th>Example from PTT</th>
  </tr>
  <tr>
    <td>Capacity</td>
    <td>competence, intelligence</td>
    <td><span style="background-color: #94d2eeff;">A 黨</span>無能！</td>
  </tr>
  <tr>
    <td>Propriety</td>
    <td>morality, ethics</td>
    <td>不投腐敗的<span style="background-color: #94d2eeff;">B 黨</span>！</td>
  </tr>
  <tr>
    <td>Veracity</td>
    <td>honesty, truthfulness</td>
    <td>整天說謊的就<span style="background-color: #94d2eeff;">C 黨</span>！</td>
  </tr>
  <tr>
    <td>Tenacity</td>
    <td>determination</td>
    <td>簽了又翻桌的<span style="background-color: #94d2eeff;">D 黨</span>！</td>
  </tr>
  <tr>
    <td>Normality</td>
    <td>unusualness</td>
    <td><span style="background-color: #94d2eeff;">E 黨</span>願意才奇怪勒！</td>
  </tr>
</table>

</div>

---

<!--_paginate: true-->
## Automated detection
- Manual annotation of Appraisal → low efficiency
- Non-generative model limitation → need to retrain
- More context-aware generative LLM → prompting
- Implementation: visualization of the evaluation

---

<!--_paginate: true-->
## Research question
<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

1. How do Taiwanese social media users employ evaluative language through <span style="font-variant:small-caps;">judgement</span> subcategories within the Appraisal framework to express opinions toward different political parties?
2. How do different prompting strategies (zero-shot vs. few-shot) influence the performance of GPT in classifying <span style="font-variant:small-caps;">judgement</span> subcategories?

</div>

---

## Literature review

---

## Evaluative Language Framework
1. Stance triangle (Du Bois, 2007)
2. Politeness theory (Brown & Levinson, 1987)
3. Appraisal framework (White, 2005)
  - Divide Attitude to 3 subsystem: <span style="font-variant:small-caps;">affect</span>, <span style="font-variant:small-caps;">judgement</span>, <span style="font-variant:small-caps;">appreciation</span>
  - Focus on <span style="font-variant:small-caps;">judgement</span> with its five subcategories

---

<!-- _style: text-align: left -->

## <span style="font-variant:small-caps;">judgement</span> in Political Discourse
1. Political comments focus on target's behavior and character. (Zappavigna, 2017; Cavasso & Taboada, 2021)
2. <span style="font-variant:small-caps;">judgement</span> is proven to be an appropriate resources in Chinese political context

---

## Automated Detection in Appraisal
- Traditional machine learning: relies on lexicons and rules, difficult to adapt to dynamic language (Casey et al., 2005)  
- Deep learning: BERT, RoBERTa show potential in ALTA Shared Task (Mollá, 2020; Aroyehun & Gelbukh, 2020)  
- ChatGPT applications (Imamovic et al., 2024): classify top-down, often misclassifies JUDGEMENT subcategories

---

## Automated Detection

---

<!--_paginate: true-->
## Methodology

<div style="font-size: 36px; line-height: 1.4; text-align: left; max-width: 100%;">

- **Data:** PTT Gossiping board
- **Manual annotation**:
  * Target entity (metonymy identification)
  * Inscribed <span style="font-variant:small-caps;">judgement</span>
  * Polarity
  * Evaluative expression (text span)
- Intercoder agreement
</div>

---

<!-- ## Annotation process -->
<img src="figure/an_1.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---

<img src="figure/an_2.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---

<img src="figure/an_3.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---

<img src="figure/an_4.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---

<!--_paginate: true-->
## Automation

* GPT-based classification
* Visualization dashboard

---

# **Results**

---

<!-- -->
<!--_paginate: true-->
#### Evaluative <span style="font-variant:small-caps;">judgement</span> Frequency
<div style="display: flex; font-family: Arial, sans-serif; font-size: 30px;">

  <!-- Overall -->
  <div style="flex: 1;">
    <div style="text-align: center; background-color: #44A6D4; color: white; padding: 6px;">DPP</div>
    <table style="width: 100%; text-align: center; border-collapse: collapse;">
      <tr style="background-color: #44A6D4; color: white;">
        <th>Subcategory</th><th>+</th><th>−</th>
      </tr>
      <tr><td><span style="font-variant:small-caps;">capacity</span></td><td>6</td><td>19</td></tr>
      <tr><td><span style="font-variant:small-caps;">normality</span></td><td>0</td><td>9</td></tr>
      <tr><td><span style="font-variant:small-caps;">propriety</span></td><td>1</td><td>129</td></tr>
      <tr><td><span style="font-variant:small-caps;">tenacity</span></td><td>0</td><td>16</td></tr>
      <tr><td><span style="font-variant:small-caps;">veracity</span></td><td>6</td><td>33</td></tr>
      <tr style="font-weight: bold;"><td>Total</td><td colspan="2">213</td></tr>
    </table>
  </div>

  <!-- KMT -->
  <div style="flex: 1;">
    <div style="text-align: center; background-color: #44A6D4; color: white; padding: 6px;">KMT</div>
    <table style="width: 100%; text-align: center; border-collapse: collapse;">
      <tr style="background-color: #44A6D4; color: white;">
        <th>Subcategory</th><th>+</th><th>−</th>
      </tr>
      <tr><td><span style="font-variant:small-caps;">capacity</span></td><td>5</td><td>52</td></tr>
      <tr><td><span style="font-variant:small-caps;">normality</span></td><td>0</td><td>1</td></tr>
      <tr><td><span style="font-variant:small-caps;">propriety</span></td><td>0</td><td>17</td></tr>
      <tr><td><span style="font-variant:small-caps;">tenacity</span></td><td>2</td><td>5</td></tr>
      <tr><td><span style="font-variant:small-caps;">veracity</span></td><td>0</td><td>7</td></tr>
      <tr style="font-weight: bold;"><td>Total</td><td colspan="2">89</td></tr>
    </table>
  </div>

  <!-- TPP -->
  <div style="flex: 1;">
    <div style="text-align: center; background-color: #44A6D4; color: white; padding: 6px;">TPP</div>
    <table style="width: 100%; text-align: center; border-collapse: collapse;">
      <tr style="background-color: #44A6D4; color: white;">
        <th>Subcategory</th><th>+</th><th>−</th>
      </tr>
      <tr><td><span style="font-variant:small-caps;">capacity</span></td><td>0</td><td>3</td></tr>
      <tr><td><span style="font-variant:small-caps;">normality</span></td><td>0</td><td>0</td></tr>
      <tr><td><span style="font-variant:small-caps;">propriety</span></td><td>3</td><td>1</td></tr>
      <tr><td><span style="font-variant:small-caps;">tenacity</span></td><td>0</td><td>0</td></tr>
      <tr><td><span style="font-variant:small-caps;">veracity</span></td><td>0</td><td>2</td></tr>
      <tr style="font-weight: bold;"><td>Total</td><td colspan="2">9</td></tr>
    </table>
  </div>

</div>

---
<!--_paginate: true-->
<!-- -->
#### Fisher's Test: <span style="font-variant:small-caps;">judgement</span> subcategories

<div style="font-family: Arial, sans-serif; font-size: 30px;">

  <table style="width: 100%; text-align: center; border-collapse: collapse;">
    <tr style="background-color: #44A6D4; color: white;">
      <th rowspan="2">Subcategory</th>
      <th colspan="2">KMT vs TPP</th>
      <th colspan="2">KMT vs DPP</th>
      <th colspan="2">TPP vs DPP</th>
    </tr>
    <tr style="background-color: #44A6D4; color: white;">
      <th>OR</th><th><em>p</em></th>
      <th>OR</th><th><em>p</em></th>
      <th>OR</th><th><em>p</em></th>
    </tr>
    <tr><td><span style="font-variant:small-caps;">capacity</span></td><td>3.563</td><td>0.086</td><td>13.395</td><td><span style="background-color: #94d2eeff;">0.000***</span></td><td>3.760</td><td>0.090</td></tr>
    <tr><td><span style="font-variant:small-caps;">normality</span></td><td>inf</td><td>1.000</td><td>0.258</td><td>0.291</td><td>0.000</td><td>1.000</td></tr>
    <tr><td><span style="font-variant:small-caps;">propriety</span></td><td>0.295</td><td>0.095</td><td>0.151</td><td><span style="background-color: #94d2eeff;">0.000***</span></td><td>0.511</td><td>0.489</td></tr>
    <tr><td><span style="font-variant:small-caps;">tenacity</span></td><td>inf</td><td>1.000</td><td>1.051</td><td>1.000</td><td>0.000</td><td>1.000</td></tr>
    <tr><td><span style="font-variant:small-caps;">veracity</span></td><td>0.299</td><td>0.192</td><td>0.466</td><td>0.093</td><td>1.558</td><td>0.636</td></tr>
  </table>

</div>

---
<!--_paginate: true-->
<!--  -->
#### Classification Report

<div style="font-family: Arial, sans-serif; font-size: 27px;">

  <table style="width: 100%; text-align: center; border-collapse: collapse;">
    <colgroup>
      <col style="width: 14%;">
      <col style="width: 12%;">
      <col style="width: 12%;">
      <col style="width: 12%;">
      <col style="width: 12%;">
      <col style="width: 12%;">
      <col style="width: 12%;">
    </colgroup>
    <tr style="background-color: #44A6D4; color: white;">
      <th rowspan="2">Subcategory</th>
      <th colspan="3">Zero-shot</th>
      <th colspan="3">Few-shot</th>
    </tr>
    <tr style="background-color: #44A6D4; color: white;">
      <th>Precision</th><th>Recall</th><th>F1</th>
      <th>Precision</th><th>Recall</th><th>F1</th>
    </tr>
    <tr><td><span style="font-variant:small-caps;">capacity</span></td><td>0.71</td><td>0.84</td><td>0.77</td><td>0.85</td><td>0.84</td><td>0.84</td></tr>
    <tr><td><span style="font-variant:small-caps;">normality</span></td><td>0.29</td><td>0.50</td><td>0.37</td><td>0.50</td><td>0.90</td><td>0.64</td></tr>
    <tr><td><span style="font-variant:small-caps;">propriety</span></td><td>0.90</td><td>0.92</td><td>0.91</td><td>0.96</td><td>0.90</td><td>0.93</td></tr>
    <tr><td><span style="font-variant:small-caps;">tenacity</span></td><td>1.00</td><td>0.13</td><td>0.23</td><td>0.78</td><td>0.91</td><td>0.84</td></tr>
    <tr><td><span style="font-variant:small-caps;">veracity</span></td><td>0.94</td><td>0.81</td><td>0.87</td><td>0.98</td><td>0.95</td><td>0.96</td></tr>
    <tr style="font-weight: bold; background-color: #f0f0f0;">
      <td>Macro Avg</td>
      <td>0.77</td><td>0.64</td><td>0.63</td>
      <td>0.81</td><td>0.90</td><td>0.84</td>
    </tr>
    <tr style="font-weight: bold; background-color: #f0f0f0;">
      <td>Weighted Avg</td>
      <td>0.84</td><td>0.81</td><td><span style="background-color: #94d2eeff;">0.80</span></td>
      <td>0.90</td><td>0.89</td><td><span style="background-color: #94d2eeff;">0.89</span></td>
    </tr>
  </table>

</div>

---
<!--_paginate: true-->
## McNemar Test
<div style="transform: scale(0.85); transform-origin: top left; width: 120%;">

<table style="width: 70%; text-align: center; font-size: 27px; border-collapse: collapse; margin: auto;">
  <thead>
    <tr style="background-color: #44A6D4; color: white;">
      <th style="padding: 10px;"></th>
      <th style="padding: 10px;">Few-shot Correct</th>
      <th style="padding: 10px;">Few-shot Incorrect</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="padding: 10px;">Zero-shot Correct</td>
      <td style="padding: 10px;">258</td>
      <td style="padding: 10px;">9</td>
    </tr>
    <tr>
      <td style="padding: 10px;">Zero-shot Incorrect</td>
      <td style="padding: 10px;">38</td>
      <td style="padding: 10px;">25</td>
    </tr>
    <tr>
      <td style="padding: 10px;"><em>McNemar χ²</em></td>
      <td style="padding: 10px;">–</td>
      <td style="padding: 10px;">16.68</td>
    </tr>
    <tr>
      <td style="padding: 10px;"><em>McNemar p-value</em></td>
      <td style="padding: 10px;">–</td>
      <td style="padding: 10px;"><span style="background-color: #94d2eeff;">0.00044***</span></td>
    </tr>
  </tbody>
</table>

</div>

---

# **Discussion**

---
<!--  -->
### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---

<!--  -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!--  -->
### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>
- **Spikes in criticism**: June & August  
- **Key evaluative terms**:  
*Dictatorship*, *Misogyny*, *Corruption*, *Trash*  
- **Triggering events**:  
  - Lai's "democracy vs dictatorship" → backlash  
  - DPP accused of misogyny → counter against DPP  
  - \#MeToo movement → DPP's handling of cases  
- **Gender issues intertwined**: sexual harassment, assault, rape linked to \#MeToo discourse

---
<!--_paginate: true-->

### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>
- **Appraisal framework**:  
  - DPP against societal expectations  
  - Party's progressive value → credibility gap  
- **Impact**:  
  - <span style="font-variant:small-caps;">propriety</span> damage harder to repair
  - Stronger erosion of legitimacy and voter support

</div>

</div>

---

<!-- -->

### KMT: Negative Evaluation of <span style="font-variant:small-caps;">capacity</span>

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---

<!-- -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!-- -->
### KMT: Negative Evaluation of <span style="font-variant:small-caps;">capacity</span>
- Spikes in criticism: April peak, November rise
- Key evaluative terms:  
*infighting*, *Supid*, *Ueless*, *No combat power* 
- Triggering events:
  - Candidate selection delays → frustration
  - Visible intra‑party conflict → loss of unity
- Organizational issues: poor decision‑making efficiency, weak coordination

---
<!--  -->
### GPT Prompt Setting: Error Analysis

---

<!--  -->
### Few-shot Improves Classification

<div style="font-size: 36px; line-height: 1.6; text-align: center; max-width: 100%;">

- Zero-shot models often confuse subcategories (<span style="font-variant:small-caps;">tenacity</span> → <span style="font-variant:small-caps;">capacity</span>, <span style="font-variant:small-caps;">normality</span> → <span style="font-variant:small-caps;">propriety</span>). 
- Few-shot prompting provides semantic cues, significantly improving classification accuracy.
- Results: <span style="font-variant:small-caps;">tenacity</span> corrected in **14/16** cases, <span style="font-variant:small-caps;">normality</span> corrected in **3/4** cases.

</div>

---
<!--_paginate: true-->
<!-- -->
### Few-shot: Error Analysis

<div style="font-size: 36px; line-height: 1.6; text-align: center; max-width: 100%;">

- Even with few-shot prompting, some misclassifications remain frequent.  
- Two major error types:  
	- <span style="font-variant:small-caps;">propriety</span> → <span style="font-variant:small-caps;">capacity</span> (10/15 cases)  
	- <span style="font-variant:small-caps;">capacity</span> → <span style="font-variant:small-caps;">normality</span> (6/14 cases)

</div>

---
<!--_paginate: true-->
<!-- -->
#### Error Type 1: <span style="font-variant:small-caps;">propriety</span> → <span style="font-variant:small-caps;">capacity</span>

<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (12)**  
Gold: <span style="font-variant:small-caps;">propriety</span> (moral judgment)  
Predicted: <span style="font-variant:small-caps;">capacity</span> (misread as competence)

(12) **民進黨的國家機器真有夠噁爛**
&emsp;&emsp;**"The DPP's state apparatus is truly disgusting."**
- Issue: Model reads "state apparatus" as an incompetent actor rather than a morally illegitimate practice.  
- Insight: Domain-specific prompts could help emphasize how political context shifts evaluative meaning.

</div>

</div>

---
<!--_paginate: true-->
<!-- -->
#### Error Type 2: *CAPACITY* → *NORMALITY*

<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (13)**  
Gold: *capacity* (competence)  
Predicted: *capacity* (abnormality)

(13) **國民黨內部一片混亂**
&emsp;&emsp;**"The KMT is in utter chaos internally."**
- Issue: Model interprets the phrase as norm deviation rather than inability to manage internal affairs.  
- Insight: More domain-tailored examples could clarify the boundary.

</div>

---
<!--_paginate: true-->
<!-- -->
### Limitation & Conclusion
- Limitations:
  - Keyword-based dataset → possible selection bias
  - Exclusion of sarcasm/irony
- Capacity to govern vs. Legitimacy to govern
- Evaluative expressions reshape legitimacy to govern
- Classification experiments:
  - Few-shot prompting improved performance.
  - Need prompts enriched with domain-oriented knowledge.


---

# **Thank you!**