# 声音克隆工作台

在浏览器里录音、保存声音、输入文字，用 Qwen3-TTS 生成你的声音。

- **在线版**：https://voice.hench.cc.cd/
- **Colab 笔记本**：[`qwen3-tts-clone.ipynb`](qwen3-tts-clone.ipynb)（[在 Colab 打开](https://colab.research.google.com/github/aliporcins/voice-clone-workbench/blob/main/qwen3-tts-clone.ipynb)，运行时选 T4 GPU）

## 用法

1. 打开在线版，录一段 10–30 秒的声音（或上传已有音频），填名称、备注和录音原文，保存到声音库。
2. 输入文字，自动按约 120 字分段。
3. 生成（二选一）：
   - **A · 直接生成**：用阿里 Qwen 官方 Hugging Face Space（Qwen/Qwen3-TTS）在线生成，免费但要排队、匿名额度有限。
   - **B · Colab 生成**：下载语音包（`voice-pack.zip`），在 Colab 打开笔记本，上传语音包，按顺序运行，下载生成音频。

## 隐私

声音默认只存在你的浏览器里（IndexedDB），不上传服务器；只有你点「生成」时，才会把声音发给 Hugging Face 或你自己传进 Colab。

## 技术

- 模型：Qwen3-TTS-12Hz-1.7B-Base（阿里 Qwen 团队，Apache-2.0）
- 前端：单页 `site/index.html`（录音 MediaRecorder、16kHz 单声道 WAV 转码、IndexedDB 声音库）
- 部署：Cloudflare Pages
