# MM-R3 : On (In-)Consistency of Vision-Language Models (VLMs)
[ACL 2025 findings] MM-R3 : On (In-)Consistency of Vision-Language Models (VLMs)
[[Paper](https://aclanthology.org/2025.findings-acl.246/)] [[HF]()] <br>
[Shih-Han Chou](https://shihhanchou.github.io/), [Shivam Chandhok](https://scholar.google.com/citations?user=ZER2BeIAAAAJ&hl=en), [James J. Little](https://www.cs.ubc.ca/~little/), [Leonid Sigal](https://www.cs.ubc.ca/~lsigal/)


## Contents
- [Install](#install)
- [Dataset](https://github.com/haotian-liu/LLaVA/blob/main/docs/Data.md)
- [Evaluation](#evaluation)


## Install
For each model, please use the original GiHub repo to setup the environment.

[LLaVa](https://github.com/haotian-liu/LLaVA), [Blip2](https://github.com/salesforce/LAVIS/tree/main/projects/blip2), [MoE-LLaVa](https://github.com/PKU-YuanGroup/MoE-LLaVA), [Qwen-VL](https://github.com/QwenLM/Qwen-VL), [mPLUG-Owl2](https://github.com/X-PLUG/mPLUG-Owl/tree/main/mPLUG-Owl2), [Blip-3](https://github.com/salesforce/LAVIS/tree/xgen-mm)


## Dataset
Please download the dataset from HuggingFace. [TBD]


## Evaluation
To run rephrase task:
```bash
# LLaVa
python LLaVa/evaluate_rephrase_okvqa.py
python LLaVa/evaluate_rephrase_infovqa.py
# blip2
python blip2/evaluate_rephrase.py
# MoE-LLaVa
deepspeed --include localhost:0 MoE-LLaVA/predict_rephrase_okvqa.py
deepspeed --include localhost:0 MoE-LLaVA/predict_rephrase_infovqa.py
# Qwen-VL
python Qwen-VL/evaluate_rephrase.py
# mPLUG-Owl2
python mPLUG-Owl2/evaluate_rephrase_okvqa.py
python mPLUG-Owl2/evaluate_rephrase_infovqa.py
```

To run masking task:
```bash
# LLaVa
python LLaVa/evaluate_masked.py
# blip2
python blip2/evaluate_masked.py
# MoE-LLaVa
deepspeed --include localhost:0 MoE-LLaVA/predict_masked.py
# Qwen-VL
python Qwen-VL/evaluate_masked.py
# mPLUG-Owl2
python mPLUG-Owl2/evaluate_masked.py
```

To run style task:
```bash
# LLaVa
python LLaVa/evaluate_style.py
# blip2
python blip2/evaluate_style.py
# MoE-LLaVa
deepspeed --include localhost:0 MoE-LLaVA/predict_style.py
# Qwen-VL
python Qwen-VL/evaluate_style.py
# mPLUG-Owl2
python mPLUG-Owl2/evaluate_style.py
```

The output will be stored in a numpy file (please refer to the sample data).

To calculate the accuracy and consistency:
```bash
# rephrase task
python Consistency_evaluate/rephrase_task/metrics.py
python Consistency_evaluate/rephrase_task/statistics.py
# masking task
python Consistency_evaluate/masking_task/metrics.py
python Consistency_evaluate/masking_task/statistics.py
# style task
python Consistency_evaluate/styling_task/metrics.py
python Consistency_evaluate/styling_task/statistics.py
```


## Citation

If you find our dataset is useful for your research and applications, please cite using this BibTeX:
```bibtex
@inproceedings{chou2025mm,
  title={MM-R3: On (In-) Consistency of Vision-Language Models (VLMs)},
  author={Chou, Shih-Han and Chandhok, Shivam and Little, Jim and Sigal, Leonid},
  booktitle={Findings of the Association for Computational Linguistics: ACL 2025},
  pages={4762--4788},
  year={2025}
}
