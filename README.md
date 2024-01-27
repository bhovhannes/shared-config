# shared-config

My shared configuration for Prettier, commitlint, etc.

## Usage

```shell
npm i -DE @bhovhannes/shared-config
```


### Renovate

In `.renovaterc`:
```
{
  "extends": ["github>bhovhannes/shared-config//renovate/default"]
}
```

### Prettier

In `.prettierrc.js`:
```
module.exports = {
  ...require('@bhovhannes/shared-config/prettier'),
  // put overrides here
}
```

### Commitlint

In `.commitlintrc.js`:
```
module.exports = {
  ...require('@bhovhannes/shared-config/commitlint'),
  // put overrides here
}
```

### Lefthook

In `lefthook.yml`:
```yaml
extends: 
  - node_modules/@bhovhannes/shared-config/lefthook/commit-msg/lint.yml
  - node_modules/@bhovhannes/shared-config/lefthook/pre-commit/format.yml
```

where:
1. `commit-msg/lint.yml` - contains hook config for linting commit message with commitlint
1. `pre-commit/format.yml` - contains hook config for formatting staged files with prettier
