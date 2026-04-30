# CommonsenseQA with Chain-of-Thought Prompting Evaluation

A comprehensive evaluation pipeline for testing different prompting strategies on commonsense reasoning tasks using large language models.

## 📊 Overview

This project evaluates **9 different prompting strategies** on the **CommonsenseQA** dataset to measure how effectively each approach improves LLM reasoning:

### Prompting Strategies Tested:

1. **Baseline** - Direct question answering
2. **Zero-shot CoT** - Ask model to think step-by-step
3. **Few-shot CoT** - Provide reasoning examples before asking
4. **RE (Rephrase-and-Expand)** - Restate question with expanded reasoning
5. **RE+** - Enhanced rephrase with additional context
6. **Plan-and-Solve (PS)** - Break problem into planning and solving steps
7. **Plan-and-Solve+** - Enhanced planning with explicit constraints
8. **Tree-of-Thought (ToT)** - Explore multiple reasoning paths
9. **Self-Consistency** - Multiple reasoning paths with answer aggregation

## 📚 Dataset

**CommonsenseQA** (`tau/commonsense_qa`)
- Multiple-choice questions requiring commonsense reasoning
- Based on ConceptNet semantic knowledge graph
- 5 answer choices per question
- 12,154 training examples, 1,221 dev examples
- Tests reasoning beyond memorization

Example:
```json
{
  "question": "Where would you find magazines alongside many other printed works?",
  "choices": ["doctor", "bookstore", "market", "train station", "mortuary"],
  "answer": "bookstore"
}
```

## 🤖 Model

**DeepSeek-R1-Distill-Qwen-7B** (`deepseek-ai/DeepSeek-R1-Distill-Qwen-7B`)
- 7 billion parameters
- Reasoning-optimized distilled model
- Based on Qwen architecture
- Balances reasoning strength, inference speed, and accessibility
- Ideal for structured reasoning evaluation

## 📂 Project Structure
```
.
├── commonsense-qa-with-chain-of-thought.ipynb  # Main notebook
├── Demonstration files/
│   ├── demo_baseline_results.json
│   ├── demo_fewshot_cot_results.json
│   ├── demo_plan_and_solve_results.json
│   ├── demo_re_results.json
│   ├── demo_self_consistency_results.json
│   └── demo_zeroshot_cot_results.json
├── evaluation_results/
│   ├── evaluation_results.csv
│   └── prompting_strategies_evaluation.csv
├── README.md
├── requirements.txt
└── .gitignore
```
## 🚀 Quick Start

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Run the Notebook
```bash
jupyter notebook commonsense-qa-with-chain-of-thought.ipynb
```

### 3. View Results
Results are saved in JSON format in the `Demonstration files/` and `evaluation_results/` directories.

## 📊 Results Summary

The notebook generates comprehensive evaluation reports including:
- Accuracy scores for each strategy
- Reasoning quality analysis
- Performance comparisons
- CSV summary with all metrics

See `evaluation_results.csv` for detailed metrics.

## 🔬 Key Findings

Each prompting strategy produces different reasoning patterns:
- **Baseline**: Direct answers without reasoning steps
- **CoT variants**: Show step-by-step thinking
- **Self-Consistency**: Improves accuracy through vote aggregation
- **Plan-and-Solve**: Best for structured multi-step reasoning
- **Tree-of-Thought**: Explores alternative reasoning paths

## 💡 Technologies Used

- Kaggle
- Hugging Face Transformers
- Hugging Face Datasets
- Jupyter Notebook
- Pandas
- DeepSeek-R1-Distill-Qwen-7B

## 📖 References

- CommonsenseQA: [https://huggingface.co/datasets/tau/commonsense_qa](https://huggingface.co/datasets/tau/commonsense_qa)
- DeepSeek-R1: [https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-7B](https://huggingface.co/deepseek-ai/DeepSeek-R1-Distill-Qwen-7B)
- Chain-of-Thought Prompting: Wei et al., 2023

## 📝 License

MIT License

## 👤 Author

Zaki Hanfer - Internship Project
