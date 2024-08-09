# PNPM Nest.js Mono Repo

Test!

Issue with pnpm 7.29 and `dedupe-peer-dependents`

# Steps to Reproduce

With `dedupe-peer-dependents`

```
pnpm add -F api @types/node
pnpm remove -F api @types/node
```

Without `dedupe-peer-dependents`
Comment it out in `.npmrc`

```
pnpm add -F api @types/node
pnpm remove -F api @types/node
```
