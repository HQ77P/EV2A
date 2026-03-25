# 🔬 EV2A

[![Paper](https://img.shields.io/badge/📄_Paper-arXiv_2026.xxxxx-b31b1b)](https://arxiv.org/abs/2026.xxxxx)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-ee4c2c.svg)](https://pytorch.org/)

> **Authors**: Haoqi Liu, Mehrdad Yaghoobi  
> the Institute for Imaging, Data and Communications, School of Engineering, University of Edinburgh, Edinburgh, U.K.

---

## 📖 Abstract

Visual microphones are designed to recover audio information from visual data acquired from camera sensors. There exist a few methods focusing on audio representation and reconstruction using filtering or optimization algorithms. However, because of the complexity of the sensing process, the overall performance of the visual microphones has been limited to date. In this paper, we propose to solve this problem with an end-to-end deep learning-based method using the event camera sensor, which only records the changes in light intensity. It is a more challenging problem, since the intensity changes are coarsely discretized, but it has its own practical benefits. We focus on the speech recovery task which requires high perceptual and objective quality to ensure the understandability of the output. The proposed model consists of architectures for the extraction of visual features and the enhancement of audio signals. It is trained and validated using real data with the paired speech and vibration recordings. The real data results demonstrate the improved recovery quality of the proposed method in objective metrics, achieving a Perceptual Evaluation of Speech Quality (PESQ) of 1.82 (range: -0.5 to 4.5) and a Short-Time Objective Intelligibility (STOI) of 0.80 (range: 0 to 1), representing improvements of 0.61 and 0.25, respectively, over state-of-the-art alternative methods. A downstream Speech-to-Text evaluation confirms the improved intelligible content recovery with a Character Error Rate (CER) of 0.17. Further experiments demonstrate the robustness of proposed method in terms of sensor's orientation, distance, and vibrating material.

<p align="center">
  <img src="assets/images/workflow0324_clip.pdf" width="85%" alt="workflow">
  <br>
  <em>图1: SpecEnhance Workflow of the Proposed Method</em>
</p>

---

## 🎯 Contributions

1. 
2. 
3. 

---

## 📊 Experiments Results

### Evaluation Metrics

| Method | PESQ ↑ | STOI ↑ | SI-SNR (dB) ↑ | |
|:-----|:------:|:------:|:--------------:|:----------:|
| Noisy Input  | 1.97 | 0.921 | 8.4  | -    |
| DCCRN        | 2.68 | 0.943 | 15.2 | 3.7  |
| CMGAN        | 3.14 | 0.961 | 17.8 | 6.2  |
| **SpecEnhance (Ours)** | **3.52** | **0.974** | **19.6** | **4.1** |

### Comparison of the Spectrograms

<table>
  <tr>
    <td align="center"><b>含噪输入</b></td>
    <td align="center"><b>SpecEnhance 输出</b></td>
    <td align="center"><b>干净参考</b></td>
  </tr>
  <tr>
    <td><img src="assets/images/spectrogram_noisy.png" width="280"></td>
    <td><img src="assets/images/spectrogram_enhanced.png" width="280"></td>
    <td><img src="assets/images/spectrogram_clean.png" width="280"></td>
  </tr>
  <tr>
    <td><img src="assets/images/waveform_noisy.png" width="280"></td>
    <td><img src="assets/images/waveform_enhanced.png" width="280"></td>
    <td><img src="assets/images/waveform_clean.png" width="280"></td>
  </tr>
</table>

<p align="center"><em>图2: 语音增强前后的频谱图与波形对比 (sample_001, SNR=5dB)</em></p>

### Comparison of the Waveforms

<p align="center">
  <img src="assets/images/waveform_comparison_detail.png" width="90%">
  <br>
  <em>图3: 不同方法在高噪声段的波形细节对比</em>
</p>

---

## 🎧 Audio Samples

We provide more audio samples in [Demo 页面](https://your-username.github.io/your-repo-name/)。

### Sample 1: Female Speaker

| 类型 | 音频 |
|:-----|:-----|
| 含噪输入 | [▶️ 播放](assets/audio/sample_001_noisy.wav) |
| DCCRN | [▶️ 播放](assets/audio/sample_001_dccrn.wav) |
| **SpecEnhance** | [▶️ 播放](assets/audio/sample_001_enhanced.wav) |
| 干净参考 | [▶️ 播放](assets/audio/sample_001_clean.wav) |

### Sample 2: Male Speaker

| 类型 | 音频 |
|:-----|:-----|
| 含噪输入 | [▶️ 播放](assets/audio/sample_002_noisy.wav) |
| DCCRN | [▶️ 播放](assets/audio/sample_002_dccrn.wav) |
| **SpecEnhance** | [▶️ 播放](assets/audio/sample_002_enhanced.wav) |
| 干净参考 | [▶️ 播放](assets/audio/sample_002_clean.wav) |

> ⚠️ **Notice**: GitHub doesn't support to direcly play the `.wav` file. Please download and play, or visit our webpage for listening: [在线 Demo 页面](https://your-username.github.io/your-repo-name/).

---

## 🎬 Vibration Recording Sample

<p align="center">
  <a href="https://www.youtube.com/watch?v=your_video_id">
    <img src="assets/images/video_thumbnail.png" width="600" alt="演示视频">
  </a>
  <br>
  <em>点击图片跳转至 YouTube 观看完整演示</em>
</p>

### 动态频谱分析

<!-- 方法1: 使用 GIF 动图（推荐用于短片段） -->
<p align="center">
  <img src="assets/videos/spectrogram_animation.gif" width="600">
  <br>
  <em>图4: 实时频谱增强过程动画 (GIF)</em>
</p>

<!-- 方法2: 使用 GitHub 原生视频支持（推荐用于较长视频） -->

https://github.com/user-attachments/assets/your-video-hash-here

<p align="center"><em>视频1: 完整的实时语音增强演示</em></p>

---

## 🚀 快速开始

### 环境配置

```bash
# 克隆仓库
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name

# 创建虚拟环境
conda create -n specenhance python=3.9 -y
conda activate specenhance

# 安装依赖
pip install -r requirements.txt
```

### 推理示例

```python
import torch
from models.spec_enhance import SpecEnhance

# 加载预训练模型
model = SpecEnhance.from_pretrained("checkpoints/best_model.pth")
model.eval()

# 读取含噪音频
noisy_audio, sr = torchaudio.load("examples/noisy_sample.wav")

# 执行增强
with torch.no_grad():
    enhanced_audio = model(noisy_audio.unsqueeze(0))

# 保存结果
torchaudio.save("examples/enhanced_output.wav", enhanced_audio.squeeze(0), sr)
print(f"增强完成！PESQ: {calculate_pesq(enhanced_audio, clean_audio):.2f}")
```

### 训练模型

```bash
# 单卡训练
python train.py --config configs/specenhance_base.yaml

# 多卡分布式训练
torchrun --nproc_per_node=4 train.py \
    --config configs/specenhance_base.yaml \
    --distributed
```

### 生成频谱可视化

```bash
python scripts/visualize.py \
    --input examples/noisy_sample.wav \
    --output assets/images/ \
    --plot-type spectrogram waveform
```

---

## 📁 项目结构

```
├── assets/
│   ├── images/           # 频谱图、波形图、架构图等
│   ├── audio/            # 音频示例文件
│   └── videos/           # 视频演示、GIF动画
├── configs/              # 训练配置文件
├── data/                 # 数据处理脚本
│   ├── dataset.py
│   └── preprocess.py
├── docs/                 # GitHub Pages Demo 页面
│   └── index.html
├── examples/             # 快速上手示例
├── models/               # 模型定义
│   ├── spec_enhance.py
│   └── modules/
├── scripts/              # 工具脚本
│   ├── visualize.py      # 频谱/波形可视化
│   ├── evaluate.py       # 评估脚本
│   └── generate_demo.py  # 生成 Demo 页面素材
├── checkpoints/          # 预训练权重 (Git LFS)
├── requirements.txt
├── train.py
├── inference.py
└── README.md
```

---

## 📝 引用

如果本工作对您的研究有所帮助，请引用：

```bibtex
@inproceedings{zhang2026specenhance,
  title     = {SpecEnhance: Joint Time-Frequency Modeling for Speech Enhancement},
  author    = {Zhang, San and Li, Si},
  booktitle = {Proceedings of ACM Multimedia},
  year      = {2026}
}

