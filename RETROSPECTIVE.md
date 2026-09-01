# FlyRank AI ML Capstone & AI Fluency Workspace

**Author:** Muhammad Abdul Rehman Saleem  
**Live Deployed Paper:** [https://rehman-dev288.github.io/FlyRank-AI-Internship/Capstone.html](https://rehman-dev288.github.io/FlyRank-AI-Internship/Capstone.html)  
**Track:** FlyRank AI Machine Learning & General AI Fluency (2026)

---

## 📌 Project Overview
This repository houses the end-to-end Machine Learning pipeline and research paper for **Content Refresh / Search Opportunity Scoring**. Built on real-world search performance data, the system predicts which web pages require editorial intervention (`needs_action`) using leakage-free cross-validation.

* **Target Audience:** Content strategists, SEO editors, and digital growth teams needing automated, ranked triage queues.
* **Core Value:** Replaces manual spreadsheet analysis with an ML-driven decision-support model that achieves **F1 = 0.74** and **ROC-AUC = 0.82** compared to heuristic baselines (F1 = 0.38).

---

## 🏗️ System Architecture

```text
┌─────────────────────────┐     ┌──────────────────────────┐     ┌─────────────────────────┐
│  Hugging Face Dataset   │ ──> │   DuckDB Data Pipeline   │ ──> │   Feature Engineering   │
│ (79M Search Performance)│     │ (Aggregates & Filtering) │     │ (Position Delta, CTR)   │
└─────────────────────────┘     └──────────────────────────┘     └─────────────────────────┘
                                                                              │
┌─────────────────────────┐     ┌──────────────────────────┐                  ▼
│  Deployed Paper & Queue │ <── │  Four-Tier Action Engine │ <── ┌─────────────────────────┐
│ (GitHub Pages / HTML)   │     │ (Decision Support)       │     │ GroupKFold Random Forest│
└─────────────────────────┘     └──────────────────────────┘     └─────────────────────────┘
🚀 Quickstart & Setup (Reproducibility Guide)Follow these steps to reproduce the dataset extraction, model evaluation, and artifact generation from scratch:PrerequisitesPython 3.10 or higherGitStep-by-step SetupBash# 1. Clone the repository
git clone [https://github.com/Rehman-dev288/FlyRank-AI-Internship.git](https://github.com/Rehman-dev288/FlyRank-AI-Internship.git)
cd FlyRank-AI-Internship

# 2. Create and activate a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# 3. Install required packages
pip install duckdb pandas scikit-learn matplotlib jupyter

# 4. Run the Capstone Notebook
jupyter notebook work/capstone_search_ranking.ipynb
📊 Model Evaluation Results (v2 Eval)Evaluated under strict GroupKFold (k=5) grouped by client_id to prevent cross-client data leakage:Model / BenchmarkF1-ScoreROC-AUCPrecisionRecallBase RateTransparent Heuristic Baseline0.380.500.310.4928.5%Random Forest (GroupKFold)0.740.820.780.7128.5%Key Insight: position_delta (rank loss dynamics) contributed 31% to model importance, proving significantly more predictive than raw impression volume drops alone.⚠️ Known Limitations & BoundariesStatic Windowing: Features rely on 30-day historical aggregates; sudden search algorithm updates within < 7 days require manual re-baselining.Non-Causal Output: Models directional opportunity scores for human editorial triage, not automated algorithmic rank guarantees.Data Boundary: URLs with fewer than 30 consecutive active days or under 100 total impressions are filtered out.🤖 Framework Transparency & AI DisclosureAI Pairing Disclosure: Built in collaboration with Claude 3.5 Sonnet / ChatGPT for code boilerplate generation, CSS styling for the research page, and LaTeX verification. I personally engineered the DuckDB query filters, designed the leakage-free GroupKFold split logic, verified zero-data-leakage constraints, and wrote the final analysis and conclusions.
---

### **2. 5-Minute Live Demo Script (For FL-09 Showcase Video)**

Record a 3–5 minute Loom/YouTube video doing a live screen share (no slides):

* **0:00–0:45 (Introduction & Live Run):**  
  *"Hi, I'm Muhammad Abdul Rehman Saleem. Today I'm demoing my FlyRank AI Capstone: a leakage-aware Content Refresh Opportunity Scoring system. Here is my live research paper running on GitHub Pages, and here is my Jupyter notebook executing live in VS Code."*
* **0:45–2:00 (Data Pipeline & Setup):**  
  *"We extract query aggregates from 79 million search rows using DuckDB. Notice how we group by `client_id` so no single client's data leaks between training and test folds."*
* **2:00–3:15 (Design Decision & Execution):**  
  *"Let's look at one key design decision: rather than filtering by raw traffic drop, we engineered `position_delta`. As you can see in the feature importance chart, rank stability matters far more than raw impressions when predicting content decay."*
* **3:15–4:15 (Honest Limitation on Camera):**  
  *"Now for an honest limitation: because this model uses a 30-day static window, if Google rolls out a core update yesterday, the model needs a 14-day rolling window to adjust. It is designed purely as decision support for human editors, never for unmonitored auto-deletions."*
* **4:15–5:00 (Closing & Verification):**  
  *"The final output exports a 4-tier action playbook and updates `submission/paper_url.txt`. Thank you!"*

---

### **3. 500+ Word Retrospective (`RETROSPECTIVE.md` for FL-10)**

Create `RETROSPECTIVE.md` in your repository root:

```markdown
# 8-Week Capstone Retrospective: From Code Execution to Engineering Rigor

**To:** Rehman (Week 1 Self)  
**From:** Muhammad Abdul Rehman Saleem (Week 8 Graduate)  
**Date:** September 2026  

---

### What I Set Out to Do
When I first opened the FlyRank AI Internship repository in Week 1, my perspective on machine learning and artificial intelligence was largely execution-focused. As a Software Engineering student at the University of Gujrat with a strong full-stack foundation, I viewed AI primarily through API integration, MERN/PERN workflows, and prompt engineering. My goal for this 8-week track was straightforward: build a functional machine learning model, complete the assignments, and earn the certification.

However, working with a 79-million-row production search dataset forced an immediate shift in my technical posture. I realized that writing code that executes without syntax errors is only 20% of the job; the remaining 80% is dataset integrity, leakage prevention, honest evaluation, and public safety.

---

### What Changed Along the Way
The biggest shift occurred during Week 5 and Week 6 when addressing data leakage. In typical academic exercises, random train-test splits are the default. But when predicting page performance across enterprise clients, a random split leaks client-specific search trends into the test set, creating inflated, fake metrics. 

Learning to implement `GroupKFold` grouped strictly by `client_id` was an eye-opening moment. My initial model metrics dropped from a suspicious F1 of 0.92 to an honest, ground-truth F1 of 0.74. That drop wasn't a failure—it was the moment the project gained real-world engineering credibility.

Additionally, my approach to AI collaboration evolved significantly. Moving from using AI as an answer generator to treating it as a rigorous thinking partner (evaluating architecture choices, auditing CSS edge cases, and stress-testing edge cases) elevated my development velocity without sacrificing technical ownership.

---

### Three Most Transferable Things I Learned

1. **Leakage-Aware Validation Discipline:**  
   Never trust a high validation score without auditing the split strategy. Grouping by domain or entity ID (`GroupKFold`) and enforcing strict time-aware splits are mandatory rules for any production-grade predictive system.

2. **Honest Framing as Credibility:**  
   In engineering documentation, acknowledging limitations—such as static date windows, baseline performance limits, and non-causal boundaries—builds far more trust with reviewers and employers than claiming flawless predictive power.

3. **End-to-End Artifact Ownership:**  
   A model trapped inside a Jupyter notebook has zero business value. Shipping a live, responsive HTML research paper hosted on GitHub Pages, complete with automated export pipelines and public-safe disclosures, is what converts raw analysis into a professional deliverable.

---

### What I Would Build Next
Building on this foundation, my next step is extending this decision-support architecture into an **Autonomous Agentic SEO Assistant**. Using FastAPI and Claude API sub-agents, I plan to connect this opportunity scoring model to a real-time CMS webhook. When a page triggers an `ACTION_REFRESH_HIGH` classification, the sub-agent will automatically pull current search intent data, draft a revised content outline, and submit it to a human editor's review queue via Slack or dashboard UI.

---

### Final Advice to My Week 1 Self
Don't rush to hit "Run All". Spend time understanding why the data is structured the way
