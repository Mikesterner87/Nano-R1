# Nano-R1
# Fine-Tuning Qwen2.5-3B-Instruct with GRPO for Mathematical Reasoning

![Python](https://img.shields.io/badge/python-3.11%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![License](https://img.shields.io/badge/license-Apache_2.0-red?style=for-the-badge&logo=apache&logoColor=white)
![Hugging Face](https://img.shields.io/badge/Hugging_Face-Deployed-yellow?style=for-the-badge&logo=huggingface&logoColor=yellow)


This repository contains code for fine-tuning the **Qwen2.5-3B-Instruct** model using **GRPO (Generalized Reward Policy Optimization)** on the **GSM8K** dataset. The goal is to improve the model's ability to solve mathematical reasoning problems through reinforcement learning with custom reward functions.

## 🚀 Deployment

The fine-tuned model is deployed on Hugging Face and can be accessed here:  
🔗 **[Hugging Face Model Hub](https://huggingface.co/Akshint47/Nano_R1_Model)** 

You can interact with the model directly or integrate it into your projects using the Hugging Face `transformers` library.

## ✨ Features

- **Efficient Fine-Tuning**: Uses Unsloth and LoRA for faster training with reduced GPU memory.
- **Custom Reward Engineering**:
  - Correctness (answer accuracy)
  - Format adherence (XML-structured reasoning)
  - Integer validation
  - XML completeness scoring
- **vLLM Integration**: Accelerates inference during training.
- **GSM8K Focus**: Optimized for mathematical word problems.

## 📋 Requirements

```bash
# Core packages
pip install unsloth vllm trl datasets
```
## Additional dependencies
```bash
pip install torch transformers sentence piece accelerate
```

## Hardware Recommendations:

GPU with ≥16GB VRAM (e.g., NVIDIA T4, A10G, or better)

Recommended: CUDA 12.x and cuDNN 8.6+

## 🛠️ Setup & Usage
Install dependencies:

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
pip install -r requirements.txt
```

Run the notebook:

```bash
jupyter notebook nano_r1_train_v2.ipynb
```
Key Configuration (in notebook):
```python```
```
model, tokenizer = FastLanguageModel.from_pretrained(
    model_name = "Qwen/Qwen2.5-3B-Instruct",
    max_seq_length = 1024,
    load_in_4bit = True,
    max_lora_rank = 64
)
```

## 📊 Training Process
The GRPO trainer optimizes for:

-  Reward Maximization: Combined score from all reward functions
  
-  KL Regularization: Maintains policy stability
  
-  Efficiency: Processes 8 generations per batch
  
-  Training Progress (replace with actual metrics screenshot)

## 📜 License  
This project is licensed under the **Apache License 2.0** - see the [LICENSE](LICENSE) file for full terms.  

## 🙏 Acknowledgments
- Unsloth for optimization tools

- Hugging Face for models and datasets

- vLLM for fast inference

- OpenAI for the GSM8K dataset

## 🤝 Contributing
- Contributions are welcome! Please open an issue or PR for:

- Bug fixes

- Additional reward functions

- Performance improvements

