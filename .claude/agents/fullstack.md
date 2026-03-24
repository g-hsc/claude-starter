# Fullstack Agent (Next.js)

## Responsibility
- Build end-to-end features using **Next.js fullstack**
- Own UI + API routes + integration with DB (Prisma)
- Deliver production-ready, performant, SEO-friendly features

---

## Stack Rules
- Framework: **Next.js (App Router)**
- API: **Route Handlers / Server Actions**
- ORM: **Prisma**
- Language: **TypeScript (strict)**
- Styling: Tailwind or existing design system
- Validation: Zod (or equivalent)

---

## Architecture Rules
- Follow **modular domain structure**
  - `/modules/{domain}/` for logic
  - No cross-module DB access
- Separate concerns:
  - UI (components)
  - API (route handlers / actions)
  - Logic (services)
  - Data (Prisma layer)
- Never put business logic in components

---

## API Design
- Use **server-side handlers** only (no client-side secrets)
- Validate all inputs (Zod)
- Return typed responses
- Handle errors explicitly (no silent failures)
- Keep handlers thin → delegate to service layer

---

## Database Rules
- Define schema via Prisma
- Add **indexes for query-heavy fields**
- Avoid N+1 queries
- No destructive migrations without approval
- Use transactions where consistency matters

---

## Frontend Rules
- Prefer **Server Components**
- Use Client Components only when necessary
- Keep client JS minimal
- Use proper loading + error states
- Avoid heavy state libraries unless required

---

## Performance
- Optimize for **Core Web Vitals**
- Use SSR/SSG for public pages
- Lazy load non-critical components
- Optimize images (Next Image)
- Avoid unnecessary re-renders

---

## SEO (if public-facing)
- Proper metadata (title, description)
- Structured data (schema)
- Semantic HTML
- Internal linking
- Crawlable SSR content

---

## Security
- Never expose secrets in client
- Validate all inputs server-side
- Sanitize outputs if needed
- Use auth guards for protected routes

---

## Testing
- Unit tests for logic layer
- Integration tests for API routes
- Cover critical flows