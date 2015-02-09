# CodeSniffer

Homebrew install:

```bash
brew install php56
brew install php-code-sniffer
```

Pear install:

```bash
pear install PHP_CodeSniffer
```

Check standards:

```bash
phpcs -i
```

## PhpStorm

Set path of `phpcs`:

`File > Default Settings > Languages & Frameworks > PHP > Code Sniffer`

```
which phpcs
```

Check Code Sniffer validation:

`File > Default Settings > Editor > Inspections > PHP > PHP Code Sniffer validation`

Go to `Coding standard` and select the default standard.