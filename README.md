# Investigative Question Generation (IQG) using Qwen-based LLMs

A **LangChain-driven, multi-stage prompting framework** that systematically generates ranked investigative questions from news articles.  
This framework evaluates **trustworthiness, bias, and factual accuracy**, combining structured prompts, Qwen-based LLMs, LangChain execution, and controlled decoding.

## 📁 Project Structure

| Folder | Description |
|--------|--------------|
| **notebooks/** | Jupyter notebooks for all 5 model runs (run10, run7, run8, run4, run6) |
| **figures/** | Methodology and visualization images for the research paper |
| **results/** | Evaluation scores, charts, and model comparison metrics |
| **docs/** | Supplementary notes, references, and documentation |

## ⚙️ Methodology Overview

The pipeline follows a **four-stage workflow**:

### **1️⃣ Data Preparation**
- Input: TREC DRAGUN news articles (`docid`, `title`, `body`)  
- Cleaning, tokenization, truncation to 2000 characters  
- Output: Preprocessed text ready for model input  

### **2️⃣ Prompt Construction & LLM Execution**
- Structured prompt template for investigative question generation (fact-checking, bias, evidence tracing)  
- Framework: **LangChain + HuggingFace + Qwen-based LLMs (Qwen3-14B / Qwen3-4B)**  
- Parameters:  
  - `temperature = 0.6–0.7`  
  - `top_p = 0.9`  
  - `max_new_tokens = 600`  
- Output: 10 investigative questions per article  

### **3️⃣ Post-Processing**
- Remove duplicates  
- Filter short or empty questions  
- Pad list to ensure 10 questions per article  

### **4️⃣ Evaluation & Reporting**
- Human/task-based scoring (coverage, coherence, novelty, bias detection)  
- Comparative evaluation across all model runs  

## 🧩 Model Runs and Performance

| Run ID | Model | Avg. Score | Notes |
|--------|--------|-------------|--------|
| `run10_qwen3_14B` | **Qwen3-14B-v5** | 🥇 **0.76** | Best consistency and topic coverage |
| `run7_qwen3_14B` | **Qwen3-14B-v3** | 🥈 **0.70** | Stable results |
| `run8_qwen3_14B_top_p` | **Qwen3-14B-v3** | 🥉 **0.63** | Balanced, moderate variation |
| `run4_qwen3_4B` | **Qwen3-4B-v3** | 0.55 | Good smaller model performance |
| `run6_qwen3_14B` | **Qwen3-14B-v1** | 0.48 | Early baseline version |


## 🧠 Tech Stack

-  **Python 3.10+**  
-  **LangChain** — for LLM orchestration  
-  **HuggingFace Transformers** — for Qwen model integration  
-  **Qwen3-14B / Qwen3-4B Models**  
-  **Pandas, Matplotlib** — for analysis and visualization  
-  **Jupyter Notebook** — for experimentation and research documentation  

## 🚀 How to Run

```bash
# Clone this repository
git clone https://github.com/AJFaisal002/Investigative-Question-Generation-IQG.git
cd Investigative-Question-Generation-IQG

# Install dependencies
pip install -r requirements.txt

# Run notebooks
jupyter notebook notebooks/

```

## 👤 Authors

## Adnan Faisal  
**Department of Computer Science & Engineering**  
Chittagong University of Engineering & Technology (CUET)  
📧 **[ajfaisal1208023@gmail.com](mailto:ajfaisal1208023@gmail.com)**

## Shiti Chowdhury  
**Department of Computer Science & Engineering**  
Chittagong University of Engineering & Technology (CUET)  
📧 **[shitichowdhury21@gmail.com](mailto:shitichowdhury21@gmail.com)**
