[Documentation Fournisseur de Service](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment déconnecter un utilisateur de FranceConnect+ ?

---

# Comment déconnecter un utilisateur de FranceConnect+ ?

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

---

Voir aussi : 

- [Comment FranceConnect+ utilise le protocole OpenId Connect ?](technique-oidc-fc.md)
- [Qu'est ce que le protocole OpenID Connect ?](technique-oidc.md)