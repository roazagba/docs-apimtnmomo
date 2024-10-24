# Configuration

### Créer un environnement sandbox utilisateur API ainsi que la clé secrète API.

Exécutez la commande ci-dessous pour créer un utilisateur API sandbox et sa clé secrète API.

```bash
momo-create-api-user {baseURL} {primaryKey} {providerCallbackHost}
```

Exemple:

```bash
momo-create-api-user https://sandbox.momodeveloper.mtn.com/ your_product_primary_key https://your-callback-url.com
```

- **baseURL** : L'URL de base pour l'API. Dans cet exemple, elle pointe vers l'environnement de test (sandbox) de MTN MoMo Developer qui est **https://sandbox.momodeveloper.mtn.com/**. Cela permet de définir l'URL de l'API à utiliser, que ce soit en mode test ou production.

- **primaryKey** : La clé primaire de l'API du produit (collection, disbursement, remittance), nécessaire pour effectuer des transactions avec le service de collecte. Elle est utilisée pour identifier l'application qui effectue les transactions.

- **providerCallbackHost** : L'URL vers laquelle les notifications ou retours d'informations seront envoyés.

Après exéxution de la commande vous aurez une réponse en console :

```text
Creating API and API Key Secrete user with the following details:
Base URL: https://sandbox.momodeveloper.mtn.com/
Primary Key: 57ca5f1907074bf590090041688d781d
Callback URL: http://localhost:8000
API User and API Key Secrete created successfully.
{
  "baseURL": "https://sandbox.momodeveloper.mtn.com/",
  "userID": "89630ce4-5756-44bd-bfea-45e1686e11c9",
  "primaryKey": "value",
  "apiKeySecret": "value",
  "targetEnvironment": "sandbox",
  "providerCallbackHost": "http://localhost:8000"
}

```

- **userID** : ID pour l'utilisateur API créé. Cet ID est utilisé pour authentifier l'utilisateur qui effectue les requêtes via l'API de produit avec la clé secrète.
- **apiKeySecret** : La clé secrète pour l'API du produit. C'est une clé sensible qui permet d'authentifier les requêtes de produit avec l'ID Utilisateur. Elle doit être protégée et ne jamais être exposée publiquement.
- **targetEnvironment** : Le type d'environnement à utiliser. Ici, il est défini sur "sandbox" pour indiquer qu'il s'agit d'un environnement de test. En production, cela serait par exemple pour le Bénin "mtnbenin".

### Variables d'environnement

- Sous Linux/Unix

```bash
export RA_BASE_URL="https://sandbox.momodeveloper.mtn.com/"
export RA_CURRENCY="EUR" # EUR pour le sandbox, en production pour Bénin c'est XOF
export RA_TARGET_ENVIRONNEMENT="sandbox"
export RA_CALLBACK_URL="http://localhost:8000"
export RA_COLLECTION_API_KEY_SECRET="apiKeySecret"
export RA_COLLECTION_PRIMARY_KEY="primaryKey"
export RA_COLLECTION_USER_ID="userID"
```

- Sous Windows

```bash
set RA_BASE_URL="https://sandbox.momodeveloper.mtn.com/"
set RA_CURRENCY="EUR" # EUR pour le sandbox, en production pour Bénin c'est XOF
set RA_TARGET_ENVIRONNEMENT="sandbox"
set RA_CALLBACK_URL="http://localhost:8000"
set RA_COLLECTION_API_KEY_SECRET="apiKeySecret"
set RA_COLLECTION_PRIMARY_KEY="primaryKey"
set RA_COLLECTION_USER_ID="userID"
```
