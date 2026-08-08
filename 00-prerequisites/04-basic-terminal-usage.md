# Basic Terminal Usage

## Overview

You don't strictly need the terminal to write HTML, but every real front-end workflow — running a local dev server, using Git, installing a static site generator — goes through it. This lesson covers the minimum fluency needed before the rest of the curriculum.

## Why It Matters

Later modules (static site generators in [11-tools-and-workflow](../11-tools-and-workflow/README.md), deployment in the real-world projects) all assume comfort typing and running shell commands.

## Core Concepts

### Navigating and managing files

```bash
pwd                    # print current directory
ls -la                  # list contents, including hidden files
cd my-site               # change directory
mkdir images               # create a directory
touch index.html             # create an empty file
```

### Serving HTML locally

Opening an `.html` file directly (`file://...`) works for simple pages, but breaks features that require a real server (fetch requests, some module scripts, service workers). A tiny local server fixes this:

```bash
npx serve .              # serves the current directory at http://localhost:3000
# or, with Python installed:
python3 -m http.server 8000
```

### `PATH` and command availability

If a command like `serve` or `tidy` says "command not found," it's usually a `PATH` issue — the tool exists but the shell doesn't know where to look for it.

```bash
echo $PATH
```

## Common Pitfalls

- Debugging a page that "isn't working" when opened via `file://`, when the real issue is a feature that needs an actual HTTP server.
- Running commands from the wrong folder — always confirm with `pwd` first.
- Forgetting that global npm-installed tools need Node's global bin directory on `PATH`.

## Key Takeaways

- `pwd`, `ls`, `cd`, `mkdir`, `touch` cover nearly all day-to-day navigation.
- Some HTML features silently fail under `file://` — serve locally (`npx serve`, `python3 -m http.server`) when in doubt.
- "Command not found" is almost always a `PATH` problem, not a missing installation.
