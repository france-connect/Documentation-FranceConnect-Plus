
---

# Comment utiliser les niveaux de garantie eIDAS sur FranceConnect+ ?

## Les niveaux eIDAS disponible sur la plateforme FranceConnect+

La plaforme FranceConnect+ est qualifié pour fournir des identités de niveau de garantie eIDAS substantiel et élevé. Le niveau de garantie faible n'est pas supporté. Si vous souhaitez obtenir des identités ayant un niveau de garantie faible, vous devez pour cela utiliser la plateforme FranceConnect. 

## Spécifier un niveau de garantie eIDAS souhaité lors de la cinématique FranceConnect+ ?

### Utilisation du paramètre *acr_values*

FranceConnect+ s'appuie sur le paramètre *acr_values* de la norme [OpenID Connect](http://openid.net/specs/openid-connect-basic-1_0.html#RequestParameters) pour permettre de préciser le niveau de garantie attendu par votre fournisseur de service. Il s'agit d'un paramètre optionnel. Si celui-ci n'est pas indiqué dans les paramètre de la requête, alors c'est le niveau de garantie le plus élevé supporté par la plateforme qui sera pris en compte, c'est à dire le niveau élevé. 

Les valeurs du paramètre à indiquer en fonction du niveau de garantie souhaitez sont les suivantes : 

- eidas2 : niveau substantiel
- eidas3 : niveau élevé

Exemple d'appel précisant un niveau eIDAS minimum :

```
https://fcp.integ01.dev-franceconnect.fr/api/v2/authorize?response_type=code&client_id=123456&redirect_uri=https%3A%2F%2Ffournisseur-de-service.dev-franceconnect.fr%2Flogin-callback&scope=openid%20profile%20email%20address%20phone%20preferred_username%20email%20address%20phone%20preferred_username&state=randomValue&nonce=randomValue&acr_values=eidas2
```

A noter que si la valeur du paramètre *acr_values* est *eidas1*, FranceConnect+ retournera une erreur indiquant que le niveau de garantie demandé n'est pas supporté par la plateforme FranceConnect+. Cette valeur correspond au niveau de garantie faible et est supporté exclusivement par la plateforme FranceConnect. 

Toute valeur différente de *eidas1*, *eidas2* et *eidas3* sera ignoré. 


### Impact pour l'utilisateur.

Lorsqu'un niveau de garantie eIDAS est demandé, alors l'utilisateur ne se verra proposer que les fournisseurs d'identités qui peuvent satisfaire sa demande. 

Ainsi, si le niveau demandé est *eidas2*, alors tous les fournisseurs d'identités disponible sur FranceConnect+ seront proposés à l'utilisateur. Si le niveau demandé est *eidas3*, alors seuls les fournisseurs d'identités pouvant fournir des identités de niveau élevé seront proposé à l'utilisateur.

## Contrôler le niveau de garantie de l'identité récupérée  

Le niveau de garantie de l'identité récupéré auprès de FranceConnect+ est indiqué dans le claim *acr* présent dans l'[ID Token](https://openid.net/specs/openid-connect-basic-1_0.html#IDToken). 

Comme indiqué dans la norme [OpenID Connect](https://openid.net/specs/openid-connect-basic-1_0.html#IDTokenValidation), votre fournisseur de service doit s'assurer que le niveau de garantie de l'identité récupéré auprès de FranceConnect+ est bien conforme à celui attendu. 

Les valeurs possible pour le claim *acr* sont les suivantes : 

- eidas2 : niveau substantiel
- eidas3 : niveau élevé


Il est de la responsabilité du Fournisseur de service de s'assurer que le niveau retourné est au moins égal ou supérieur à celui demandé (si eidas2 est demandé, eidas3 doit être accepté tout comme eidas2).

---

Voir aussi : 

- [Qu'est ce qu'eIDAS et quels sont les niveaux de garantie de FranceConnect+ ?](../projet/projet-niveau-eidas.md)
- [Comment FranceConnect+ utilise le protocole OpenId Connect ? ](technique-oidc.md)