# DP TinyBERT GLUE Benchmarks

Welcome to **DP TinyBERT GLUE Benchmarks**!  
This repository provides a unified, reproducible framework for parameter-efficient and standard fine-tuning of [TinyBERT](https://huggingface.co/prajjwal1/bert-tiny) on GLUE tasks, with and without Differential Privacy (DP), using [Opacus](https://opacus.ai/) and [PEFT](https://github.com/huggingface/peft).

## 🚀 Project Overview

- **Compare**: Soft Prompt, Prefix, LoRA, Full Fine-Tuning, Last-Layer Fine-Tuning, Soft Prompt + LoRA, Prefix + LoRA.
- **Privacy**: Run all methods with both standard training (ε = ∞) and DP-SGD (ε ≈ 8).
- **Datasets**: SST2, QNLI, QQP, MNLI (GLUE suite).
- **Model**: TinyBERT (prajjwal1/bert-tiny) for fast, hardware-friendly experiments.
- **Metrics**: Validation accuracy, number of trainable parameters, and privacy budget (ε).

## 📂 Repository Structure

| File/Folder                | Description                                        |
|----------------------------|----------------------------------------------------|
| `dp_tinybert_glue.ipynb`   | Main Colab notebook: all code for experiments      |
| `README.md`                | This file                                          |
           |

## 📝 Methods Compared

- **Soft Prompt Tuning**
- **Prefix Tuning**
- **LoRA (Low-Rank Adaptation)**
- **Full Fine-Tuning**
- **Last-Layer Fine-Tuning**
- **Soft Prompt + LoRA**
- **Prefix + LoRA**

All methods are implemented using the [PEFT library](https://github.com/huggingface/peft) for modular, parameter-efficient adaptation.

## 🔐 Differential Privacy

- **DP-SGD** implemented with [Opacus](https://opacus.ai/).
- **Privacy Budget**: Experiments target ε ≈ 8 (δ = 1e-5), as recommended in ["Flocks of Stochastic Parrots"](https://openreview.net/forum?id=u6Xv3FuF8N).
- **Noise Multiplier**: Tuned for each dataset/method to achieve the desired ε.
- **Reporting**: Each run prints ε, accuracy, and trainable parameters for easy comparison.

## 📊 Example Results Table

| Dataset | Method                | Trainable Params | ε (epsilon) | Accuracy |
|---------|-----------------------|------------------|-------------|----------|
| SST2    | Soft Prompt           | 2,560            | 7.8         | 0.5092   |
| SST2    | Prefix                | 10,240           | 7.8         | 0.5092   |
| SST2    | LoRA                  | 8,450            | 7.8         | 0.5092   |
| ...     | ...                   | ...              | ...         | ...      |

## 🛠️ How to Use

1. **Open the notebook** in [Google Colab](https://colab.research.google.com/).
2. **Install dependencies** (first code cell).
3. **Upload or tokenize GLUE datasets** as instructed.
4. **Run the unified experiment loop** to train and evaluate all methods.
5. **Tune the noise multiplier** for DP runs to achieve ε ≈ 8.
6. **Record results** for your report or publication.

## 📖 References

- ["Flocks of Stochastic Parrots: Differentially Private Prompt Learning for Large Language Models"](https://openreview.net/forum?id=u6Xv3FuF8N)
- [Opacus Documentation](https://opacus.ai/)
- [PEFT: Parameter-Efficient Fine-Tuning](https://github.com/huggingface/peft)
- [TinyBERT Model Card](https://huggingface.co/prajjwal1/bert-tiny)

## 🤝 Contributing

Pull requests, issues, and suggestions are welcome!  
If you use this repo for your research, please cite the referenced paper and consider starring the repository.

## 📬 Contact

For questions or collaborations, open an issue or reach out via GitHub.

**Happy experimenting with privacy-preserving, parameter-efficient NLP!**
