
Documentation Fournisseur de Service

---

Vous souhaitez implémenter FranceConnect+ sur votre site? Vous êtes au bon endroit ! Cette documentation présente l'ensemble des informations à connaitre sur FranceConnect+

# Préambule

Cette documentation est à destination des Fournisseurs de Service souhaitant intégrer FranceConnect+. 
FranceConnect+ met à disposition du Fournisseur de Service des identités de niveau de garantie eIDAS Susbtantiel et Elevé. 
FranceConnect+ s'implémente sur une plateforme distincte de la plateforme FranceConnect qui reste dédiée aux identités de niveau de garantie "faible".

# Je veux devenir Fournisseur de Service 

Vous souhaitez devenir Fournisseur de Service pour FranceConnect+, voici les questions à vous poser : 

* [Quelles sont les étapes pour devenir Fournisseur de Service ?](pilotage/pilotage-etapes.md)
* [Quels sont les différents acteurs que je dois faire intervenir dans mon organisation pour devenir Fournisseur de Service ?](pilotage/pilotage-demarches-acteurs.md)
* [Quelles sont les différences entre FranceConnect et FranceConnect+ ?](pilotage/pilotage-differences-fc-fc+.md)
* [Quels sont les fournisseurs d'identités disponible sur FranceConnect+ ? ](pilotage/piloge-fi.md)
* [Je suis déjà Fournisseur de Service pour FranceConnect, que dois je faire en plus pour devenir Fournisseur de Service pour FranceConnect+ ?](pilotage/pilotage-integrer-fc+-apres-fc.md)


# Je gère un projet d'intégration de FranceConnect+

Vous avez lancé un projet pour devenir FranceConnect+ et vous souhaiter connaitre les différentes problématique d'intégration de FranceConnect+, voici les questions à vous poser : 

## Je souhaite savoir comment fonctionnement FranceConnect+

- [Quelles sont les données que je peux récupérer par FranceConnect+ sur mes usagers ?](projet/projet-donnees-fc+.md)
- [Qu'est ce qu'eIDAS et quels sont les niveaux de garantie de FranceConnect+ ?](projet/projet-niveau-eidas.md)
- [Quel est l'écosystème de FranceConnect+ ?](projet/projet-ecosysteme-fc+.md)
- [Comment puis-je réaliser des tests de FranceConnect+ avant de soumettre ma demande d'habilitation ?](projet-tests-sans-datapass.md)
- [Comment effectuer ma demande d'habilitation pour FranceConnect+ ?](../projet/projet-datapass.md)

# J'intègre FranceConnect+ dans mon service en ligne

## Je veux savoir comment fonctionne FranceConnect+

- [Qu'est ce que OpenID Connect ?](technique/technique-oidc.md)
- [Comment FranceConnect+ utilise OpenID Connect?](technique/technique-oidc-fc.md)

## Je veux savoir comment utiliser FranceConnect+

- [Comment accéder aux différents environnements de FranceConnect+ ?](technique/technique-env-fc.md)
- [Comment utiliser les scopes OpenID Connect pour accéder aux données des utilisateurs ? ](technique/technique-scope-fc.md)
- [Comment utiliser les niveaux de garantie eIDAS sur FranceConnect+ ?](technique/technique-eidas.md)


## Je veux connaitre les règles d'intégration du bouton dans mon service

- [Comment intégrer le bouton FranceConnect+ à mon service ?](technique/technique-boutons-fc.md)


# Je veux déconnecter l'utilisateur de FranceConnect

Pour les niveaux Substantiel et Elevé, FranceConnect+ ne gère pas de session utilisateur et demande systématique à l'utilisateur de se ré-authentifier auprès d'un Founisseur d'Identité.

Cependant, il est tout de même demandé au Fournisseur de Service de gérer : 
* la déconnexion auprès de FranceConnect
* la révocation de l’accès token

## Cinématique de déconnexion par un Fournisseur de Service

FranceConnect+ implémente la section sur la déconnexion en cours de spécification dans la norme OpenID Connect : https://openid.net/specs/openid-connect-frontchannel-1_0.html#RPLogout

FranceConnect+ ne gère pas la déconnexion de l'usager au service FranceConnect+ à la fermeture du navigateur.

Le Fournisseur de Service doit pouvoir déconnecter l'utilisateur de sa session FranceConnect. La cinématique globale est celle-ci :

1. L' utilisateur clique sur un lien de déconnexion présenté par le FS.
2. Le FS doit déconnecter l'utilisateur de son application et de sa session FranceConnect.
3. L' utilisateur est redirigé vers la page de retour spécifiée par le FS.
4. Le FS doit préciser l'URL où l'on doit rediriger l'utilisateur une fois qu'il a choisi de se déconnecter ou non de FranceConnect+ via le paramètre post_logout_redirect_uri, ainsi que passer l'id_token récupéré lors de l'authentification de l'utilisateur via le paramètre id_token_hint.

Il est obligatoire de renseigner les différentes urls de redirections de déconnexion dans les paramètres client

## Révocation de l'access token

En tant que Fournisseur de Service, vous avez la possibilité de révoquer un *access token*. Pour cela, FranceConnect+ respecte les spécifications OAuth 2.0 sur lesquelles se base OpenId Connect. La spécification de la révocation de token se trouve à cette adresse https://tools.ietf.org/html/rfc7009 

# Gestion d'erreurs entre FranceConnect+ et le Fournisseur de Service

En tant qu'OpenID Connect provider, FranceConnect+ peut renvoyer toutes sortes d'erreurs à une application cliente. Pour ce faire, FranceConnect+ passe par le mécanisme de retour d'erreurs d'un fournisseur d'identité openid connect tel que décrit dans la norme ( http://openid.net/specs/openid-connect-core-1_0.html#AuthError, en particulier les sections 3.1.2.6 (authentification), 3.1.3.4 (jeton d'accès), 5.3.3 (service d'informations utilisateur) )


# Les données de FranceConnect+ qui expirent

FranceConnect+ gère plusieurs types de données ayant une durée de vie limitée lors du déroulé d'une authentification par OpenID Connect ou de la fourniture d'un jeton d'accès à une ressource protégée (cinématique OAuth2 classique). Chacune de ces données possède une durée de vie qui lui est propre au delà de laquelle elle doit être régénérée. En voici le détail :

| Type | Utilisé lors de ... | Durée de vie |
| ------ | ------ | ------ |
| Session Web | A chaque authentification et pour maintenir la session côté FranceConnect+ | 30 minutes sans action |
| Access Token | Récupération d'informations (phase 3 cinématique d'authentification / cinématique OAuth2) | 60 secondes |
| Authorization code | Code fourni lors du début de la démarche d'authentification, il sert ensuite à récupérer l'access token | 30 secondes |
| Consentement | Consentement donné par l'utilisateur pour l'accès à une ressource protégée (associée à un scope au sens OAuth2) | 5 secondes |


# Glossaire


* **FC_URL :**  URL de FranceConnect+ 
* **FS_URL :** Votre URL, en tant que fournisseur de service  
* **FD_URL :** URL du fournisseur de données
* **CALLBACK_URL_DATA :** le callback du FS, communiqué lors de son inscription auprès de FC 
* **POST_LOGOUT_REDIRECT_URI :** L'URL de redirection après la demande de déconnexion FC 
* **CLIENT_ID :** Identifiant du FS, communiqué lors de son inscription auprès de FC 
* **CLIENT_SECRET :** Le secret du FS, communiqué lors de son inscription auprès de FC 
* **AUTHZ_CODE :** Code retourné (dans l'URL) par FC au FS lorsque ce dernier fait un appel sur le endpoint FC_URL/api/v1/authorize. Il est ensuite passé (dans le corps de la requête HTTP POST) lors de l'appel sur le endpoint FC_URL/api/v1/token
* **ACCESS_TOKEN :** oken retourné (dans le corps HTTP) par l'appel au endpoint FC_URL/api/v2/token. Il est ensuite passé lors de l'appel au endpoint FC_URL/api/v2/userinfo 
* **SCOPES :** Liste des scopes demandés séparés par des espaces (donc par %20 au format unicode dans l'URL)  
	
Voici la liste supportée par FranceConnect+ :

    * openid : obligatoire, permet de demander l'identifiant technique de l'utilisateur au format OpenIDConnect
    * profile : obligatoire, permet de récupérer l'essentiel de l'identité pivot. Si disponible, renvoie aussi le preferred_username
    * birth : obligatoire, permet de récupérer la ville et le département de naissance de la personne (identité pivot)
    * email : obligatoire, permet de récupérer l'adresse électronique de la personne

Cette liste de scopes est définie par la norme OpenIDConnect

L'identité pivot complète se récupère soit par le scope identite_pivot, soit en cumulant deux scopes différents (profile + birth) car les informations de ville et de département de naissance de la personne ne font pas partie des données pouvant être renvoyées en soumettant le scope 'profile' seul. Le découpage est fait ici dans un souci de se conformer à la norme.

* **ID_TOKEN :** Objet JWT retourné par l'appel au endpoint FC_URL/api/21/token. L'objet JWT est un objet JSON formatté et signé. Le JSON doit contenir ces six clés : aud,exp,iat,iss,sub et nonce.

Exemple de JWT : 

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwczovL2ZjcC5kb2NrZXIuZGV2LWZyYW5jZWNvbm5lY3QuZnIiLCJzdWIiOiI0ZDMyN2RkMWU0MjdkYWY0ZDUwMjk2YWI3MWQ2ZjNmYzgyY2NjNDA3NDI5NDM1MjFkNDJjYjJiYWU0ZGY0MWFmdjEiLCJhdWQiOiJhMGNkNjQzNzJkYjZlY2YzOWMzMTdjMGM3NGNlOTBmMDJkOGFkN2Q1MTBjZTA1NDg4M2I3NTlkNjY2YTk5NmJjIiwiZXhwIjoxNjE5NjA0NTE4LCJpYXQiOjE2MTk2MDQ0NTgsIm5vbmNlIjoiY3VzdG9tTm9uY2UxMSIsImlkcCI6IkZDIiwiYWNyIjoiZWlkYXMxIiwiYW1yIjpudWxsfQ.AdbcnBJluh1UZb4ylEM6oSoarHw-Cb_4--kFWfOJre4
```

Exemple de header du JWT :
```json
{
  "typ": "JWT",
  "alg": "HS256"
}
```

Exemple de payload du JWT :

```json
{
  "iss": "https://fcp.docker.dev-franceconnect.fr",
  "sub": "4d327dd1e427daf4d50296ab71d6f3fc82ccc40742943521d42cb2bae4df41afv1",
  "aud": "a0cd64372db6ecf39c317c0c74ce90f02d8ad7d510ce054883b759d666a996bc",
  "exp": 1619604518,
  "iat": 1619604458,
  "nonce": "customNonce11",
  "idp": "FC",
  "acr": "eidas1",
  "amr": null
}
```
Les champs *aud, exp, iat, iss, sub* sont des champs obligatoires de la norme OpenId Connect. Le *nonce* est un  paramètre obligatoirement envoyé lors de l'appel à `/authorization`. Le FS doit impérativement vérifier que la valeur correspond bien à celle qu'il a envoyée, et qui doit être liée à la session de l'utilisateur.

Si vous utilisez une librairie pour transformer le json en JWT, il génèrera une chaîne de caractères constitué de 3 chaînes base64 séparées par un point.


* **ID_TOKEN_HINT :** Objet JWT identique au format ID_TOKEN qui a été reçu lors de l'échange avec l'appel à FC_URL/api/v1/token et doit être passé en paramètre lors de l'appel à FC_URL/api/v2/logout
* **USER_INFO :**  Voir la section identité pivot
* **STATE :** Champ obligatoire, généré aléatoirement par le FS, que FC renvoie tel quel dans la redirection qui suit l'authentification, pour être ensuite vérifié par le FS. Il est utilisé afin d’empêcher l’exploitation de failles CSRF
* **NONCE :**	Champ obligatoire, généré aléatoirement par le FS que FC renvoie tel quel dans la réponse à l'appel à /token, pour être ensuite vérifié par le FS. Il est utilisé pour empêcher les attaques par rejeu
* **SUB :** Identifiant technique (unique et stable dans le temps pour un individu donné) fourni par FranceConnect+ au FS. Le SUB est présent dans l'IdToken retourné au FS ainsi que dans les informations d'identité. Le SUB retourné par FranceConnect+ est spécifique à chaque fournisseur de service (i.e: Un usager aura toujours le même SUB pour un Fournisseur de Service donné, en revanche il aura un SUB différent par Fournisseur de Service qu'il utilise).
