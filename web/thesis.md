---
marp: true
theme: uncover
html: true
---

<!-- _class: lead -->

<!-- 封面投影片（_class: lead 讓它整頁置中、無頁碼） -->

### Political Comment Opinion Analysis and Applications of Large Language Models: A Case Study of Social Media Comments on Taiwan’s 2024 Presidential Election

<div style="position: absolute; bottom: 30px; left: 100px; font-size: 0.8em; text-align: left;">

Hao-Yun Chuang  
Linguistic Institute, NCCU  
2025 October

</div>

---

# **Quick Recaps**

---

<!--_paginate: true-->
### Research background & motivation

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Motivation:** PTT is key to political evaluation, but existing automatic analysis focuses on polarity, ignoring deeper evaluative dimension.
- **Goal:** Apply **Appraisal framework** to automatically detect Judgement in political comments and analyze how parties are evaluated during 2024 Presidential Election.
- **Contribution:** Combines annotation and LLM-based classification to build a system for fine-grained political discourse analysis.

</div>

---

## Methodology

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Data:** PTT Gossiping board comments (14018 instances).
- **Annotation:** polarity & inscribed Judgement subcategories (manual)
- **Automation:** GPT-based classification and visualization system.

</div>

---

# **Results**

---

<!--_paginate: true-->
#### Evaluative *Judgement* Frequency
<br>
<div style="transform: scale(1);">

<table style="width: 100%; text-align: center; border-collapse: collapse; font-size: 18px;">
  <tr style="background-color: #44A6D4; color: white;">
    <th>Party</th>
    <th>Total Annotations</th>
    <th>Most Frequent Subcategory</th>
    <th>Polarity Distribution (Negative / Positive)</th>
  </tr>
  <tr>
    <td>DPP</td>
    <td>230</td>
    <td>Neg. <i>propriety</i> (140/230)</td>
    <td>Predominantly Negative</td>
  </tr>
  <tr>
    <td>KMT</td>
    <td>91</td>
    <td>Neg. <i>capacity</i> (54/91)</td>
    <td>Predominantly Negative</td>
  </tr>
  <tr>
    <td>TPP</td>
    <td>9</td>
    <td>Limited Data (Newer Party)</td>
    <td>Mostly Negative</td>
  </tr>
</table>

</div>

---
<!--_paginate: true-->
#### Fisher's Test: *Judgement* subcategories

<div style="transform: scale(1);">

<table style="width: 100%; text-align: center; border-collapse: collapse; font-size: 24px;">
  <tr style="background-color: #44A6D4; color: white;">
    <th>Party Comparison</th>
    <th>Subcategory</th>
    <th>Odds Ratio</th>
    <th>Significance</th>
  </tr>
  <tr>
    <td>KMT vs DPP</td>
    <td><i>capacity</i></td>
    <td>14×</td>
    <td>Significant</td>
  </tr>
  <tr>
    <td>KMT vs DPP</td>
    <td><i>propriety</i></td>
    <td>1/7× (DPP higher)</td>
    <td>Significant</td>
  </tr>
  <tr>
    <td>TPP vs KMT</td>
    <td>All Subcategories</td>
    <td>N/A</td>
    <td>Not Significant</td>
  </tr>
  <tr>
    <td>TPP vs DPP</td>
    <td>All Subcategories</td>
    <td>N/A</td>
    <td>Not Significant</td>
  </tr>
</table>

</div>

---
<!--_paginate: true-->
#### Fisher's Test: Subcategories with Polarity

<div style="transform: scale(1);">

<table style="width: 100%; text-align: center; border-collapse: collapse; font-size: 28px;">
  <tr style="background-color: #44A6D4; color: white;">
    <th>Judgment Dimension</th>
    <th>Polarity</th>
    <th>Targeted Party</th>
    <th>Significance</th>
  </tr>
  <tr>
    <td><i>propriety</i></td>
    <td>Negative</td>
    <td>DPP</td>
    <td>Significant</td>
  </tr>
  <tr>
    <td><i>capacity</i></td>
    <td>Negative</td>
    <td>KMT</td>
    <td>Significant</td>
  </tr>
</table>

</div>

---
<!--_paginate: true-->
## Classification Report

<div style="transform: scale(0.85); transform-origin: top left; width: 120%;">

<table style="width: 100%; border-collapse: collapse; text-align: center; font-size: 28px;">
  <thead>
    <tr style="background-color: #44A6D4; color: white;">
      <th style="padding: 10px; min-width: 200px;">JUDGEMENT Category</th>
      <th style="padding: 10px; min-width: 160px;">Prompting Type</th>
      <th style="padding: 10px; min-width: 100px;">Precision</th>
      <th style="padding: 10px; min-width: 100px;">Recall</th>
      <th style="padding: 10px; min-width: 100px;">F1 Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Overall Macro-average</td>
      <td>Zero-shot</td>
      <td>0.61</td>
      <td>0.63</td>
      <td><strong>0.62</strong></td>
    </tr>
    <tr>
      <td>Overall Macro-average</td>
      <td>Few-shot</td>
      <td>0.84</td>
      <td>0.86</td>
      <td><strong>0.85</strong></td>
    </tr>
    <tr>
      <td><i>tenacity</i></td>
      <td>Zero-shot</td>
      <td>0.55</td>
      <td>0.50</td>
      <td>0.52</td>
    </tr>
    <tr>
      <td><i>tenacity</i></td>
      <td>Few-shot</td>
      <td>0.78</td>
      <td>0.82</td>
      <td>0.80</td>
    </tr>
    <tr>
      <td><i>normality</i></td>
      <td>Zero-shot</td>
      <td>0.58</td>
      <td>0.60</td>
      <td>0.59</td>
    </tr>
    <tr>
      <td><i>normality</i></td>
      <td>Few-shot</td>
      <td>0.81</td>
      <td>0.83</td>
      <td>0.82</td>
    </tr>
  </tbody>
</table>

</div>

---
<!--_paginate: true-->
## McNemar test
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
      <td style="padding: 10px;">0.00044</td>
    </tr>
  </tbody>
</table>

</div>

---
<!--_paginate: true-->
## Summary

<div style="font-size: 26px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Negative sentiment dominates**: DPP mostly for _propriety_; KMT for _capacity_.  
- **Statistical focus**: _propriety_ (DPP) & _capacity_ (KMT)  shows significance.  
- **Model boost**: Few-shot outperforms zero-shot (F1 ↑ ~0.2).  
- **Significant improvement**: McNemar χ² = 16.68, p < 0.001 confirms performance improvement.  
- **Analytical value**: Results validate automated judgment detection.  

<br>

👉 **Next:** Use these findings to guide the development of *System Design & Discussion*,  focusing on how they affect real-world applications through visualization tools.

</div>


---

# **System Design & Discussion**

---

<div style="font-size: 24px; line-height: 1.6; text-align: center; max-width: 100%;">

# DPP: negative evaluation of _propriety_

</div>

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---
<!--_paginate: true-->
<div style="display: flex; justify-content: center; align-items: center; height: 100%;">

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

## \#MeToo: DPP's _propriety_ Crisis
1. Event time: began in late May and early June
2. Background: survivors of sexual harassment and assault speaks out
3. Outcome: The DPP, built on progressive values, became a key target.

</div>

</div>

---

<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
### Observation and Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- **Breach of expectations:** DPP's slow, opaque response clashed with its progressive image.
- **Focus:** Criticism targeted _propriety_ over other subcategories.
- **Consequences:** Moral failure hurts legitimacy more deeply.
- **Support:** Moral scandals cut voter support more (von Sikorski, 2018); undemocratic acts seen as moral flaws (Walter & Redlawsk, 2019).

</div>

---

<div style="font-size: 24px; line-height: 1.6; text-align: center; max-width: 100%;">

# KMT: negative evaluation of _capacity_

</div>
<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---
<!--_paginate: true-->
<div style="display: flex; justify-content: center; align-items: center; height: 100%;">

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

### Delayed Nomination: Doubts on KMT's _capacity_
1. Event time: increased in April
2. Background: Kuomintang's delayed presidential candidate nomination
3. Outcome: being criticized at its organizational management ability

</div>

</div>

---

<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
### Observation and Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- **From party to governance:** Voters extrapolated nomination indecision to doubts about the KMT's ability to govern effectively.
- **Legitimacy impact:** _capacity_ criticisms undermine public trust in a party’s readiness for office. 
- **Research alignment:** Intra-party conflict before elections erodes confidence and weakens performance (Klingelhöfer & Müller, 2024).

</div>

---

### GPT Prompt setting: Error Analysis

---

### Few-shot Improves Classification

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- Zero-shot models often confuse subcategories (*tenacity* → *capacity*, *normality* → *propriety*). 
- Few-shot prompting provides semantic cues, significantly improving classification accuracy.
- Results: _tenacity_ corrected in **14/16** cases, _normality_ corrected in **3/4** cases.

</div>

---
<!--_paginate: true-->
### Few-shot: Error Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- Even with few-shot prompting, some misclassifications remain frequent.  
- Two major error types:  
	- *propriety* → *capacity* (10/15 cases)  
	- *capacity* → *normality* (6/14 cases)

</div>

---
<!--_paginate: true-->
#### Error Type 1: *PROPRIETY* → *CAPACITY*

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (12)**  
Gold: *propriety* (moral judgment)  
Predicted: *capacity* (misread as competence)

(12) **民進黨的國家機器真有夠噁爛**
&emsp;&emsp;**"The DPP’s state apparatus is truly disgusting."**
- Issue: Model reads "state apparatus" as an incompetent actor rather than a morally illegitimate practice.  
- Insight: Domain-specific prompts could help emphasize how political context shifts evaluative meaning.

</div>

</div>

---
<!--_paginate: true-->
#### Error Type 2: *CAPACITY* → *NORMALITY*

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (13)**  
Gold: *capacity* (competence)  
Predicted: *capacity* (abnormality)

(13) **國民黨內部一片混亂**
&emsp;&emsp;**"The KMT is in utter chaos internally."**
- Issue: Model interprets the phrase as norm deviation rather than inability to manage internal affairs.  
- Insight: More domain-tailored examples could clarify the boundary.

</div>