# DrivingWorld: Constructing World Model for Autonomous Driving via Video GPT
## [HomePage](https://huxiaotaostasy.github.io/DrivingWorld/index.html) | [arXiv]()
This project is the implementation of our Paper: [DrivingWorld: Constructing World Model for Autonomous Driving via Video GPT](https://arxiv.org/abs/2303.09875). We proposed an auto-regressive world model for autonomous driving.

![Teaser](./images/teaser.png)

## Usage
### Installation

```bash
git clone https://github.com/YvanYin/DrivingWorld.git
cd DrivingWorld
pip3 install -r requirements.txt
```
* Download the pretrained models from [Hugging Face](https://huggingface.co/huxiaotaostasy/DrivingWorld/tree/main), and move the pretrained parameters to `DrivingWorld/pretrained_models/*`

### Data Preparation
For the public dataset, we use [NuPlan](https://nuplan.org/) and [OpenDV-YouTube](https://github.com/OpenDriveLab/DriveAGI?tab=readme-ov-file#opendv) for testing.

We download `nuPlan Val Split` in [NuPlan](https://nuplan.org/). And we follow [OpenDV-YouTube](https://github.com/OpenDriveLab/DriveAGI/blob/main/opendv/README.md) to get the validation set.

We share the `json` files in [Hugging Face](https://huggingface.co/huxiaotaostasy/DrivingWorld/tree/main).


### Evaluation 
Script for the default setting (conditioned on 15 frames, on Nuplan Validation set, adopt topk sampling):
```bash
cd tools
sh demo_test_long_term_nuplan.sh
sh demo_test_long_term_youtube.sh
sh demo_test_change_road.sh
```
You can change the setting with config file in \<configs/\>

## Reference
We thank for [VQGAN](https://github.com/CompVis/taming-transformers), [LlamaGen](https://github.com/FoundationVision/LlamaGen) and [LLlama 3.1](https://github.com/meta-llama/llama3) for their codebase.