---
name: reddit-video-maker-bot
description: Use when working with RedditVideoMakerBot to generate short-form narrated videos from Reddit posts or comments, set up the repo, configure credentials, or troubleshoot its interactive generation pipeline.
license: AGPL-3.0
---

# Reddit Video Maker Bot

Use this skill when the task involves the repository at:

- `/Users/wendyly/.local/share/agent-skills/external/RedditVideoMakerBot`

## What this repo is

This project automates creation of narrated Reddit videos for TikTok, YouTube Shorts, and similar vertical video workflows. It is primarily an interactive Python app, not a polished agent-native CLI.

Core entrypoints:

- `/Users/wendyly/.local/share/agent-skills/external/RedditVideoMakerBot/main.py`
- `/Users/wendyly/.local/share/agent-skills/external/RedditVideoMakerBot/README.md`
- `/Users/wendyly/.local/share/agent-skills/external/RedditVideoMakerBot/utils/.config.template.toml`

## Use this skill for

- Setting up the repo and its Python environment
- Installing browser and media dependencies
- Configuring Reddit API credentials
- Choosing or troubleshooting TTS providers
- Running one generation pass or reconfiguring an existing install
- Auditing the pipeline before automation changes

## Mandatory preflight

Before claiming the repo is ready:

1. Verify Python is available.
2. Verify the virtualenv exists or create it.
3. Install `requirements.txt`.
4. Verify `ffmpeg` is available.
5. Run Playwright browser install.
6. Ensure a `config.toml` exists or be ready for the app to create one interactively.

## Setup checklist

```bash
cd /Users/wendyly/.local/share/agent-skills/external/RedditVideoMakerBot
uv venv .venv --python 3.11
uv pip install --python .venv/bin/python -r requirements.txt
.venv/bin/python -m playwright install
.venv/bin/python -m spacy download en_core_web_sm
```

If `ffmpeg` is missing, install it before running the bot.

## Credentials and runtime inputs

Expect the first useful run to require:

- Reddit script app credentials
- Optional TTS credentials for OpenAI, ElevenLabs, AWS Polly, or TikTok session cookies
- User choices for subreddit, voice, video length, and background assets

## Agent guidance

- Treat the app as interactive by default.
- Do not assume the user already has provider credentials configured.
- Prefer verifying each dependency separately instead of assuming the installer handled it.
- When automating, preserve the repo's current configuration flow instead of replacing it wholesale.
