---
marp: true
theme: uncover
html: true
---

<!-- _class: lead -->

<!-- Good afternoon everyone. Today, I will present my research, Political Comment Opinion Analysis and Applications of Large Language Models: A Case Study of Social Media Comments on Taiwan’s 2024 Presidential Election.
This study focuses on how we can use large language models, or LLMs, to understand public opinion in online political discussions — specifically, how people evaluate political parties on PTT, one of Taiwan’s most influential online forums. -->

### Political Comment Opinion Analysis and Applications of Large Language Models: A Case Study of Social Media Comments on Taiwan's 2024 Presidential Election

<div style="position: absolute; bottom: 30px; left: 100px; font-size: 0.8em; text-align: left;">

Hao-Yun Chuang  
Linguistic Institute, NCCU  
2025 October

</div>

---

# **Quick Recaps**

---

<!--_paginate: true-->
<!-- Let’s start with a quick background.
PTT has become a central space for political evaluation and opinion expression in Taiwan. However, most existing automatic analysis only focuses on polarity — simply labeling texts as positive or negative.
This approach overlooks the different dimensions embedded in them. Therefore, this study uses Judgement, a category from the Appraisal framework, which looks at how people evaluate morality, competence, integrity, and values, to see how commenter evaluate political party.

The goal of this study is to apply the Appraisal framework to automatically detect Judgement in political comments and to examine how different parties were evaluated during the 2024 presidential election.
The contribution is twofold: build a system that combines manual annotation and LLM-based classification, and use it to provide a fine-grained analysis of political discourse. -->

### Research background & motivation

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Motivation:** PTT is key to political evaluation, but existing automatic analysis focuses on polarity, ignoring deeper evaluative dimension.
- **Goal:** Apply **Appraisal framework** to automatically detect Judgement in political comments and analyze how parties are evaluated during 2024 Presidential Election.
- **Contribution:** Combines annotation and LLM-based classification to build a system for fine-grained political discourse analysis.

</div>

---

<!-- Here’s a brief overview of the methodology.
Our data comes from 14,018 comments collected from the PTT Gossiping board. Each comment was manually annotated for polarity and Judgement subcategories.
Then used GPT-based classification to automate this process and developed a visualization system to explore evaluative patterns in the results. -->
## Methodology

<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Data:** PTT Gossiping board comments (14018 instances).
- **Annotation:** polarity & inscribed Judgement subcategories (manual)
- **Automation:** GPT-based classification and visualization system.

</div>

---

# **Results**

---

<!-- Moving on to the results.
Across all parties, negative Judgement dominates the online discourse.
	•	For the DPP, the most frequent criticism was in the propriety category — meaning people questioned its morality and integrity.
	•	For the KMT, criticism focused on capacity, referring to perceived incompetence or organizational weakness.
	•	For the TPP, the data size was smaller, which may due to the fact that TPP is relatively new, so people tend to evaluate its principal rather than the party. Their comments were still mostly negative.

This suggests that negative evaluations are a central feature of Taiwan’s political evaluation online, but the focus of criticism differs between parties. -->
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
<!-- Statistical analysis with Fisher’s exact test confirms these patterns.
	•	The KMT was 14 times more likely to receive negative evaluations in capacity compared to the DPP.
	•	Conversely, the DPP was seven times more likely to be criticized for propriety.
 -->
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
<!-- Afterwards, another fisher's test was applied adding polarity as the new variable to see what polarity of the evaluation in kmt and dpp is significant. It shows that:
	•	Negative propriety judgments were strongly associated with the DPP.
	•	Negative capacity judgments were strongly associated with the KMT. -->
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
<!-- Now let’s look at the model performance, we compared zero-shot and few-shot prompting.
	•	With zero-shot prompting, the macro F1 score was around 0.62.
	•	With few-shot prompting — where we provide example annotations — performance improved significantly to 0.85.

This shows that giving the model a few labeled examples helps it better capture subtle evaluative meanings. -->
## Classification Report

<div style="transform: scale(0.85); transform-origin: top left; width: 120%;">

<table style="width: 100%; border-collapse: collapse; text-align: center; font-size: 28px;">
  <thead>
    <tr style="background-color: #44A6D4; color: white;">
      <th style="padding: 10px; min-width: 200px;"></th>
      <th style="padding: 10px; min-width: 160px;">Prompt setting</th>
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
  </tbody>
</table>

</div>

---
<!--_paginate: true-->
<!-- We also conducted a McNemar test to measure whether the improvement was statistically significant.
The results — χ² = 16.68, p < 0.001 — confirm that few-shot prompting significantly outperforms zero-shot prompting.
This suggests that example-based learning is crucial for tasks involving complex evaluative language like Judgement classification. -->
<!-- ## McNemar test
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

--- -->
<!--_paginate: true-->
<!-- To summarize the main findings:
	1.	Negative evaluations dominate PTT political discourse.
	2.	The DPP is primarily criticized for propriety (morality), while the KMT faces criticism for capacity (competence).
	3.	These patterns are statistically significant and reflect deeper narratives about each party.
	4.	Few-shot prompting greatly improves classification accuracy.
	5.	Automated Judgement detection offers valuable insights for analyzing political language at scale.

These results set the stage for the system design and discussion section, where we explore how visualization tools and case studies can reveal the real-world implications of these findings. -->
## Summary

<div style="font-size: 26px; line-height: 1.6; text-align: left; max-width: 100%;">

- **Mostly Negative comment**: neg. _propriety_ (DPP); neg. _capacity_ (KMT)
- **Statistical focus**: _propriety_ (DPP) & _capacity_ (KMT)  shows significance.  
- **Model improvement**: Few-shot outperforms zero-shot (F1 ↑ ~0.2).  
- **Significant improvement**: McNemar χ² = 16.68, p < 0.001 confirms performance improvement.  
- **Analytical value**: Results validate automated judgment detection.  

<br>

👉 **Next:** Use these findings to guide the development of *System Design & Discussion*,  focusing on how they affect real-world applications through visualization tools.

</div>


---

# **System Design & Discussion**

---
<!-- If we choose negative evaluation of propriety in DPP, We can see from in the election year, there's a spike approximately between May and August. -->
##### DPP: negative evaluation of _propriety_

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---

<!-- If we look closely at how people express evaluation of propriety through word cloud, we can found that alongside 獨裁 ‘dictatorship’, many gender-related terms appear—such as 性騷擾 ‘sex-
ual harassment’, 外遇 ‘affair’, 強姦 ‘rape’, and 性侵犯 ‘sexual assault’. -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!-- If tracing back to the news during that period, we can found that evaluations focus on the #MeToo movement in 2023.
As survivors came forward in late May and June, the DPP — a party that prides itself on progressive values — faced intense scrutiny for its handling of sexual harassment cases.
Public criticism concentrated on propriety, accusing the party of hypocrisy, authoritarianism, and moral failure. -->
<div style="display: flex; justify-content: center; align-items: center; height: 100%;">

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

## \#MeToo: DPP's _propriety_ Crisis
1. Event time: began in late May and early June
2. Background: survivors of sexual harassment and assault speaks out
3. Outcome: The DPP, built on progressive values, became a key target.

</div>

</div>

---

<!--_paginate: true-->

<!-- Such breaches of moral expectations are particularly damaging because they undermine a party’s legitimacy — Sikorski and Walter's research also confirms that moral scandals may cut voter support more. -->
### Observation and Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- **Breach of expectations:** DPP's slow, opaque response clashed with its progressive image.
- **Focus:** Criticism targeted _propriety_ over other subcategories.
- **Consequences:** Moral failure hurts legitimacy more deeply.
- **Support:** Moral scandals cut voter support more (von Sikorski, 2018); undemocratic acts seen as moral flaws (Walter & Redlawsk, 2019).

</div>

---
<!-- Next, if we choose negative capacity in KMT, we can see from in the election year, there's a spike approximately between March and May. -->

##### KMT: negative evaluation of _capacity_

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---

<!-- (March and May) If we look closely at how people express evaluation of propriety through word cloud, it highlights evaluative expressions such as 內鬥, 智障, and 不團結, which dominated online comments during
this period.  -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!--If tracing back to the news during that period, a second case study looks at the KMT’s delayed nomination process.
Criticism spiked in April as the party struggled to decide on a presidential candidate, suggesting deficacy in organizational ability. -->
<div style="display: flex; justify-content: center; align-items: center; height: 100%;">

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

### Delayed Nomination: Doubts on KMT's _capacity_
1. Event time: increased in April
2. Background: Kuomintang's delayed presidential candidate nomination
3. Outcome: being criticized at its organizational management ability

</div>

</div>

---

<!--_paginate: true-->
<!--The frequent mention of 內鬥 reflects widespread frustration with the KMT’s inability to present a unified front during the critical phase of candidate selection. These expression of indecision and infight was widely interpreted as a sign of poor leadership and weak organizational capacity.
Critiques of capacity extend beyond party politics — they lead voters to question a party’s ability to govern effectively. Research also suggests that intra-party conflict before election may erode confidence and weaken the election performance -->
### Observation and Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- **From party to governance:** Voters extrapolated nomination indecision to doubts about the KMT's ability to govern effectively.
- **Legitimacy impact:** _capacity_ criticisms undermine public trust in a party's readiness for office. 
- **Research alignment:** Intra-party conflict before elections erodes confidence and weakens the performance of election (Klingelhöfer & Müller, 2024).

</div>

---

### GPT Prompt setting: Error Analysis

---

<!-- Zero-shot models often confuse similar subcategories — for example, interpreting tenacity as capacity or normality as propriety.
With few-shot prompting, the model learns semantic cues that help it make finer distinctions.
As a result, tenacity is correctly identified in 14 out of 16 cases, and normality in 3 out of 4, showing that targeted examples can significantly improve classification. -->
### Few-shot Improves Classification

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- Zero-shot models often confuse subcategories (*tenacity* → *capacity*, *normality* → *propriety*). 
- Few-shot prompting provides semantic cues, significantly improving classification accuracy.
- Results: _tenacity_ corrected in **14/16** cases, _normality_ corrected in **3/4** cases.

</div>

---
<!--_paginate: true-->
<!-- Even with few-shot prompting, some misclassifications remain.
The most common errors are confusing propriety with capacity — 10 out of 15 times — and capacity with normality — 6 out of 14 times.
These cases show that evaluative meanings are still hard for the model to capture precisely.-->
### Few-shot: Error Analysis

<div style="font-size: 30px; line-height: 1.6; text-align: center; max-width: 100%;">

- Even with few-shot prompting, some misclassifications remain frequent.  
- Two major error types:  
	- *propriety* → *capacity* (10/15 cases)  
	- *capacity* → *normality* (6/14 cases)

</div>

---
<!--_paginate: true-->
<!-- Here, the model often mistakes moral judgments for evaluations of ability.
For example: “The DPP’s state apparatus is truly disgusting.”
The gold label is propriety, because it criticizes the unethical use of state power. But the model predicts capacity, interpreting it as a comment on competence.
This reflects how political language can blur the line between morality and performance, making classification challenging. -->
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
<!-- Another recurring error is reading competence evaluations as norm deviations.
For example: “The KMT is in utter chaos internally.”
The gold label is capacity, since the comment targets the party’s lack of organizational control.
However, the model labels it normality, focusing instead on the idea of deviation from order. This shows how overlapping meanings in political discourse can still lead to confusion. -->
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

---
<!-- Let’s wrap up with the core insights from this study.  
First, we found that citizens evaluate political actors through two main lenses: capacity to govern and legitimacy to govern.  
Online comments aren’t just noise—they reflect deeper public perceptions and help shape party images.  
Our annotation work revealed consistent patterns in how these judgments are expressed linguistically.  
On the technical side, few-shot prompting improved classification accuracy, but context still matters.  
To move forward, models need richer political domain knowledge to better interpret evaluative language.  
Ultimately, these expressions in online discourse play a powerful role in shaping democratic debate. -->


<div style="font-size: 30px; line-height: 1.6; text-align: left; max-width: 100%;">

### Conclusion
• Citizens evaluate parties via capacity and propriety
• Online comments reflect deeper political perceptions
• Annotation reveals clear judgment patterns
• Few-shot prompting improves classification, but context matters
• Future models need political domain knowledge

</div>