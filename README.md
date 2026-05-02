# pi Extension Tutor

A guided pi skill for learning to build pi extensions through the Workspace Sentinel tutorial project.

## Install from GitHub

After publishing this repository, users can install it with:

```bash
pi install git:github.com/<your-github-user>/pi-extension-tutor
```

Or install a pinned tag:

```bash
pi install git:github.com/<your-github-user>/pi-extension-tutor@v0.1.0
```

Then reload pi and start the skill:

```text
/reload
/skill:pi-extension-tutor
```

## Development

The skill lives in:

```text
skills/pi-extension-tutor/
```

The default state template is committed:

```text
skills/pi-extension-tutor/state_default.json
```

Per-user progress is intentionally ignored and should not be committed:

```text
skills/pi-extension-tutor/state/progress.json
```
