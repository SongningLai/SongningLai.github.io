---
layout: page
permalink: /blogs/DRIVE/index.html
title: DIRVE
---


# DRIVE: Dependable Robust Interpretable Visionary Ensemble Framework in Autonomous Driving

Songning Lai*, Tianlang Xue*, Lijie Hu, Hongru Xiao, Jiemin Wu, Ninghui Feng, Runwei Guan, Haicheng Liao, Zhenning Li, Yutao Yue†


[![Website shields.io](https://img.shields.io/website?url=http%3A//poco.is.tue.mpg.de)](https://NA) [![YouTube Badge](https://img.shields.io/badge/YouTube-Watch-red?style=flat-square&logo=youtube)](https://NA)  [![arXiv](https://img.shields.io/badge/arXiv-2406.05036-00ff00.svg)](https://arxiv.org/2406.05036)  

## Abstract

Recent advancements in autonomous driving have seen a paradigm shift towards end-to-end learning paradigms, which map sensory inputs directly to driving actions, thereby enhancing the robustness and adaptability of autonomous vehicles. However, these models often sacrifice interpretability, posing significant challenges to trust, safety, and regulatory compliance. To address these issues, we introduce **{DRIVE}** -- **D**ependable **R**obust **I**nterpretable **V**isionary **E**nsemble Framework in Autonomous Driving, a comprehensive framework designed to improve the dependability and stability of explanations in end-to-end unsupervised autonomous driving models. Our work specifically targets the inherent instability problems observed in the Driving through the Concept Gridlock (DCG) model, which undermine the trustworthiness of its explanations and decision-making processes. We define four key attributes of **DRIVE**: consistent interpretability, stable interpretability, consistent output, and stable output. These attributes collectively ensure that explanations remain reliable and robust across different scenarios and perturbations. Through extensive empirical evaluations, we demonstrate the effectiveness of our framework in enhancing the stability and dependability of explanations, thereby addressing the limitations of current models. Our contributions include an in-depth analysis of the dependability issues within the DCG model, a rigorous definition of \textbf{DRIVE} with its fundamental properties, a framework to implement **DRIVE**, and novel metrics for evaluating the dependability of concept-based explainable autonomous driving models. These advancements lay the groundwork for the development of more reliable and trusted autonomous driving systems, paving the way for their broader acceptance and deployment in real-world applications.

*``We can only see a short distance ahead, but we can see plenty there that needs to be done.'' - {Alan Turing}*


## Motivation

- **Enhancing Public Trust**: Despite significant advancements in autonomous driving technology, public trust remains low due to concerns over loss of control and the lack of transparency in decision-making processes. Achieving widespread commercial adoption necessitates developing systems that users can understand and trust.

- **Addressing Black Box Issues**: Many current autonomous driving models, based on deep learning, function as black boxes, hindering interpretability and thus reducing confidence in their operations. Post-hoc explanations, while attempted, fail to provide real-time insights into the decision-making process, highlighting the need for anticipatory explanations.

- **Meeting Regulatory Requirements**: Regulations such as the EU's GDPR emphasize the right to explanation, underscoring the importance of transparent autonomous systems. Meeting these legal requirements and ensuring that autonomous vehicles are dependable and interpretable is crucial for both regulatory compliance and fostering public acceptance.

## Contributions


- **In-depth Analysis of DCG Dependability**: We identify and analyze a significant dependability issue in generating textual descriptions from visual data due to alignment instability between text and images, providing insights into the challenges of creating reliable and interpretable autonomous driving systems.

- **Rigorous Definition and Properties of DRIVE**: We formally define the concept of **DRIVE** (Dependable Robust Interpretable Visionary Ensemble Framework in Autonomous Driving) and outline its four fundamental properties—consistent and stable interpretability, along with consistent and stable output—offering a structured approach to evaluate and enhance the explainability of autonomous driving models.

- **Framework for Optimizing Dependability**: To address the fidelity issues identified in DCG, we propose a framework that optimizes parameters with minimal alteration, ensuring the integrity of pre-trained large model parameters while aligning with our definition of dependability. Empirical evaluations validate the effectiveness of this framework in improving the reliability and robustness of autonomous driving systems.

## Framework

<p align="center">
  <img src="./model.png" alt="Overview of the TimeSieve Framework. The upper part illustrates the overall architecture of TimeSieve, which consists of the Wavelet Decomposition Block (WDB), Wavelet Reconstruction Block (WRB), Information Fusion and Compression Block (IFCB), and the prediction. The input time series data, $T \times C$, is decomposed by WDB into coefficients $cA$ and $cD$, which are processed by IFCB. The WRB then reconstructs the data, followed by the predictor generating the corresponding forecast steps.">
</p>

  
## How to Use the Code

* [1. Setup and Installation](#setup)

* [2.Dependencies](#Dependencies)

* [3. Quick Start](#quickstart)

* [4. Datasets](#datasets)

* [4. Train](#train)

* [5. Evaluation](#eval)

* [6. Acknowledgments](#acknowledgements)

<!--
## Setup and Installation <a name="setup"></a>


Clone the repository: 

```shell
git clone https://github.com/sato-team/Stable-Text-to-motion-Framework.git
```

Create fresh conda environment and install all the dependencies:

```
conda env create -f environment.yml
conda activate SATO
```

The code was tested on Python 3.8 and PyTorch 1.8.1.

## Dependencies<a name="Dependencies"></a>

```shell
bash dataset/prepare/download_extractor.sh
bash dataset/prepare/download_glove.sh
```

## **Quick Start**<a name="quickstart"></a>

A quick reference guide for using our code is provided in quickstart.ipynb.

## Datasets<a name="datasets"></a>

We are using two 3D human motion-language dataset: HumanML3D and KIT-ML. For both datasets, you could find the details as well as download [link](https://github.com/EricGuo5513/HumanML3D).
We perturbed the input texts based on the two datasets mentioned. You can access the perturbed text dataset through the following [link](https://drive.google.com/file/d/1XLvu2jfG1YKyujdANhYHV_NfFTyOJPvP/view?usp=sharing).
Take HumanML3D for an example, the dataset structure should look like this:  
```
./dataset/HumanML3D/
├── new_joint_vecs/
├── texts/ # You need to replace the 'texts' folder in the original dataset with the 'texts' folder from our dataset.
├── Mean.npy 
├── Std.npy 
├── train.txt
├── val.txt
├── test.txt
├── train_val.txt
└── all.txt
```
### **Train**<a name="train"></a>

We will release the training code soon.

### **Evaluation**<a name="eval"></a>

You can download the pretrained models in this [link](https://drive.google.com/drive/folders/1rs8QPJ3UPzLW4H3vWAAX9hJn4ln7m_ts?usp=sharing). 

```shell
python eval_t2m.py --resume-pth pretrained/vq_best.pth --resume-trans pretrained/net_best_fid.pth --clip_path pretrained/clip_best.pth
```


## Acknowledgements<a name="acknowledgements"></a>

We appreciate helps from :

- Open Source Code：[T2M-GPT](https://github.com/Mael-zys/T2M-GPT), [MoMask ](https://github.com/EricGuo5513/momask-codes), [MDM](https://guytevet.github.io/mdm-page/), etc.
- [Hongru Xiao](https://github.com/Hongru0306), [Erhang Zhang](https://github.com/zhangerhang), [Lijie Hu](https://sites.google.com/view/lijiehu/homepage), [Lei Wang](https://leiwangr.github.io/), [Mengyuan Liu](), [Chen Chen](https://www.crcv.ucf.edu/chenchen/) for discussions and guidance throughout the project, which has been instrumental to our work.
- [Zhen Zhao](https://github.com/Zanebla) for project website.
- If you find our work helpful, we would appreciate it if you could give our project a star!
## Citing<a name="citing"></a>
-->


If you find this document useful for your research, please consider citing the following repository and paper:
```bibtex
@misc{TimeSieve_repo,
  author       = "{Ninghui Feng and Songning Lai and Zhenxiao Yin and Fobao Zhou and Hang Zhao}",
  title        = "{TimeSieve: Extracting Temporal Dynamics through Information Bottlenecks}",
  howpublished = "{GitHub repository}",
  note         = "{URL: \url{https://github.com/xll0328/TimeSieve/}}",
  year         = {2024},
}

@misc{feng2024timesieve,
      title={TimeSieve: Extracting Temporal Dynamics through Information Bottlenecks}, 
      author={Ninghui Feng and Songning Lai and Fobao Zhou and Zhenxiao Yin and Hang Zhao},
      year={2024},
      eprint={2406.05036},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

