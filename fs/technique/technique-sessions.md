[Documentation Fournisseur](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Quelles sont les durées de vie des sessions et jetons de FranceConnect+ ? 

---

# Quelles sont les durées de vie des sessions et jetons de FranceConnect+ ?

FranceConnect+ gère plusieurs types de données ayant une durée de vie limitée lors du déroulé d'une authentification par OpenID Connect ou de la fourniture d'un jeton d'accès à une ressource protégée (cinématique OAuth2 classique). Chacune de ces données possède une durée de vie qui lui est propre au delà de laquelle elle doit être régénérée. En voici le détail :

| Type | Utilisé lors de ... | Durée de vie |
| ------ | ------ | ------ |
| Session Web | A chaque authentification et pour maintenir la session côté FranceConnect+ | 30 minutes sans action |
| Access Token | Récupération d'informations (phase 3 cinématique d'authentification / cinématique OAuth2) | 60 secondes |
| Authorization code | Code fourni lors du début de la démarche d'authentification, il sert ensuite à récupérer l'access token | 30 secondes |
| Consentement | Consentement donné par l'utilisateur pour l'accès à une ressource protégée (associée à un scope au sens OAuth2) | 5 secondes |

--- 