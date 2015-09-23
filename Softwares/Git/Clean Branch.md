# Clean Branch

```bash
git clone --no-checkout https://github.com/account/project
git checkout --orphan gh-pages
git rm -rf .
git clean -fdx
git push origin gh-pages
```
