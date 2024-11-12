# AspireUpdate Translations

Translators, please make PRs here. You only need to submit PRs for the .po files, .mo, .json, and .l10n.php files will be generated automatically. Please add the .po files to the `languages` folder. Thanks.

Uses [`Language_Pack_Maker`](https://github.com/afragen/language-pack-maker) installed via composer to create a directory of zip archives of translation .mo/.po/.json/.l10n.php files and a `language-pack.json` file containing data to pass to Git Updater or afragen/translations-updater.

The format of the generated JSON file is as follows.

```json
[
  {
    "translations": [
      {
        "type": "(plugin|theme) from Git Updater",
        "slug": "{$slug}",
        "language": "en_US",
        "version": "from Git Updater",
        "updated": "PO-Revision-Date from .po file header",
        "package": "/packages/git-updater-en_US.zip",
        "autoupdate": "1"
      }
    ]
  }
]
```

The update transient expects the `$transient->translations` in the following format.

```php
$transient->translations( array(
	0 => array(
		'type'       => 'plugin',
		'slug'       => 'akismet',
		'language'   => 'de_CH',
		'version'    => '3.1.11',
		'updated'    => '2016-05-12 18:04:38',
		'package'    => 'https://downloads.wordpress.org/translation/plugin/akismet/3.1.11/de_CH.zip',
		'autoupdate' => 1,

	),
) );
```
