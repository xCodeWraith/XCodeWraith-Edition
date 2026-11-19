# 🎬 Product-to-Social-Media AI Video Generator (2026 Edition)

[![n8n](https://img.shields.io/badge/Workflow-n8n-FF6D5A?style=for-the-badge&logo=n8n)](https://n8n.io)
[![Gemini](https://img.shields.io/badge/Model-Gemini%202.5%20Pro-4285F4?style=for-the-badge&logo=google)](https://deepmind.google/technologies/gemini/)
[![Kling AI](https://img.shields.io/badge/Motion-Kling%202.6-7928CA?style=for-the-badge)](https://klingai.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
![Status](https://img.shields.io/badge/Status-Production%20Ready-success?style=for-the-badge)

> **Enterprise-grade AI video automation pipeline that transforms a single static product photo into high-converting 9:16 social media ad reels (TikTok, Instagram Reels, YouTube Shorts).**

---

## 🚀 Key Features

*   **🔍 Multimodal Visual Analysis (Gemini 2.5 Pro):** Deconstructs product imagery, extracts brand identity, and writes narrative ad scripts tailored for engagement.
*   **🎥 Cinematic Motion Synthesis (Kling 2.6):** Converts static product photos into realistic video clips featuring professional camera movements (push-in, 360 orbit, smooth panning).
*   **🎵 Sound Design & Foley (Fal Audio v2):** Generates bespoke background audio, voiceovers, and ambient sound effects (ASMR, crisp commercial audio).
*   **✂️ Automated Assembly & Rendering (FFmpeg):** Combines visual clips, synchronizes audio, applies motion transitions, and exports high-definition 9:16 video.
*   **📱 Human-in-the-Loop Review (Telegram Bot):** Dispatches pre-rendered previews to your Telegram chat with quick-action approval buttons (`Approve & Publish` / `Regenerate`).

---

## ⚙️ System Architecture

```
┌─────────────────────────┐
│  Single Product Photo   │
└─────────────────────────┘
             │
             ▼
┌─────────────────────────┐       ┌─────────────────────────┐
│  Gemini 2.5 Pro Vision  │ ────> │  Fal.ai Audio Engine    │
│  Script & Prompt Gen    │       │  Ambient & Voiceover    │
└─────────────────────────┘       └─────────────────────────┘
             │                                 │
             ▼                                 │
┌─────────────────────────┐                    │
│  Kling 2.6 Motion       │                    │
│  Cinematic Video Render │                    │
└─────────────────────────┘                    │
             │                                 │
             └────────────────┬────────────────┘
                              │
                              ▼
               ┌─────────────────────────────┐
               │  FFmpeg Video Compositing   │
               │  Transitions, 9:16 Render   │
               └─────────────────────────────┘
                              │
                              ▼
               ┌─────────────────────────────┐
               │  Telegram Review & Approval │
               │  (Human-in-the-Loop)        │
               └─────────────────────────────┘
```

---

## 🛠️ Prerequisites & Credentials

To deploy this workflow in your n8n environment, configure credentials for:

1.  **Telegram Bot API:** Bot Token and Chat ID (for preview delivery and approval buttons).
2.  **Google Gemini API:** Access to `gemini-2.5-pro` model.
3.  **Fal.ai API Key:** For Kling 2.6 motion generation and Fal Audio synthesis.
4.  **ImgBB / S3 Storage:** Temporary image hosting endpoint for video model ingestion.

---

## 🚀 Quickstart Deployment

### Step 1: Import Workflow
1.  Download `product_video_workflow.json` from this repository.
2.  In n8n, navigate to **Workflows** → **Import from File**.

### Step 2: Configure Credentials
1.  Open the workflow canvas and locate the highlighted credential nodes.
2.  Input your respective API keys for Gemini, Fal.ai, and Telegram.

### Step 3: Trigger Execution
*   Send a product image URL or upload a file directly through the configured webhook or Telegram command:
    ```bash
    /generate [Product Name] [Image URL]
    ```
*   Receive the rendered preview in Telegram within ~90 seconds, review the draft, and confirm deployment.

---

**Developed & Maintained by:** [xCodeWraith DEV.](https://github.com/xCodeWraith)  
**License:** [MIT](LICENSE)
