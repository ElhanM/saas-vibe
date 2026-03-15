# Dependencies

- Before adding: can stdlib or an existing dep handle this? If yes, don't add
- Avoid micro-deps — a trivial function is better than a package
- Prefer established packages (years of use, wide adoption) over new ones
- Commit lockfiles — never floating versions in production
- Comment non-obvious dep choices near the import so future engineers understand why
