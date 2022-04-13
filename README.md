# Description

This repository has been made to test .htaccess configurations in an isolated area.

## Motivation

As someone who is not very advanced in htaccess and related configurations, I wanted to have somewhere to test htaccess files which is easily portable. If an .htaccess file has some issues then that whole part of the server can fail to load or reveal private data. This library aims to be something that can be copied into a server and then easily tested upon without security risks, and also containing common presets.

## Presets

The following are added by default because are common:

- .env
- .htaccess
- .composer.json
- .composer.lock
- .git
- package.json
- package-lock.json
- node_modules
- vendor

## Preset tests

The following js function generates the URLs for testing:

```js
/**
 * Execute the following example on the htaccess-tester main page.
 * @example const parts = location.href.split('/'); parts.pop(); const url = parts.join('/') generateHtaccessTestURLs(url)
 * @param {string} [base]
 */
function generateHtaccessTestURLs(base = 'http://localhost:8080') {
    const TEST_LOCATIONS = ['.env', '.htaccess', '.composer.json', 'composer.lock', '.git/index.html', 'package.json', 'package-lock.json', 'node_modules/index.html', 'vendor/index.html']
    return TEST_LOCATIONS.map(item => {
        return `${base}/files/sub-dir/${item}`
    })
}
```

## Usage

Please freely customize the .htaccess file and add files to the [files](./files/) directory.
