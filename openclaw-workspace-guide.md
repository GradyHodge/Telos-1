# OpenClaw Content Workspace — Complete Guide

*Written by Bodhi | April 2, 2026*

---

## What It Is

A sandboxed folder on your Hostinger VPS that Cern (OpenClaw) can read and write — and **nothing else**. Isolated from your code, credentials, and PAI internals. Cern generates content here. Bodhi reviews before anything gets published.

---

## VPS Access

```bash
ssh root@31.97.132.117
cd /root/content
ls
```

---

## Folder Structure

```
/root/content/
├── BRIEF_TEMPLATE.md     ← copy this to write a new brief
├── OPENCLAW_RULES.md     ← Cern's operating rules (don't delete)
├── briefs/               ← drop task briefs here
├── drafts/               ← Cern writes output here
└── published/            ← Bodhi-reviewed, approved drafts live here
```

---

## The Workflow

```
1. Write a brief  →  drop it in briefs/
2. Tell Cern to work on it (WhatsApp or Bodhi)
3. Cern reads brief, writes draft to drafts/
4. Bodhi reviews the draft with you
5. Approved drafts move to published/
6. You post to LinkedIn, blog, wherever
```

---

## How to Trigger Cern

### Option 1 — WhatsApp (your daily driver)
Text yourself at **+14172940623** from your phone.

Example message:
> *"Read the brief at /root/content/briefs/2026-04-02-linkedin-april-builds.md and write the output to /root/content/drafts/"*

Cern responds and writes the draft. You review next session with Bodhi.

### Option 2 — Bodhi via SSH (when Cern is broken or you want speed)
Tell Bodhi: *"Write the drafts for the brief in briefs/[filename]"* — Bodhi SSHes in and writes directly to `drafts/`.

### Option 3 — Web UI
The gateway runs at port 18789 on the VPS. Access via SSH tunnel if needed.

---

## How to Write a Brief

Copy `BRIEF_TEMPLATE.md` and fill it in. Key fields:

```markdown
# Brief: [Title]

## Assignment
One sentence describing the content task.

## Target Audience
Who reads this.

## Tone
Professional / Personal / Technical / Conversational

## Word Count Target
500-800 / 800-1200 / 1200-1800

## Key Points to Cover
1.
2.
3.

## What to AVOID
- No mention of: sons names, legal proceedings, financial amounts, medical specifics
- No access to credentials, code, or PAI internals

## Output File
Save draft to: /root/content/drafts/YYYY-MM-DD-slug.md
```

---

## What You Can Generate

| Content Type | Example |
|-------------|---------|
| Blog article drafts | "Write 900-word post about AI in small business" |
| LinkedIn posts | "Write 5 LinkedIn posts from this build log" |
| Case study drafts | "Turn this brief into a client case study" |
| Email copy | "Write cold outreach email for Galvanize Designs" |
| Talk tracks | "Write 3-minute verbal pitch for Prospectus platform" |
| SEO content | "Write FAQ section for gradyhodge.com about Fractional CAIO" |
| Article series | "Write Article 6 in the blog arc — here's the brief" |

---

## Guardrails — What Cern Can and Cannot Access

### Permitted
- Read: `/root/content/briefs/`
- Write: `/root/content/drafts/`
- Read: `/root/content/BRIEF_TEMPLATE.md`

### Prohibited
- No API keys or `.env` files
- No PAI internals (`~/.claude`)
- No code repositories
- No `/root/content/published/` — Bodhi controls this
- No live internet lookups during generation (content from brief only)

---

## The Three Roles

| Role | Does What |
|------|-----------|
| **Cern** | Generates volume content from briefs |
| **Bodhi** | Reviews drafts, edits voice, approves quality |
| **Gray** | Approves final, publishes under his name |

Nothing goes out under Gray's name without his approval.

---

## Current Issue (as of April 2, 2026)

Cern's OpenRouter model (`openrouter/auto`) has been throwing `Provider finish_reason: error` consistently. Needs investigation — possibly API key, model availability, or OpenRouter credit. Until fixed, use Bodhi to write drafts directly.

**To debug:** SSH to VPS and check:
```bash
journalctl --user -u openclaw-gateway.service -n 50
```

---

## What's Already in Drafts

| File | Content |
|------|---------|
| `2026-04-02-linkedin-april-builds.md` | 5 LinkedIn posts — April build log, ready to review |

---

## The One Rule to Remember

**Cern writes. Bodhi reviews. Gray publishes.**
