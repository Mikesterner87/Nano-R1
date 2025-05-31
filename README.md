# Nano-R1: Fine-Tuning Qwen2.5-3B-Instruct Model

![Nano-R1](https://img.shields.io/badge/Nano--R1-Fine--Tuning--Model-brightgreen)

Welcome to the **Nano-R1** repository! This project demonstrates the process of fine-tuning the **Qwen2.5-3B-Instruct** model using **Generalized Reward Policy Optimization (GRPO)** on the **GSM8K dataset**. This README provides all the information you need to get started with the project.

## Table of Contents

- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Releases](#releases)
- [Contact](#contact)

## Introduction

In the realm of natural language processing, fine-tuning models for specific tasks is essential for achieving high performance. The **Qwen2.5-3B-Instruct** model is designed to understand and generate human-like text. This project focuses on fine-tuning this model using **GRPO** to enhance its performance on the **GSM8K dataset**, which consists of various mathematical problems.

## Getting Started

To get started with the **Nano-R1** project, you will need to clone the repository and install the necessary dependencies. Follow the steps below to set up your environment.

### Prerequisites

- Python 3.7 or higher
- pip (Python package installer)
- Git

### Clone the Repository

You can clone the repository using the following command:

```bash
git clone https://github.com/Mikesterner87/Nano-R1.git
cd Nano-R1
```

### Install Dependencies

After cloning the repository, install the required packages:

```bash
pip install -r requirements.txt
```

## Features

- Fine-tuning of the **Qwen2.5-3B-Instruct** model.
- Implementation of **GRPO** for effective training.
- Utilization of the **GSM8K dataset** for model evaluation.
- Support for various adapters and configurations.
- Easy integration with Hugging Face libraries.

## Installation

To run the project, you need to install the required libraries. The `requirements.txt` file contains all necessary dependencies. Use the following command to install them:

```bash
pip install -r requirements.txt
```

Make sure to have the following libraries installed:

- `transformers`
- `torch`
- `safetensors`
- `trl`
- `text-generation-inference`

## Usage

Once you have set up the environment, you can start fine-tuning the model. Use the following command to begin the training process:

```bash
python train.py --dataset gsm8k --model qwen2-5
```

You can adjust parameters in the `train.py` script to customize your training process. Refer to the comments in the code for guidance.

### Example of Fine-Tuning

Here’s a simple example of how to use the fine-tuned model for text generation:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer

model_name = "your_fine_tuned_model"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForCausalLM.from_pretrained(model_name)

input_text = "What is 7 + 5?"
inputs = tokenizer(input_text, return_tensors="pt")
outputs = model.generate(**inputs)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

This code snippet demonstrates how to load your fine-tuned model and generate text based on a prompt.

## Contributing

We welcome contributions to the **Nano-R1** project. If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/YourFeature`).
6. Open a pull request.

Please ensure that your code adheres to the existing style and includes tests where applicable.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Releases

You can find the latest releases and downloadable files [here](https://github.com/Mikesterner87/Nano-R1/releases). Please download and execute the files as needed to get the most out of this project.

For detailed information about each release, visit the [Releases](https://github.com/Mikesterner87/Nano-R1/releases) section.

## Contact

For any questions or feedback, feel free to reach out:

- GitHub: [Mikesterner87](https://github.com/Mikesterner87)
- Email: mikesterner87@example.com

Thank you for your interest in the **Nano-R1** project! We hope you find it useful for your fine-tuning tasks.