## Behavior Rules

- Always keep **commit messages** to a single, clear line.
  Do **not** mention Claude, do **not** use "Co-authored-by", or add fluff.
- When memory is below 8% remaining, stop all work and ask:
  _"Memory is low — should I compact or write a chat note first?"_
- Always use `/compact` or a chat note to preserve state before memory resets.
- **Phase:** A single-responsibility task (e.g. “add login endpoint”), ≤2000 output tokens, testable, revertible, and commit-sized.
- Skip planning if:  
  A. The request is focused and clear.  
  B. Your plan mirrors the request.  
  C. The task fits in one Phase.

- If planning, outline Phases explicitly and state which Phase you'll begin with.

- Never continue to the next Phase without approval.

## Chat & User Notes

- Support the following commands:
  - `/chat_note` or `/note` — summarize the session:
    - What was done
    - Why we did it
    - What worked / didn’t
    - Lessons learned
    - Anything we did or learned which was non-obvious, or which we planned but did not implement, that that future human or AI workers would not be able to figure out just by reading other files and code.
  - Notes should be succinct whenever possible, but specific when necessary.

- Store notes in:
  - `../notes/chat`
  - If not found, try `./notes/chat`
  - If neither path exists, create `./notes/chat` automatically.
  - User notes are stored in a /user directory alongside /chat

- Name files like:
  - `1_YYYYMMDD_short_summary_title.md`
  - `2_YYYYMMDD_next_summary_title.md` (auto-incremented)

- Always read the latest chat note and latest user note if not yet read.
- Avoid repeating any information you or I have already learned or stated, unless we are planning, summarizing, or I have requested it.
- Read any README.md files for the current project for context (at current path or 1 level down)

## Efficiency Tips

- Avoid reprocessing large prompts repeatedly — cache or summarize when possible.
- Don’t restate context unless it has changed.
- When writing summaries, plans, etc, write them only in a file or in chat, whichever is specified (default is chat not file)
- If output gets long, ask: _“Should I continue verbosely or summarize?”_
- Prefer small tool-assisted chunks over large speculative actions.

## Code Quality & Error Detection

- Always use `mcp__ide__getDiagnostics` to check for IDE errors/warnings when:
  - Starting work on a codebase
  - After making code changes
  - Before completing tasks
  - When debugging issues

- Proactively run type checking commands when available:
  - `npm run typecheck` / `yarn typecheck` / `pnpm typecheck`
  - `tsc --noEmit`
  - Language-specific checkers (mypy, cargo check, etc.)

- Run linting to catch code quality issues:
  - `npm run lint` / `yarn lint` / `pnpm lint`
  - `eslint`, `pylint`, `clippy`, etc.

- Address all diagnostics found before marking tasks complete
- Use formatting tools to maintain consistent code style
- Never ignore TypeScript/compiler errors without explicit user approval

## Visual Testing & Screenshots

- Take screenshots when possible to verify visual changes when working on UI/frontend projects:
  - Use `npm run screenshot` or equivalent project commands
  - Screenshots help validate that changes work as expected
  - Essential for Three.js, Canvas, WebGL, and visual applications

- Use Playwright for automated visual testing:
  - Run `npm run test:visual` for visual regression tests
  - Take screenshots with `playwright test --update-snapshots` to update baselines
  - Compare before/after screenshots to validate improvements

- Review screenshots when:
  - Making visual changes to applications
  - Debugging rendering issues
  - Verifying responsive design
  - Confirming animations and interactions work correctly

## Development Server Protocol

- Use separate ports for user and Claude development servers:
  - User port: 3000 (default) - `npm run dev`
  - Claude port: 3001 - `npm run dev:claude`
  - This prevents conflicts when both are running simultaneously

- Claude-specific commands to use:
  - `npm run dev:claude` - Start Claude's dev server on port 3001
  - `npm run screenshot:claude` - Take screenshots from Claude's server
  - `npm run test:visual:claude` - Run visual tests on Claude's server

## Project Context

- Respect any `CLAUDE.md` or `CLAUDE.local.md` in the current project.
- When both exist, merge this file first, then the local one.

## 

## Style Guide

- Never leave spaces or tabs on empty lines or at the end of lines.
- Leave 1 blank line at the end of every file
- Limit indents to 3 levels 80% of the time, 4 levels 90% of the time, and 5 levels max 100% of the time.
- Keep files short. Most files (75%) should be under 150 lines, all files under 250 lines.
- Identify when files are getting too big and proactively suggest how to split them up.
- Each file should have a clear purpose, respecting separation of concerns.
- Do not hard code specific solutions for general problems.
- Do not 'hack' workarounds for problems without asking first.
- Do not undo changes unless they are small or the user has approved or requested it.
- Do suggest undoing or removing work that is no longer necessary.
- Do not make speculative changes anticipating a future purpose unless asked.
- Avoid using the word 'proper' in code, comments, commits, everywhere.
- Never put a timeline in a plan or other doc without me explicitly requesting that (ex: 'Phase 3 (Week 2)').

### Code Comments
- Do not leave comments that just state or restate obvious information.
- Examples of an unnecessary comments I do not want you to make:
``` ts
  // Get current path as string
  static getCurrentPath(): string { ... }
```
``` ts
  // Initialize the script
  static initialize() { ... }
```
``` ts
    // Add close button
    const closeBtn = document.createElement('button');
```
- Do not make comments about changes vs previous versions, or comments that could simply be a note made in chat. If a code comment could just be a note in the chat, then put it in the chat and not in the code or file.
- More unnecessary comment examples:
``` ts
// loadRealFileSystem method was removed since it was no longer needed.
```
``` ts (git change log)
-     element.rotate()
+     // No rotation for the element
```
``` ts
someVar.height = 10px; // Now 25% higher, as requested
```
``` ts
// Position at top-right corner, much more prominent
  plane.position.set(parentWidth * 0.3)
```
```ts
const width = 0.3; // 30% of folder width
const height = 0.45; // 1.5x as tall as it is wide
```

# End of ~/.claude/CLAUDE.md
