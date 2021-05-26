# Les données usagers
Les données usagers sont fournies par les Fournisseurs d'Identité aux Fournisseurs de Service, via FranceConnect, conformément à l'habilitation obtenue via [datapass.api.gouv.fr](https://datapass.api.gouv.fr), et le choix des données réalisé par le fournisseur de service dans cette demande.

L'identité pivot permet d'identifier un utilisateur particulier.

* Nom de naissance
* Prénoms
* Sexe
* Date de naissance
* Code géographique INSEE de la ville de naissance
* Code géographique INSEE du pays de naissance

En complément, il est possible d'obtenir le nom d'usage. Cependant cette donnée n'est pas obligatoirement connue par tous les Fournisseurs d'Identité.

Vous pouvez avoir accès également à l'adresse email. Cette donnée de contact a également été vérifiée par le Fournisseur d'identité. Il est à remarquer que la donnée "adresse email" peut différer selon le Fournisseur d'Identité choisi par l'usager.

FranceConnect transmet systématiquement au Fournisseur de Service un identifiant unique pour chaque utilisateur : 

* Cet identifiant est spécifique à chaque Fournisseur de Service. Un même utilisateur aura donc un identifiant unique différent pour chacun des Fournisseurs de Service auxquels il accède. 
* Cet identifiant est le même quelque soit le Fournisseur d'Identité qui est utilisé par l'utilisateur. 

A noter que pour les niveaux de garantie d'identité eIDAS 2 et 3 (substantiel et élevé), les données d'identité fournies au fournisseur de service sont celles directement issues du fournisseur d'identité choisi par l'utilisateur, sans redressement RNIPP (INSEE). Ces données peuvent donc légèrement varier d'un fournisseur d'identité à l'autre, nous préconisons donc de réaliser le rapprochement/réconciliation sur la base de l'identifiant unique de l'utilisateur fourni par FranceConnect.