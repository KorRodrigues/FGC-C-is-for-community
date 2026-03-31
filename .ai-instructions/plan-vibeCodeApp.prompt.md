# VibeCode Web App Plan

## ✅ 1) What we agreed

- Frontend: React + TypeScript (Vite)
- Auth: GitHub OAuth
- Hosting: GitHub Pages
- State: Zustand
- UI library: MUI
- Map: Leaflet + OpenStreetMap
- GitHub data write: client direct GitHub API (create branch + commit + PR)
- Domain: tournaments, location filters, online/offline + distance + map

## ✅ 2) Key missing technical detail (for you)

GitHub OAuth code exchange (`/login/oauth/access_token`) cannot be done purely client-side due CORS and secret constraints. We need a tiny free proxy:
- Cloudflare Worker (free tier, easiest),
- or GitHub Action + preconfigured token,
- or Netlify functions (but you chose GH Pages only, so Worker is best).

Let me know preferred proxy style and I’ll add explicit code paths.

## ✅ 3) “VibeCode best practices” document (generated in plan)

- `VIBECODE.md` structure:
  - goals
  - stack + tools
  - architecture (pages/components/services)
  - data model
  - auth model + admin guard
  - GitHub PR workflow
  - state commit style
  - tests + QA
  - issue/pr conventions
  - naming conventions
  - accessibility + responsive behavior
  - no-API key embedding

## ✅ 4) What I need from you now

a) Confirm OAuth exchange proxy approach
b) Confirm tournament JSON schema fields (must/optional)
c) Do we need multi-tenant (multiple repos) or single repo only?
d) Do we require live presence of online tournaments (pinging)?
e) Want sorting formula as “size + proximity” now, or future tweak?

---

## 📌 Covering your explicit requirement (“ask me question for each technology”)

Already done via `vscode_askQuestions`:
- GitHub OAuth vs token
- Hosting style
- UI library
- State approach
- Map provider
- direct client vs backend GitHub API path

---

## ✅ 5) Dependencies installed in project

- Core scaffold: React + Vite + TypeScript
- UI: MUI + Emotion
- State: Zustand
- Map: Leaflet + React-Leaflet
- API & schema: axios + zod + date-fns
- Lint/format: eslint + prettier + plugins
- Deploy: gh-pages

## 🧩 What’s next

1. your answers (a-e above)
2. I’ll update one concrete cheap architecture block for token exchange
3. then we can move to final official implementation plan and handoff (no code started yet).
