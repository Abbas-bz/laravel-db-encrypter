# Laravel Db Encrypter Package For Mongodb

This package was created to encrypt and decrypt values of Eloquent model attributes.

&#x1F537; &#x1F537; &#x1F537; &#x1F537;

&#x1F537; &#x1F537; &#x1F537; &#x1F537; 

### Works on jenssegers/mongodb now

&#x1F537; &#x1F537; &#x1F537; &#x1F537;

&#x1F537; &#x1F537; &#x1F537; &#x1F537;

## Donnations
If You think this package helped You, please donate. Thank You.

https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=SPYLWZ8Y5E4JE&source=url

## Key features

* Encrypt, decrypt values stored in database fields
* Using standard Laravel's Crypt service
* Easy configuration

## Requirements

* Laravel: 6.0 and up
* PHP: 7.1 and newer

#### Database schema

Encrypted values are stored as plain text so in most cases takes up more spaces then unencrypted one.
Recommendation is to alter table column to `TEXT` type.
If you want use `VARCHAR` or `CHAR` column type still you need to check if encrypted value fit.

#### Note:
Do not worry if you have current data in your database not encrypted and added column to `$encryptable`  - they will return as is.    
On save values will be encrypted and everything will work fine.

## Installation

Via Composer command line:

```bash
$ composer require payamjafari/laravel-db-encrypter
```

## Usage

1. Use the `betterapp\LaravelDbEncrypter\Traits\EncryptableDbAttribute` trait in any Eloquent model that you wish to use encryption
2. Define a `protected $encryptable` array containing a list of the encrypted attributes.

For example:

```php
use Jenssegers\Mongodb\Eloquent\Model;
use betterapp\LaravelDbEncrypter\Traits\EncryptableDbAttribute;

class Client extends Model {
    use EncryptableDbAttribute;

    /** @var array The attributes that should be encrypted/decrypted */
    protected array $encryptable = [
        'id_number', 
        'email',
    ];
}
```

3. You can use Laravel's original $casts to cast decrypted values

### License
The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
