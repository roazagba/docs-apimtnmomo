# Configuration

```bash
php artisan vendor:publish --provider="Roazagba\ApiMTNMomo\Providers\MTNMoMoServiceProvider" --tag="config"
```

### Créer un environnement sandbox utilisateur API ainsi que la clé secrète API.

```bash
php artisan momo:create-api-user {baseURL} {primaryKey} {providerCallbackHost}
```

- **baseURL** : L'URL de base pour l'API. Dans cet exemple, elle pointe vers l'environnement de test (sandbox) de MTN MoMo Developer qui est **https://sandbox.momodeveloper.mtn.com/**. Cela permet de définir l'URL de l'API à utiliser, que ce soit en mode test ou production.

- **primaryKey** : La clé primaire de l'API du produit (collection, disbursement, remittance), nécessaire pour effectuer des transactions avec le service de collecte. Elle est utilisée pour identifier l'application qui effectue les transactions.

- **providerCallbackHost** : L'URL vers laquelle les notifications ou retours d'informations seront envoyés.

Exemple:

```bash
php artisan momo:create-api-user https://sandbox.momodeveloper.mtn.com/ your_product_primary_key https://your-callback-url.com
```

Après exéxution de la commande vous aurez une réponse en console :

```text
[baseURL] => https://sandbox.momodeveloper.mtn.com/
[userID] => 6eb8a48f-f113-444c-97df-a3b7f088a6f2
[primaryKey] => 85a5f074bf59202441688d781dks65
[apiKeySecret] => 6eb444c8a48fea6ec3a39985a5f074bf5
[targetEnvironment] => sandbox
[providerCallbackHost] => https://your-callback-url.com
```

- **userID** : ID pour l'utilisateur API créé. Cet ID est utilisé pour authentifier l'utilisateur qui effectue les requêtes via l'API de produit avec la clé secrète.
- **apiKeySecret** : La clé secrète pour l'API du produit. C'est une clé sensible qui permet d'authentifier les requêtes de produit avec l'ID Utilisateur. Elle doit être protégée et ne jamais être exposée publiquement.
- **targetEnvironment** : Le type d'environnement à utiliser. Ici, il est défini sur "sandbox" pour indiquer qu'il s'agit d'un environnement de test. En production, cela serait par exemple pour le Bénin "mtnbenin".

### Variables d'environnement dans le fichier .env

```env
RA_BASE_URL="https://sandbox.momodeveloper.mtn.com/"
RA_CURRENCY="EUR" # EUR pour le sandbox, en production pour Bénin c'est XOF
RA_TARGET_ENVIRONNEMENT="sandbox"
RA_CALLBACK_URL="http://localhost:8000"
RA_COLLECTION_API_KEY_SECRET="apiKeySecret"
RA_COLLECTION_PRIMARY_KEY="primaryKey"
RA_COLLECTION_USER_ID="userID"
```
