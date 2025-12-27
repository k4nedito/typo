### Project Rules — Markdown Editor (SvelteKit)

**Stack assumptions**

* SvelteKit (latest)
* TypeScript, strict mode
* Tailwind CSS (+ typography, forms)
* pnpm
* No external state library unless justified

---

### General rules

* Prefer **simple, explicit code** over abstractions.
* Do not introduce libraries unless asked.
* Do not invent APIs, components, or files.
* Respect SvelteKit server/client boundaries.
* No placeholder logic or fake data.
* No comments unless explaining non-obvious behavior.

---

### Svelte / SvelteKit

* Use **Svelte 5 / runes** syntax when applicable.
* Use `<script lang="ts">` always.
* Prefer `$props`, `$state`, `$derived` over stores.
* Avoid writable stores for app-wide state unless required.
* No `$page` or `$session` misuse.

Routing:

* UI logic → `+page.svelte`
* Load logic → `+page.ts`
* Server-only logic → `+page.server.ts`
* API endpoints → `+server.ts`

Never import from `$lib/server` in client code.

---

### TypeScript

* `any` is forbidden.
* Narrow types explicitly.
* Prefer union types over enums.
* Prefer readonly where possible.
* No implicit `undefined` handling—be explicit.

If a type is unclear, stop and ask instead of guessing.

---

### Tailwind / UI

* Use **utility classes only**.
* No inline styles.
* No custom CSS unless unavoidable.
* Favor spacing, typography, and color consistency over effects.
* No gradients, shadows, or animations unless explicitly requested.

Typography:

* Markdown preview uses `prose`.
* Editor text uses mono font.
* UI chrome uses sans font.

---

### Markdown editor specifics

* Treat markdown as **data**, not HTML.
* No `innerHTML` unless sanitized.
* Parsing/rendering must be deterministic.
* Editor and preview are separate concerns.
* Cursor position and selection must be preserved on updates.

---

### Performance & behavior

* Avoid unnecessary reactivity.
* Avoid re-rendering editor content on every keystroke if not needed.
* Prefer derived state over recomputation.
* No debounce unless UX demands it.

---

### What Copilot should NOT do

* Do not redesign the UI.
* Do not add feature creep (accounts, sync, cloud, auth).
* Do not add analytics, tracking, or telemetry.
* Do not assume mobile unless stated.
* Do not generate marketing copy.

---

### When uncertain

* Ask for clarification instead of inventing behavior.
* If multiple valid implementations exist, choose the **simplest** one and explain the tradeoff briefly.

