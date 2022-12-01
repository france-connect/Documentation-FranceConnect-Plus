
---

# Quels échanges ont lieu entre mon service et FranceConnect+ lors d'une cinématique ?


## Détail du fonctionnement

Le diagramme de flux représente entre  l'utilisateur, FranceConnect+ et votre service est le suivant.



<img src="../diagrams/diagram-sequence-fs-fc.png" alt="drawing" />

                        
La récupération de l'identité pivot doit être faite dans la suite immédiate des appels précédents (authentification et récupération du code). Le fait d'appeler ce Web service plus tard n'est aujourd'hui pas proposé.

---

Voir aussi : 

- [Comment FranceConnect+ utilise le protocole OpenId Connect ?](technique-oidc-fc.md)
- [Qu'est ce que le protocole OpenID Connect ?](technique-oidc.md)