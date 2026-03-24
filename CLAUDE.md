# Development Workflow Guidelines

## Core Stack
- Use **TypeScript** for all JS projects
- ORM: **Prisma**
- Frontend: **Next.js**
- Fullstack apps: **Next.js (API routes / server actions)**
- Backend-only services: **NestJS**
- Analytics / data workloads:
  - Use **Python (Pandas, PySpark, etc.)** when heavy data processing
  - Use **Node.js** when tightly coupled with product APIs
- Use lightweight, actively maintained packages only (no deprecated libs)

## Code Quality
- Strong typing everywhere (no `any` unless justified)
- Define **clear interfaces/contracts**
- Keep functions small, testable, predictable
- Avoid unnecessary abstractions

## Git Workflow

## Git Workflow

### Branching Strategy
- `main` → production (protected)
- `develop` → integration
- `feature/*`, `fix/*`, `hotfix/*`

### Rules
- No direct commits to `main` or `develop`
- All changes must go through **Pull Requests (PRs)**
- PR must:
  - Pass lint, type-check, and tests
  - Be reviewed
  - Have clear description (what + why)

### AI-Specific Branch Rules
- ALWAYS create a new branch before starting any work
- NEVER work directly on `main` or `develop`
- NEVER merge branches (AI must not perform merges)
- Branch naming format:


## Git Hooks & CI
- Husky pre-commit:
  - lint
  - format
  - type-check
- Husky pre-push:
  - tests
  - build validation
- CI blocks merge on failure

## AI Usage Rules

### Autonomy (Controlled)
- AI can:
  - Scaffold projects
  - Write code
  - Refactor safely
  - Suggest DB changes

- AI cannot (without explicit approval):
  - Run destructive DB migrations
  - Delete or overwrite production data
  - Introduce breaking architectural changes
  - Deploy directly to production

### Required Behavior
- Start tasks **end-to-end (scaffold → implement → validate)**
- Always explain major decisions
- Follow repo standards strictly
- Prefer incremental changes over large rewrites

### Validation Checklist
- Code compiles
- Types are correct
- No lint errors
- Fits module boundaries
- No unnecessary dependencies

## Architecture
- Modular domain-based structure
- Each module owns its schema
- No direct cross-module DB access
- Aggregations handled in logic layer

## Database
- Add indexes during design
- Design for analytics from day one
- Clean migration history
- Avoid unreviewed schema changes

## Performance
- Optimize Core Web Vitals
- Prefer SSR/SSG
- Optimize images and payload size

## SEO (Public Sites)
- Strong metadata + schema
- Proper interlinking
- Server-rendered content

## Security
- Encrypt sensitive data
- Validate all inputs
- Secure auth flows
- Never expose secrets

## Testing
- Unit tests for core logic
- Integration tests for flows
- No untested critical paths

## Observability
- Log events and errors
- Maintain traceability
- Monitor performance

## General Principles
- Prefer simple over clever
- Build for scale and change
- Optimize for speed + stability + revenue impact