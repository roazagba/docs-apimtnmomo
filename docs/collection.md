# Collection

```php
use Roazagba\ApiMTNMomo\MTNMoMoConfig;
use Roazagba\ApiMTNMomo\Products\MTNMoMoCollection;

$config = new MTNMoMoConfig();

$collection = new MTNMoMoCollection($config);
```

**createTransaction()** opération permettant de demander un paiement à un consommateur (payeur). Le payeur est invité à autoriser le paiement. La transaction sera exécutée une fois que le payeur aura autorisé le paiement. La demande de paiement est en attente jusqu'à ce que la transaction soit autorisée ou refusée par le payeur ou qu'elle soit interrompue par le système.

```php

$params = [
    'amount' => '2',
    'referenceExternalID' => rand(1000000000000000, 9999999999999999) . '',
    'numberMoMo' => '22969411836',
    'description' => 'transaction',
    'note' => 'newtransaction'
];

$custom_params = [
    'firstname' => 'Ro',
    'lastname' => 'AZ',
    'email' => 'roazagba@gmail.com',
    'anotherField' => 'anotherValue'
];

$createTransaction = $collection->createTransaction($params, $custom_params);

$transactionId = $createTransaction['transactionId'];

$customParams = $createTransaction['customParams'];
```

**getTransaction()** opération permettant de récupérer les détails de la transaction et du statut

```php
$transaction = $collection->getTransaction($transactionId);
```

**getAccountBalance()** opération permettant d'obtenir le solde de son propre compte.

```php
$balance = $collection->getAccountBalance();
```

**getBasicUserInfo()** opération permettant de renvoyer les informations personnelles du titulaire du compte. L'opération ne nécessite aucun consentement de la part du titulaire du compte.

```php
$numberMoMo = '46733123460';
$user_info = $collection->getBasicUserInfo($numberMoMo);
```
