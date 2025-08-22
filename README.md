# DAAF - Digital Augmentation & Application Factory

Monorepo for the DAAF website and Sanity Studio.

- **web/** – SvelteKit static site (Tailwind v4, mdsvex)
- **studio/** – Sanity Studio (content authoring)
- Deploy target: **Netlify** for `web/` (configured via `netlify.toml` at repo root)

## Requirements

- Node **v24.6.0**
- npm **11.5.1**
- Git

Optionally, use **nvm** or **Volta** to pin versions.

```bash
# nvm (recommended)
nvm install 24.6.0
nvm use 24.6.0
node -v && npm -v
```

## Repo structure

```md
DAAF/
├─ web/            
├─ studio/         
├─ .editorconfig
├─ .gitattributes
├─ .gitignore
├─ .nvmrc
├─ .npmrc
├─ .prettierrc.json
├─ .prettierignore
├─ netlify.toml
├─ package.json
├─ README.md
└─ .vscode/
   └─ extensions.json
```

## Getting started

```bash
# Clone and enter
git clone <your-repo-url> DAAF
cd daaf

# Pin Node
nvm use 24.6.0  # or install first if needed

# Install (will prepare workspaces)
npm install
```

### Useful scripts (from repo root)

```bash
npm run web:dev      # (Step 2 will wire SvelteKit dev)
npm run web:build    # (Step 2 will produce static site to web/build)
npm run web:preview

npm run studio:dev   # (Step 2 will run Sanity Studio)
npm run studio:build
```

## Netlify

`netlify.toml` is set to build from the `web/` workspace and publish its `build/` folder.

- **Base**: `web`
- **Publish**: `build`
- **Command**: `npm run build`
- **Environment**: `NODE_VERSION=24.6.0`, `NPM_VERSION=11.5.1`

> In Step 2, we’ll add the SvelteKit app (adapter-static) and mdsvex setup inside `web/`.

## Conventions

- LF line endings enforced via `.gitattributes`
- 2-space indentation via `.editorconfig`
- Code formatting via Prettier (`npm run format`)
