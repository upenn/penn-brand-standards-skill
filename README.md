# Penn Brand Standards — Agent Skill

An [agent skill](https://code.claude.com/docs/en/skills) that packages the University of Pennsylvania's official brand standards so AI coding assistants (ZCode, Claude Code, and compatible agents) apply them automatically when building or reviewing Penn-branded work.

Instead of hoping the model remembers "Penn red and blue," the skill puts the authoritative values and rules in context on demand:

- **Official colors** — Penn Red `#990000` / PMS 201, Penn Blue `#011F5B` / PMS 288, with CMYK/RGB conversions and the web-only accent palette (`#82AFD3`, `#F2C100`, grays)
- **Typography by medium** — EB Garamond + Roboto for the web (with Penn's own Google Fonts embed), Perpetua + ITC Stone Serif for the identity and stationery
- **Logo rules** — every official variant, color treatments, clear space, sizing, and the full "never do" list
- **Lockup patterns** — department, school, joint-program, and co-branding rules
- **Stationery specs** — business card, letterhead, and envelope dimensions, margins, type sizes, and paper stock for print vendors
- **Web identity requirements** — the five required footer links, palette proportions, and why you shouldn't clone the upenn.edu homepage
- **Name use & approvals** — short-form naming, licensing, student-group sign-offs, and restricted symbols (seal, Split P)

## Install

Copy the `penn-brand-standards/` folder into your skills directory:

```bash
# Personal (available in every project)
git clone https://github.com/upenn/penn-brand-standards-skill.git
cp -R penn-brand-standards-skill/penn-brand-standards ~/.agents/skills/

# Or project-scoped
cp -R penn-brand-standards-skill/penn-brand-standards <project>/.agents/skills/
```

ZCode and Claude Code both discover skills in `.agents/skills/` (project) and `~/.agents/skills/` (personal).

## Usage

The skill triggers automatically whenever you mention Penn, UPenn, University of Pennsylvania, or ask for Penn-branded work. You can also invoke it explicitly:

> /penn-brand-standards Build a landing page for the Penn Libraries Spring Open House — make it official.

> /penn-brand-standards Give me print-vendor specs for a business card for our department's new associate director.

> /penn-brand-standards Can we print the Penn logo in gold for our symposium poster?

The skill uses progressive disclosure: a compact `SKILL.md` carries the values needed for most tasks, while three reference files (`references/logos-and-lockups.md`, `references/stationery-and-print.md`, `references/web-identity.md`) hold deep detail the agent reads only when the task calls for it.

## Structure

```
penn-brand-standards/
├── SKILL.md                              # Colors, typography, logo essentials, web requirements
└── references/
    ├── logos-and-lockups.md              # Variants, lockups, restricted symbols, approvals
    ├── stationery-and-print.md           # Business cards, letterhead, envelopes, print colors
    └── web-identity.md                   # Web palette, fonts, required footer links
```

## Source and authority

Derived from the public Penn Brand Standards (https://branding.web-resources.upenn.edu), including the Brand Guidelines PDF updated August 13, 2025. The official site is always the source of truth — if this skill and the official guidelines ever disagree, the official guidelines win, and please open an issue here so the skill can be corrected.

The University of Pennsylvania name, logo, shield, and related insignia are trademarks of the University of Pennsylvania. This skill references Penn's public brand standards for compliance purposes; official logo files must be downloaded from the [Penn branding site](https://branding.web-resources.upenn.edu/logos-and-branding/download-penn-logos) by members of the University community.

## Contributing

Corrections and updates welcome — especially when Penn revises the guidelines. Open an issue or pull request with the change and, where possible, a link to the official source that justifies it.
