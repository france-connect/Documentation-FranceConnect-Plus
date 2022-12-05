
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
- [Comment déconnecter un utilisateur de FranceConnect+ ?](technique/technique-deconnexion.md)
- [Quelles sont les durées de vie des sessions et jetons de FranceConnect+ ?](technique/technique-sessions.md)


## Je veux connaitre les règles d'intégration du bouton dans mon service

- [Comment intégrer le bouton FranceConnect+ à mon service ?](technique/technique-boutons-fc.md)




# Gestion d'erreurs entre FranceConnect+ et le Fournisseur de Service

En tant qu'OpenID Connect provider, FranceConnect+ peut renvoyer toutes sortes d'erreurs à une application cliente. Pour ce faire, FranceConnect+ passe par le mécanisme de retour d'erreurs d'un fournisseur d'identité openid connect tel que décrit dans la norme ( http://openid.net/specs/openid-connect-core-1_0.html#AuthError, en particulier les sections 3.1.2.6 (authentification), 3.1.3.4 (jeton d'accès), 5.3.3 (service d'informations utilisateur) )
