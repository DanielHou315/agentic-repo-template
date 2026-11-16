<!--
  README guide (delete this comment once filled):
  - Title: the project's name, not a sentence. Short and searchable.
  - Tagline (the blockquote): one bold sentence with the words people search for. Say what it is,
    what it works with, and what it does without.
  - First paragraph: who it is for and what it lets them do, in plain words. Link the key terms.
  - Show it working (GIF or screenshot in docs/) before any install steps.
  - GitHub "About" panel, which search engines index:
      description: the tagline, ~150 characters, front-loaded with keywords
      topics:      10-20 lowercase tags (domain, language, ecosystem, synonyms people search)
      website:     the package page or docs site
  - Keep this file to what a newcomer needs. Detail goes in docs/ and is linked from here.
-->

# Repository Template

<!-- Badges (https://shields.io): version, downloads, license, runtime, CI. Keep it to one row. -->
[![license: <fill in>](https://img.shields.io/badge/license-<fill_in>-blue.svg)](LICENSE)

> **This is a simple template to create an AI-agent native codebase.**

<fill in: one paragraph. Who it is for, what it lets them do, and the one thing that makes it
different. Link the key terms on first mention.>

<p align="center">
  <img src="docs/<fill in: demo>.gif" width="600" alt="<fill in: describe what the demo shows>">
  <br>
  <em><fill in: one-line caption.></em>
</p>

<fill in: where it is published, e.g. "Published on <registry> as `<name>`.">

## Using This Template

1. Click **Use this template** on GitHub, or clone and re-init the history.
2. Fill in the title, badges, tagline and intro above, and `Repo Introduction`, `Repo Map` and
   `Commands` in [`AGENTS.md`](AGENTS.md).
3. Add a `LICENSE` and an `.envrc.example`.
4. Set the GitHub description, topics and website (see the comment at the top of this file).
5. Delete this section.

## Table of contents

- [Installation](#installation)
- [Quick start](#quick-start)
- [Features](#features)
- [Reference](#reference)
- [Compatibility](#compatibility)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

More detail lives in [`docs/`](docs/): <fill in: links to configuration, reference, and development docs>.

## Installation

<fill in: prerequisites in one sentence, e.g. "You need <runtime> ≥ <version>.">

<!-- One table row per platform or harness when there are several ways to install. -->
| Platform | Install |
|---|---|
| <fill in> | `<fill in>` |

Environment variables are loaded by [direnv](https://direnv.net); copy `.envrc.example` to
`.envrc`, fill it in, and run `direnv allow`.

## Quick start

```sh
# 1. <fill in: first step, with a comment saying what happens>
<fill in>

# 2. <fill in: check that it works>
<fill in>

# 3. <fill in: the first real use>
<fill in>
```

<fill in: what to try next, e.g. an example prompt or command.>

## Features

<!-- One short subsection per feature a user would look for. Link to docs/ for depth. -->

### <fill in: feature>

<fill in: two or three sentences and a minimal example.>

## Reference

<!-- The commands, tools, endpoints or options, grouped, one line each. Full detail in docs/. -->

**<fill in: group>**

| Name | Purpose |
|---|---|
| `<fill in>` | <fill in> |

## Compatibility

<!-- What it runs on or works with. Use footnotes for caveats instead of long cells. -->

| | **<fill in>** | **<fill in>** |
|---|---|---|
| Versions | <fill in> | <fill in> |
| <fill in: capability> | ✅ | — ¹ |

¹ <fill in: caveat.>

## Contributing

Issues and pull requests are welcome on [GitHub](../../issues).

```sh
<fill in: one line that installs, checks, tests and builds>
```

Humans and agents follow the same rules, kept in [`AGENTS.md`](AGENTS.md): one branch and worktree
per change, test first, merge through PRs. Releases follow [Semantic Versioning](https://semver.org)
and are tagged `vX.Y.Z`; release notes are in the [changelog](CHANGELOG.md).

## License

[<fill in>](LICENSE)<fill in: optional reason, e.g. inherited from a ported dependency.>

## Acknowledgements

<fill in: projects this builds on or borrows from, with links. The Engineering Principles in
`AGENTS.md` are adapted from [Karpathy-inspired coding guidelines](https://github.com/forrestchang/andrej-karpathy-skills).>

<fill in, if relevant: "This project is not affiliated with <trademark owner>.">
