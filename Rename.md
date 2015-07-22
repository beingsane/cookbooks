# Rename

##### Multiple Files

```bash
find . -iname "*.txt" -exec bash -c 'mv "$0" "${0%\.txt}.md"' {} \;
```

##### Remove underscore from start of name file

```bash
find . -type f -name "_*" -exec sh -c 'd=$(dirname "$1"); mv "$1" "$d/$(basename "$1" | tr -d _)"' sh {} \;
```
