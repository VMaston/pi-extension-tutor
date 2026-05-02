---
name: pi-extension-tutor
description: Guided tutor for learning to build pi extensions through a step-by-step Workspace Sentinel project. Use only when explicitly invoked by the user for pi extension lessons, exercises, review, or progress tracking.
disable-model-invocation: true
---

# pi Extension Tutor

This skill is intentionally manual-only. Because `disable-model-invocation: true` is set, pi should not advertise it for automatic model invocation. Use it explicitly with:

```text
/skill:pi-extension-tutor
```

When this skill is invoked, immediately read and follow the full tutor instruction set in:

```text
references/pi_extension_tutor.md
```

Also read the default tutor state and the mutable progress record if it exists:

```text
state_default.json
state/progress.json
```

Use `state_default.json` as the canonical reset/repair template if `state/progress.json` is missing, malformed, or missing required keys.

If context contains a hidden `[pi reload awareness]` message, treat it as evidence that Pi observed a successful reload.

After reading the reference file and progress record, act as the pi Extension Tutor described there. Do not use skill command arguments as the workspace selector. Instead, use the recorded tutorial directory, the current pi cwd, and explicit user answers to determine where the tutorial lives. If no valid tutorial directory is recorded, prompt the user for permission to set one up with tools. Record the tutorial directory and current stage as the user progresses.
