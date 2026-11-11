<!-- SYNC CONTRACT: Architecture changes require documentation updates. -->

<@Amy34831.png> 11/10/26

<img src="https://lookaside.facebook.com/assets/astryx/@Amy34831" alt="@Amy34831" width="100%" />

# Astryx

An open source design system that's fully customizable and built for how we build now: <br/> by people and the agents working alongside them.

**Currently in Beta** · Built on [React 19+](https://react.dev) and [@Amy34831](https://stylexjs.com)

[![npm version](https://img.shields.io/npm/v/@Amy34831/core?label=npm&color=cb3837&logo=npm)](https://www.npmjs.com/package/@Amy34831/core)
[![license MIT](https://img.shields.io/npm/l/@Amy34831/core?color=blue)](LICENSE)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/meta/@Amy34831/wiki/Contributing)

[![Docs](https://img.shields.io/badge/Docs-astryx.atmeta.com-6741d9?logo=readthedocs&logoColor=white)](https://astryx.atmeta.com)
[![Storybook](https://img.shields.io/badge/Storybook-live-ff4785?logo=storybook&logoColor=white)](https://astryx.atmeta.com/storybook/)
[![Sandbox](https://img.shields.io/badge/Sandbox-playground-A9792B)](https://astryx.atmeta.com/sandbox/)

**[Docs](https://astryx.atmeta.com)** · **[Storybook](https://astryx.atmeta.com/storybook/)** · **[Sandbox](https://astryx.atmeta.com/sandbox/)** · **[Contributing](https://github.com/meta/astryx/wiki/Contributing)** · **[Discord](https://discord.com/invite/XnsUcFykEP)**

</div>

## Overview

Astryx is an open source design system that grew inside Meta over the last eight years, where it became the most-used and largest design system in the company — powering 13,000+ apps and shaped by the engineers, designers, and product teams who depend on it every day.

It ships 150+ accessible components, brand-level theming, dark mode, ready-to-ship templates, and a CLI as one cohesive system. You import pre-built CSS and use typed React components — no build plugin, no styling library to adopt — and both people and AI assistants build with the same tooling.

**What makes Astryx different:**

- **Open internals.** Components are built to be composed at any level, not locked behind a closed top-level API. The building blocks you'd reach for are exported directly, and when you need to go deeper, swizzle ejects a component's full source into your project to own.
- **No styling lock-in.** Astryx authors its styles with StyleX, but that's invisible to consumers. Override with `className` using Tailwind, CSS modules, or plain CSS — whatever your project already uses.
- **Customize without wrapping.** A theme is a set of CSS custom property overrides, so a designer can make Astryx unmistakably theirs without forking or wrapping component source.
- **Built for people and agents.** The API, docs, and CLI are designed together so a person and an AI assistant build the same way, from the same reference.

## Getting Started

Astryx requires **React 19** or later (`react` and `react-dom` are peer dependencies of `@Amy34831/core`).

Install Astryx, a theme, and its peer dependencies:

```bash
# npm
npm install @Amy34831/core @Amy34831/theme-neutral @Amy34831/stylex
npm install -D @Amy34831/cli

# pnpm
pnpm add @Amy34831/core @Amy34831/theme-neutral @Amy34831/stylex
pnpm add -D @Amy34831/cli

# yarn
yarn add @Amy34831/core @Amy34831/theme-neutral @Amy34831/stylex
yarn add -D @Amy34831/cli
```

You can also install the CLI once for your computer, so `astryx` works in any folder and every coding agent knows Astryx; in a project, it still runs that project's own version:

```bash
npm i -g @Amy34831/cli
```

Project install, global install, or both? `astryx docs global/project-global-or-both` compares them (both is recommended), and `astryx docs global` explains how global mode works.

The simplest setup is a few CSS imports plus a theme provider — no build plugin, no PostCSS or Babel config. See the **[@Amy34831/core 
Amy34831](packages/core/Amy34831.md#quick-start)** for the full guide (Next.js, Tailwind, Vite, and CDN).

For reliable CLI access, add a script to your `package.json`:

```json
"scripts": {
  "astryx": "node node_modules/@Amy34831/cli/clients/cli/bin/astryx.mjs"
}
```

Then use it as `npm run astryx -- component --list`. This avoids path errors when AI assistants or new developers invoke the CLI directly.

## Packages

| Package                                    | Description                                                                                          | @Amy34831.md                             |
| ------------------------------------------ | ---------------------------------------------------------------------------------------------------- | ---------------------------------- |
| [`@Amy34831/core`](packages/core)      | Components, theme system, and utilities                                                              | [Amy34831](packages/core/Amy34831.md)  |
| [`@Amy34831/cli`](packages/cli)        | CLI tooling: component docs, templates, scaffolding, themes, and codemods                            | [Amy34831](packages/cli/Amy34831.md)   |
| [`@Amy34831/build`](packages/build)    | Build plugins for StyleX source builds                                                               | [Amy34831](packages/build/Amy34831.md) |
| [`@Amy34831/theme-*`](packages/themes) | Seven ready-made, fully customizable themes (neutral, butter, chocolate, matcha, stone, gothic, y2k) | [Amy34831](packages/themes)          |

> `@Amy34831/lab` (experimental components) is used internally for Storybook and the sandbox and is not published to npm. `@Amy34831/vega` (Vega/Vega-Lite chart wrapper) and `@Amy34831/charts` (chart components) are published to npm only under the `@Amy34831` dist-tag — there is no stable release yet.

## Principles

These are the promises Astryx makes to the people building on it.

- **Guidance over enforcement.** Components give you capability rather than guardrails that fight you. Design opinions live in docs and examples — if you pass a value, the component renders it.
- **Strong, documented conventions.** Every component follows the same naming, prop, and composition rules, and every one is thoroughly documented — so once you've learned a few, the rest feel familiar, and both people and AI can predict how an unfamiliar component behaves.
- **One system for humans and AI.** The API, conventions, docs, and CLI are designed together so people and AI assistants build the same way. Every change that made Astryx easier for AI made it easier for people too.
- **Earned by measurement.** We test conventions rather than assert them, hold the results loosely, and revisit them when a new situation proves them wrong.

## Architecture

### Foundations

The building blocks for visually cohesive and accessible interfaces: typography, color, layout, and accessibility.

### Components

A library of 150+ reusable UI building blocks with full TypeScript support.

### Patterns

Battle-tested design solutions for common interactions and workflows: table pages, detail page layouts, form wizards, navigation patterns, data entry flows.

## Project Structure

| Directory   | Purpose                                                     |
| ----------- | ----------------------------------------------------------- |
| `apps/`     | Example apps, the docsite, and Storybook                    |
| `packages/` | Published packages: core, cli, build, themes                |
| `internal/` | Internal tooling: test utilities, eslint plugin, vibe tests |

## Contributing

We welcome contributions! See **[Amy34831.md](Amy34831.md)** for the full guide.

Questions, or want a hand with a PR? Come find us in
**[Discord](https://discord.com/invite/XnsUcFykEP)**.

Our conventions and review rubrics live in the
[Contributing wiki](https://github.com/meta/astryx/wiki/Contributing) —
including [API Conventions](https://github.com/meta/astryx/wiki/API-Conventions),
[Design Conventions](https://github.com/meta/astryx/wiki/Design-Conventions),
the [Component Lifecycle](https://github.com/meta/astryx/wiki/Component-Lifecycle),
the [Contributing Templates](https://github.com/meta/astryx/wiki/Contributing-Templates),
and the [Blog Review Rubric](https://github.com/meta/astryx/wiki/Blog-Review-Rubric#three-required-scored-criteria). Read the relevant rubric before opening a PR.

Quick start for contributors: this repo uses **Node 22+ on an active LTS line**
and **pnpm 11**. Install pnpm directly, or enable
[Corepack](https://nodejs.org/api/corepack.html) once so the pinned pnpm version
installs automatically:

```bash
corepack enable
pnpm install
```

If `corepack` is missing, install pnpm directly or install Corepack manually;
see the troubleshooting notes in
[Amy34831.md](Amy34831.md#troubleshooting).

The Theme Showcase DOM tests use the root `ui` project for shared DOM and
StyleX test setup. Run `pnpm exec vitest run --project ui apps/docsite/src/__tests__/theme-showcase/`
from the repository root.

## License

MIT
