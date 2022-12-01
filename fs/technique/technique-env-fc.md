[Documentation Fournisseur](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment accéder aux différents environnements de FranceConnect+ ?

---

# Comment accéder aux différents environnements de FranceConnect+ ?

FranceConnect met à disposition deux environnements : 

- intégration : à utiliser pour l'ensemble de vos développements et test hors production
- production : à utiliser uniquement pour votre service en production


## Accès à l'environnement d'intégration FranceConnect+

# Récupération des clés d'intégration

Pour accéder à l'intégration, après validation de votre demande d'habilitation, vous devez effectuer une [demande de création d'un fournisseur de service pour FranceConnect+](https://www.demarches-simplifiees.fr/commencer/demande-de-creation-d-un-fs-fc-plus).

## Accès à l'environnement d'intégration

Pour vous permettre de réaliser les développements liés à l'intégration de FranceConnect, nous mettons à disposition un environnement d'intégration. Les accès à cet environnement se font à travers des clés qui vous sont communiquées sur votre espace partenaire. 

Pour utiliser l'environnement d'intégration, il faut au préalable avoir : 
- avoir fait une demande datapass et que celle-ci soit validée
- avoir fait une demande de création d'un FS en environnement d'intégration FC+ et avoir reçu vos clés d'intégration

Sur notre environnement d'intégration, vous pouvez utiliser le fournisseur d'identité "Démonstration" dont les données sont modifiables ici : https://github.com/france-connect/identity-provider-example/blob/master/database.csv


Les adresses de notre environnement d'intégration sont les suivantes : 

| EndPoint | Adresse |
| ------ | ------ |
| Discovery URL | https://auth.integ01.dev-franceconnect.fr/api/v2/.well-known/openid-configuration | 
| Authorization | https://auth.integ01.dev-franceconnect.fr/api/v2/authorize |
| Token | https://auth.integ01.dev-franceconnect.fr/api/v2/token | 
| UserInfo | https://auth.integ01.dev-franceconnect.fr/api/v2/userinfo | 
| Logout | https://auth.integ01.dev-franceconnect.fr/api/v2/session/end | 

## Accès à l'environnement de production FranceConnect+

# Récupération des clés de production

Pour accéder à l'intégration, après qualification de votre intégration de FranceConnect+ dans votre service, vous devez effectuer une [demande de création d'un fournisseur de service pour FranceConnect+](https://www.demarches-simplifiees.fr/commencer/demande-de-creation-d-un-fs-fc-plus).

## Accès à l'environnement de production

Pour avoir accès à l'environnement de production FranceConnect+, il faut au préalable avoir : 

1. Reçu la qualification de vos développements par FranceConnect+ sur un environnement autre que votre production. 
2. Demandé une mise en production via le formulaire à votre disposition ( *TODO lien vers le formulaire de MEP FC+*)
3. Configuré votre fournisseur de service de production FranceConnect+ avec les clés de production qui vous ont été fournies par l'équipe FranceConnect. 

**Attention :** Il ne faut surtout pas utiliser les clés d'intégration que vous avez utilisées lors de vos développements avec votre Fournisseur de Service en production. Les clés d'intégration ne sont utilisables que sur l'environnement d'intégration FranceConnect+. De même, il n'est pas possible d'utiliser des clés de production de FranceConnect sur FranceConnect+. 


Les adresses de notre environnement de production sont les suivantes : 

| EndPoint | Adresse |
| ------ | ------ |
| Discovery URL | https://auth.franceconnect.gouv.fr/api/v2/.well-known/openid-configuration | 
| Authorization | https://auth.franceconnect.gouv.fr/api/v2/authorize |
| Token | https://auth.franceconnect.gouv.fr/api/v2/token | 
| UserInfo | https://auth.franceconnect.gouv.fr/api/v2/userinfo | 
| Logout | https://auth.franceconnect.gouv.fr/api/v2/session/end | 


---

Voir aussi :

- [Comment effectuer ma demande d'habilitation pour FranceConnect+ ?](../projet/projet-datapass.md)