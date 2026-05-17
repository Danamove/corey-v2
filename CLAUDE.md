# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What This Project Is

This folder holds the **design package** for **Corey**, a B2B SaaS-style product by AddedValue. Corey is a sourcing-as-a-service tool for freelance tech recruiters: customer fills a brief, gets a daily/weekly Excel of matching profiles to their email. Optional outreach add-on (Pro tier) sends emails from the customer's own inbox via OAuth.

This is **not yet a codebase**. There is no build, no tests, no implementation. The MVP build comes next. Anything Claude is asked to do here is either (a) refine the design, (b) start the implementation, or (c) generate adjacent artifacts (copy, email templates, onboarding, etc.).

## Repo Contents

- `design-spec.md` is the source of truth. Read this first. 11 sections covering audience, structure, copy, pricing, technical MVP plan, and open decisions.
- `README.md` is the human-friendly index. Less detailed than `design-spec.md`.
- `mockups/` contains 7 standalone HTML files, one per landing-page section. Open in browser to preview. These are reference, not production code.

## Locked Decisions (do not relitigate)

- **Brand:** Corey. First in a planned family (Corey Match, Corey Brief, etc., are future siblings, not part of MVP).
- **Brand color:** amber `#fbbf24`. Dark slate backgrounds (`#0f172a`, `#1e293b`).
- **Language:** Hebrew first. English version comes after Israeli-market validation.
- **Channels:** form on site + email only. No dashboard, no WhatsApp, no app.
- **Pricing model:** decreasing per-role tariff. ₪990 first role, ₪690 roles 2-4, ₪490 role 5+. Outreach add-on +₪400/role. 7-day free trial, 1 role, no credit card.
- **Audience:** solo freelance recruiters and boutique agencies (2-5 recruiters) in Israeli tech. Not enterprise, not bulk hiring, not global.
- **Supported roles:** Backend, Frontend, Fullstack, DevOps, Product. Junior to Senior. Anything else routes to a custom-plan path.
- **AddedValue stays separate.** Corey is a new product, not a rebrand. AddedValue continues with its founder/CTO clients independently.

## Writing Rules (apply to any copy Claude generates for this project)

- **No em-dashes, no en-dashes, no hyphens as clause separators.** Use periods, commas, colons, or middle-dots (·) instead. Compound words like "no-brainer" are fine.
- **No overpromises.** Never claim things the product can't deliver 100% of the time. Banned phrases: "competitors don't see this", "you'll be first to reach out", "100% match", "guaranteed placement". Prefer concrete deliverables and mindset shifts over comparative or competitive claims.
- **Don't sell the agents.** Customers don't care that AI agents run this. They care about the Excel arriving in their inbox. Avoid architecture explanations on the customer-facing site.
- **Hebrew copy, English technical terms.** LinkedIn, Boolean, OAuth, Excel stay in English. Body copy is Hebrew.
- **RTL layout** for any new HTML/UI.

## Open Decisions (Section 8 of design-spec.md)

1. Domain (corey.com / .ai / .co)
2. Israeli payment provider. **Stripe does not work in Israel.** Candidates: Cardcom, Tranzila, Pay.IL, Paddle (global).
3. Final logo design (current is a placeholder)
4. Support email address (corey-specific or reuse dana@added-value.co.il)
5. Terms & Privacy templates for Israeli commerce

## When Asked to Build the MVP

The `design-spec.md` section 7 lays out the technical MVP plan. Before writing implementation code, invoke the `writing-plans` skill to produce a structured implementation plan with phases and checkpoints. Do not start coding from the design doc directly.

Estimated MVP timeline (per design-spec.md): 4-8 weeks. Stack is not yet locked. Next.js or Astro for the static landing page is appropriate; backend pipeline reuses Dana's existing sourcing agents (Crustdata, LinkedIn).

## When Asked to Iterate the Design

Use the brainstorming skill again, anchored to the existing `design-spec.md`. Locked decisions above should hold unless Dana explicitly reopens them. Drafts and intermediate versions live in `C:\Users\USER\headhunting-brainstorm\.superpowers\brainstorm\` (separate from this folder).

## What Not to Add

- No Bio section (deferred by Dana)
- No agent/architecture explanation in customer-facing copy
- No WhatsApp bot in MVP
- No dashboard in MVP
- No "Market Signal Layer" framing that implies exclusivity (it is timing/prioritization, not exclusive access)
