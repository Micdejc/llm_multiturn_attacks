
# Large Language Model (LLM) Multi-turn Attacks

This is the repository for "[Jailbreaking LLMs Through Tense Manipulation
 in Multi-Turn Dialogues](<Insert Link Here>)" by [Michael Tchuindjang](<Insert Link Here>), [Nathan Duran](<Insert Link Here>), [Phil Legg](<Insert Link Here>), and [Faiza Medjek](<Insert Link Here>). The proposed attack, dubbed the "Grammatical Mirage Attack," is a multi-turn strategy that leverages tense manipulation within dialogues to bypass the guardrails of Large Language Models (LLMs).



## Updates
- (2025-07-04) Released the first version of the paper's dataset on GitHub.
- (2025-07-01) Our paper was accepted at the 24th UK Workshop on Computational Intelligence (UKCI 2025), to be held at Edinburgh Napier University from September 3–5, 2025.


## Table of Contents

- [Installation](#installation)
- [Models](#models)
- [Experiments](#experiments)
- [Reproducibility](#reproducibility)
- [License](#license)
- [Citation](#citation)

## Installation

Please make sure to install the following python librairies as dependencies to run the multi-turn attack (Grammatical Mirage Attack)

1. jupyter
2. pandas
3. google-genai
4. openai
5. anthropic

```bash
pip install jupyter pandas google-genai openai anthropic
```

LM Studio has been installed to run the experiments with the open-source LLMs. You can follow the official link to download and install it: [LM Studio](https://lmstudio.ai/)

The experiments with closed-source LLMs were conducted via Application Programming Interface (API) calls obtained through paid subscriptions, as these models are commercial.

## Models

During the experiements, a selection of widely used large language models (LLMs), representative of current safety research, were employed as targets. These included open-source models such as Llama 2-7B [Here](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGUF) and Qwen 2-7B [Here](https://huggingface.co/Qwen/Qwen2-7B-Instruct-GGUF), as well as closed-source models like GPT-4o-mini and Gemini-2.0-Flash. In addition, Mistral-v0.1-7B [Here](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF) was used as the LLM assistant to generate the multi-turn datasets. 

## Experiments 

The [`daseline dataset`](Baseline_Dataset_Advbench_HarmBench.csv) file contains contains data derived from well-known adversarial benchmarks: AdvBench [1] and HarmBench [2].

 - To perform multi-turn data generation, please follow the instructions in [`Multiturn_dataset_generation.ipynb`](Multiturn_dataset_generation.ipynb).

 - To run single-turn or multi-turn attacks against open-source and closed-source models, refer to the instructions provided in [`Opensource_LLM_jailbreaking`](Opensource_LLM_jailbreaking) and [`Closesource_LLM_jailbreaking`](Closesource_LLM_jailbreaking) files, respectively.

A few examples of our experimental results are included in [`examples`](examples) folder.

## Reproducibility

A note for hardware: all experiments we run use one or multiple NVIDIA GeForce RTX 4090 GPUs, which have 32GiB memory per chip. 

## Acknowledgements and Citation

We thank the following open-source repositories:
- [1] [AdvBench](https://github.com/llm-attacks/llm-attacks)
- [2] [HarmBench](https://github.com/centerforaisafety/HarmBench)

If you find this useful in your research, please consider citing:

```
@misc{zou2023universal,
      title={Jailbreaking LLMs Through Tense Manipulation in Multi-Turn Dialogues}, 
      author={Michael Tchuindjang, Nathan Duran, Phil Legg, and Faiza Medjek},
      year={2025},
      eprint={},
      archivePrefix={},
      primaryClass={}
}
```

## License
Copyright (c) 2025, Michael Tchuindjang 
All rights reserved.
