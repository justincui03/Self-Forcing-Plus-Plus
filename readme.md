## Self-Forcing++: Towards Minute-Scale High-Quality Video Generation
[![Paper](https://img.shields.io/badge/ArXiv-Paper-brown)]()
[![Code](https://img.shields.io/badge/GitHub-Self%20Forcing%2B%2B-pink)](https://github.com/justincui03/Self-Forcing-Plus-Plus)
[![Demo](https://img.shields.io/badge/Demo-Page-blue)](https://self-forcing-plus-plus.github.io/)

[![Watch the demo](./assets/demo_first_frame.jpg)](https://self-forcing-plus-plus.github.io/)

## ✨ TDLR: Multi-Minute Streaming Long Video Generation with High Quality

This work tackles the challenge of generating long, high-quality videos with diffusion models, which are usually limited by costly transformers and short-horizon teachers. We propose a simple method that leverages teacher knowledge and self-generated video segments to guide autoregressive students without retraining on long-video datasets. Our approach preserves temporal consistency, avoids error accumulation, and scales video length up to **4 minutes 15 seconds**, equivalent to **99.9%** of the maximum span supported by our base model's position embedding, significantly outperforming prior methods on fidelity and consistency benchmarks.

## ⚙️ Main Workflow
![main workflow](./assets/main_workflow.jpg)
Bi-directional diffusion can be seen as a process of gradually restoring a degraded target. We adapt it to autoregressive generation by having a short-horizon teacher refine the student’s outputs and then distilling these correction knowledge back into the student model.

## 🔥 Concurrent Work
Both [Rolling Forcing](https://kunhao-liu.github.io/Rolling_Forcing_Webpage/) and [LongLive](https://nvlabs.github.io/LongLive/) , as well as [ours](https://self-forcing-plus-plus.github.io/), are able to generate high-quality videos up to multiple minutes long, which marks a significant advance in autoregressive long video generation compared to previous methods. While all methods adopt a windowed distillation strategy, **Rolling Forcing** introduces **progressively** varied noise levels across frames combined with attention sink frames, **LongLive** employs **sink frames** with KV recaching for prompt switching, **our** approach relies solely on historical KV cache without sink frames.

## Reproduce Our Work
Our code will be released soon. Our work can be reproduced based on [Self Forcing](https://github.com/guandeh17/Self-Forcing) by following [how to reproduce our work](https://self-forcing-plus-plus.github.io/#reproducing_results).




## Acknowledgement
We sincerely thank the following work for their exceptional effort.
- [Self-Forcing](https://github.com/guandeh17/Self-Forcing): the codebase we built upon. 
- [Wan](https://github.com/Wan-Video/Wan2.1): the base model we built upon.
- [CausVid](https://github.com/tianweiy/CausVid): the codebase that shows asymmetric distillation is possible.
- [DMD](https://github.com/tianweiy/DMD2): the key distillation technique used by our method

## Citation
Please consider citing our work if it's useful. Together we hope to make long video generation better and longer.
```bibtex
@article{cui2025self,
  title={Self-Forcing++: Towards Minute-Scale High-Quality Video Generation},
  author={Cui, Justin and Wu, Jie and Li, Ming and Yang, Tao and Li, Xiaojie and Wang, Rui and Bai, Andrew and Ban, Yuanhao and Hsieh, Cho-Jui},
  journal={arXiv preprint arXiv:2510.02283},
  year={2025}
}
```
