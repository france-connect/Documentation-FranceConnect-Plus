[Documentation Fournisseur de Service](../README.md) > [Gerer un projet d'integration FranceConnect+](../README.md#je-veux-devenir-fournisseur-de-service) > Données accessible via FranceConnect+

---

# Je veux connaitre les données que je peux récupérer de FranceConnect+ 

Les données usagers sont fournies par les Fournisseurs d'Identité aux Fournisseurs de Service, via FranceConnect+, conformément à l'habilitation obtenue via [datapass.api.gouv.fr](https://datapass.api.gouv.fr), et le choix des données réalisé par le fournisseur de service dans cette demande.

L'identité pivot permet d'identifier un utilisateur particulier.

* Nom de naissance
* Prénoms
* Sexe
* Date de naissance
* [Code géographique INSEE de la ville de naissance](https://www.insee.fr/fr/information/2560452)
* [Code géographique INSEE du pays de naissance](https://www.insee.fr/fr/information/2560452)

En complément, il est possible d'obtenir le nom d'usage. Cependant cette donnée n'est pas obligatoirement connue par tous les Fournisseurs d'Identité. Cette donnée ne sera donc pas transmise systématiquement si vous la demandez.

Vous pouvez avoir accès également à l'adresse email. Cette donnée de contact a également été vérifiée par le Fournisseur d'identité. Il est à remarquer que la donnée "adresse email" peut différer selon le Fournisseur d'Identité choisi par l'usager.

FranceConnect+ transmet systématiquement au Fournisseur de Service un identifiant unique pour chaque utilisateur : 

* Cet identifiant est spécifique à chaque Fournisseur de Service. Un même utilisateur aura donc un identifiant unique différent pour chacun des Fournisseurs de Service auxquels il accède. 
* Cet identifiant est le même quelque soit le Fournisseur d'Identité qui est utilisé par l'utilisateur. 
* Cet identifiant n'est amené à changer quand dans le cas particulier où l'utilisateur a fait modifié ses données d'état civil. Dans tous les autres cas, cet identifiant sera systématiquement le même. 

Les données d'identité fournies au fournisseur de service sont celles directement issues du fournisseur d'identité choisi par l'utilisateur. Ces données peuvent donc légèrement varier d'un fournisseur d'identité à l'autre, nous préconisons donc de réaliser le rapprochement/réconciliation sur la base de l'identifiant unique de l'utilisateur fourni par FranceConnect+. Il est également possible de récupérer des données provenant du RNIPP en complément des données d'identités provenant du fournisseur d'identité. Cependant, ces données ne disposent pas du niveau de garantie substantiel ou élevé et doivent être utilisé uniquement pour faciliter le rapprochement/réconciliation.

--- 

Voir aussi : 

- [Comment utiliser les scopes OpenID Connect pour accéder aux données des utilisateurs ? ](../technique/technique-scope-fc.md)