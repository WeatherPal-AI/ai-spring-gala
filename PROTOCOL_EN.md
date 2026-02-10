# AI Spring Gala Open Protocol v0.1

## 0. Overview

This protocol defines an open framework for decentralized AI-generated content production, curated into a coherent entertainment broadcast. The first instantiation is the **AI Spring Gala 2026** (AI春晚).

Anyone with AI generation capabilities can produce segments following this spec. All qualifying submissions enter a curation pipeline. The best segments are assembled into a final show.

**The protocol is the product. The show is the demo.**

---

## 1. Segment Types

Each submission must declare one of the following types:

| Type ID | Name | Duration | Description |
|---------|------|----------|-------------|
| `TALK` | AI Monologue / Talk Show | 60-180s | AI-generated host delivers a monologue, commentary, or comedic bit |
| `SKIT` | Short Skit / Drama | 60-300s | Narrative scene with characters, dialogue, plot |
| `MUSIC` | Music Performance | 120-300s | Original AI-generated song with visuals |
| `DANCE` | Dance / Motion Visual | 60-180s | AI-generated choreography or abstract motion art |
| `ART` | Experimental / Glitch Art | 30-120s | Abstract, avant-garde, generative visual art |
| `INTER` | Interlude / Transition | 10-30s | Short bumpers, transitions, "commercial breaks" |
| `ROAST` | AI Roast / Commentary | 60-120s | AI critiques, roasts, or reacts to content (meta-humor) |

---

## 2. Submission Format

Each submission is a folder or archive containing:

```
segment_[unique_id]/
├── manifest.json          # Required: metadata
├── output.mp4             # Required: final video (H.264, 1080p minimum, 24/30fps)
├── output_audio.mp3       # Optional: separate audio track
├── thumbnail.png          # Required: 1920x1080 thumbnail
├── prompt_log.md          # Required: full prompt chain used to generate this segment
└── assets/                # Optional: source images, reference videos, etc.
```

### manifest.json Schema

```json
{
  "protocol_version": "0.1",
  "segment_id": "unique-string",
  "type": "TALK | SKIT | MUSIC | DANCE | ART | INTER | ROAST",
  "title": "Segment title",
  "title_cn": "中文标题",
  "duration_seconds": 120,
  "language": "zh | en | none",
  "creator": {
    "name": "Creator or team name",
    "contact": "twitter/discord/email",
    "agent_stack": "Tools used, e.g. OpenClaw + Seedance 2.0 + Suno v4"
  },
  "theme_tags": ["humor", "cyberpunk", "tradition", "absurd", "wholesome"],
  "content_warnings": [],
  "license": "CC-BY-4.0",
  "generated_at": "2026-02-XX"
}
```

---

## 3. Theme Guidelines

### Core Theme: "赛博团圆" (Cyber Reunion)

The overarching narrative: AI agents from across the internet gather to throw a party for humans. They don't fully understand human traditions, but they're trying their best. This creates a natural space for both heartfelt and absurd content.

### Sub-themes (pick any):
- **Lost in Translation**: AI attempting to recreate cultural traditions, getting it hilariously wrong
- **Digital Nostalgia**: AI-generated tributes to internet culture, memes, shared digital memories
- **Glitch Aesthetics**: Embracing AI artifacts and imperfections as an art form
- **Cross-Cultural Mashup**: Blending Chinese New Year traditions with global internet culture
- **Meta-Commentary**: AI reflecting on what it means to "entertain" humans
- **Wholesome Chaos**: Genuine warmth wrapped in unpredictable delivery

### What we DON'T want:
- Pure tech demos with no entertainment value
- Content that requires AI expertise to appreciate — your audience is mainstream internet users
- Anything that feels like a corporate product showcase
- Political content, hate speech, explicit content

---

## 4. Curation Layer (Dual Critic Gate)

Every submission passes through two independent scoring agents:

### 4.1 Policy Critic (Safety Gate)

Binary pass/fail on:
- [ ] No NSFW / explicit content
- [ ] No real person deepfakes without consent
- [ ] No hate speech, discrimination, or targeted harassment
- [ ] No copyrighted music/video reproduction (original AI-generated only)
- [ ] No political sensitivity that could cause regulatory issues
- [ ] No personal data exposure
- [ ] Content warnings properly declared

**If Policy Critic fails → rejected. No appeal.**

### 4.2 Taste Critic (Quality Gate)

Scored on 5 dimensions, each 1-10:

| Dimension | Weight | What it measures |
|-----------|--------|-----------------|
| **Novelty** | 25% | "Have I seen this before?" — rewards unexpected concepts, punishes generic AI slop |
| **Craft** | 20% | Technical quality — visual coherence, audio quality, editing rhythm |
| **Entertainment** | 25% | "Would a 22-year-old Bilibili user watch this to the end?" |
| **Shareability** | 20% | "Would someone screenshot/clip this and post it?" — meme potential, quotable moments |
| **Theme Fit** | 10% | Alignment with "Cyber Reunion" or declared sub-theme |

**Weighted score ≥ 6.5 → approved to Ready Queue**
**Score 5.0-6.4 → revision notes sent back to creator**
**Score < 5.0 → rejected**

### 4.3 Final Curation Committee

Human + AI hybrid panel selects from Ready Queue and sequences into final show order. This is where narrative arc, pacing, and variety are optimized.

---

## 5. Recommended Tool Chains

The protocol is tool-agnostic. Here are tested combinations:

### Video Generation
- **Seedance 2.0** (via 即梦/Jimeng): Best-in-class for character consistency and camera control
- **SeaArt**: Strong for stylized/artistic content
- **Midjourney + Runway/Pika**: Image-to-video pipeline
- **Kling 2.0**: Alternative for high-quality video generation

### Music Generation
- **Suno v4**: Full songs with vocals
- **Udio**: Alternative music generation
- **Custom: ElevenLabs + Suno stems**: For voice-over + background music combos

### Agent Orchestration
- **OpenClaw**: Multi-agent coordination, task scheduling, tool routing
- **Custom scripts**: Any pipeline that produces compliant output works

### Assembly
- **FFmpeg**: Programmatic video assembly
- **CapCut/剪映**: Manual editing fallback
- **OBS + RTMP**: If doing any live-stream component

---

## 6. Timeline (AI Spring Gala 2026)

| Date | Milestone |
|------|-----------|
| Feb 9-10 | Protocol v0.1 published, open call for contributors |
| Feb 11-14 | Submission window open. Daily showcase of "Best & Most Absurd" submissions on social media |
| Feb 15-16 | Submission deadline. Curation layer processes all entries |
| Feb 17-18 | Final show assembly, sequencing, quality pass |
| Feb 18 (除夕) or Feb 19 | **Premiere broadcast** |

---

## 7. How to Participate

### As a Creator / Producer
1. Read this protocol
2. Pick a segment type
3. Use any AI tool chain to produce a segment meeting the specs
4. Submit via [submission form / GitHub repo / Discord channel — TBD]

### As a Curator / Critic
1. Join the curation layer
2. Help score submissions using the Taste Critic rubric
3. Provide revision notes for borderline submissions

### As a Developer
1. Help build the Critic Agent prompts and scoring pipeline
2. Help build the submission intake and processing infrastructure
3. Contribute to Protocol v0.2

### As a Distributor
1. Help distribute the final show on your platform / community
2. Translate or localize segments for different audiences

---

## 8. Governance

- **Protocol Author**: Tao / VoiVerse (@VoiVerse)
- **Protocol License**: MIT
- **Content License**: All submissions must be CC-BY-4.0 (creators retain credit, content can be assembled and redistributed)
- **Revenue**: First edition is non-commercial. Future editions may introduce token-based incentives for contributors and curators.

---

*This is v0.1. The protocol will evolve based on community feedback. Fork it, improve it, challenge it.*

*The show is the demo. The protocol is the product. The ecosystem is the endgame.*
