[Documentation Fournisseur](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment FranceConnect+ utilise le protocole OpenId Connect ?

---

# Comment FranceConnect+ utilise le protocole OpenId Connect ? 

FranceConnect+ met en oeuvre le protocole OpenID Connect pour permettre à un fournisseur de service de déléguer à FranceConnect+ l'identificiation et l'authentification des usagers, ainsi que la gestion des consentements qui sont nécessaire à la transmission des données personnelles des utilisateurs auprès du fournisseur de service.  

## Les acteurs

Pour rappel, le protocole OpenID Connect défini les acteurs suivants : *User*, *Relying Party* et *OpenID Provider*. 

OpenId Connect fait intervenir 3 acteurs : 

| Acteur OpenId Connect | Acteur dans le contexte FranceConnect+ |
| ------ | ------ |
| User |  Usager du fournisseur de service |
| Relying Party | Fournisseur de service | 
| OpenID Provider | FranceConnect+ |

## Flow OpenID Connect

Le protocole OpenID Connect propose différents *flow* permettant de récupérer des tokens. FranceConnect+ n'implémente que [Authorization code flow](https://openid.net/specs/openid-connect-core-1_0.html#CodeFlowAuth).

## Discovery Mode

Le protocole OpenID Connect permet à *l'Identity Provider* d'exposer à *Relying Party* de récupérer dynamiquement ses données de configuration (*meta-data*). 

[Plus d'information sur OpenID Connect Discovery](https://openid.net/specs/openid-connect-discovery-1_0.html)

FranceConnect+ expose ses méta-data via les discovery url suivante : 

| Environnement | Adresse |
| ------ | ------ |
| Integration | https://auth.integ01.dev-franceconnect.fr/api/v2/.well-known/openid-configuration | 
| Production | https://auth.franceconnect.gouv.fr/api/v2/.well-known/openid-configuration |



## Signature et chiffrement des jetons

FranceConnect+ permet de récupérer différents types de jetons : 

| Jeton | Format |
| --- | --- |
| *access token* | chaine de caractères |
| *id_token* | JWT | 
| *user info* | JWT | 

L'ensemble de jetons JWT fournis par FranceConnect+, c'est à dire l'ID Token et les *User Info* sont chiffrés et signés afin de garantir un niveau de confidentialité et d'intégrité afin de satisfaire les exigences des niveaux de garantie subtantiel et élévée défini dans le règlement eIDAS. 

### Signature des jetons 

Les jetons sont **signés** par FranceConnect en utilisant les clés de chiffrement de FranceConnect+ afin de permettre au fournisseur de service de **s'assurer que ces deux jetons sont bien emis par FranceConnect+**. Le fournisseur de service doit donc vérifier la signature des jetons en ayant pris le soin de récupérer les clés publiques de signature de FranceConnect+. 

La **signature** permet de garantir **l'intégrité** et **l'authenticité** des données échangées. 

## Chiffrement des jetons 

Les jetons sont **chiffrés** par FranceConnect en utilisant un des clés publiques de chiffrement mis à disposition par le fournisseur de service afin de **s'assurer que seul le fournisseur de service ne puisse consulter** les informations présentes dans ces jetons. Le fournisseur de service doit mettre à disposition de FranceConnect+ ses clés publiques de chiffrement.   

Le **chiffrement** permet de garantir la **confidentialité** des données échangées.

## Algorithme de signature et de chiffrement

Tous les échanges de jetons JWT entre FranceConnect+ et le Fournisseur de Service sont signés et chiffrés en utilisant les algorithmes suivants :

**Signature de jetons par FranceConnect+** :

- Asymétrique : 

       - ES256 (EC + SHA256)

**Chiffrement des jetons (jwe+jws)** :

- Hybride :

      - RSA-OEAP + AES256-GCM 
      - ECDH-ES + AES256-GCM

Les spécifications des algorithmes de signatures et de chiffrements utilisés sont les suivantes :

* [JWA - https://tools.ietf.org/html/rfc7518](https://tools.ietf.org/html/rfc7518)
* [JWS - https://tools.ietf.org/html/rfc7515#appendix-A.3](https://tools.ietf.org/html/rfc7515#appendix-A.3)
* [JWE - https://tools.ietf.org/html/rfc7516#appendix-A.1](https://tools.ietf.org/html/rfc7516#appendix-A.1)

#### Exposition des clés de singature

Les clés publiques de signature de FranceConnect+ sont disponibles via la *JWKS URL* présente dans les méta-data de la *Discovery URL* à l'adresse suivantes et sont changées régulièrement :

| Environnement | adresses du endpoint |
| ------ | ------ |
| intégration | https://auth.integ01.dev-franceconnect.fr/api/v2/jwks |
| production | https://auth.franceconnect.gouv.fr/api/v2/jwks |  

#### Exposition des clés de chiffrement

Les clés publiques de chiffrement du fournisseur de service doivent être exposées à FranceConnect+ par le fournisseur de service sous la forme d'une *URL* au format JWK. 

[Plus d'information sur le JWK](https://datatracker.ietf.org/doc/html/rfc7517)

---

Voir aussi : 

- [Qu'est ce que le protocole OpenID Connect ?](technique-oidc.md)
- [Quels échanges ont lieu entre mon service et FranceConnect+ lors d'une cinématique ?](technique-oidc-flux.md)
