# Naming Conventions

- No abbreviations — use full words (exceptions: `id`, `url`, `api`, `db`, `ctx`, `err`)
- Functions: describe the action — `calculateMonthlyTotal`, not `calc` or `process`
- Booleans: `isActive`, `hasPermission`, `canEdit` — not `active`, `permission`
- Collections: plural — `users`, `invoiceItems`, not `userList`, `invoiceItemArray`
- Avoid filler suffixes: `Manager`, `Helper`, `Util`, `Data` alone say nothing
- Consistency: if the codebase uses `getUserById`, don't introduce `fetchUserWithId`
- Match names to the type's zero value — `false`, `0`, `""`, `nil` should represent the natural no-op; a filter `onlyActive bool` defaults to `false`, silently excluding the common case — name it `onlyInactive` instead; applies to any type, not just booleans
- Avoid double negatives: if you find yourself writing `!isNotActive`, the name is wrong
