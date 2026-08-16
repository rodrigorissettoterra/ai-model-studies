# AI Model Studies

> **From classical Machine Learning to Deep Learning, Generative AI, Agentic Systems, MLOps, experimentation, and recommendation systems.**

A collection of hands-on studies designed to explore **how AI and Machine Learning models behave, how they should be evaluated, and what is required to move from experimentation toward reliable real-world systems**.

The goal of this repository is not to collect isolated algorithms or maximize benchmark scores. Each notebook is structured around a **technical question**, a reproducible experiment, appropriate evaluation metrics, and a discussion of the trade-offs behind the results.

<p>
  <img src="https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter&logoColor=white" alt="Jupyter">
  <img src="https://img.shields.io/badge/Google-Colab-F9AB00?logo=googlecolab&logoColor=white" alt="Google Colab">
  <img src="https://img.shields.io/badge/Machine%20Learning-Studies-green" alt="Machine Learning">
  <img src="https://img.shields.io/badge/Generative%20AI-Studies-purple" alt="Generative AI">
  <img src="https://img.shields.io/badge/Agentic%20AI-Studies-red" alt="Agentic AI">
</p>

---

## Why this repository exists

Machine Learning is much more than fitting a model.

A useful AI system requires understanding:

* how data should be prepared and validated;
* how models should be compared;
* which metrics actually represent the problem;
* how to avoid data leakage;
* how uncertainty affects decisions;
* how retrieval and generation should be evaluated;
* when an agent should use tools;
* when multi-agent architectures are justified;
* how models behave after deployment;
* how monitoring, observability, drift, and feedback affect production systems;
* how experiments can support causal decisions;
* and how ranking systems should be evaluated beyond simple prediction accuracy.

These studies were created to investigate those questions progressively.

---

## Learning path

```text
Classical Machine Learning
        ↓
Deep Learning
        ↓
NLP & Transformers
        ↓
Time Series Forecasting
        ↓
Embeddings & Semantic Search
        ↓
Retrieval-Augmented Generation
        ↓
RAG Evaluation
        ↓
Tool-Using Agents
        ↓
Multi-Agent Systems
        ↓
Serving, Monitoring & MLOps
        ↓
Experimentation & Causal Inference
        ↓
Recommendation & Ranking Systems
```

---

# Studies

## 01 — Classical Machine Learning

### 001 — Breast Cancer Classification

**Problem:** Supervised binary classification
**Focus:** Classification workflow, model evaluation, and predictive performance

A study of the fundamental workflow behind a supervised classification problem, from data exploration and preprocessing to model training and evaluation.

[View notebook](./001_breast_cancer_classification.ipynb)

---

### 002 — Churn Prediction

**Problem:** Customer churn classification
**Focus:** Logistic Regression, Random Forest, threshold selection, and business-oriented metrics

Instead of treating accuracy as the only objective, this study investigates how changing the classification threshold affects the trade-off between **precision and recall**.

Metrics include:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC
* Average Precision

[View notebook](./002_churn_prediction.ipynb)

---

### 003 — House Price Regression

**Problem:** Regression
**Focus:** Predicting continuous values and evaluating regression performance

A study of the end-to-end regression workflow, including preprocessing, model comparison, prediction errors, and interpretation of regression metrics.

[View notebook](./003_house_prices_regression.ipynb)

---

## 02 — Deep Learning

### 004 — MNIST: MLP vs CNN

**Problem:** Image classification
**Focus:** Comparing fully connected neural networks with convolutional architectures

This experiment investigates how architecture affects performance when working with image data.

The goal is not only to classify handwritten digits, but to understand **why convolutional inductive biases are useful for visual tasks**.

[View notebook](./004_mnist_mlp_vs_cnn.ipynb)

---

### 005 — Transfer Learning on CIFAR-10

**Problem:** Image classification
**Focus:** Transfer Learning and pretrained representations

A study of how pretrained neural networks can reuse previously learned representations and reduce the amount of task-specific learning required.

[View notebook](./005_transfer_learning_cifar10.ipynb)

---

## 03 — Natural Language Processing

### 006 — TF-IDF vs Transformer for Sentiment Analysis

**Problem:** Text classification
**Focus:** Classical NLP vs Transformer-based representations

This study compares two different generations of NLP approaches:

```text
TF-IDF + classical ML
        vs
Transformer representations
```

The objective is to understand what modern language representations add beyond traditional sparse text features.

[View notebook](./006_sentiment_tfidf_vs_transformer.ipynb)

---

## 04 — Time Series

### 007 — Time Series Forecasting

**Problem:** Forecasting future observations
**Focus:** Temporal validation, forecasting baselines, model comparison, and error analysis

Time series problems require a different validation mindset because **future observations must never leak into the past**.

This study explores forecasting while preserving temporal structure during training and evaluation.

[View notebook](./007_time_series_forecasting.ipynb)

---

## 05 — Embeddings & Retrieval

### 008 — Semantic Search with Embeddings

**Problem:** Information retrieval
**Focus:** Embeddings, semantic similarity, and vector-based search

Traditional keyword search asks:

> Do these documents contain the same words?

Semantic search asks:

> Do these documents express similar meanings?

This study explores how embeddings transform text into vector representations that can be used for semantic retrieval.

[View notebook](./008_semantic_search_embeddings.ipynb)

---

## 06 — Retrieval-Augmented Generation

### 009 — RAG Question Answering

**Problem:** Knowledge-grounded question answering
**Focus:** Retrieval-Augmented Generation

A practical RAG pipeline combining:

```text
Documents
   ↓
Chunking
   ↓
Embeddings
   ↓
Retrieval
   ↓
Context
   ↓
Language Model
   ↓
Answer
```

The experiment investigates how external knowledge can be retrieved and supplied to a language model instead of relying exclusively on information encoded in model parameters.

[View notebook](./009_rag_question_answering.ipynb)

---

### 010 — RAG Evaluation

**Problem:** Evaluating retrieval and generated answers
**Focus:** Measuring RAG quality beyond subjective inspection

Building a RAG system is only half the problem.

The next question is:

> How do we know whether it actually works?

This study explores evaluation at different layers of the RAG pipeline, separating the quality of **retrieval** from the quality of the **generated answer**.

[View notebook](./010_rag_evaluation.ipynb)

---

## 07 — Agentic AI

### 011 — Agent Tool Use

**Problem:** Tool-using AI agents
**Focus:** Tool selection, execution, reasoning loops, and failure handling

Language models alone cannot directly query private systems, calculate arbitrary values reliably, or execute business operations.

Agents extend their capabilities through tools.

This study explores the loop:

```text
User Request
     ↓
Language Model
     ↓
Tool Selection
     ↓
Tool Execution
     ↓
Observation
     ↓
Next Decision
```

The emphasis is not simply whether the agent produces an answer, but whether it chooses and executes the **correct tool**.

[View notebook](./011_agent_tool_use.ipynb)

---

### 012 — Single Agent vs Multi-Agent Supervisor

**Problem:** Agent coordination and specialization
**Focus:** Routing, delegation, specialization, latency, and coordination overhead

Does splitting a problem across specialized agents actually improve the system?

This study compares:

```text
Single Generalist Agent
          vs
Supervisor + Specialized Agents
```

Evaluation includes:

* Task Success Rate
* Specialist Coverage
* Routing accuracy
* Tool execution
* Redundant delegations
* Handoffs
* Number of model calls
* Latency
* Coordination overhead

The goal is not to prove that multi-agent systems are always better, but to identify **when specialization helps and when it only adds complexity**.

[View notebook](./012_multi_agent_supervisor.ipynb)

---

## 08 — MLOps & Production AI

### 013 — Serving, Monitoring & MLOps

**Problem:** Taking a model beyond the notebook
**Focus:** Serving, observability, monitoring, drift, and operational reliability

A model that performs well during experimentation is not automatically a production-ready AI system.

This study builds the operational layer around model inference:

```text
Client
   ↓
FastAPI
   ↓
Schema Validation
   ↓
Model Inference
   ↓
Prediction
```

With additional operational capabilities:

```text
             Model Service
                  │
       ┌──────────┼──────────┐
       ↓          ↓          ↓
     Logs       Metrics     Traces
       │          │          │
       └──────────┼──────────┘
                  ↓
              Monitoring
                  ↓
          Drift + Feedback
```

Topics include:

* FastAPI
* Pydantic schemas
* model versioning
* health checks
* readiness and liveness
* structured logging
* request IDs
* Prometheus metrics
* latency monitoring
* OpenTelemetry
* feature drift
* delayed ground truth
* concurrent testing
* Docker

[View notebook](./013_serving_monitoring_mlops.ipynb)

---

## 09 — Experimentation & Causal Inference

### 014 — A/B Testing and Causal Inference

**Problem:** Randomized experimentation and product decision-making
**Focus:** Statistical inference, causal effects, uncertainty, and practical significance

Observed differences are not automatically meaningful decisions.

This study simulates an e-commerce A/B experiment and investigates how to move from:

```text
Observed Difference
        ↓
Statistical Evidence
        ↓
Effect Size
        ↓
Uncertainty
        ↓
Business Relevance
        ↓
Decision
```

Topics include:

* experimental design;
* statistical power;
* sample size estimation;
* randomization checks;
* absolute and relative effects;
* confidence intervals;
* two-proportion tests;
* bootstrap estimation;
* Welch's t-test;
* CUPED variance reduction;
* multiple-testing correction;
* heterogeneous treatment effects;
* practical significance;
* guardrail metrics.

The central question is not simply:

> Is the p-value below 0.05?

It is:

> Is the effect credible, meaningful, and safe enough to justify a decision?

[View notebook](./014_ab_testing_causal_inference.ipynb)

---

## 10 — Recommendation Systems

### 015 — Recommendation and Ranking Systems

**Problem:** Personalized Top-K recommendation
**Focus:** Ranking quality, personalization, coverage, diversity, and cold start

Recommendation systems are not simply prediction systems.

The real question is:

> Can the system place relevant items near the top of the list for each user?

This study compares:

1. Popularity baseline
2. Content-based recommendation
3. Collaborative Filtering
4. Hybrid Ranking

The evaluation goes beyond prediction error and uses ranking metrics such as:

* Precision@K
* Recall@K
* MAP@K
* NDCG@K
* Hit Rate@K
* Catalog Coverage
* Category Diversity

The study also explores:

* temporal train/test splitting;
* recommendation leakage;
* exclusion of previously seen items;
* latent factors;
* hybrid ranking;
* long-tail behavior;
* cold-start strategies;
* relevance vs coverage trade-offs.

[View notebook](./015_recommender_system_ranking.ipynb)

---

# What these studies emphasize

Across the repository, the experiments follow a few recurring principles.

### 1. Start with a question

Each study begins with a problem or hypothesis instead of starting from an algorithm.

### 2. Establish a baseline

Complex models are useful only when they improve something that can be measured.

### 3. Choose metrics that match the problem

Accuracy is not enough for every classification problem.

RMSE is not enough for every forecasting problem.

Prediction error is not enough for recommendation systems.

A generated answer that sounds good is not enough for RAG.

### 4. Protect evaluation integrity

Whenever applicable, the studies consider issues such as:

* train/test separation;
* temporal leakage;
* threshold selection;
* unseen test data;
* reproducibility;
* appropriate baselines.

### 5. Evaluate systems, not only models

Modern AI applications contain several interacting components.

For example:

```text
RAG = Retrieval + Generation

Agent = Model + Tools + Control Loop

Multi-Agent = Agents + Routing + Coordination

Production AI = Model + API + Observability + Monitoring

Recommendation = Candidate Generation + Ranking + Business Constraints
```

A useful evaluation strategy must understand those components separately.

### 6. Discuss trade-offs and limitations

The objective is not to present every experiment as a success.

Understanding **why an approach fails, where it becomes expensive, and what assumptions it depends on** is often more useful than reporting another high score.

---

# Topics covered

| Area                 | Topics                                                                 |
| -------------------- | ---------------------------------------------------------------------- |
| **Machine Learning** | Classification, regression, model comparison, threshold tuning         |
| **Deep Learning**    | MLP, CNN, transfer learning                                            |
| **NLP**              | TF-IDF, Transformers, sentiment analysis                               |
| **Time Series**      | Forecasting, temporal validation                                       |
| **Embeddings**       | Vector representations, semantic similarity                            |
| **RAG**              | Retrieval, chunking, generation, evaluation                            |
| **Agentic AI**       | Tool use, agent loops, routing, multi-agent coordination               |
| **MLOps**            | Serving, APIs, monitoring, observability, drift                        |
| **Experimentation**  | A/B testing, power analysis, CUPED, causal inference                   |
| **Recommendation**   | Collaborative filtering, content-based systems, ranking, Top-K metrics |

---

# Technologies explored

The notebooks use technologies from different areas of the Python AI ecosystem, including:

* Python
* NumPy
* Pandas
* Matplotlib
* scikit-learn
* deep learning frameworks
* Transformer models
* embeddings
* vector similarity
* FastAPI
* Pydantic
* Prometheus
* OpenTelemetry
* Docker
* Jupyter Notebook
* Google Colab

The exact stack varies according to the technical question investigated in each study.

---

# Running the notebooks

The notebooks are designed to be easy to inspect and reproduce.

Most can be executed directly in **Google Colab**, and the notebooks include an **Open in Colab** button.

You can also clone the repository:

```bash
git clone https://github.com/rodrigorissettoterra/ai-model-studies.git
cd ai-model-studies
```

Then open the desired notebook using Jupyter or another compatible environment.

Some Deep Learning and Generative AI experiments may benefit from a GPU runtime.

---

# Repository philosophy

This repository is intentionally **not a single production application**.

It is a collection of focused experiments used to study specific concepts, architectures, evaluation strategies, and engineering trade-offs.

Each notebook tries to answer one question well.

Larger end-to-end systems — involving data platforms, orchestration, APIs, deployment, CI/CD, monitoring, and production infrastructure — are better represented as dedicated projects rather than compressed into individual notebooks.

---

# Final perspective

The progression of this repository reflects a broader view of modern Data Science and AI:

```text
Predict
   ↓
Evaluate
   ↓
Understand
   ↓
Retrieve
   ↓
Generate
   ↓
Act
   ↓
Coordinate
   ↓
Deploy
   ↓
Monitor
   ↓
Experiment
   ↓
Optimize decisions
```

Models matter.

But reliable AI systems require much more than models.

---

## Author

Maintained by [@rodrigorissettoterra](https://github.com/rodrigorissettoterra).

Contributions, discussions, suggestions, and feedback are welcome.
