# Oasis Luxury Med Spa — UGC Video Generator

Automated UGC-style video creation for **Oasis Luxury Med Spa** (Pearland, TX) using n8n workflow automation.

## Overview

This n8n workflow generates short-form social media videos featuring AI-generated visuals and voiceovers tailored to med spa services — Botox, laser treatments, body contouring, skincare, and more.

## Pipeline

```
Form Input → AI Script Generation → AI Image → Text-to-Speech → Video Synthesis → Google Drive → Google Sheets Log
```

## Services Covered

- Laser treatments (Fotona 4D, SmoothEye)
- Microneedling (SkinPen, DNA treatments)
- Body contouring & skin tightening
- Botox & fillers
- Hair removal & restoration
- Weight loss solutions
- Massage services
- Professional skincare

## Business Details

- **Location:** 7930 Broadway Street Suite 116, Pearland, TX
- **Phone:** 832-295-3086
- **Website:** oasisluxurymedspa.com

## Setup

1. Import the workflow JSON into your n8n instance
2. Configure API credentials (Gemini, ElevenLabs, Hedra, Google Drive, Google Sheets)
3. Trigger via the form or webhook

## Tech Stack

- **n8n** — Workflow automation
- **Gemini Pro** — Script generation & image creation
- **ElevenLabs** — Text-to-speech
- **Hedra** — Video synthesis
- **Google Drive** — Video storage
- **Google Sheets** — Output logging
