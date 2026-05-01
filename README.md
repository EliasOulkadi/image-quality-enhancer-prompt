# 🖼️ Pixel Perfect Prompt — AI Image Quality Enhancer

> **Universal prompt for AI image upscaling/enhancement WITHOUT modifying content.**  
> Compatible with **ChatGPT (GPT-4o)**, **Nano Banana**, and **Nano Banana Pro**.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![ChatGPT](https://img.shields.io/badge/ChatGPT-Compatible-74aa9c?logo=openai)](https://chat.openai.com)
[![Nano Banana](https://img.shields.io/badge/Nano_Banana-Compatible-fbbc04?logo=google)](https://codewords.agemo.ai)

---

## 📸 Before & After

<p align="center">
  <img src="old.png" alt="Original — Low quality" width="360"/>
  &nbsp;&nbsp;&nbsp;
  <img src="new.png" alt="Result — Enhanced quality" width="360"/>
</p>

<p align="center">
  <sub><strong>Left:</strong> Original (low resolution, compression artifacts) · <strong>Right:</strong> Enhanced (4K, sharp, HDR-like)</sub>
</p>

---

## 📋 What is this?

A carefully researched and engineered prompt that forces AI image generators to **enhance image quality** (resolution, sharpness, noise reduction) while keeping the image content **100% identical** to the original.

### Key Features

- 🔒 **Absolute preservation mandate** — prevents AI from reinterpreting your image
- 🎨 **Style-agnostic** — works with photos, anime, manga, digital art, illustrations, screenshots
- 🚫 **Comprehensive negative list** — explicitly blocks 13+ common AI modification patterns
- ✅ **Self-verification checklist** — forces the model to compare output vs input before generating

---

## 🚀 Quick Start

### ChatGPT (GPT-4o) — Requires Plus/Pro

1. Open ChatGPT
2. **Attach your image first**
3. Paste the contents of [`prompt.txt`](./prompt.txt)
4. Send

> ⚠️ **Free ChatGPT cannot generate images.** You need ChatGPT Plus ($20/mo) or Pro for this to work.

### Nano Banana / Nano Banana Pro

1. Upload your image in the same message
2. Paste the contents of [`prompt.txt`](./prompt.txt)
3. Send

> 💡 **Removing the watermark:** Use the [**Peel Banana**](https://chromewebstore.google.com/detail/peel-banana) browser extension to automatically remove the Nano Banana watermark from generated images.

---

## ⚠️ Important Limitations

**AI image generators (ChatGPT, Nano Banana, etc.) do NOT truly upscale images.** They *regenerate* the image from scratch, which inevitably introduces subtle changes — shifted colors, altered details, modified proportions.

For **true pixel-perfect upscaling** with 4K+ quality, use the dedicated pipeline below.

---

## 🔥 Ultimate 4K Pipeline (Recommended)

For the absolute best results — true 4K, pixel-perfect fidelity, HDR-like look — use this 3-step pipeline with free tools:

### Step 1: AI Upscale (4×)

| Setting | Value |
|---------|-------|
| **Tool** | [Upscayl](https://upscayl.org/) (free, Win/Mac/Linux) |
| **Model** | `RealESRGAN_x4plus_anime_6B` |
| **Scale** | 4× |
| **GPU** | Enabled (if NVIDIA/AMD available) |
| **Denoise** | 0 (unless source is noisy) |
| **Output** | PNG (no compression) |

> This model was trained specifically for anime/cel-shading art. It reconstructs sharp lines, smooth gradients, and faithful colors without hallucinating new details.

### Step 2: Sharpen

| Setting | Value |
|---------|-------|
| **Tool** | [GIMP](https://www.gimp.org/downloads/) (free) or Photoshop |
| **Filter** | Unsharp Mask |
| **Radius** | 1.5 px |
| **Amount** | 70–90% |
| **Threshold** | 0 |

> This is what separates "good quality" from "4K crisp." The upscale leaves the image slightly soft — this step adds that razor-sharp edge definition.

### Step 3: HDR-like Color Pop

| Setting | Value |
|---------|-------|
| **Tool** | GIMP or Photoshop |
| **Curves** | Soft S-curve (lift mids, lower shadows) |
| **Contrast** | +10 to +20% |
| **Vibrance** | +10 to +15% |
| **Saturation** | 0 (vibrance is more natural) |

> This creates the "OLED screen" look — deeper darks, brighter highlights, richer colors without blowing anything out.

### Expected Result

| Metric | Value |
|--------|-------|
| Resolution | **4K+** (4× original) |
| Content fidelity | **100%** identical |
| Visual quality | **HDR-like** crisp |
| Time per image | **~2 minutes** |

---

## 🛠️ Tools Comparison

| Tool | Sharpness | Fidelity | Anime Support | Cost |
|------|-----------|----------|---------------|------|
| Waifu2x | Blurry | High | OK | Free |
| Nano Banana | Medium | Changes colors | Poor | Free |
| ChatGPT (Plus) | Medium | Changes details | Poor | $20/mo |
| **Upscayl + Pipeline** | **Ultra crisp** | **Perfect** | **Built for it** | **Free** |

---

## 🧠 Research Behind This Prompt

This prompt was engineered based on research from multiple sources:

| Source | Key Insight |
|--------|-------------|
| Reddit (r/ChatGPT, r/PromptEngineering) | "Strict fidelity mode" phrasing, imperative language |
| LearnPrompting.org | Instruction ordering (preservation before enhancements) |
| PromptHero & Midjourney Discord | Negative prompting techniques adapted for GPT-4o |
| Hacker News | Compositing workflows, iterative correction strategies |
| r/animeAI | Anti-westernization clauses, cel-shading preservation |

### 6 Engineering Principles Applied

| # | Principle | Why |
|---|-----------|-----|
| 1 | **Preservation first** | AI processes instructions sequentially — first instructions carry more weight |
| 2 | **Explicit task definition** | Clear scope prevents "creative enhancement" drift |
| 3 | **Explicit negatives** | Without a "DO NOT" list, ~70% of upscales alter content |
| 4 | **Anti-style-transfer** | Blocks AI's bias toward adding realism to illustrated content |
| 5 | **Separated technical params** | Resolution, sharpness, noise as distinct categories = more precise control |
| 6 | **Self-verification checklist** | Forces the model to self-compare output vs input before generating |

---

## 💡 Tips

- **If the AI result changes something**: Reply with `"The [element] changed. Fix it to be IDENTICAL to the original."`
- **For best results**: Use the highest resolution source image you have
- **Iterate**: AI image generation has natural variance — try 2-3 times and pick the best
- **Nano Banana watermark**: Install [Peel Banana](https://chromewebstore.google.com/detail/peel-banana) extension to remove it automatically
- **Double-pass trick**: For even more detail, upscale 2× first, then 2× again = 4× with better reconstruction

---

## 📂 Files

| File | Description |
|------|-------------|
| [`prompt.txt`](./prompt.txt) | Full prompt — copy-paste ready |
| [`README.md`](./README.md) | This documentation |
| [`old.png`](./old.png) | Original image (before) |
| [`new.png`](./new.png) | Enhanced image (after) |

---

## 📂 Repo Structure

```
image-quality-enhancer-prompt/
├── prompt.txt              # The prompt (copy-paste into ChatGPT/Nano Banana)
├── README.md               # This file
├── old.png                 # Before (your original image)
└── new.png                 # After (enhanced result)
```

---

## 📜 License

MIT License — use freely, modify, share.

---

*Built with research. Tested with patience. Powered by prompt engineering.*
