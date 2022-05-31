# php-filecoin-address 


```lang=bash
$ composer require adamyu1024/filecoin-address
```

## Usage

Create a new address:

```php
<?php

require_once 'vendor/autoload.php';

use adamyu1024\Filecoin\Address;

$address = new Address();

//setting network type
$address->currentNetwork = Address::TESTNET;

// get address
$address->get();
// t1hb4737umuzzbcfd3xxk3bdtwezgistj7dycypvi

$address->getPrivateKey();
// ee2868ca9485673b36c38ba4f18551be25d08dd9be9bd24c44cd626b37cadae4

$address->getPublicKey();
// 040c53eabf2389b06d36cb4e65a935c5473c0d2a0dd130b6a00bb1e3f987d7b7719079f5f1be4c3b35f3a12e31191632bf8fdd73de5cae553eadbd63d2cba41879

$privatekey = $address->getPrivateKey();
bin2hex('{"Type":"secp256k1", "PrivateKey": base64_encode(hex2bin(privatekey))}');
// 7b2254797065223a22736563703235366b31222c2022507269766174654b6579223a203769686f797053465a7a73327734756b38595652766958516a646d2b6d394a4d524d3169617a664b3275513d7d
```

Or load one from private key:

```php
<?php

require_once 'vendor/autoload.php';

use adamyu1024\Filecoin\Address;

$privateKey = 'ee2868ca9485673b36c38ba4f18551be25d08dd9be9bd24c44cd626b37cadae4';

$address = new Address($privateKey);

//setting network type
$address->currentNetwork = Address::TESTNET;

// get address
$address->get();
// t1hb4737umuzzbcfd3xxk3bdtwezgistj7dycypvi

$address->getPrivateKey();
// ee2868ca9485673b36c38ba4f18551be25d08dd9be9bd24c44cd626b37cadae4

$address->getPublicKey();
// 040c53eabf2389b06d36cb4e65a935c5473c0d2a0dd130b6a00bb1e3f987d7b7719079f5f1be4c3b35f3a12e31191632bf8fdd73de5cae553eadbd63d2cba41879
```

## License

MIT
