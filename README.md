# Troy Sybert

Physician in internal and preventive medicine and clinical informatics, building machine-learning systems to a clinical-research standard of rigor. I care less about leaderboard numbers than about whether a result survives honest evaluation: leak-safe pipelines, nested cross-validation, calibration, and feature attribution that is not an artifact. Most of what follows runs locally, by design.

## AI / ML Portfolio

A set of self-contained projects. In every one the domain is incidental; the point is the method. Each repo modernizes a coursework baseline into a reproducible, leak-safe pipeline and documents what actually held up.

### Evaluation discipline on tabular data

- **[ensemble-classification](https://github.com/HacksterT/ensemble-classification)** — Predicting U.S. work-visa outcomes with bagging and boosting ensembles, evaluated under nested cross-validation with bootstrap confidence intervals, calibration, and permutation importance. Headline finding: six model families converge to one feature-set ceiling, and the differences are inside the noise. Serves as the classical-baseline template for the Clinical-QML Benchmark.
- **[supervised-classification](https://github.com/HacksterT/supervised-classification)** — Logistic regression and decision trees on an imbalanced personal-loan target, with threshold choice driven by the cost of errors rather than raw accuracy. Also feeds the Clinical-QML Benchmark as a classical reference model.
- **[neural-network](https://github.com/HacksterT/neural-network)** — A feed-forward network on bank-churn data, built to answer the question that actually matters for tabular problems: does a neural network beat gradient-boosted trees here, once both are evaluated honestly?

### Deployment and serving

- **[model-deployment](https://github.com/HacksterT/model-deployment)** — An end-to-end local deployment: an XGBoost regression pipeline trained, served from a Flask API, and driven by a Streamlit UI, with no cloud dependency. The point is the deployment discipline, not the sales domain.

### Local-first generative AI

- **[healthcare-rag](https://github.com/HacksterT/healthcare-rag)** — Retrieval-augmented question answering over a medical reference manual, running entirely on local infrastructure (Ollama embeddings and generation, Chroma vector store). Page-cited answers, no API keys, no data leaving the machine.

## How these fit together

The tabular projects share one evaluation backbone and increasing model complexity, from linear and tree baselines through ensembles to a neural network, which makes them a controlled study of when added complexity earns its keep. The two classical-baseline projects feed a forthcoming **Clinical-QML Benchmark** that asks whether quantum machine learning offers any advantage over these honest classical references on clinical tabular data. The deployment and RAG projects round the portfolio out with serving and local generative AI.

## Stack

Python (3.13, `uv`), scikit-learn, XGBoost, TensorFlow/Keras, imbalanced-learn, SHAP; Flask and Streamlit for serving; Ollama and Chroma for local RAG. Reproducible environments, documented findings, local-first where possible.
