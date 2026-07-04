# 20-Week AI/ML Engineer Roadmap — ML + MLOps Interleaved

**Structure:** Math → Core ML (with MLOps woven in from Week 4) → Deep Learning → LLMs → RAG → CI/CD & Advanced MLOps → Cloud → Final Integration.

**Target pace:** ~10 hrs/week (~1.5 hrs/day, 6 days/week). Adjust up/down based on your actual bandwidth — the week order matters more than the exact hour count.

**Core principle:** From Week 4 onward, every model you train gets logged, versioned, containerized, and served as a *habit* — not saved for a separate "MLOps module" at the end. This mirrors how it's actually done on the job.

---

## WEEK 1 — Math Foundations (12 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Vectors, matrices, matrix multiplication | 3 | 3Blue1Brown "Essence of Linear Algebra" (1.5x speed) | Implement matrix multiply from scratch in NumPy |
| Derivatives, gradients (intuition only) | 2 | 3Blue1Brown "Essence of Calculus" Ep 1-4 | None — intuition only |
| Mean, variance, std dev, Gaussian distribution | 2 | StatQuest "Statistics Fundamentals" playlist | Compute z-scores on a sample dataset |
| Bayes' Theorem | 1.5 | StatQuest "Bayes theorem, clearly explained" | Solve 3 practice problems |
| Precision, Recall, F1, Confusion Matrix | 2 | StatQuest "Sensitivity and Specificity" | Compute all four by hand on a sample confusion matrix |
| Buffer/review | 1.5 | — | — |

**Skip entirely:** eigenvalues, SVD, integral calculus, formal proofs.

---

## WEEK 2 — Core ML Part 1: Regression & Classification (10 hrs)

*No MLOps yet — build the "why" first.*

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Linear + logistic regression, gradient descent | 4 | Andrew Ng ML Specialization Course 1 (2x speed) | Implement logistic regression from scratch in NumPy |
| scikit-learn API fluency | 3 | sklearn "Getting Started" + `Pipeline`, `train_test_split` | Rebuild the above using sklearn |
| Model evaluation basics (accuracy, confusion matrix in code) | 3 | sklearn `classification_report` docs | Evaluate your model properly, not just accuracy |

---

## WEEK 3 — Core ML Part 2: Tree Models & Imbalanced Data (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Decision Trees, Random Forest, XGBoost | 4 | Andrew Ng Course 2 Wk4 + XGBoost official docs | Train all three on a public tabular dataset |
| Imbalanced datasets (class weighting, SMOTE) | 5 | imbalanced-learn official docs | Compare accuracy vs F1 vs PR-AUC on an imbalanced dataset |
| Buffer | 1 | — | — |

---

## WEEK 4 — Core ML Part 3: Evaluation, Anomaly Detection **+ MLOps habit begins** (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| ROC-AUC, PR-AUC, calibration curves | 3 | sklearn `precision_recall_curve`, `roc_curve` docs | Plot both, choose a threshold with justification |
| Anomaly detection (Gaussian-based, Isolation Forest) | 4 | Andrew Ng Course 3 Wk2 + sklearn `IsolationForest` | Build an anomaly scorer on a synthetic dataset |
| **[MLOps starts here] Experiment tracking with MLflow** | 3 | MLflow official quickstart | Log every model you've trained so far this week (params, metrics, artifacts) |

> **From this point on, MLflow logging is not optional for any model you train — treat it as part of "finishing" a model, not an extra step.**

---

## WEEK 5 — Core ML Part 4: Clustering, Graphs **+ MLOps: Docker & Serving** (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Clustering (K-Means, DBSCAN) | 3 | Andrew Ng Course 3 Wk1 + sklearn clustering docs | Cluster a public dataset, visualize results |
| Graph algorithms (NetworkX, community detection) | 4 | NetworkX tutorial + `python-louvain` docs | Build a graph, run Louvain community detection |
| **[MLOps] Docker fundamentals** | 2 | Docker official "Get Started" | Containerize one of your trained models |
| **[MLOps] FastAPI serving** | 1 | FastAPI official tutorial | Serve your containerized model via a REST endpoint |

---

## WEEK 6 — Core ML Part 5: Feature Engineering **+ MLOps: Registry & Versioning** (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Feature engineering fundamentals | 3 | Read 2-3 top Kaggle competition write-ups | Engineer 5 new features on your dataset |
| **[MLOps] Model registry & versioning** | 2 | MLflow Model Registry docs | Register your best model, move it through Staging → Production |
| **[MLOps] Data versioning** | 2 | DVC quickstart | Version your dataset across 2 iterations |
| **[MLOps] Docker Compose (multi-container)** | 3 | Docker Compose docs | Run your API + MLflow tracking server together locally |

**Project Checkpoint 1 (end of Week 6):** A complete classical-ML project — trained, evaluated, tracked in MLflow, versioned with DVC, containerized, and served via FastAPI. Push to GitHub with a proper README.

---

## WEEK 7 — Buffer & Consolidation (8 hrs)

| Task | Hours |
|---|---|
| Catch up on anything from Weeks 1-6 that didn't stick | 4 |
| Polish Project Checkpoint 1 repo (docs, code cleanup) | 2 |
| Review: write a 1-page summary of your ML+MLOps pipeline in your own words | 2 |

---

## WEEK 8 — Deep Learning Part 1: Neural Nets & CNNs (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Keras Sequential API, training loops | 3 | TensorFlow "Basic classification" tutorial | Train a neural net on MNIST |
| Regularization (dropout, batch norm, early stopping) | 2 | TensorFlow docs | Add regularization, compare validation loss |
| CNNs (convolution, pooling, transfer learning) | 5 | TensorFlow CNN tutorial | Build a CNN on CIFAR-10/Fashion-MNIST; try transfer learning with MobileNet |

---

## WEEK 9 — Deep Learning Part 2: Sequence Models (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| RNN/LSTM fundamentals | 5 | TensorFlow "Time series forecasting" tutorial | Build an LSTM for a time-series or sequence task |
| **[MLOps habit continues]** Log this model in MLflow, containerize it too | 2 | — | Don't skip this — keep the habit alive |
| Buffer | 3 | — | — |

---

## WEEK 10 — Deep Learning Part 3: Transformers & Fine-tuning (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Transformer architecture (conceptual) | 3 | Jay Alammar "The Illustrated Transformer" | Diagram the architecture from memory |
| Hugging Face `transformers`: fine-tuning | 5 | HF quickstart + fine-tuning tutorial | Fine-tune DistilBERT on a text classification dataset |
| Buffer | 2 | — | — |

---

## WEEK 11 — Deep Learning Part 4: Embeddings **+ MLOps wrap-up for DL** (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Embeddings + similarity search | 3 | `sentence-transformers` docs | Build a semantic similarity demo |
| **[MLOps]** Track, version, containerize your fine-tuned model from Week 10 | 3 | — | Full MLOps loop applied to a DL model this time |
| Buffer/consolidate | 4 | — | — |

**Project Checkpoint 2 (end of Week 11):** A fine-tuned transformer model, deployed the same way as Checkpoint 1 (MLflow + Docker + FastAPI). Push to GitHub.

---

## WEEK 12 — LLMs Part 1 (9 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| How LLMs work (tokenization, attention, generation) | 4 | Andrej Karpathy "Let's build GPT" | Write a 1-page summary in your own words |
| Prompt engineering (few-shot, CoT, structured output) | 3 | Anthropic prompt engineering docs (docs.claude.com) | Test 5 prompt variants on the same task |
| API integration (Claude/OpenAI) | 2 | Official API docs | Script that sends input → gets structured JSON output |

---

## WEEK 13 — LLMs Part 2 (9 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Function calling / tool use | 3 | Anthropic/OpenAI function-calling docs | Build an LLM app that calls at least one external tool |
| Fine-tuning vs prompting vs RAG | 2 | Read 2 comparison articles | Write a decision table |
| LoRA/PEFT (conceptual + one hands-on run) | 3 | HF PEFT docs, Colab free GPU | One small fine-tuning run |
| Buffer | 1 | — | — |

**Project Checkpoint 3 (end of Week 13):** A small LLM-powered tool using function calling or structured output.

---

## WEEK 14 — RAG Part 1 (8 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| RAG concept, when it beats fine-tuning | 2 | DeepLearning.AI "LangChain: Chat with Your Data" | — |
| Vector databases, embeddings, similarity search | 3 | ChromaDB official quickstart | Index a set of documents |
| Chunking strategies | 2 | LangChain docs on text splitters | Test 2 chunking strategies, compare |
| Buffer | 1 | — | — |

---

## WEEK 15 — RAG Part 2 (9 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Build end-to-end RAG pipeline | 4 | LangChain or LlamaIndex quickstart | Query → retrieve → LLM answer, with citations |
| RAG evaluation (faithfulness, relevance) | 3 | RAGAS library docs | Score your pipeline on 10 test queries |
| Buffer | 2 | — | — |

**Project Checkpoint 4 (end of Week 15):** A RAG-based Q&A system with source citations.

---

## WEEK 16 — CI/CD & Advanced MLOps (10 hrs)

*This is where MLOps goes deeper than the "habit" level from Weeks 4-11.*

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| CI with GitHub Actions (lint, test, build) | 2 | GitHub Actions official docs | Workflow: push → pytest → build Docker image |
| CD with GitHub Actions (auto-deploy) | 2 | GitHub Actions + Render/Railway docs | Auto-deploy on merge to main |
| Reproducible pipelines (Prefect) | 2 | Prefect "Getting Started" | Build a DAG: ingest → feature-engineer → train → evaluate |
| Model monitoring & drift detection | 3 | Evidently AI docs | Detect drift by feeding a shifted dataset into your monitor |
| Automated retraining trigger | 1 | Combine drift detector + retraining script | If drift > threshold → trigger retraining |

---

## WEEK 17 — Cloud Part 1: AWS Fundamentals (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| Core services overview | 3 | AWS Cloud Practitioner Essentials (free) | — |
| S3 (object storage) | 2 | AWS S3 docs | Store datasets/artifacts in S3 |
| IAM (roles, policies) | 2 | AWS IAM docs | Create a least-privilege role |
| EC2 (compute) | 2 | AWS EC2 docs | Launch an instance, deploy a container manually once |
| ECR (container registry) | 1 | AWS ECR docs | Push a Docker image to ECR |

---

## WEEK 18 — Cloud Part 2: Deployment & Managed ML (10 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| ECS/Fargate (container orchestration) | 5 | AWS ECS Fargate getting-started guide | Deploy a containerized app via Fargate |
| Lambda + API Gateway | 3 | AWS Lambda docs | Deploy a lightweight scoring function as Lambda |
| CloudWatch (monitoring/logging) | 2 | AWS CloudWatch docs | Pipe application logs to CloudWatch |

---

## WEEK 19 — Cloud Part 3: SageMaker & Cleanup (9 hrs)

| Topic | Hours | Resource | Practice |
|---|---|---|---|
| SageMaker (managed ML) | 4 | AWS SageMaker "Get Started" | Train or deploy one model via SageMaker |
| Cost management basics | 1 | AWS Billing dashboard + Budgets | Set a budget alert |
| Buffer + resource cleanup | 2 | — | Delete/stop everything running |
| Consolidate: deploy Checkpoint 1 or 2 project fully to AWS | 2 | — | End-to-end cloud deployment |

**Project Checkpoint 5 (end of Week 19):** One of your earlier projects, fully deployed on AWS (ECS/Fargate or Lambda), with logs in CloudWatch.

---

## WEEK 20 — Final Integration & Portfolio Polish (10 hrs)

| Task | Hours |
|---|---|
| Consolidate all checkpoint projects into clean, documented GitHub repos | 3 |
| Write architecture diagrams for your top 1-2 projects | 2 |
| Write results write-ups (metrics, trade-offs, what you'd improve) | 2 |
| Update resume/LinkedIn with specific tools + project outcomes | 1 |
| Mock interview prep — be ready to explain every tool choice and trade-off | 2 |

---

## Total Time Check

| Weeks | Focus | Approx. Hours |
|---|---|---|
| 1 | Math | 12 |
| 2-7 | Core ML + MLOps habit-building | ~59 |
| 8-11 | Deep Learning + continued MLOps habit | ~40 |
| 12-13 | LLMs | 18 |
| 14-15 | RAG | 17 |
| 16 | CI/CD + Advanced MLOps | 10 |
| 17-19 | Cloud | 29 |
| 20 | Final integration | 10 |
| **Total** | | **≈ 195 hours over 20 weeks (~10 hrs/week)** |

---

## Tools Summary

| Layer | Tool |
|---|---|
| Classical ML | scikit-learn, XGBoost |
| Deep Learning | TensorFlow/Keras |
| NLP/LLM | Hugging Face Transformers, Claude/OpenAI API |
| Graph analysis | NetworkX, python-louvain |
| Imbalanced data | imbalanced-learn |
| RAG | LangChain or LlamaIndex, ChromaDB, RAGAS |
| Experiment tracking | MLflow |
| Data versioning | DVC |
| Pipeline orchestration | Prefect |
| Drift detection | Evidently AI |
| Serving | FastAPI |
| Containers | Docker, Docker Compose |
| CI/CD | GitHub Actions |
| Cloud | AWS: S3, IAM, EC2, ECR, ECS/Fargate, Lambda, SageMaker, CloudWatch |

---

## Non-Negotiable Rule
Starting Week 4, **no model gets treated as "done" until it's logged in MLflow.** Starting Week 5, **no model gets treated as "deployable" until it's containerized.** This habit is the entire point of interleaving MLOps with ML instead of bolting it on at the end — by Week 20 it should feel automatic, not like a separate skill you learned once and forgot.
