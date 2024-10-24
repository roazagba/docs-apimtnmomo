# Collection

```python
from raapimtnmomo.config import MTNMoMoConfig
from raapimtnmomo.mtn_momo_collection import MTNMoMoCollection
import random

config = MTNMoMoConfig()
```

**create_transaction()** opération permettant de demander un paiement à un consommateur (payeur). Le payeur est invité à autoriser le paiement. La transaction sera exécutée une fois que le payeur aura autorisé le paiement. La demande de paiement est en attente jusqu'à ce que la transaction soit autorisée ou refusée par le payeur ou qu'elle soit interrompue par le système.

```python

params = {
    'amount': '2',
    'referenceExternalID' : random.randint(1000000000000000, 9999999999999999),
    'numberMoMo': '22969411836',
    'description': 'transaction',
    'note': 'newtransaction'
}
collection = MTNMoMoCollection(config)

create_transaction = collection.create_transaction(params)
```

**get_transaction()** opération permettant de récupérer les détails de la transaction et du statut

```python
transactionId = create_transaction['transactionId']
transaction = collection.get_transaction(transactionId)
```

**get_account_balance()** opération permettant d'obtenir le solde de son propre compte.

```python
balance = collection.get_account_balance()
```

**get_basic_user_info()** opération permettant de renvoyer les informations personnelles du titulaire du compte. L'opération ne nécessite aucun consentement de la part du titulaire du compte.

```python
number_momo = '46733123460'
user_info = collection.get_basic_user_info(number_momo)
```
