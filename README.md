# LLM Writing Distortion
 
<div align="left" style="line-height: 1;">
  <a href="" target="_blank">
    <img alt="arXiv" src="https://img.shields.io/badge/arXiv-2506.07468-b31b1b?logo=arxiv&logoColor=white"/>
  </a>
  <a href="https://github.com/abdulhaim/llm_writing_distortion" target="_blank">
    <img alt="GitHub" src="https://img.shields.io/badge/GitHub-llm--writing--distortion-181717?logo=github"/>
  </a>
</div>

This repository accompanies the paper:  
**[How LLMs Distort Our Written Language]()**  
by *Marwa Abdulhai, Isadora White, Yanming Wan, Ibrahim Qureshi, Joel Z. Leibo, Max Kleiman-Weiner, Natasha Jaques.*
  
---
 
## Overview
 
We study these effects across three evaluation settings:

 - **Human Evaluation** — A randomized controlled trial where participants wrote an argumentative essay with or without access to an LLM.
- **ArgRewrite Analysis** — With a dataset of 86 human-written argumentative essays with expert feedback collected in 2021 (before the release of ChatGPT), we performed a counterfactual analysis comparing human revisions to revisions produced by three frontier LLMs (gpt-5-mini, gemini-2.5-flash, claude-3.5-haiku) across five revision types (general, minimal, grammar, completion, expansion).
- **ICLR Analysis** — An analysis of the strengths and weaknesses of 18k peer reviews from ICLR 2026 (where 21% were found to be LLM-generated).
 
---
 
## Repository Structure
 
```
llm_writing_distortion/
├── iclr_analysis/          # Diversity and homogenization analysis on ICLR co-writing data
├── argrewrite_analysis/    # Analysis of LLM-assisted revisions on the ArgRewrite corpus
├── ArgRewrite/             # ArgRewrite dataset files
├── NRC-Emotion-Lexicon/    # NRC Emotion Lexicon for sentiment and emotion scoring
├── human_evaluation/       # Human evaluation data and analysis notebooks
├── requirements.txt
└── README.md
```
 
---
 
## Quick Start
 
### Installation
 
We recommend setting up a clean conda environment:
 
```bash
git clone https://github.com/abdulhaim/llm_writing_distortion
cd llm_writing_distortion
conda create --name writing_distortion python=3.10
conda activate writing_distortion
pip install -r requirements.txt
```
 
### Running the Analysis
 
Each subdirectory contains Jupyter notebooks that can be run independently:
 
- **`human_evaluation/`** — Open the notebook to inspect human evaluation results comparing human-written and LLM-assisted writing samples.
- **`argrewrite_analysis/`** — Open the notebook to analyze content and emotional shifts across revision stages in the ArgRewrite corpus.
- **`iclr_analysis/`** — Open the notebook to reproduce diversity metrics (lexical and semantic homogenization scores) across writing conditions from the ICLR 2024 study.

 
---
 
## Datasets
 
### ArgRewrite-v2
The [ArgRewrite-v2 corpus](http://argrewrite.cs.pitt.edu/) (Chen et al., 2022) contains 86 argumentative essays written by university students in 2021, each paired with expert feedback and a human-revised second draft. Because this dataset predates the release of ChatGPT, it enables a clean counterfactual comparison: what would a human have written versus what an LLM produces given the same essay and the same expert feedback.
 
### NRC Emotion Lexicon
The [NRC Word-Emotion Association Lexicon](https://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm) (Mohammad and Turney, 2013) maps English words to eight basic emotions (anger, anticipation, disgust, fear, joy, sadness, surprise, trust) and two sentiments (positive, negative). Used to quantify shifts in affective tone induced by LLM revisions relative to human edits.
 
### LIWC-22
The [Linguistic Inquiry and Word Count (LIWC-22)](https://www.liwc.app) tool (Boyd et al., 2022; Tausczik and Pennebaker, 2010) categorizes words across 90+ dimensions including summary variables (analytic thinking, clout, authenticity), grammatical categories (pronouns, prepositions), and psychological processes (cognitive mechanisms, social processes). Used to measure shifts in analytical thinking style and authenticity between human-written and LLM-edited text.
 
### ICLR 2026 Peer Reviews
Peer reviews from ICLR 2026, with LLM-generation labels from the [Pangram AI classifier](https://www.pangram.com/blog/pangram-predicts-21-of-iclr-reviews-are-ai-generated). We analyze 18k reviews drawn from papers that received exactly one fully human-written and one fully LLM-generated review, ensuring unbiased sampling across conditions.

---
 
## Dependencies
 
```
pandas
numpy
matplotlib
scikit-learn
sentence_transformers
```
 
---
 
## Citation
 
If you use this code or build on this analysis, please cite the associated work. 
  
