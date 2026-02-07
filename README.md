# Investigative Question Generation (IQG) using Qwen-based LLMs

A **LangChain-driven, multi-stage prompting framework** that systematically generates ranked investigative questions from news articles.  
This framework evaluates **trustworthiness, bias, and factual accuracy**, combining structured prompts, Qwen-based LLMs, LangChain execution, and controlled decoding.

## 📁 Project Structure

| Folder | Description |
|--------|--------------|
| **notebooks/** | Jupyter notebooks for all CUET Task~1 runs, including QwQ-32B, Qwen3-14B (v1–v5), Qwen3-4B (v2–v3), DeepSeek-R1-Qwen-32B, and Mistral-based systems |
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
- Framework: **LangChain + HuggingFace + reasoning- and Qwen-based LLMs (QwQ-32B, Qwen3-14B, Qwen3-4B, DeepSeek-R1-Qwen-32B, Mistral-based models)**  
- Decoding Parameters:  
  - `temperature = 0.5`  
  - `top_p = 0.8`  
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

| Run ID | Model | Avg. Score (Rectified) | Notes |
|--------|--------|------------------------|-------|
| **`CUET-QwQ-32B`** | **QwQ-32B** | 🥇 **0.215** | Strongest CUET run; robust reasoning |
| `CUET-qwen14B-v2` | Qwen3-14B | 🥈 **0.195** | Best Qwen-based configuration |
| `CUET-DeepSeek-R1-Qwen-32B` | DeepSeek-R1 + Qwen-32B | 0.184 | Reasoning-oriented, stable |
| `CUET-Mistral-Small-24B` | Mistral-Small-24B | 0.182 | Compact, topic-sensitive |
| `CUET-qwen14B-v3` | Qwen3-14B | 0.175 | Broad investigative style |
| `CUET-qwen14B-v5` | Qwen3-14B | 0.165 | Decoding + LoRA optimized |
| `CUET-qwen4B-v3` | Qwen3-4B | 0.165 | Lightweight baseline |
| `CUET-qwen4B-v2` | Qwen3-4B | 0.153 | Exploratory decoding |
| `CUET-qwen14B-v1` | Qwen3-14B | 0.150 | Early baseline |
| `CUET-unsloth-Mistral-Small` | Unsloth-Mistral | 0.081 | Fast but heavily penalized |


## 🧠 Tech Stack

-  **Python 3.10+**  
-  **LangChain** — for LLM orchestration  
-  **HuggingFace Transformers** — for Qwen model integration  
-  **Qwen-based and Reasoning LLMs** 
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
