# 🚀 Fine-Tuning Collection

A collection of Google Colab notebooks exploring different techniques to adapt Large Language Models for specific tasks. This repository documents my journey from basic instruction tuning to advanced optimization.

## 📋 Current Projects

### 1. TinyLlama Fine-Tuning & GGUF Export
This notebook demonstrates the end-to-end process of training a lightweight model and converting it for local use.
* **Model:** `unsloth/tinyllama-chat`
* **Key Features:** 4-bit loading, LoRA integration, and GGUF quantization.

### 2. Llama-3.2-1B Mobile Optimization (The Android Project)
This is the latest project, specifically fine-tuned and optimized for running on Android devices via Termux.
* **Model:** `unsloth/Llama-3.2-1B-Instruct`
* **Key Features:** Unsloth optimization, Custom Dataset Training, and GGUF Export.
* **Goal:** Run a personalized AI assistant on a smartphone without internet.

---

## 🛠️ How to use these Notebooks
1. **Open:** Click the "Open in Colab" badge above.
2. **GPU Check:** Go to `Runtime` > `Change runtime type` and ensure **T4 GPU** (or better) is selected.
3. **Run All:** You can run all cells sequentially. The notebooks are documented with Markdown explanations before every code block to help you understand the "Why" behind the "How."

## 📲 How to Run on Android
Please read:
👉 **[instruction_to_run_on_android](instruction_to_run_on_android)**

### Quick Download (For my specific model)
If you have already set up Termux, you can download my fine-tuned model directly using this command:

wget -O ~/llama.cpp/models/llama-3.2-1b-instruct.Q4_K_M.gguf https://huggingface.co/RomanNihal/PocketLlama-1B-Coder/resolve/main/llama-3.2-1b-instruct.Q4_K_M.gguf