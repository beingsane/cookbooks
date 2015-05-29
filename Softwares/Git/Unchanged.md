# Unchanged

Prevent to receive changed files:

```bash
git update-index --no-assume-unchanged <file>
```

Ignore local changed files:

```bash
git update-index --assume-unchanged <file>
```

List files with `assume-unchanged`:

```bash
git ls-files -v | grep '^h'
```
