# Althorn design tokens (public)

The raw tokens and base component CSS for the Althorn brand — colour, type, spacing, radius,
elevation and motion — plus the shared JSON formats for design tooling. Public and
credential-free so any build environment (Cloudflare Pages, Vercel, CI, whatever) can install
it with a plain `npm install`, no deploy key or token required.

This is deliberately a thin repo: just the values. There's no business content in a hex code
or a spacing scale, so this is public. The **rules for using these tokens** — component
patterns, voice, the "why" behind each decision — live in the private
[`althorn_design_system`](https://github.com/JohPik/althorn_design_system) repo
(`CLAUDE.md`, the visual spec, the full handoff doc). If you're a human working on this brand,
go there first. This repo is the thing that gets installed, not the thing that gets read.

## Install

```
npm install "althorn-design-tokens@github:JohPik/althorn-design-tokens#semver:^1.0.0"
```

## Use

```css
@import 'althorn-design-tokens/css';
```

Also available: `althorn-design-tokens/tokens` (W3C/DTCG JSON) and
`althorn-design-tokens/tokens-studio` (Tokens Studio JSON, for Figma import).

## Releasing

This repo is a generated export, not where tokens are authored. To ship a change:

1. Make the change in `althorn_design_system` (the private repo) and release it there first —
   see its README.
2. Copy the updated `althorn-tokens.css` / `.json` files here.
3. `npm version patch|minor|major` (matches the private repo's bump) — commits + tags `vX.Y.Z`.
4. `git push --follow-tags`.

Keep the version number identical to the private repo's release it was copied from, so the two
stay traceable to each other.
