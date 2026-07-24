# Reusable Protocols & Workflows

## 1. Project Scaffolding Protocol
```bash
# For any new project
1. mkdir PROJECT-NAME && cd PROJECT-NAME
2. Create: README.md, .gitignore, LICENSE (MIT), ARCHITECTURE.md
3. Create: requirements.txt (Python) or package.json (Node)
4. Create: .env.example (never commit .env)
5. Create: src/ directory structure
6. Create: tests/ directory
7. git init && git add . && git commit -m "Initial scaffold"
8. Create GitHub repo && push
```

## 2. HTML-to-Production Protocol
```bash
# Single HTML → Production app
1. Extract CSS → styles/ directory
2. Extract JS → scripts/ directory
3. Extract images → assets/ directory
4. Create index.html with external references
5. Add GSAP + ScrollTrigger + Lenis
6. Add responsive breakpoints
7. Add meta tags (OG, Twitter, schema.org)
8. Run Lighthouse audit (target: 90+ all categories)
9. Deploy to Vercel/Netlify
```

## 3. AI-Assisted Development Loop
```
Phase 1: PLAN (Frontier model)
  - Read requirements
  - Design architecture
  - Create task breakdown
  
Phase 2: BUILD (Economy model)
  - Implement each task
  - Write tests
  - Build documentation
  
Phase 3: REVIEW (Frontier model)
  - Code review
  - Security audit
  - Performance check
  
Phase 4: DEPLOY
  - Run full test suite
  - Deploy to staging
  - Verify in production
```

## 4. Skill Development Protocol
```bash
# Create new skill
1. mkdir skill-NAME && cd skill-NAME
2. Create SKILL.md with frontmatter (name, description)
3. Create references/ for detailed docs
4. Create scripts/ for executable tools
5. Create agents/openai.yaml for UI metadata
6. Validate with quick_validate.py
7. Test with 3 realistic prompts
8. Iterate until reliable
```

## 5. Research Deep Dive Protocol
```
Step 1: Define question clearly
Step 2: Spawn 3+ parallel research subagents
  - Subagent 1: Primary sources (docs, papers)
  - Subagent 2: Secondary sources (blogs, tutorials)
  - Subagent 3: Community sources (forums, GitHub)
Step 3: Cross-validate findings
Step 4: Synthesize into structured report
Step 5: Extract actionable insights
Step 6: Store in knowledge/ directory
```

## 6. E-Commerce Launch Checklist
- [ ] Product catalog with real images
- [ ] Shopping cart with persistence
- [ ] Checkout flow (Stripe integration)
- [ ] User authentication
- [ ] Order management
- [ ] Email notifications
- [ ] SEO (schema.org, sitemap, robots.txt)
- [ ] Analytics (GA4)
- [ ] Performance (Lighthouse 90+)
- [ ] Accessibility (WCAG 2.2 AA)
- [ ] Mobile responsive
- [ ] Error pages (404, 500)
- [ ] Legal pages (privacy, terms)
- [ ] Admin dashboard
- [ ] Backup strategy
- [ ] Monitoring/alerting

## 7. Git Commit Convention
```
type(scope): description

Types: feat, fix, docs, style, refactor, test, chore, perf
Scope: project name or component
Description: imperative mood, max 72 chars

Examples:
feat(belentani): add Matrix rain effect
fix(hotel): booking wizard price calculation
docs(aion): update API documentation
perf(ecommerce): optimize image loading
```

## 8. Security Checklist
- [ ] No API keys in code (use .env)
- [ ] Input validation on all endpoints
- [ ] SQL injection prevention (parameterized queries)
- [ ] XSS prevention (output encoding)
- [ ] CSRF protection
- [ ] Rate limiting on APIs
- [ ] HTTPS everywhere
- [ ] Security headers (CSP, HSTS, X-Frame-Options)
- [ ] Dependency audit (npm audit, pip audit)
- [ ] Secrets in secret manager (not .env in production)
