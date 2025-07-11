# 📊 Dataset Documentation

This repository contains `.csv` files used to analyze the behavior of large language models (LLMs) under adversarial prompts in the cybersecurity domain. Each file includes structured information about the prompts, model responses, and jailbreak success criteria.

## 🗂️ Column Descriptions

| Column Name               | Description |
|---------------------------|-------------|
| **Prompt/New Prompt**     | Single adversarial prompt submitted to the LLM. |
| **SemanticCategory**      | Broad cybersecurity category (from AdvBench or HarmBench). |
| **Subtopic**              | Specific cybersecurity topic: `Hacking`, `Malware`, or `Phishing`. |
| **QueryType**             | Type of query: `Instruction` (asks for how-to steps) or `Script` (asks for code/script). |
| **Past**                  | Reformulation of the prompt in past tense. |
| **Present Turn 1–3**      | First, second, and third steps in a multi-turn attack using the present-tense prompt. |
| **Past Turn 1–3**         | First, second, and third steps in a multi-turn attack using the past-tense prompt. |
| **Model**                 | Name of the LLM being targeted. |
| **Version**               | Specific version of the LLM used. |
| **Temp.**                 | Temperature parameter used during prompt execution. |
| **Unique ID**             | Unique identifier for each query instance. |
| **Multi Step**            | Indicates turn index in a multi-turn attack (`0` for single-turn, `1–3` for multi-turn). |
| **Response**              | The LLM’s full response to the prompt. |
| **Date Time**             | Timestamp of the request. |
| **Human**                 | Manual jailbreak assessment: `1` = Jailbroken, `0` = Not Jailbroken. |
| **Success**               | Rule-based (automated) jailbreak judgment: `1` = Jailbroken, `0` = Not Jailbroken. |
| **llama-guard-3-8b Judge**| Judgment from LlamaGuard 3 (8B): `1` = Jailbroken, `0` = Not Jailbroken. |
| **gpt-4.1 Judge**         | Judgment from GPT-4.1: `1` = Jailbroken, `0` = Not Jailbroken. |

## 📌 Notes

- **Single-turn vs Multi-turn**: If `Multi Step` = `0`, it's a single prompt. If `1–3`, it's part of a multi-turn attack sequence.
- **Judgment Columns**: Three different judgment perspectives are included — human, rule-based, and model-based.

## 🧪 Purpose

These datasets are intended for research on:
- Jailbreaking LLMs via adversarial prompts
- Evaluating LLM robustness in cybersecurity contexts
- Benchmarking automated jailbreak detection systems

## 📧 Contact

For questions or collaborations, feel free to reach out via [GitHub Issues](https://github.com/Micdejc/llm_multiturn_attacks/issues) or contact me directly.
