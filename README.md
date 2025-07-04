
# Large Language Model (LLM) Multi-turn Attacks

This is the repository for "[Jailbreaking LLMs Through Tense Manipulation
 in Multi-Turn Dialogues](<Insert Link Here>)" by [Michael Tchuindjang](<Insert Link Here>), [Nathan Duran](<Insert Link Here>), [Phil Legg](<Insert Link Here>), and [Faiza Medjek](<Insert Link Here>). The proposed attack, dubbed the "Grammatical Mirage Attack," is a multi-turn strategy that leverages tense manipulation within dialogues to bypass the guardrails of Large Language Models (LLMs).



## Updates
- (XXXX-XX-XX) News 1...
- (XXXX-XX-XX) News 2...


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
pip install pandas google-genai openai anthropic
```

LM Studio has been installed to run the experiments with the LLMs. You can follow the official link to download and install it: [LM Studio]([https://example.com](https://lmstudio.ai/))


## Models

During the experiements, a selection of widely used large language models (LLMs), representative of current safety research, were employed as targets. These included open-source models such as Llama 2-7B [Here](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGUF) and Qwen 2-7B [Here](https://huggingface.co/Qwen/Qwen2-7B-Instruct-GGUF), as well as closed-source models like GPT-4o-mini and Gemini-2.0-Flash. In addition Mistral-v0.1-7B [Here](https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF) was use as LLM assistant to generate the multi-turn datasets.

## Experiments 

The [`daseline dataset`](Baseline_Dataset_Advbench_HarmBench.csv) file contains code to reproduce GCG experiments on AdvBench.

The `experiments` folder contains code to reproduce GCG experiments on AdvBench.

- To run individual experiments with harmful behaviors and harmful strings (i.e. 1 behavior, 1 model or 1 string, 1 model), run the following code inside `experiments` (changing `vicuna` to `llama2` and changing `behaviors` to `strings` will switch to different experiment setups):

```bash
cd launch_scripts
bash run_gcg_individual.sh vicuna behaviors
```

- To perform multiple behaviors experiments (i.e. 25 behaviors, 1 model), run the following code inside `experiments`:

```bash
cd launch_scripts
bash run_gcg_multiple.sh vicuna # or llama2
```

- To perform transfer experiments (i.e. 25 behaviors, 2 models), run the following code inside `experiments`:

```bash
cd launch_scripts
bash run_gcg_transfer.sh vicuna 2 # or vicuna_guanaco 4
```

- To perform evaluation experiments, please follow the directions in `experiments/parse_results.ipynb`.

Notice that all hyper-parameters in our experiments are handled by the `ml_collections` package [here](https://github.com/google/ml_collections). You can directly change those hyper-parameters at the place they are defined, e.g. `experiments/configs/individual_xxx.py`. However, a recommended way of passing different hyper-parameters -- for instance you would like to try another model -- is to do it in the launch script. Check out our launch scripts in `experiments/launch_scripts` for examples. For more information about `ml_collections`, please refer to their [repository](https://github.com/google/ml_collections).

## Reproducibility

A note for hardware: all experiments we run use one or multiple NVIDIA A100 GPUs, which have 80G memory per chip. 

We include a few examples people told us when reproducing our results. They might also include workaround for solving a similar issue in your situation. 

- [Prompting Llama-2-7B-Chat-GGML](https://github.com/llm-attacks/llm-attacks/issues/8)
- [Possible Naming Issue for Running Experiments on Windows](https://github.com/llm-attacks/llm-attacks/issues/28)

Currently the codebase only supports training with LLaMA or Pythia based models. Running the scripts with other models (with different tokenizers) will likely result in silent errors. As a tip, start by modifying [this function](https://github.com/llm-attacks/llm-attacks/blob/main/llm_attacks/base/attack_manager.py#L130) where different slices are defined for the model.

## Citation
If you find this useful in your research, please consider citing:

```
@misc{zou2023universal,
      title={Universal and Transferable Adversarial Attacks on Aligned Language Models}, 
      author={Andy Zou and Zifan Wang and J. Zico Kolter and Matt Fredrikson},
      year={2023},
      eprint={2307.15043},
      archivePrefix={arXiv},
      primaryClass={cs.CL}
}
```

## License
`llm-attacks` is licensed under the terms of the MIT license. See LICENSE for more details.
