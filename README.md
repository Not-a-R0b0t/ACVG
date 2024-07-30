## Action-conditioned video data improves predictability
Long-term video generation and prediction remain challenging in computer vision, particularly in partially observable scenarios where cameras are mounted on moving platforms. The interaction between observed image frames and the motion of the recording agent introduces additional complexities. This paper introduces the Action-Conditioned Video Generation (ACVG) framework to address these issues. This novel approach investigates the relationship between actions and generated image frames through a deep dual Generator-Actor architecture. ACVG generates video sequences conditioned on the actions of robots, enabling exploration and analysis of how vision and action mutually influence each other in dynamic environments. We evaluate the framework's effectiveness on an indoor robot motion dataset consisting of sequences of image frames and actions taken by the robotic agent. We conduct a comprehensive empirical study comparing ACVG to other state-of-the-art frameworks and also a detailed ablation study.

## RoAM dataset:
Please follow the instructions in https://github.com/meenakshisarkar/RoAM-dataset to download and extract the image frames in "data/RoAM_dataset/processed" directory.

## Instructions for running code
```bash
# Training ACVG with only Generator:
#Please comment/uncomment the following in setup.bash
export DATAPATH="data/RoAM_dataset/processed/train" in setup.bash
#export DATAPATH="../data/RoAM_dataset/processed/test"
export G_TRAIN=True
export A_TRAIN=False

source setup.bash
python main_run.py

# Training ACVG with only Actor and pretrained Generator:
#Please comment/uncomment the following in setup.bash
export DATAPATH="data/RoAM_dataset/processed/train" in setup.bash
#export DATAPATH="../data/RoAM_dataset/processed/test"
export G_TRAIN=False
export A_TRAIN=True

source setup.bash
python main_run.py

# Training ACVG with both Actor and  Generator:
#Please comment/uncomment the following in setup.bash
export DATAPATH="data/RoAM_dataset/processed/train" in setup.bash
#export DATAPATH="../data/RoAM_dataset/processed/test"

source setup.bash
python main_run.py

# Testing ACVG
source setup.bash
python main_run.py

