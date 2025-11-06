Investigative Question Generation (IQG) using Qwen-based LLMs
A LangChain-driven, multi-stage prompting framework that systematically generates ranked investigative questions from news articles.
The system evaluates trustworthiness, bias, and factual accuracy, combining structured prompts, Qwen-based LLMs, LangChain execution, and controlled decoding.

📁 Project Structure
Folder	Description
notebooks/	Contains all Jupyter notebooks for model runs (run10, run7, run8, run4, run6)
figures/	Methodology and visualization images for the research paper
results/	Evaluation results, charts, and model comparison metrics
docs/	Supplementary notes, references, and paper content

⚙️ Methodology Overview
The pipeline follows a four-stage framework:
Data Preparation
Input: TREC DRAGUN news articles (docid, title, body)
Cleaning, tokenization, truncation to 2000 characters
Output: Preprocessed text for LLM input
Prompt Construction & LLM Execution
Prompt Template: Fact-checking, bias, and evidence tracing questions
Execution: LangChain + HuggingFace + Qwen-based LLMs (Qwen3-14B / 4B)
Parameters: temperature = 0.6–0.7, top_p = 0.9, max_new_tokens = 600

Post-Processing
Remove duplicates
Filter short questions
Pad to ensure 10 questions per article
Evaluation & Reporting
Human and task-based scoring (coverage, coherence, novelty)

Comparative evaluation across 5 model versions

🧩 Model Runs
Run ID	Model	Avg. Score	Notes
run10_qwen3_14B	Qwen3-14B-v5	0.76	Best performance, balanced and consistent
run7_qwen3_14B	Qwen3-14B-v3	0.70	Stable results
run8_qwen3_14B_top_p	Qwen3-14B-v3	0.63	Balanced, moderate variation
run4_qwen3_4B	Qwen3-4B-v3	0.55	Good for smaller model
run6_qwen3_14B	Qwen3-14B-v1	0.48	Baseline version

Tech Stack

Python 3.10+

LangChain — for LLM orchestration

HuggingFace Transformers — for Qwen integration

Qwen3-14B / Qwen3-4B models

Pandas, Matplotlib — for evaluation

Jupyter Notebook — for analysis and visualization

🚀 How to Run
# Clone repository
git clone https://github.com/AJFaisal002/Investigative-Question-Generation-IQG.git
cd Investigative-Question-Generation-IQG

# Install dependencies
pip install -r requirements.txt

# Run notebooks or individual scripts
jupyter notebook notebooks/

📊 Key Visuals

Methodology diagrams (Fig. 1a & Fig. 1b)

Model performance comparison

Parameter sensitivity analysis


🪶 License

Licensed under the MIT License
.

👤 Author

Adnan Faisal
Department of Computer Science & Engineering
Chittagong University of Engineering & Technology (CUET)
📧 ajfaisal1208023@gmail.com

Shiti Chowdhury
Department of Computer Science & Engineering
Chittagong University of Engineering & Technology (CUET)
📧 shitichowdhury21@gmail.com
