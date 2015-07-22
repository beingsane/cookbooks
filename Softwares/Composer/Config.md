# Config

```bash
composer config --list

vim ~/.composer/config.json
```

```json
{
    "config": {
        "github-protocols": [
            "https"
        ]
    },
    "repositories": [
        {
            "packagist": false
        },
        {
            "type": "composer",
            "url": "http://packagist.org",
            "options": {
                "ssl": {
                    "verify_peer": "false"
                }
            }
        }
    ]
}
```
