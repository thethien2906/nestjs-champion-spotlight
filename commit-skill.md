# Gitmoji Commit Guidelines

Standardized convention for repository commit messages using [Gitmoji](https://gitmoji.dev/).

---

## Philosophy

The emoji provides the immediate visual and semantic category of the commit. Because the Gitmoji carries the high-level intent, commit messages must be **concise, direct, and imperative**.

### Format

```
<emoji> <concise-imperative-summary>
```
*or using shortcode:*
```
:<gitmoji-shortcode>: <concise-imperative-summary>
```

**Examples:**
* `🎉 Initial commit` or `:tada: Initial commit`
* `✨ Add pilot authentication guard` or `:sparkles: Add pilot authentication guard`
* `🐛 Fix synchronization rate clamp` or `:bug: Fix synchronization rate clamp`
* `📝 Update MAGI telemetry specifications` or `:memo: Update MAGI telemetry specifications`
* `♻️ Refactor Eva unit module structure` or `:recycle: Refactor Eva unit module structure`

---

## Core Gitmoji Reference

| Gitmoji | Shortcode | Intended Usage | Example |
| :---: | :--- | :--- | :--- |
| 🎉 | `:tada:` | Initial commit | `:tada: Initial commit` |
| ✨ | `:sparkles:` | Introduce new feature / capability | `:sparkles: Add Eva sortie log endpoint` |
| 🐛 | `:bug:` | Fix a bug | `:bug: Resolve circular dependency in AuthModule` |
| 📝 | `:memo:` | Add or update documentation | `:memo: Document MAGI voting consensus` |
| ♻️ | `:recycle:` | Refactor code (no behavior change) | `:recycle: Extract pilot validation pipe` |
| 🎨 | `:art:` | Improve code structure / formatting | `:art: Format DTO naming conventions` |
| ⚡️ | `:zap:` | Improve performance | `:zap: Add Redis caching for telemetry feed` |
| 🔒️ | `:lock:` | Fix or improve security / permissions | `:lock: Restrict commander routes with guard` |
| 🧪 | `:test_tube:` | Add or update tests | `:test_tube: Add unit tests for sync rate logic` |
| 🏗️ | `:building_construction:` | Architectural / structural changes | `:building_construction: Scaffold monorepo for microservices` |
| 🔧 | `:wrench:` | Configuration file modifications | `:wrench: Add database migration scripts` |
| 📦️ | `:package:` | Add or update dependencies | `:package: Install @nestjs/bullmq and redis` |
| 🚀 | `:rocket:` | Deployment / release preparations | `:rocket: Add multi-stage Dockerfile` |
| 💥 | `:boom:` | Breaking changes | `:boom: Redesign sortie payload contract` |
| 🚑️ | `:ambulance:` | Critical hotfix | `:ambulance: Fix memory leak in WebSocket gateway` |

---

## Rules of Engagement

1. **Be Concise:** Since the emoji tells the "what kind", the text only needs to describe the "what". Keep the message under 50 characters whenever possible.
2. **Imperative Mood:** Use "Add", "Fix", "Update", "Remove" instead of "Added", "Fixing", "Updated".
3. **One Concern Per Commit:** Keep commits atomic. Don't mix `:sparkles:` with `:recycle:`.
4. **Emoji or Shortcode:** Both native UTF-8 emojis (`✨`) and shortcodes (`:sparkles:`) are valid, but keep it consistent with GitHub rendering.
