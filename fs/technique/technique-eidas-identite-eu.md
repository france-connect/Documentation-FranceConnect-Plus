[Documentation Fournisseur](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment récupérer les données d'identités provenant d'un pays européens via la noeud eIDAS français ? 

---

# Comment récupérer les données d'identités provenant d'un pays européens via la noeud eIDAS français ? 

Il est possible de permettre aux usagers des autres pays européens d'accéder à votre service en s'authentifiant avec le schéma d'identification de leur pays. 

Pour votre service, cela se passe en utilisant la plateforme FranceConnect+.

## Quelles sont les données d'identité accessible pour un usager européen ? 

| Claim | Obligatoire | Commentaire |
| ------ | ------ | ------ |
| openid | X | même format que pour une identité française |
| gender |   | `male`, `female` ou `unspecified` |
| birthdate | X | même format que pour une identité française, ne gère pas les présumés nées|
| birthplace | | Ne correspond pas à un COG. Le format est libre pour chaque pays. |
| given_name | X | Correspond au prénom de la personne. Ce n'est pa obligatoirement le prénom de naissance.|
| family_name | X | Contient le nom d'usage de la personne | 



## Comment savoir s'il s'agit d'une identité provenant d'un fournisseur d'identité français ou d'une identité européenne ?

Cette information est indiqué dans le claim *amr* qui peut contenir plusieurs valeurs. Il est nécessaire de demander cette information via la demande du claim spécifique *amr*.

| Valeur | Origine de l'identité |
| ------ | --------------------- |
| fr     | identité provenant d'un fournisseur d'identité français |
| eidas  | identité provenant d'un schéma d'identité d'un autre pays |

---

Voir aussi : 

- [Qu'est ce qu'eIDAS et quels sont les niveaux de garantie de FranceConnect+ ?](../projet/projet-niveau-eidas.md)
