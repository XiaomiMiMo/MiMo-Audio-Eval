<div align="center">
  <picture>
    <source srcset="https://github.com/XiaomiMiMo/MiMo-VL/raw/main/figures/Xiaomi_MiMo_darkmode.png?raw=true" media="(prefers-color-scheme: dark)">
    <img src="https://github.com/XiaomiMiMo/MiMo-VL/raw/main/figures/Xiaomi_MiMo.png?raw=true" width="60%" alt="Xiaomi-MiMo" />
  </picture>
</div>

<h3 align="center">
  <b>
    <span>━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━</span>
    <br/>
    MiMo-Audio-Eval Toolkit
    <br/>
    <span>━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━</span>
    <br/>
  </b>
</h3>

<br/>

<div align="center" style="line-height: 1;">
  |
  <a href="https://github.com/XiaomiMiMo/MiMo-Audio" target="_blank">🤖 GitHub</a>
  &nbsp;|
  <a href="https://huggingface.co/collections/XiaomiMiMo/mimo-audio-68cc7202692c27dae881cce0" target="_blank">🤗 HuggingFace</a>
  &nbsp;|
  <a href="https://github.com/XiaomiMiMo/MiMo-Audio/blob/main/MiMo-Audio-Technical-Report.pdf" target="_blank">📄 Paper</a>
  &nbsp;|
  <a href="https://xiaomimimo.github.io/MiMo-Audio-Demo" target="_blank">📰 Blog</a>
  &nbsp;|
  <br/>
</div>

<br/>

## Introduction

Welcome to the **MiMo-Audio-Eval** toolkit! This toolkit is designed to evaluate various audio language models as described in the **MiMo-Audio** paper. It provides a flexible and extensible framework, supporting a wide range of datasets, tasks, and models, specifically for evaluating pre-trained or supervised fine-tuned (SFT) audio language models. The toolkit is ideal for researchers and developers who need to assess the performance of these models across different tasks and datasets.

## Supported Datasets, Tasks, and Models

The MiMo-Audio-Eval toolkit supports a comprehensive set of datasets, tasks, and models. Some of the key features include:

* **Datasets**:

  * AISHELL1
  * LibriSpeech
  * SeedTTS
  * Expresso
  * InstructTTSEval
  * SpeechMMLU
  * MMAR
  * MMAU
  * MMAU-Pro
  * MMSU
  * ESD
  * Big Bench Audio
  * MultiChallenge Audio

* **Tasks**:

  * **Pretrain**:

    * ICL General Knowledge Evaluation
    * ICL Audio Understanding Evaluation
    * ICL Speech-to-Speech Generation

  * **SFT**:

    * ASR
    * TTS / InstructTTS
    * Audio Understanding and Reasoning
    * Spoken Dialogue

* **Models**:

  * MiMo-Audio
  * Step-Audio2
  * Kimi-Audio
  * Baichuan-Audio
  * Qwen-Omni


## Getting Started

To get started with the MiMo-Audio-Eval toolkit, follow the instructions below to set up the environment and install the required dependencies.

### Prerequisites (Linux)

* Python 3.12
* CUDA >= 12.0

### Installation:

```bash
git clone --recurse-submodules https://github.com/XiaomiMiMo/MiMo-Audio-Eval
cd MiMo-Audio-Eval
pip install -r requirements.txt
pip install flash-attn==2.7.4.post1
pip install -e .
```

**Note: For evaluating Qwen2.5-Omni, please install the following dependencies:**

```bash
pip install transformers==4.52.3 qwen-omni-utils[decord]
```

> \[!Note]
> If the compilation of flash-attn takes too long, you can download the precompiled wheel and install it manually:
>
> * [Download Precompiled Wheel](https://github.com/Dao-AILab/flash-attention/releases/download/v2.7.4.post1/flash_attn-2.7.4.post1+cu12torch2.6cxx11abiFALSE-cp312-cp312-linux_x86_64.whl)
>
> ```sh
> pip install /path/to/flash_attn-2.7.4.post1+cu12torch2.6cxx11abiFALSE-cp312-cp312-linux_x86_64.whl
> ```

### Download evaluation data:

```bash
python download_data.py
```

### (Optional) Download required models:

#### For Voice Conversion evaluation:

Download the [WavLM model](https://drive.google.com/file/d/1-aE1NfzpRCLxA4GUxX9ITI3F9LlbtEGP/view?usp=sharing) and place it in the `data/` directory.

#### For Big Bench Audio and MultiChallenge Audio evaluations:

Export your OpenAI API Key:

```bash
export OPENAI_API_KEY="your_openai_api_key_here"
```

## Usage

We provide a series of evaluation scripts in the `eval_scripts` directory, including scripts for evaluating both pre-trained models and SFT models. These scripts can be used to reproduce the results presented in our paper. An example usage is as follows:

```bash
bash $scripts <model_path> <tokenizer_path> <model_name>
```


## Citation

```bibtex
@misc{coreteam2025mimoaudio,
      title={MiMo-Audio: Audio Language Models are Few-Shot Learners}, 
      author={LLM-Core-Team Xiaomi},
      year={2025},
      url={https://github.com/XiaomiMiMo/MiMo-Audio}, 
}
```


## Contact

Please contact us at [mimo@xiaomi.com](mailto:mimo@xiaomi.com) or open an issue if you have any questions.
