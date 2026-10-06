## Global instructions

- When refactoring existing code, check relevant files for existing tests and update them if necessary.
- When adding new code, prefer to write easily mockable and testable code, and include tests where applicable.
- Limit the amount of comments you put in the code to a strict minimum. You should almost never add comments, except sometimes on non-trivial code, function definitions if the arguments aren't self-explanatory, and class definitions and their members.
- Do not remove existing comments unless they are directly related to what you are changing.

## Repository Structure

This is a monorepo containing three main projects:

- `firefox-ios/` - Firefox for iOS (main app, scheme: `Fennec`)
- `focus-ios/` - Firefox Focus for iOS (scheme: `Focus`)
- `BrowserKit/` - Shared Swift Package mostly used in Firefox

## Common Commands

### Build & Test

```bash
# Build for testing (Firefox)
fxios test
```

### JavaScript User Scripts

Needed to be ran whenever we make JavaScript changes.

```bash
npm run build   # production build
npm run dev     # watch mode with source maps
```

### Linting

SwiftLint runs automatically via Xcode build phases on the Client target. Install via `brew install swiftlint`. Configuration is in `.swiftlint.yml`.
SwiftLint also runs whenever code is pushed to the remote, using hooks.

### Pull requests

Pull requests needs to be opened with the provided `PULL_REQUEST_TEMPLATE`. Update relevant section. 
GitHub ticket number can be found at the bottom of the JIRA ticket.

## Runbooks

- **Xcode version upgrade.** When bumping the Xcode version used by CI/local builds, follow [docs/xcode-upgrade.md](docs/xcode-upgrade.md).

## Living Project Board

`PROJECT_BOARD.md` is this repository's shared living project board. Before starting substantial work, scan it for relevant context. During normal work, agents should proactively add concise, actionable entries when they discover something with genuine future value, including:

- useful technical discoveries
- optimization opportunities
- implementation tricks
- architectural ideas
- possible future improvements
- experiments worth running
- unresolved issues or questions
- follow-up work that should not be lost

Do this proactively even when the discovery is incidental to the current task. Do not add trivial observations, temporary debugging chatter, information already documented elsewhere, generic suggestions with no project relevance, or every step performed during a task. The board supports memory but is not a source of truth when repository code, documentation, or current state contradicts it.

When an item is implemented, mark it complete and optionally record the date and commit/PR, moving it to `Done` when useful. Delete or archive obsolete entries when appropriate.

Updating `PROJECT_BOARD.md` as a side effect of another task is allowed and encouraged when a worthwhile discovery is made. Recording an idea is allowed; implementing unrelated ideas is not.

Preserve all existing repository-specific instructions.
