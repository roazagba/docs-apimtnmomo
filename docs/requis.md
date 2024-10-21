# Pré-requis

!> Avant l'intégration, assurez-vous d'avoir faire les étapes suivantes.

1. Créer un compte développer sur [https://momodeveloper.mtn.com](https://momodeveloper.mtn.com)
2. Souscrire aux produits que vous vous voulez utiliser à [https://momodeveloper.mtn.com/products](https://momodeveloper.mtn.com/products) Exemple: **collection**, **disbursement**, **remittance**

   - **Collection**: L'encaissement est un service qui permet aux partenaires Mobile Money de recevoir des paiements pour des biens et des services en utilisant MTN Mobile Money. Les services peuvent être offerts en face à face, comme MomoPay, ou à distance, à la fois hors ligne et en ligne. Les paiements peuvent être initiés par le client sur USSD/App/Web ou par le marchand, qui reçoit une demande de débit pour approbation.

     Une fois le service activé, un compte d'encaissement est créé pour le partenaire, sur lequel les fonds sont déposés/reçus. Le partenaire est en mesure d'effectuer des paiements ultérieurs à ses fournisseurs/partenaires/employés (B2B ou B2C) et/ou de liquider les fonds collectés sur leurs comptes bancaires respectifs.

     Le service offre la possibilité de collecter des paiements en ligne, des factures, des remboursements de prêts, des contributions à des activités et des versements pour des remboursements de services et de produits convenus d'un commun accord. Umeme, National Water, URA, NSSF, DSTV, pour n'en citer que quelques-uns, sont des exemples de partenaires qui collectent des factures.

   - **Disbursement**: Les décaissements sont un service qui permet aux partenaires de Mobile Money d'envoyer de l'argent en masse à différents destinataires en un seul clic. Cette configuration peut être exécutée manuellement (se connecter au système, télécharger la liste des bénéficiaires et déclencher les paiements) ou automatisée (nécessite une configuration unique des listes de bénéficiaires et des commandes pour effectuer le paiement).

     Voici quelques exemples de partenaires qui utilisent ce service : Les sociétés de paris pour payer les gagnants, les versements de fonds aux réfugiés/bénéficiaires, entre autres.

     Il est prévu que le partenaire ouvre un compte de décaissement auprès de MTN et que ce compte soit préfinancé pour permettre les paiements une fois que les demandes émanent du partenaire.

   - **Remittance**: Les transferts de fonds sont une solution qui permet à un client de transférer ou de recevoir des fonds de la diaspora vers le compte du destinataire de Mobile Money en monnaie locale. Il s'agit d'une solution automatisée dans laquelle l'argent est transféré en temps réel lorsque la demande arrive dans le système (elle fonctionne de la même manière que la solution automatisée de décaissement).

     L'expéditeur se connecte sur le Web/l'application/l'USSD (USSD uniquement pour les transferts sortants) ou se rend au point de vente de l'expéditeur pour envoyer de l'argent. Une demande est alors envoyée au système du partenaire local qui déclenche un paiement dans le portefeuille du destinataire.

     Le partenaire est tenu d'ouvrir un compte auprès de MTN et d'y charger des fonds pour faciliter le transfert de fonds (entrant et sortant).

3. Allez dans le profil developper [https://momodeveloper.mtn.com/profile](https://momodeveloper.mtn.com/profile), vous trouverez les clés primaire et secondaire de chaque produit.

   ```bash
   Primary Key => Subscription Key (Clé abonnement)
   ```

4. Cas d'utilisation du mode sandbox à [https://momodeveloper.mtn.com/api-documentation/testing](https://momodeveloper.mtn.com/api-documentation/testing)
