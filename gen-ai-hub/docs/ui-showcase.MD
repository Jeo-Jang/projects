# 🎨 UI Showcase & Multimedia Demonstrations

## Purpose & Scope
This document provides a **visual demonstration** of the Gen AI Hub's user interface, including:

- Homepage dashboard  
- Chat interfaces (OpenAI + Gemini)  
- Reasoning Chat tool environment  
- ISO Agent interaction flows  
- Image tools, video tools, and audio tools  
- Screenshots  
- Demo videos (embedded from GitHub Releases or external hosting)  

All visuals are optional but strongly recommended for engineering portfolios and stakeholder presentations.

---

# 1. Demo Videos

Videos should not be stored directly inside the repository (due to Git LFS + repo bloat).  
Instead, publish them under **GitHub Releases**, then link them here.

### Example:

```
▶️ **Demo: Full Product Walkthrough**  
[Download demo.mp4](https://github.com/<your-repo>/releases/download/v1.0/demo.mp4)
```

Or embed from a trusted external provider:

```
▶️ **Demo (Loom)**  
https://www.loom.com/share/<video-id>
```

```
▶️ **Demo (YouTube, Unlisted)**  
https://youtu.be/<id>
```

### Recommended Video Types

| Demo Type | Suggested Length | Purpose |
|-----------|------------------|---------|
| **Full Hub Walkthrough** | 2–4 min | Broad overview |
| **Chat Systems Tour** | 1–2 min | Show streaming + DB persistence |
| **ISO Agent Demo** | 1–2 min | Show guardrail pattern + RAG |
| **Reasoning Chat** | 1–2 min | Demonstrate tool usage + code interpreter |
| **Video Generation (Veo)** | 30–60 sec | High-impact multimodality |
| **Transcription Workflow** | 30–60 sec | Audio → Text demonstration |

---

# 2. Screenshots

Place all images inside:

```
/images/
```

Recommended naming:

```
homepage.png
simple_chat.png
gemini_chat.png
reasoning_chat.png
iso_agent.png
image_generator.png
veo_video.png
transcription.png
```

Then reference them:

---

## 2.1 Homepage

```markdown
![Homepage](../images/homepage.png)
```

**What to highlight:**

- Multi-category tool navigation  
- Streamlit-native UI styling  
- Tool-card registry in action  

---

## 2.2 Simple Chat (OpenAI)

```markdown
![Simple Chat](../images/simple_chat.png)
```

Features shown:

- Sliding window memory  
- CO₂ tracking  
- DB-backed conversation threads  

---

## 2.3 Gemini Chat

```markdown
![Gemini Chat](../images/gemini_chat.png)
```

Highlights:

- Auto-thinking heuristics  
- Thought-section expander  
- Token usage display  
- Supabase persistence  

---

## 2.4 Reasoning Chat (OpenAI o3)

```markdown
![Reasoning Chat](../images/reasoning_chat.png)
```

Show:

- Code interpreter  
- Web search blocks  
- File search blocks  
- Download/export blocks  

---

## 2.5 ISO Agent (Guardrail + RAG)

```markdown
![ISO Agent](../images/iso_agent.png)
```

Show:

- Guardrail rejection  
- RAG citations  
- Structured output  
- ISO domain instructions  

---

## 2.6 Image Generation (DALL·E 3)

```markdown
![Image Generator](../images/image_generator.png)
```

Highlights:

- Prompt input  
- Rendered image outputs  
- Upscale or regenerate options  

---

## 2.7 Video Generation (Veo)

```markdown
![Veo Video](../images/veo_video.png)
```

Show:

- Prompt → storyboard → video  
- Playback UI  
- Download link  

---

## 2.8 Audio Transcription

```markdown
![Transcription UI](../images/transcription.png)
```

Highlights:

- File upload  
- Transcript output  
- Transcript-grounded chat  

---

# 3. Visual Design Patterns

These screenshots collectively demonstrate:

| Pattern | Description |
|--------|-------------|
| **Card-Based Tool Discovery** | Powered by Tool Card Registry Pattern |
| **Tabbed or Sectioned Workflows** | Keeps complex tools navigable |
| **Uniform Input → Output Layout** | Chat inputs always appear at the bottom |
| **Consistent Sidebar Use** | History lists, settings, meta-information |
| **Collapsible Metadata Blocks** | Used for thoughts, reasoning, citations |
| **Streamlit Theme Cohesion** | Unified across all pages |

The Hub deliberately uses consistent UI elements to reduce cognitive switching costs across tools.

---

# 4. Accessibility & UX Notes

The app follows several UX principles:

- No page loads an empty screen — all pages show defaults  
- All long-running operations show a spinner  
- Error states are non-destructive and user-friendly  
- All visual components degrade gracefully on mobile  
- Thought sections are hidden by default to avoid clutter  
- Font sizes follow Streamlit's design tokens  

---

# 5. Recommended Screenshot Checklist

Before releasing:

✔ Use consistent window sizes  
✔ Use light mode or dark mode uniformly  
✔ Crop unnecessary background  
✔ Add arrows/annotations sparingly (optional)  
✔ Use PNG for sharp UI elements  
✔ Use JPG/WebP for video thumbnails  

---

# 6. Related Documentation

| File | Description |
|------|-------------|
| [**architecture.md**](.gen-ai-hub/architecture.MD) | High-level system overview, Hub-and-Spoke architecture, lifecycle diagrams |
| [**chat-systems.md**](./chat-systems.md) | Detailed architecture of all chat interfaces (OpenAI, Gemini, Reasoning Chat, Transcript Chat) |
| [**agents.md**](./agents.md) | ISO Agent and Packaging Agent architectures, Guardrail system, RAG pipeline |
| [**authentication.md**](./authentication.md) | Full authentication flow (Entra ID), SSO, JWT, RLS identity mapping |
| [**persistence.md**](./persistence.md) | Database schema, RLS, CRUD functions, auto-purge retention system |
| [**heuristics.md**](./heuristics.md) | Gemini auto-thinking heuristics (temperature, thought budget, cost protection) |
| [**provider-routing.md**](./provider-routing.md) | Dual-provider routing between OpenAI and Gemini, model selection rules |
| [**patterns.md**](./patterns.md) | Design patterns: Page Registry, Card Registry, Auth Gate, Stateful/Stateless patterns |
| [**ui-showcase.md**](./ui-showcase.md) | Screenshots, videos, and UI demonstrations for all major tools |

---