

---

# Comment utiliser les scopes OpenID Connect pour accéder aux données des utilisateurs ? 

Les données des utilisateurs mis à disposition d'un fournisseur de service est décrit à la page [Je veux connaitre les données que je peux récupérer de FranceConnect+ ](../projet/projet-donnees-fc+.md). Pour rappel les données d'identité accessible sont les suivantes : 

* Nom de naissance
* Prénoms
* Sexe
* Date de naissance
* [Code géographique INSEE de la ville de naissance](https://www.insee.fr/fr/information/2560452)
* [Code géographique INSEE du pays de naissance](https://www.insee.fr/fr/information/2560452)
* Nom d'usage

## Scope et Claims dans OpenID Connect

### Qu'est ce qu'un scope dans OpenID Connect ? 

> Les clients OpenID Connect utilisent des *scopes* tels que définis dans la section 3.3 de [OAuth 2.0 [RFC6749]](https://openid.net/specs/openid-connect-basic-1_0.html#RFC6749) pour spécifier quels privilèges d'accès sont demandés pour les *access token*. Les *scopes* associées aux *access token* déterminent les ressources qui seront disponibles lorsqu'elles sont utilisées pour accéder aux *endpoints* protégés par OAuth 2.0. Pour OpenID Connect, les *scopes* peuvent être utilisées pour demander que des ensembles d'informations spécifiques soient mis à disposition en tant que *claims*.

*Source: [OpenID Connect Basic Client Implementer's Guide 1.0](https://openid.net/specs/openid-connect-basic-1_0.html#Scopes)*

Le protocole OpenID Connect défini un certain nombre de [scopes standards](https://openid.net/specs/openid-connect-basic-1_0.html#Scopes) qu'il est possible d'étendre avec des *scopes* spécifiques supplémentaires en fonction du besoin de l'*identity provider*.

*En bref :* Les scopes permettent de définir l'ensemble des informations à disposition du fournisseur de service pour une cinématique. 

### Qu'est ce qu'un claim dans OpenID Connect ? 

Dans OpenId Connect, un claim est une information relative à l'utilisateur ou à la phase l'authentification. Ces informations peuvent être disponible soit dans l'ID Token, soit dans la réponse du UserInfo. Les claims retournés dans ces jetons dépendent des scopes associés à l'*access token*. 

Le protocole OpenId Connect defini un certain nombre de [claims standards](https://openid.net/specs/openid-connect-core-1_0.html#Claims).

*En Bref :* Les claims sont les informations sur l'utilisateur ou la phase d'authentification disponible dans l'ID Token ou dans la réponse de UserInfo. 

## Les scopes et les claims dans FranceConnect+

### Liste des claims 

#### Les données d'identité

| Champs       | Type   | Description | Format |
|--------------|--------|-------------|--------|
| given_name   | string | les prénoms séparés par des espaces (standard OpenIDConnect) | [A-Za-zÀÂÄÇÉÈÊËÎÏÔÖÙÛÜŸàâäçéèêëîïôöùûüÿÆŒæœ -'] |                                             |
| family_name  | string | le nom de famille de naissance (standard OpenIDConnect) |  [A-ZÀÂÄÇÉÈÊËÎÏÔÖÙÛÜŸÆŒ \-']|                                                 |
| birthdate    | string | la date de naissance au format YYYY-MM-DD (standard OpenIDConnect)                                    | [ YYYY-01-01 ] - (\d{4})-01-01 - (Présumé mois) [ YYYY-MM-01 ] - (\d{4})-(\d{2})-01 - (Présumé jours) [ YYYY-MM-DD ] - (\d{4})-(\d{2})-(\d{2}) |
| gender       | string | male pour les hommes, female pour les femmes (standard OpenIDConnect)| Masculin : M (male) Féminin : F (female) |  
| birthplace   | string | le code INSEE du lieu de naissance sur 5 chiffres (ou une chaîne vide si la personne est née à l'étranger). Une lettre peut être présente pour les personnes nées en corse.| Si né en France (Taille de 5) [(([0-8][0-9AB])|(9[0-8AB]))[0-9]{3}] - [Details](http://xml.insee.fr/schema/cog.html#CodeCommuneFrancaiseOuPaysOuTerritoireEtranger_stype) - [Liste](https://www.insee.fr/fr/information/3363419) <br/>En cas de pays étranger : Champs vide | 
| birthcountry | string | le code INSEE du pays de naissance sur 5 chiffres    | Pour les pays étrangers (Taille de 5 ) [99[0-9]{3}] - [Details](http://xml.insee.fr/schema/cog.html#CodePaysOuTerritoireEtranger_stype) Pour la France 99100  |


### Les données complémentaires

| Champs       | Type   | Description | Format |
|--------------|--------|-------------|--------|
| sub          | string | identifiant technique (standard OpenIDConnect) | 66 caractères hexa + lettre 'v' |
| email        | string | l'adresse électronique de contact de la personne (standard OpenIDConnect) | [RFC 5322](https://xml2rfc.tools.ietf.org/public/rfc/html/rfc5322.html#addrspec) |
| preferred_username | string | le nom d'usage (standard OpenIDConnect) | [A-ZÀÂÄÇÉÈÊËÎÏÔÖÙÛÜŸÆŒ \-'] |

### Les données sur l'authentification

Les claims relatifs à l'authentification disponible par FranceConnect+ sont des claims standards et sont disponible uniquement dans l'ID Token. Ces claims sont les suivants : 

- amr
- acr
- sid
- auth_time
- iss

[Plus d'informations sur ces claims](https://openid.net/specs/openid-connect-basic-1_0.html#IDToken)

### Correspondance entre scope et claims sur FranceConnect+

Le tableau suivant décris la liste des *claims* accessible en fonction des *scopes* associés à l'access token.

| Scope       | Claims   |
| --- | --- |
| openid | sub |
| gender | gender |
| birthdate | birthdate |
| birthcountry | birthcountry |
| birthplace | birthplace |
| given_name | given_name |
| family_name | family_name |
| email | email |
| preferred_username | preferred_username |
| profile | family_name, given_name, preferred_username, gender, birthdate |
| birth | birthplace, birthcountry |
| identite_pivot |given_name, family_name, birthdate, gender, birthplace, birthcountry  |