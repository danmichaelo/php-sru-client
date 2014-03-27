[![Build Status](https://travis-ci.org/scriptotek/php-sru-client.png?branch=master)](https://travis-ci.org/scriptotek/php-sru-client)
[![Coverage Status](https://coveralls.io/repos/scriptotek/php-sru-client/badge.png?branch=master)](https://coveralls.io/r/scriptotek/php-sru-client?branch=master)

## php-sru-client

A simple PHP class for making [Search/Retrieve via URL](http://www.loc.gov/standards/sru/) (SRU) requests,using the 
[Guzzle HTTP client](http://guzzlephp.org/)
and returning 
[QuiteSimpleXMLElement](//github.com/danmichaelo/quitesimplexmlelement) instances.

If you prefer a simple text response, you might have a look at
the [php-sru-search](https://github.com/Zeitschriftendatenbank/php-sru-search) package.

### Install using Composer

Add the package to the `require` list of your `composer.json` file.

```json
{
    "require": {
        "scriptotek/sru-client": "dev-master"
    },
}
``` 

and run `composer install` to get the latest version of the package.

### Example

```php
require_once('vendor/autoload.php');
use Scriptotek\SruClient;

$url = 'http://sru.bibsys.no/search/biblioholdings';

$client = new SruClient($url, array(
    'schema' => 'marcxml',
    'version' => '1.1',
    'user-agent' => 'OpenKat/0.1'
);

$response = $client->search('dc.title="Hello world"');

```
