# Oasis Luxury Med Spa — UGC Video Generator

Automated UGC-style video creation for **Oasis Luxury Med Spa** (Pearland, TX) using n8n workflow automation.

## Overview

This n8n workflow generates short-form social media videos featuring AI-generated visuals and voiceovers tailored to med spa services — Botox, laser treatments, body contouring, skincare, and more.

## Pipeline

```
Form Input → Avatar Selection → AI Script Generation → AI Image → Text-to-Speech → Video Synthesis → Google Drive → Google Sheets Log
```

## Avatar System

**30 diverse AI avatars** (28 female + 2 male) spanning ages 21–50, each with unique appearance, personality, and matched ElevenLabs voice.

- **Age range:** 21–50 years old
- **Ethnicities:** Hispanic/Latina, African American, Caucasian, East Asian, Middle Eastern, Mixed Race, South Asian, Brazilian, Japanese, Somali-American, Colombian, North African/Arab, Mexican-American, West African, Greek, Korean-American, Persian, Biracial, Eastern European, Ethiopian, Italian, Puerto Rican
- **Roles:** Aestheticians, Specialists, Directors, Consultants, Technicians, and more
- **Selection:** Choose a specific avatar or use "Auto-Rotate (Surprise Me)" for variety
- **Full catalog:** See `avatars.json` for complete avatar details

### ElevenLabs Voices (9 total)

| Voice | Style | Assigned To |
|-------|-------|-------------|
| Rachel | Warm, professional | Isabella, Mei, Yuki, Layla |
| Bella | Soft, elegant | Sienna, Olivia, Elena, Destiny |
| Elli | Young, friendly | Madison, Aria, Camila, Aaliyah, Luna, Mia, Zara |
| Domi | Strong, assertive | Fatima, Daria, Amara |
| Charlotte | Warm, sophisticated | Jasmine, Priya, Harper, Natasha |
| Dorothy | Calm, pleasant | Naomi, Victoria, Keiko |
| Lily | Warm, motherly | Sofia, Aisha, Valentina |
| Adam | Deep, authoritative | Marcus |
| Antoni | Warm, well-rounded | Daniel |

## Form Fields

| Field | Options |
|-------|---------|
| Avatar Selection | Auto-Rotate or pick from 30 avatars |
| Video Type | Call to Action, Tips & Education, Before & After, Service Spotlight |
| Topic/Service | 14 med spa services |
| Video Length | 5s, 10s, 15s |
| Custom Message | Optional override for AI-generated script |
| Background Style | 6 options (4 generic + 2 Oasis branded) |

## Background Styles

- Luxury Spa Interior (Soft Lighting)
- Clean Clinical (Modern White)
- Elegant Treatment Room
- Neutral Studio (Soft Glow)
- **Oasis Branded (Gold Logo Center)** — Features the Oasis gold teardrop logo
- **Oasis Branded (Logo Watermark Corner)** — Subtle branded watermark

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

## Project Structure

```
├── oasis_medspa_ugc_workflow.json   # Main n8n workflow (import this)
├── avatars.json                     # Full 30-avatar catalog with voice mappings
├── assets/
│   └── logos/
│       ├── oasis_logo_vertical.jpg  # Stacked logo (teardrop above text)
│       └── oasis_logo_horizontal.png # Side-by-side logo (teardrop left of text)
└── README.md
```

## Setup

1. Import `oasis_medspa_ugc_workflow.json` into your n8n instance
2. Configure API credentials (Gemini, ElevenLabs, Hedra, Google Drive, Google Sheets)
3. Replace placeholder IDs: `YOUR_GOOGLE_DRIVE_FOLDER_ID` and `YOUR_GOOGLE_SHEET_ID`
4. Add Google Sheets columns: Timestamp, Character, Gender, Age, Role, Ethnicity, Avatar Selection, Video Type, Topic, Script, Duration (sec), Background, Filename, Drive URL, Status
5. Trigger via the form or webhook

## Tech Stack

- **n8n** — Workflow automation
- **Google Gemini** — Script generation & image creation (photorealistic avatars)
- **ElevenLabs** — Text-to-speech (9 voice profiles)
- **Hedra** — Video synthesis (talking head)
- **Google Drive** — Video storage
- **Google Sheets** — Output logging
