# Stuart PHP Client
For more details, visit https://docs.stuart.com.

## Install
Via Composer

``` bash
$ composer require maximilientyc/stuart-php
```

## Usage
### Authenticate

```php
$useSandbox = true; // will use https://sandbox-api.stuart.com
$api_client_id = '65176d7a1f4e734f6723hd690825f166f8dadf69fb40af52fffdeac4593e4bc'; // can be found here: https://admin-sandbox.stuart.com/client/api
$api_client_secret = '681ae68635c7aadef5cd1jdng8ef357a808cd9dc794811296446f19268d48fcd'; // can be found here: https://admin-sandbox.stuart.com/client/api

$httpClient = new HttpClient($useSandbox, $api_client_id, $api_client_secret);
```

### Create a Job

```php
$origin = [
    'address' => '18 rue sidi brahim, 75012 Paris',
    'company' => 'WeSellWine Inc.',
    'first_name' => 'Marcel',
    'last_name' => 'Poisson',
    'phone' => '0628739512'
];
$destination = [
    'address' => '5 rue sidi brahim, 75012 Paris',
    'company' => 'Jean-Marc SAS',
    'first_name' => 'Jean-Marc',
    'last_name' => 'Pinchu',
    'phone' => '0628046934'
];
$package_size = 'small';

$job = new Job($origin, $destination, $package_size, $httpClient);
$job.create();
```