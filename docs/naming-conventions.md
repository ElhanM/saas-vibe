# Naming Conventions

- No abbreviations — use full words (exceptions: `id`, `url`, `api`, `db`, `ctx`, `err`)
- Functions: describe the action — `calculateMonthlyTotal`, not `calc` or `process`
- Booleans: `isActive`, `hasPermission`, `canEdit` — not `active`, `permission`
- Collections: plural — `users`, `invoiceItems`, not `userList`, `invoiceItemArray`
- Avoid filler suffixes: `Manager`, `Helper`, `Util`, `Data` alone say nothing
- Consistency: if the codebase uses `getUserById`, don't introduce `fetchUserWithId`
