## BitSetup Action

This action sets up Bit with good rules and caching using pnpm. It installs Node.js, pnpm, and initializes Bit.

### Inputs

- `bit-token` (required): Bit token.
- `resolve-org` (optional): Bit organization name, defines if should resolve dependencies using bit.
- `ws-dir` (optional): Bit workspace path.
- `node-version` (optional): Node version. Default is 18.
- `pnpm-version` (optional): Pnpm version. Default is latest.
- `cache-capsules` (optional): Cache bit capsules. Default is true.
- `cache-bvm` (optional): Cache BVM binary. Default is true.

### Example usage

```yaml
name: Bit Setup and test

on:
  push:

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Bit Setup
        uses: vturb/bit-setup-action@v1
        with:
          bit-token: ${{ env.BIT_CONFIG_USER_TOKEN }}

      - name: Bit Test
        run: bit test
```
