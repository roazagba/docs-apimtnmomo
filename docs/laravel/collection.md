# Collection

!> Pour ce produit j'ai laissé, certains APIs pour permettre à d'autres de contribuer. Les APIs importants ci-dessous.

```php
use Roazagba\ApiMTNMomo\MTNMoMoConfig;
use Roazagba\ApiMTNMomo\Products\MTNMoMoCollection;

$config = new MTNMoMoConfig();

$collection = new MTNMoMoCollection($config);
```

**createTransaction()** opération permettant de demander un paiement à un consommateur (payeur). Le payeur est invité à autoriser le paiement. La transaction sera exécutée une fois que le payeur aura autorisé le paiement. La demande de paiement est en attente jusqu'à ce que la transaction soit autorisée ou refusée par le payeur ou qu'elle soit interrompue par le système. **La requête est asynchrone**.

```php

/**
 * Crée une nouvelle transaction pour demander un paiement.
 *
 * @param array $params Tableau qui contient 'amount', 'referenceExternalID', 'numberMoMo', 'description', and 'note'.
 * @param array $custom_params Paramètres personnalisés supplémentaires pour la transaction (facultatif).
 * @return array Renvoie un tableau contenant 'transactionId' et tout autre paramètre personnalisé.
 * @throws Exception Si les clés requises sont manquantes ou si la réponse indique une erreur.
 */

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
/**
 * Récupérer le statut d'une transaction par son ID de référence.
 *
 * @param string $xReferenceId L'ID de référence de la transaction.
 * @return array Retourne un tableau avec les détails de la transaction.
 * @throws Exception Si l'ID de référence de la transaction n'est pas valide ou si la demande échoue.
 */

$transaction = $collection->getTransaction($transactionId);
```

**getAccountBalance()** opération permettant d'obtenir le solde de son propre compte.

```php
/**
 * Récupérer le solde du compte pour le produit encaissement.
 *
 * @param string|null $currency Paramètre de devise facultatif pour des soldes spécifiques.
 * @return array Renvoie un tableau contenant les détails du solde du compte.
 * @throws Exception Si la demande échoue.
 */

$balance = $collection->getAccountBalance();
```

**getBasicUserInfo()** opération permettant de renvoyer les informations personnelles du titulaire du compte. L'opération ne nécessite aucun consentement de la part du titulaire du compte.

```php
/**
 * Récupérer les informations de base de l'utilisateur à partir de son numéro MoMo.
 *
 * @param string $numberMoMo Le numéro MoMo de l'utilisateur.
 * @return array Retourne un tableau contenant les informations de base de l'utilisateur.
 * @throws Exception Si la demande échoue.
 */

$numberMoMo = '46733123460';
$user_info = $collection->getBasicUserInfo($numberMoMo);
```
