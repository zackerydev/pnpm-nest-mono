# PNPM Nest.js Mono Repo

Issue with pnpm and multiple versions of @nestjs/core?

Not sure what's happening here or if this should work or not.

But it looks like two separate versions of Nest.js core are conflicting with one another and not exporting `ModuleRef`

## Steps to Reproduce

```
gh repo clone zgriesinger/pnpm-nest-mono
cd pnpm-nest-mono
pnpm i
pnpm -r build
pnpm -F api start
```

It should bomb out with `ModuleRef` not found. I have no idea why or how it could be not found.

My first inclination is that due to there being two versions of `@nestjs/common` in the `pnpm-lock.yaml`:

```yaml
"@nestjs/core": 9.1.6_bx3wiubfryfbvpzqwr6ml4ajpu # line 40
'@nestjs/core': 9.1.6_yjxybkvltbh2d3oivnq5etx3oi # line 1041
```

Meaning `@nestjs/terminus` and the main `api` are using different instances of `@nestjs/core`

I'm not sure if this is an issue in Nest or PNPM 🤔
