# pi Extension Tutor

A guided pi skill for learning how to build pi extensions by creating a real project: **Workspace Sentinel**.

Workspace Sentinel starts as a tiny project-local extension that announces when it loads, then grows module by module into a useful workflow assistant with slash commands, custom tools, safety gates, state, UI, custom rendering, and package-ready structure.

## Who this is for

Use this if you want to learn how pi extensions work by building one yourself instead of reading API docs in isolation.

The tutor is intentionally interactive:

- It explains each concept briefly.
- It shows focused TypeScript examples.
- It gives you an exercise to implement in your own Workspace Sentinel extension.
- It reviews your files when you say you are done.
- It tracks your tutorial directory, current module, and experience level in local skill state.

The tutor does **not** normally write the tutorial code for you. If you ask for setup help, hints, step-by-step guidance, skipping, or auto-completion, it can help more directly.

## What you will build

The tutorial uses a project-local pi extension at:

```text
.pi/extensions/workspace-sentinel/index.ts
```

By the end, Workspace Sentinel can include:

- load notifications and lifecycle status
- a `/sentinel` slash command
- custom LLM-callable tools
- streaming scans with `pi.exec()`
- custom tool rendering
- bash and file-safety hooks
- input transformation and prompt/context injection
- branch-aware state reconstruction
- session metadata helpers
- custom UI/dashboard pieces
- package-ready distribution

## Learning path

### Phase 1: Extension Foundations

1. **Loadable Extension Shell** — create the first project-local extension and verify `/reload` discovers it.
2. **Slash Commands** — add a `/sentinel` command.
3. **Lifecycle Status** — show turn progress while the agent works.

### Phase 2: Custom Tools and Rendering

4. **First Custom Tool** — register a `sentinel_note` tool.
5. **Tool Actions, Enums, and Prompt Metadata** — expand the tool with actions and prompt guidance.
6. **Streaming Work and `pi.exec()`** — add a scan tool with progress updates.
7. **Custom Tool Rendering** — make tool calls/results display cleanly in pi.

### Phase 3: Event Hooks and Safety

8. **Bash Permission Gate** — intercept risky bash commands.
9. **Protected Paths** — guard sensitive/generated files.
10. **Input Transformation** — add a Sentinel-specific input shortcut.
11. **System Prompt and Context Injection** — add concise workspace policy context.

### Phase 4: State, Sessions, and Branching

12. **Branch-Aware State Reconstruction** — make state survive reloads/resumes/branch navigation correctly.
13. **Session Metadata** — name sessions or bookmark important points.
14. **Compaction and Tree Hooks** — preserve Sentinel context during compaction/tree flows.

### Phase 5: UI, Messages, and Distribution

15. **Custom UI Dashboard** — add an interactive dashboard.
16. **Widgets, Autocomplete, and Editor UX** — add lightweight UX enhancements.
17. **Custom Messages and Rendering** — emit custom rendered status/report messages.
18. **Package-Ready Distribution** — prepare the extension as an installable pi package.

## Installation

After this repository is published to GitHub, install it with:

```bash
pi install git:github.com/VMaston/pi-extension-tutor
```

Then reload pi and start the tutor:

```text
/reload
/skill:pi-extension-tutor
```

## Recommended tutorial setup

For best results, start pi from the directory where you want to build Workspace Sentinel. pi discovers project-local extensions from the current working directory.

Example:

```bash
mkdir -p ~/dev/workspace-sentinel-tutorial
cd ~/dev/workspace-sentinel-tutorial
pi
```

Then invoke:

```text
/skill:pi-extension-tutor
```

If the tutor does not have a valid tutorial directory recorded yet, it can offer to create the tutorial project structure and install local development dependencies for you.

## Local state

The skill keeps small per-user progress state in:

```text
skills/pi-extension-tutor/progress.json
```

That file should not be committed or published. It records only:

- tutorial directory
- current module hint
- experience level

The committed default state template lives at:

```text
skills/pi-extension-tutor/references/state_default.json
```

## Development

The skill content lives in:

```text
skills/pi-extension-tutor/
```

Package metadata is in:

```text
package.json
```

The package is discoverable by pi because `package.json` contains:

```json
{
    "keywords": ["pi-package"],
    "pi": {
        "skills": ["./skills"]
    }
}
```

## Security note

pi skills can instruct an agent to run commands or edit files. Review skill content before installing third-party skills or pi packages.
