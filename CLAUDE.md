# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Session Memory

**WICHTIG:** Es gibt ein Session Memory unter `.claude/session-memory.md` - **immer zuerst lesen** um den aktuellen Projektstand zu kennen!

Nach jeder Session eine kurze Notiz im Session Memory hinzufügen.

## Commands

```bash
npm run dev       # Start dev server (http://localhost:3000)
npm run build     # Build for production
npm run preview   # Preview production build
npm run generate  # Generate static site
npx eslint .      # Run linter
```

## Architecture

This is a Nuxt 4 application using Vue 3 with the following modules:

- **@nuxt/ui** - UI component library
- **@nuxt/image** - Image optimization
- **@nuxt/eslint** - ESLint integration (config extends from `.nuxt/eslint.config.mjs`)
- **@nuxt/a11y** - Accessibility checking
- **@nuxt/hints** - Performance hints
- **@nuxt/scripts** - Script management
- **@nuxt/test-utils** - Testing utilities

## Project Structure

- `app/` - Application source (Vue components, pages, layouts)
- `public/` - Static assets served at root
- `nuxt.config.ts` - Nuxt configuration
- `.claude/session-memory.md` - Session Memory (Projektfortschritt)

## Design System

- **Primärfarbe:** Orange (#f97316 / orange-500)
- **Hintergrund:** Dunkel (gray-950, gray-900)
- **Text:** Weiß und Grau
- **Bilder:** Externe URLs von peppermint-digital.de
