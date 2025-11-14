---
marp: true
theme: uncover
html: true
---


<!-- _class: lead -->

<!-- Good afternoon everyone. My name is Hao‑Yun Chuang from the Graduate Institute of Linguistics at NCCU. Today I will present my study Evaluations of Political Judgements: A Corpus-Based Appraisal Analysis of Online Comments on the Taiwan 2024 Presidential Election and its Utility for LLM Implementation.   -->

#### Evaluations of Political Judgements: A Corpus-Based Appraisal Analysis of Online Comments on the Taiwan 2024 Presidential Election and its Utility for LLM Implementation

<div style="position: absolute; bottom: 30px; left: 100px; font-size: 0.8em; text-align: left;">

Hao-Yun Chuang  
Graduate Institute of Linguistics, NCCU  
18 November 2025

</div>

---
<!-- Let me begin with the nature of online political comments.  
On platforms like PTT, people like to discuss and criticize to the topics related to the politics, so political comments such as ‘腐化的Ａ黨’ are common. A 黨 in these comments function as cognitive shortcuts, shaping how people perceive entire parties rather than just individuals. Therefore, this study will focus on how people evaluate parties.  
These kinds of political comment spread rapidly, are anonymous, grassroots in nature, and highly diverse. This makes them a rich source for analyzing the public opinion in the political discourse. -->
<!--_paginate: true-->
## Online Political Comment
- 「腐化的Ａ黨」→ political comment
- As an cognitive shortcut
→ people tend to evaluate political party (Gastil, 2014)
- Characteristics
  - Immediacy and rapid dissemination
  - Anonymity and grassroot nature
  - Diversity and large scale

---
<!-- Most NLP research on analyzing such public opinion has mostly focused on polarity — whether a comment is positive or negative.  
But It overlooks evaluative dimensions such as competence, honesty, or morality.  
My study argues that we need fine‑grained categories to understand how party are evaluted in the online political discourse.  -->

<!--_paginate: true-->
### Deeper Understanding of the Comment
- 「腐化的Ａ黨」 
* → evaluation of the morality
- Research in NLP mostly limits at polarity exploration.
* More fine-grained categories of evaluation are needed.
- It helps understand how political party's image is constructed and challenged.

---

<!-- To address this, I adopt the Appraisal framework proposed by White in 2005. This framework, rooted in Systemic Functional Linguistics, analyzes how language conveys attitudes and evaluations. It provides structured categories that allow us to go beyond simple sentiment and capture nuanced dimensions in the evaluation. -->
<!--_paginate: true-->
#### Appraisal Framework (Martin & White, 2005)

- Derives from Systemic Functional Linguistics (Halliday& Matthiessen, 2004)
- Provides a tool to systematically describe how speakers or writers evaluate through language.  
- Commonly applied in different texts (e.g., politics, media, education)


---
<!-- Within the Appraisal framework, my focus is on the subcategories of Judgement. Judgement is the way language evaluates people and groups, not simply in terms of positive or negative attitudes, but in terms of specific social values. It is divided into five subcategories, each highlighting a different dimension of evaluation.

The first is Capacity, which refers to competence and effectiveness. When someone says, “Ａ黨又沒實力” the criticism is not about morality or honesty, but about a lack of skill, resources, or practical ability. In other words, the party is judged as incapable of delivering results, and this is why the phrase “no competence” directly signals a Capacity judgement.

The second is Propriety, which concerns morality and ethical conduct. When we hear, “Ｂ黨公平公正公開” the evaluation is  about whether it acts in line with moral standards. Fairness, justice, and openness are ethical benchmarks, and praising them positions the party as morally credible. This is why Propriety is closely tied to ideas of fairness, justice, and transparency.

The third is Veracity, which deals with honesty and truthfulness. If someone says, “Ｃ黨都在說謊” the negative evaluation is about deception. The party is framed as untrustworthy, and the harm lies in misleading the public. This is distinct from incompetence or immorality; it is specifically about truthfulness.

The fourth is Tenacity, which highlights determination and resolve. For example, “Ｄ黨保持從政初心” praises perseverance and steadfastness. The evaluation here is about holding firm to values and enduring challenges, which is seen as admirable persistence.

Finally, we have Normality, which evaluates whether behavior is typical or socially expected. When someone says, “Ｅ黨同意才奇怪” the judgement is about deviation from what is considered normal. The party is framed as unusual or unexpected, and that strangeness itself becomes the evaluative expression.

Together, these five subcategories—Capacity, Propriety, Veracity, Tenacity, and Normality—allow us to see not just whether an evaluation is positive or negative, but what kind of value is being asserted. They reveal whether the speaker is targeting competence, morality, honesty, resolve, or normality.-->
<!--_paginate: true-->
## <span style="font-variant:small-caps;">judgement</span> & Subcategories
<div style="transform: scale(1);">

<table style="width: 100%; text-align: left; border-collapse: collapse; font-size: 32px;">
  <tr style="background-color: #44A6D4; color: white;">
    <th>Subcategory</th>
    <th>What it Evaluates</th>
    <th>Example from PTT</th>
  </tr>
  <tr>
    <td>Capacity</td>
    <td>competence, intelligence</td>
    <td>A 黨又<span style="background-color: #94d2eeff;">沒實力</span>！</td>
  </tr>
  <tr>
    <td>Propriety</td>
    <td>morality, ethics</td>
    <td>Ｂ黨最<span style="background-color: #94d2eeff;">公平公正公開</span>！</td>
  </tr>
  <tr>
    <td>Veracity</td>
    <td>honesty, truthfulness</td>
    <td>Ｃ黨都在<span style="background-color: #94d2eeff;">說謊</span>！</td>
  </tr>
  <tr>
    <td>Tenacity</td>
    <td>determination</td>
    <td>Ｄ黨<span style="background-color: #94d2eeff;">保持</span>從政初心！</td>
  </tr>
  <tr>
    <td>Normality</td>
    <td>unusualness</td>
    <td>E 黨願意才<span style="background-color: #94d2eeff;">奇怪</span>勒！</td>
  </tr>
</table>

</div>

---

<!-- To stress the connection between Judgement subcategories and the politics, Previous studies show that political comments often focus on behavior and character.  
Also, because Appraisal framework relies heavily on context, in Chinese political contexts, JUDGEMENT has also proven to be especially relevant.  
because it captures accusations of dishonesty, incompetence, or moral failure.-->
<!--_paginate: true-->

## <span style="font-variant:small-caps;">judgement</span> in Political Discourse
- Political comments focus on target's behavior and character (Zappavigna, 2017; Cavasso & Taboada, 2021).
- <span style="font-variant:small-caps;">judgement</span> is proven to be an appropriate resources in Chinese political context (L. Li et al., 2025).

---
<!-- Manual annotation of categories in Appraisal is very time‑consuming. So the researchers turned to the model classification. Traditional machine learning models require retraining and lack flexibility. Large language models, however, are more context‑aware, which also fit the nature of the Appraisal framework. By designing prompts, we can guide them to classify evaluative language automatically. I also implemented a visualization dashboard to make these evaluations accessible. -->
<!--_paginate: true-->

### Research Gap
- Annotation problem & solutions
  - Manual annotation → inefficient
  - Traditional ML → lexicon-based (Casey et al., 2005) <!--poor adaptability-->
  - Deep learning → BERT, RoBERTa (Mollá, 2020; Aroyehun & Gelbukh, 2020) <!--need retrain-->
  - Generative LLM → instruction-based prompting (Imamovic et al., 2024) <!--still misclassifies Judgement subcategories-->
- Implementation:
  - visualization of the evaluation

---
<!--My study addresses two main questions:

1.  How do Taiwanese social media users employ evaluative language through JUDGEMENT subcategories to express opinions toward political parties?
2.  How do different prompting strategies — zero‑shot versus few‑shot — influence GPT’s performance in classifying these subcategories?-->
<!--_paginate: true-->
## Research Questions
<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

1. How do Taiwanese social media users employ evaluative language through <span style="font-variant:small-caps;">judgement</span> subcategories within the Appraisal framework to express opinions toward different political parties?
2. How do different prompting strategies (zero-shot vs. few-shot) influence the performance of GPT in classifying <span style="font-variant:small-caps;">judgement</span> subcategories?

</div>

---
<!-- The data comes from the PTT Gossiping board, scraped from January 12, 2023 to January 12, 2024, which is the whole presidential election year before the election day. After filering the keyword, finally 14018 comments were to be annotated. Here is the annotation process.
. -->
<!--_paginate: true-->
## **Methodology**

---
## Data Annotation
<div style="font-size: 36px; line-height: 1.4; text-align: left; max-width: 100%;">

- **Data:** PTT Gossiping board
- **Date**: 2023.01.12 - 2024.01.12
- **Filtering (keywords)**: 14018 comments
</div>

---
<!--_paginate: true-->

<!-- for example, to understand the process, first we have to see the target entity -->
<img src="figure/an_1.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---
<!--_paginate: true-->

<!-- to understand the process, first we have to see the target entity. Here because the target of this study is political party, so XX黨 is the target entity -->
<img src="figure/an_2.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---
<!--_paginate: true-->

<!-- if the target entity contains metonymic expression, for example, here kmt is political party from the surface, but it actually refers to the headquarter of the kmt.  -->
<img src="figure/an_3.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---
<!--_paginate: true-->

<!-- Metonymic expression like this are excluded from the study. -->
<img src="figure/an_4.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---
<!--_paginate: true-->

<!-- because 說謊 evaluates the truthfulness of the XX 黨, it belongs to the negative evaluation of veracity -->
<img src="figure/an_5.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---
<!--_paginate: true-->

<!-- and the evaluative expression here is 說謊 -->
<img src="figure/an_6.png" alt="背景圖" style="width:100%; height:100%; object-fit:cover;">

---

# **Results**

---

<!-- The table from left to right shows the frequency of the judgements in DPP, kmt and tpp The results show clear differences across parties.  
For the DPP, negative Propriety evaluations dominated, which shows 129 comments.  
For the KMT, negative Capacity evaluations were most frequent, which shows 52 comments.  
The TPP received far fewer evaluations overall, which may due to its newer presence. -->
<!--_paginate: true-->
#### <span style="font-variant:small-caps;">judgement</span> Frequency
<div style="display: flex; font-family: Arial, sans-serif; font-size: 30px;">

  <!-- Overall -->
  <div style="flex: 1;">
    <div style="text-align: left; background-color: #00A65A; color: white; padding: 6px;"><b>DPP</b></div>
    <table style="width: 100%; text-align: left; border-collapse: collapse;">
      <tr style="background-color: #00A65A; color: white;">
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
    <div style="text-align: left; background-color: #005AB5; color: white; padding: 6px;"><b>KMT</b></div>
    <table style="width: 100%; text-align: left; border-collapse: collapse;">
      <tr style="background-color: #005AB5; color: white;">
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
    <div style="text-align: left; background-color: #20B2AA; color: white; padding: 6px;"><b>TPP</b></div>
    <table style="width: 100%; text-align: left; border-collapse: collapse;">
      <tr style="background-color: #20B2AA; color: white;">
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
<!-- Statistical tests confirmed significant differences.  
For example, CAPACITY evaluations were 13 times more likely to target the KMT than the DPP.  
Meanwhile, PROPRIETY evaluations were 7 times more likely to target the DPP than KMT.  
These findings highlight distinct evaluative patterns pairwise. Moreover, DPP's negative propriety and KMT's negative capacity all show dominant number in contributing the significance in the statistical test. Later we will investigate deeper the reason behind through the visualization dashboard.-->
#### Fisher's Test: <span style="font-variant:small-caps;">judgement</span> subcategories

<div style="font-family: Arial, sans-serif; font-size: 30px;">

  <table style="width: 100%; text-align: left; border-collapse: collapse;">
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

<!--So let's first take a closer look at why dpp was evaluated mainly on Propriety. So if we look at the evaluation of negative propriety the whole year, we can find two spike that close to each other. So we will focus on these two spike, which is around June to August -->
### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---

<!--_paginate: true-->

<!-- To see exactly how dpp is evaluate, we can adjust the panel from June to August -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!--   
As we can see from the previous slides, Key terms include dictatorship, misogyny, corruption, and trash. tracing back to the original news and the temporal overlap,
these were linked to Lai’s ‘democracy vs dictatorship’ statement, people refute that dpp is the one who is dictator. Worth to note that because of the #MeToo movement was under the spotlight at that time, though may not be directly related to metoo movement, as long as it's propriety-related issue, people also like to raise questions about the DPP’s handling of gender issues altogether. -->
### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>
- **Spikes in criticism**: June & August  
- **Key evaluative terms**:  
專制 'dictatorship', 厭女 'misogyny', 貪污 'corruption'
- **Triggering events**:  
  - Lai's "democracy vs dictatorship" → backlash  
  - DPP accused of misogyny → counter against DPP  
- **Gender issues intertwined**: sexual harassment, assault, rape linked to \#MeToo discourse

---
<!-- This scandal is against societal expectations about dpp because dpp brands itself on progressive value. However, this scandal may create credibility gap for people, which is harder to repair, and might cause stronger erosion of legitimacy and voter support -->
<!--_paginate: true-->

### DPP: Negative Evaluation of <span style="font-variant:small-caps;">propriety</span>
- DPP against societal expectations  
- Party's progressive value → credibility gap  
- **Impact**:  
  - <span style="font-variant:small-caps;">propriety</span> damage harder to repair
  - Stronger erosion of legitimacy and voter support

</div>

</div>

---
<!--_paginate: true-->

<!--Subsequently, kmt also shows a significant difference comparing to dpp, so If we look at the evaluation of negative capacity the whole year for kmt, we can find the highest spike around April. So next we will focus on this spike-->
### KMT: Negative Evaluation of <span style="font-variant:small-caps;">capacity</span>

<iframe
	src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=trend_line&embedded=true&scale=1&scroll=220"
	width="1200"
	height="800"
	style="border:0; max-width:100%; aspect-ratio:16/9;"
	loading="lazy"
></iframe>

---
<!--_paginate: true-->

<!-- To see exactly how dpp is evaluate, samely, we can adjust the panel from march to april. we can see terms like 內鬥智障 in the word cloud, so -->
<iframe
  src="https://publicopiniondashboard-milanochuang.streamlit.app/?section=wordcloud&embedded=true&scale=1"
  width="1200"
  height="800"
  style="border:0;max-width:100%;aspect-ratio:16/9;"
  loading="lazy">
</iframe>

---
<!--_paginate: true-->
<!-- 
Terms like infighting and useless reflected frustration with delays in candidate selection and visible intra‑party conflict.  
These evaluations framed the KMT as organizationally incompetent and the loss of unity, and it might be seen by the commenter and the voter as a sign of poor leadership to the country -->
### KMT: Negative Evaluation of <span style="font-variant:small-caps;">capacity</span>
- Spikes in criticism: April peak, November rise
- Key evaluative terms:  
內鬥 'infight', 智障 'stupid', 無能 'useless'
- Triggering events:
  - Candidate selection delays → frustration
  - Visible intra‑party conflict → loss of unity
- Organizational issues: poor decision‑making efficiency, weak coordination

---
<!-- And let's move on to the model classification. -->
# **Model Classification**

---


<!--_paginate: true-->
<!-- Comparing zero‑shot and few‑shot prompting, few‑shot consistently outperformed zero‑shot.  
Overall, the weighted F1 score rose from 0.80 to 0.89. -->
#### Classification Report

<div style="font-family: Arial, sans-serif; font-size: 27px;">

  <table style="width: 100%; text-align: left; border-collapse: collapse;">
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
    <tr style="background-color: #0f5b7fff; color: white;">
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
<!-- McNemar test confirmed that the improvement of the model was statistically significant.  
Few‑shot prompting corrected many errors that zero‑shot had made, showing the value of carefully designed prompts.” -->
<!--_paginate: true-->
## McNemar Test
<div style="transform: scale(0.85); transform-origin: top left; width: 120%;">

<table style="width: 70%; text-align: left; font-size: 27px; border-collapse: collapse; margin: auto;">
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
<!--  -->
### GPT Prompt Setting: Error Analysis

---
<!--_paginate: true-->

<!-- Zero-shot models often confuse similar subcategories — for example, interpreting tenacity as capacity or normality as propriety.
With few-shot prompting, the model learns semantic cues that help it make finer distinctions.
As a result, tenacity is correctly identified in 14 out of 16 cases, and normality in 3 out of 4, showing that targeted examples can significantly improve classification. -->
### Few-shot Improves Classification

<div style="font-size: 36px; line-height: 1.6; text-align: center; max-width: 100%;">

- Zero-shot models often confuse subcategories (<span style="font-variant:small-caps;">tenacity</span> → <span style="font-variant:small-caps;">capacity</span>, <span style="font-variant:small-caps;">normality</span> → <span style="font-variant:small-caps;">propriety</span>). 
- Few-shot prompting provides semantic cues, significantly improving classification accuracy.
- Results: <span style="font-variant:small-caps;">tenacity</span> corrected in **14/16** cases, <span style="font-variant:small-caps;">normality</span> corrected in **3/4** cases.

</div>

---
<!--_paginate: true-->
<!-- However, Even with few-shot prompting, some misclassifications remain.
The most common errors are confusing propriety with capacity — 10 out of 15 times — and capacity with normality — 6 out of 14 times.
These cases show that evaluative expression are still hard for the model to capture precisely. So let's look closely at theses errors. -->
### Few-shot: Error Analysis

<div style="font-size: 36px; line-height: 1.6; text-align: center; max-width: 100%;">

- Even with few-shot prompting, some misclassifications remain frequent.  
- Two major error types:  
	- <span style="font-variant:small-caps;">propriety</span> → <span style="font-variant:small-caps;">capacity</span> (10/15 cases)  
	- <span style="font-variant:small-caps;">capacity</span> → <span style="font-variant:small-caps;">normality</span> (6/14 cases)

</div>

---
<!--_paginate: true-->
<!-- Here, the model often mistakes propriety for evaluations of capacity.
For example: “民進黨的國家機器真有夠噁爛”
The gold label is propriety, because it criticizes the unethical use of state power in the context of the democratic country. Becasue the word state appratus itself means the manipulative power of the government, the model predicts capacity, interpreting it as a comment on competence.
This reflects how political language can confuse without knowing the context of the data, making classification challenging. -->
#### Error Type 1: <span style="font-variant:small-caps;">propriety</span> → <span style="font-variant:small-caps;">capacity</span>

<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (12)**  
Gold: <span style="font-variant:small-caps;">propriety</span>
Predicted: <span style="font-variant:small-caps;">capacity</span>

(12) **民進黨的國家機器真有夠噁爛**
&emsp;&emsp;**"The DPP's state apparatus is truly disgusting."**
- Issue: Model reads "state apparatus" as an incompetent actor rather than a morally illegitimate practice.  
- Insight: Domain-specific prompts could help emphasize how political context shifts evaluative meaning.

</div>

</div>

---
<!--_paginate: true-->
<!-- 
Another recurring error is reading capacity as normality.
For example: “國民黨內部一片混亂” the gold label is CAPACITY because 一片混亂 ‘utter chaos’ actually evaluates the party’s managerial incompetence, but the model misclassified it as NORMALITY, interpreting it as a deviation from the actual order in the room. It shows its ability to identify the metonymy. Since such expressions in political contexts often signal inability rather than mere abnormality, deeper investigation in metonymy identificaiton with LLM could help reduce this ambiguity.-->
#### Error Type 2: <span style="font-variant:small-caps;">capacity</span> → <span style="font-variant:small-caps;">normality</span>

<div style="font-size: 36px; line-height: 1.6; text-align: left; max-width: 100%;">

**Example (13)**  
Gold: <span style="font-variant:small-caps;">capacity</span>  
Predicted: <span style="font-variant:small-caps;">normality</span>

(13) **國民黨中央一片混亂**
&emsp;&emsp;**"The KMT central is in utter chaos internally."**
- Issue: Model interprets the phrase as norm deviation rather than inability to manage internal affairs.  
- Insight: More domain-tailored examples could clarify the boundary.

</div>

---
<!--_paginate: true-->
<!-- However, this study has limitations: keyword‑based data may introduce bias, sarcasm and irony were excluded, and only inscribed evaluations were analyzed.  
Nevertheless, the findings show that: when it comes to the infight in the party, people tend to evaluate it as the deficiency of the ability, while commenters also tend to evaluate how party handle scandals to see if the party is morally legitimate enough to govern.
This demonstrates the potential of large language models to assist in political discourse analysis, while also highlighting the need for domain‑specific prompt design.” -->
### Conclusion & Limitation
- Commenters focus more on the evaluations of <span style="font-variant:small-caps;">propriety</span> and <span style="font-variant:small-caps;">capacity</span> <!--修改-->
- Classification experiments:
  - Few-shot prompting improved performance.
  - Need prompts enriched with domain-oriented knowledge.
- Limitations:
  - Keyword-based dataset → possible selection bias
  - Exclusion of sarcasm/irony


---
<!-- 1. annotator agreement 要放進來
     2. 正負面評論那邊要講正符號負符號代表什麼 v
     3. Frequency of judgement subcategory
     4. polarity exploration v
     5. P.3 grammar check
     6. P.3 詳細罵他什麼東西 
     7. P.4 sfl citation, martin & white 2005 v
     8. 靠左v
     9. judgement subcategories 不用加分
     10.implementation 分行 v
     11. research questions v
     12. citation v
     13. P.12 總共幾筆資料，爬了什麼時候到什麼時候 v
     14. P.13 metonymy 過程要呈現，標記過程 
     15. P.17 拿掉 v
     16. 表格符合政黨顏色 v
     17. 文字指引看表格 
     18. P.20 直接接 24 v
     19. 人民在選舉中會特別在意這兩種 v
     20. P36 第三點刪掉 v
     21. 先講 conclusion 再講 limitation v
     22. 全部 subcategory 都 smallcaps v
     -->
# **Thank you!**