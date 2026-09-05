**Birla Institute of Technology & Science, Pilani**

Work Integrated Learning Programmes Division

**M.Tech (AIML/SEZG) — AIML ZG519: Natural Language Processing Applications**

**Assignment: Sentiment Analysis — A Comparative Study**

**PS2 — Movie / OTT Platform Reviews**

# 1. Objective

This assignment gives you hands-on experience building and critically comparing multiple sentiment analysis pipelines — spanning classical Machine Learning, Deep Learning, fine-tuned Transformers, and Generative AI / LLM prompting — on your assigned domain dataset. You will evaluate each approach not only on accuracy but on training cost, inference latency, robustness, and interpretability, and justify which approach best fits real-world deployment in your domain.

# 2. Problem Statement PS2: Movie / OTT Platform Reviews

| **Field** | **Details** |
| --- | --- |
| Domain | Entertainment / Media |
| Business Scenario | An OTT streaming platform wants to auto-tag viewer reviews to power content recommendations and moderate abusive content. |
| Suggested Dataset & Access | IMDB Movie Reviews — load_dataset("imdb") OR Rotten Tomatoes Critic Reviews (Kaggle) |
| Aspect Focus | acting, plot/story, cinematography, pacing |
| Assigned Groups | Groups 6 – 10 |

Sample size: sample 5,000–10,000 rows (stratified by class) if your dataset is larger than that; use the SAME sample across all four modelling approaches (Parts B–E) so your comparison stays fair. If your dataset naturally has fewer rows, use the full dataset and note the smaller size explicitly in your report.

# 3. Tasks & Weightage (Total: 10 Marks)

| **Part** | **Task** | **Marks** |
| --- | --- | --- |
| A | Data exploration, preprocessing (light + heavy cleaning pipelines) on your assigned dataset | 1 |
| B | Classical ML: TF-IDF + Naive Bayes AND Logistic Regression/SVM, with hyperparameter tuning | 2 |
| C | Deep Learning: Embedding + BiLSTM/LSTM/GRU/CNN, with training curves | 2 |
| D | Transformer fine-tuning: DistilBERT/BERT (or domain-appropriate variant) via HuggingFace Trainer | 2 |
| E | GenAI/LLM prompting: zero-shot AND few-shot sentiment classification | 1.5 |
| F | Comparative analysis: consolidated metrics table, charts, domain-specific robustness stress-test, written summary | 1.5 |
|  | **Total** | **10** |

# 4. Detailed Requirements

## 4.1 Preprocessing

- Implement two cleaning functions: a heavier one (stopword removal, lemmatization) for the classical ML pipeline, and a lighter one for DL/Transformer/LLM pipelines.
- Justify in a markdown cell why over-cleaning can hurt neural/LLM-based models.

## 4.2 Classical Machine Learning

- TF-IDF (or Bag-of-Words) features with Multinomial Naive Bayes and one of Logistic Regression / Linear SVM.
- Hyperparameter tuning on at least one model using GridSearchCV or RandomizedSearchCV.
- Report Accuracy, Precision, Recall, F1 (weighted) and confusion matrices for both models.

## 4.3 Deep Learning

- An embedding layer (pre-trained embeddings preferred, or trained from scratch) feeding a BiLSTM/LSTM/GRU/CNN classifier.
- Plot training vs. validation accuracy/loss curves.
- Report test-set metrics, confusion matrix, parameter count, and training time.

## 4.4 Transformer Fine-Tuning

- Fine-tune distilbert-base-uncased (or a domain-appropriate variant) using HuggingFace transformers + datasets.
- If compute-limited, use a smaller subset and state this explicitly — keep the comparison fair and clearly annotated.
- Report metrics, confusion matrix, fine-tuning time, and per-sample inference latency.

## 4.5 GenAI / LLM Prompting

- Zero-shot prompting: classify sentiment with no examples in the prompt.
- Few-shot prompting: include 3–5 labelled examples in the prompt.
- Evaluate on a sample (100–200 rows) to manage API cost; report accuracy/F1 and estimated cost per 1,000 predictions.

## 4.6 Comparative Analysis

- Consolidate Accuracy, F1, training/setup time, inference latency, and approximate cost into one table.
- Include at least one comparison chart.
- Stress-test all approaches on 5 self-written tricky examples in your domain (acting, plot/story, cinematography, pacing) covering negation, sarcasm, and mixed sentiment; tabulate predictions side by side.
- Write a 250–400 word summary recommending which approach fits (a) a high-traffic, cost-sensitive deployment, and (b) a low-volume, high-stakes use case in your domain — and note one privacy/ethics consideration of sending this domain's user text to a third-party LLM API.

# 5. Deliverables

- One executed Jupyter notebook per GROUP (all cells run top-to-bottom, outputs visible) named `PS2_Group<GroupNo>_NLP_SentimentAnalysis_Assignment.ipynb`
- The notebook template provided on eLearn may be used as a starting point — see `Sentiment_Analysis_Assignment_Template.ipynb`
- No API keys or secrets committed in the submitted notebook

# 6. Evaluation Rubric

| **Criterion** | **Weight** | **What is assessed** |
| --- | --- | --- |
| Correctness & completeness of each pipeline (Parts A–E) | 50% | Code runs end-to-end; each approach is implemented as specified; metrics correctly computed |
| Depth of comparative analysis (Part F) | 20% | Meaningful, well-supported comparison beyond accuracy alone; quality of domain-specific stress-test discussion |
| Reflection questions & written summary | 15% | Depth of reasoning, correct use of course concepts, clarity of domain-relevant recommendations |
| Code quality & reproducibility | 15% | Readable code, reusable functions, fixed random seeds, clear markdown narration |

# 7. Submission & Deadline

Submit via the eLearn portal under the EC-1 Assignment link, ONE submission per group with all group member names and IDs listed in the notebook header. Refer to the eLearn announcement for the exact due date.

# 8. Queries & Support

For any clarifications on this problem statement, dataset access, or evaluation criteria,

email **kirankbarnana@wilp.bits-pilani.ac.in** with subject line "AIML ZG519 - PS<X> Query - Group <YourGroupNo>".

Please allow 2–3 working days for a response before the deadline.
