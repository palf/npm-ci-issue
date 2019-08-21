# NPM Investigation

## quick

```
npm run test
```

## detail

The dependency `prettier` has been moved from `devDependencies` to regular `dependencies`;
the `package-lock.json` file has _not_ been updated, and `npm install` has _not_ been run.

So `prettier` exists in `package-lock.json` with the flag of `dev: true`.

Executing `npm ci --only=production` keeps `uuid` and removes `prettier`,
where I would expect the command to fail with an error, with something like:

> `package.json` and `package-lock.json` out of sync
