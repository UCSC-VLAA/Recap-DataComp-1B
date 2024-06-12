[//]: # (<p align="center">)

[//]: # (  <img src="asset/logo.png"  height=120>)

[//]: # (</p>)


# <div align="center">👉 What If We Recaption Billions of Web Images with LLaMA-3?<div> 

[//]: # (### <div align="center"> ICLR 2024 Spotlight <div> )

<div align="center">
  <a href="https://github.com/UCSC-VLAA/Recap-DataComp-1B"><img src="https://img.shields.io/static/v1?label=Recap-DataComp1B Code&message=Github&color=blue&logo=github-pages"></a> &ensp;

  <a href="https://www.haqtu.me/Recap-Datacomp-1B"><img src="https://img.shields.io/static/v1?label=Project%20Page&message=Github&color=blue&logo=github-pages"></a> &ensp;
  <a href="https://huggingface.co/datasets/UCSC-VLAA/Recap-DataComp-1B"><img src="https://img.shields.io/static/v1?label=Recap-DataComp1B&message=HF&color=yellow"></a> &ensp;
  <a href=""><img src="https://img.shields.io/static/v1?label=Paper&message=Arxiv:Recap-DataComp1B&color=red&logo=arxiv"></a> &ensp;
</div>

---



> [**What If We Recaption Billions of Web Images with LLaMA-3?**](https://www.haqtu.me/Recap-Datacomp-1B/)<br>
> [Xianhang Li*](https://xhl-video.github.io/xianhangli/), [Haoqin Tu*](), 
> [Mude Hui*](https://thefllood.github.io/mudehui.github.io/), [Zeyu Wang*](https://scholar.google.com/citations?user=hqDyTg8AAAAJ&hl=zh-CN&oi=ao),
> [Bingchen Zhao*](https://bzhao.me/),
> [Junfei Xiao](https://lambert-x.github.io/), [Sucheng Ren](https://oliverrensu.github.io/), 
> [Jieru Mei](https://meijieru.com/), [Qing Liu](https://qliu24.github.io/), 
> [Huangjie Zheng](https://huangjiezheng.com/), 
> [Yuyin Zhou](https://yuyinzhou.github.io/),
> [Cihang Xie](https://cihangxie.github.io/)
> <br>UC Santa Cruz, University of Edinburgh, JHU, Adobe, UT Austin<br>


---
## Breaking News 🔥🔥!!

- (🔥 New) June. 12, 2024. 💥 We are excited to announce the release of Recap-DataComp-1B. Stay tuned for the upcoming release of our models!!!

Star 🌟us if you think it is helpful!!


---
## 🚩 **New Features/Updates**

- ✅ June. 12, 2024. Release the dataset.  <a href="https://huggingface.co/datasets/UCSC-VLAA/Recap-DataComp-1B"><img src="https://img.shields.io/static/v1?label=Recap-DataComp1B&message=HF&color=yellow"></a> &ensp;

---

## Contents
* [Dataset & Model Zoo](#-dataset-model)
* [Download Datasets](#-download-data)
* [Acknowledgement](#acknowledgements)
* [Citation](#bibtex)

---

## 🐱 Abstract
<b>TL; DR: <font color="red">Recap-Datacomp-1B</font>is a large-scale image-text dataset that has been recaptioned using an advanced LLaVA-1.5-LLaMA3-8B model to enhance the alignment and detail of textual descriptions.</b>

<details><summary>CLICK for the full abstract</summary>
Web-crawled image-text pairs are inherently noisy. Prior studies demonstrate that
semantically aligning and enriching textual descriptions of these pairs can significantly
enhance model training across various vision-language tasks, particularly
text-to-image generation. However, large-scale investigations in this area remain
predominantly closed-source. Our paper aims to bridge this community effort,
leveraging the powerful and open-sourced LLaMA-3, a GPT-4 level LLM. Our
recaptioning pipeline is simple: first, we fine-tune a LLaMA-3-8B powered LLaVA-
1.5 and then employ it to recaption ∼1.3 billion images from the DataComp-1B
dataset. Our empirical results confirm that this enhanced dataset, Recap-DataComp-
1B, offers substantial benefits in training advanced vision-language models. For
discriminative models like CLIP, we observe enhanced zero-shot performance in
cross-modal retrieval tasks. For generative models like text-to-image Diffusion
Transformers, the generated images exhibit a significant improvement in alignment
with users’ text instructions, especially in following complex queries.
</details>

---

![Examples of the original caption and our recaption in DataComp-1B, and word distributions.](assets/images/teaser.png)

---

## 🔥🔥Dataset and Model Zoo

We are pleased to announce the release of our recaptioned datasets, including Recap-DataComp-1B and Recap-COCO-30K, as well as our caption model, LLaVA-1.5-LLaMA3-8B. Stay tuned for the upcoming release of our CLIP and T2I models!

| Dataset           | #Samples | url                                                                                                                                                                                                          |
|:------------------|:---------|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Recap-DataComp-1B | 1.24B    |https://huggingface.co/datasets/UCSC-VLAA/Recap-DataComp-1B |
| Recap-COCO-30K    | 30.5K    |https://huggingface.co/datasets/UCSC-VLAA/Recap-COCO-30K |





| Model                        | Type              | url                                                           |
|:-----------------------------|:------------------|:--------------------------------------------------------------|
| LLaVA-1.5-LLaMA3-8B          | Our caption model | https://huggingface.co/tennant/llava-llama-3-8b-hqedit        |
| Recap-CLIP                   | CLIP              | incoming                                                      |
| Recap-DiT                    | text2image        | incoming                                                      |



---

## 🔥🔥Download dataset

1. first download all the shards contains url and captions from [huggingface](https://huggingface.co/datasets/UCSC-VLAA/Recap-DataComp-1B/tree/main/data/train_data).
2. second use [img2dataset](https://github.com/rom1504/img2dataset) tool to  download the images and captions.
3. Example script:
```bash
img2dataset --url_list Recap-DataComp-1B/train_data  --input_format "parquet" \
--url_col "url" --caption_col "re_caption" --output_format webdataset \
--output_folder recap_datacomp_1b_data --processes_count 16 --thread_count 128 \
--save_additional_columns '["org_caption"]' --enable_wandb True
```

---

[//]: # (# 🔥🔥🔥 Why Recap-Datacomp-1B? )

[//]: # (## Better CLIP)

[//]: # ()
[//]: # ()
[//]: # ()
[//]: # (## Better Text-to-Image Diffusion)



## 💪To-Do List

- [] Model Release



## 📖BibTeX
  



## 🤗Acknowledgements
This work is partially supported by a gift from Adobe, TPU Research Cloud (TRC) program, Google
Cloud Research Credits program, AWS Cloud Credit for Research program, Edinburgh International
Data Facility (EIDF) and the Data-Driven Innovation Programme at the University of Edinburgh.

---
## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=UCSC-VLAA/Recap-DataComp-1B&type=Date)](https://star-history.com/#UCSC-VLAA/Recap-DataComp-1B&Date)