## Context

The Fart Symphony Conductor is a single-file HTML application (`index.html`) that implements an absurd audio-based captcha using the Web Audio API. It requires microphone access via `getUserMedia`, which mandates HTTPS in production browsers. The repository `misterlami/kilo-challenge-captcha` is already on GitHub with a `main` branch. GitHub Pages provides free static hosting with automatic HTTPS, making it the ideal deployment target.

## Goals / Non-Goals

**Goals:**
- Make the captcha publicly accessible via a permanent URL
- Zero ongoing cost and maintenance
- HTTPS support for microphone access
- Deployment with no code changes

**Non-Goals:**
- Custom domain setup
- CI/CD pipeline for automated deployment
- Performance optimization or CDN configuration
- Analytics or monitoring

## Decisions

### Decision: Deploy from `main` branch root (not `gh-pages` branch)
- **Rationale**: The entire app is a single `index.html` at the repo root. Creating a separate `gh-pages` branch adds complexity with no benefit. GitHub Pages can serve directly from `main`.
- **Alternatives considered**:
  - `gh-pages` branch with a build script — unnecessary overhead for a single static file
  - GitHub Actions workflow to deploy — adds CI/CD complexity that isn't needed

### Decision: No code changes to `index.html`
- **Rationale**: The file is fully self-contained with inline CSS and JS. All assets (Web Audio API, Canvas) are generated at runtime. There are no relative asset paths that would break under a `/kilo-challenge-captcha/` base path.
- **Alternatives considered**:
  - Adding a `<base>` tag — not needed since there are no sub-resource references
  - Injecting a deploy script — would overcomplicate a trivial task

## Risks / Trade-offs

- **GitHub Pages cold start**: First request after inactivity may be slightly slower. Acceptable for a demo/captcha use case.
- **No custom domain**: URL will be `https://misterlami.github.io/kilo-challenge-captcha/`. Fine for challenge submission; custom domain can be added later if needed.
- **Manual deployment**: Each push to `main` triggers a redeploy (GitHub Pages auto-deploys from branch). No manual action needed after initial setup.
