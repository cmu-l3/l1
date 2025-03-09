<div align="center">
    <h1> L1: Controlling How Long A Reasoning Model Thinks With Reinforcement Learning</h1>
    <a href="https://cmu-l3.github.io/l1"><img src="https://img.shields.io/website?down_message=down&style=for-the-badge&up_message=up&url=https%3A%2F%2Fcmu-l3.github.io/l1"></a>
<a href="https://arxiv.org/abs/2503.04697"><img src="https://img.shields.io/badge/arXiv-2504.04697-red.svg?style=for-the-badge"></a>
<a href="https://huggingface.co/collections/l3lab/l1-67cacf4e39c176ca4e9890f4"><img src="https://img.shields.io/badge/Hugging%20Face-Model-blue?style=for-the-badge&logo=huggingface"></a>
<a href="https://colab.research.google.com/drive/1E7A327gO5ph06-kZ6E71AWmqQxLE0kqX?usp=sharing"><img src="https://img.shields.io/badge/Colab-Notebook-orange?style=for-the-badge&logo=googlecolab"></a>
    <br>
</div>

<br>
<br>

## How to Use?

### Installation

```bash
git clone https://github.com/cmu-l3/l1.git
cd l1
pip install -e verl
pip install packaging
pip install ninja
pip install flash-attn --no-build-isolation
pip install -e .
```


### Prepare Dataset

You can use scripts in `scripts/data` to prepare your own dataset.

Example, generate data for traininng L1-Exact:
```
python scripts/data/deepscaler_dataset.py 
```

For L1-Max:
```
python scripts/data/deepscaler_dataset.py --use_both_both
```

For Evaluation on AIME2025, GPQA, LSAT and MMLU, you can use scripts in `scripts/eval`:
```
python scripts/eval/generate_aime.py
python scripts/eval/generate_gpqa.py
python scripts/eval/generate_lsat.py
python scripts/eval/generate_mmlu.py
```

### Train Models

You can skip this step if you want to use our pre-trained models.

You can run scripts in `scripts/train` to train your own models. Make sure to specify the correct data path.

### Evaluate Models

Use one of `scripts/eval` to evaluate your models. Make sure to specify the correct model path.

For example, evaluate L1-Exact on AIME2025:
```
./scripts/eval/eval_model_token.sh --model path/to/your/model --num-tokens <num_tokens> --datasets aime2025
```

## Acknowledgments

- We would like to thank DeepSeek for releasing Deepseek-r1 and distilled models, 
- Qwen for releasing super-awesome Qwen-2.5 math Models, and 
- [Agentica](https://github.com/agentica-project/deepscaler) for codebase, and opensourcing their models and datasets! 


## Citation

If you use L1/LCPO in your research, please cite:

```bibtex
@misc{aggarwal2025l1controllinglongreasoning,
  title={L1: Controlling How Long A Reasoning Model Thinks With Reinforcement Learning}, 
  author={Pranjal Aggarwal and Sean Welleck},
  year={2025},
  eprint={2503.04697},
  archivePrefix={arXiv},
  primaryClass={cs.CL},
  url={https://arxiv.org/abs/2503.04697}, 
}
```


