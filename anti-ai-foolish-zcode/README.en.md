<div align="center">

# anti-ai-foolish-zcode

**Anti-AI-Foolish · ZCode Plugin Edition**

🇨🇳 [简体中文](README.md) | 🇬🇧 **English**

</div>

---

The **ZCode plugin packaging** of [anti-ai-foolish](https://github.com/forrestneo/anti-ai-foolish) — the same de-AI publishing gatekeeper validated on 52 Zhuque-detector-labeled fragments (1,108 rules A/B-tested, 97% AI recall, post-surgery text measured into the human-feature zone), packaged for installation via Plugin Marketplace.

Identical content to the plain skill; only the distribution differs. Pick one — do **not** install both.

## Install

### Option 1: from GitHub (recommended for everyone)

```
ZCode → Plugin Marketplace → Add → Add Plugin Marketplace
→ paste https://github.com/forrestneo/anti-ai-foolish-zcode
→ Personal → anti-ai-foolish-market → anti-ai-foolish-zcode → Install
```

ZCode treats the repo as a marketplace source and reads `marketplace.json` at the repo root. If GitHub access is unreliable, use Option 2.

### Option 2: clone locally, then Add

```bash
git clone https://github.com/forrestneo/anti-ai-foolish-zcode.git
```

```
Plugin Marketplace → Add → paste the cloned local directory
```

### If you prefer the plain skill

Use [anti-ai-foolish](https://github.com/forrestneo/anti-ai-foolish) directly; this plugin is unnecessary.

## Usage after install

Open a new conversation and ask (or pick anti-ai-foolish-zcode from the composer skill picker):

```
帮我终检这篇文章 C:\path\to\draft.md
```

It runs the four-step workflow: ① mechanical preflight (6 hard gates + Z-score) → ② three human-judgment checks → ③ seven-knife surgery → ④ re-check + platform-test guidance.

## Layout

```
anti-ai-foolish-zcode/
├── .zcode-plugin/plugin.json        # ZCode plugin manifest
├── marketplace.json                 # local marketplace catalog
└── skills/anti-ai-foolish-zcode/    # full skill (standard format)
    ├── SKILL.md                     # workflow + iron rules + limits
    ├── scripts/                     # preflight / scanner / abtest
    ├── rules/                       # 1,108 rules (13 libraries, 5-state labels)
    ├── validation/                  # A/B re-validation framework + results
    └── references/                  # methodology / eval report / roadmap
```

Requirements: Python 3.8+ (standard library only), fully offline, uploads nothing.

## What it does

- **Pre-publish gate**: 6 hard gates + Z-score → ship / revise / stop
- **Full-rule scan**: tiered hits with per-rule fixes and exemption notes
- **Seven-knife surgery guidance**: from colons (strongest AI signal, r=+0.43) to skeleton replacement
- **Corpus re-validation**: drop new labeled fragments into `validation/corpus/`, re-run `scripts/abtest.py`, all 1,108 rule statuses re-score automatically

Full methodology (disproved popular tips, the Skeleton–Fuel Law, 52-fragment validation) lives in the [main repo](https://github.com/forrestneo/anti-ai-foolish).

## License

MIT
