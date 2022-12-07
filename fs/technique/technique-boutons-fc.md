[Documentation Fournisseur de Service](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment intégrer le bouton FranceConnect+ à mon service ?

---

# Comment intégrer le bouton FranceConnect+ à mon service ?

En fonction du type de service, il existe deux intégrations possibles du bouton FranceConnect+ : 
- intégration en se basant sur le Système de Design de l'État;
- intégration ne se basant pas sur le Système de Design de l'État.

## Intégration du Système de Design de l'État

Votre service doit utiliser le [systeme de Design de l'État](https://www.systeme-de-design.gouv.fr/). Celui-ci intègre directement un bouton FranceConnect+. Vous pouvez consulter directement dans la documentation du composant [Bouton FranceConnect](https://www.systeme-de-design.gouv.fr/elements-d-interface/composants/bouton-franceconnect).


## Intégration hors du systeme de Design de l'Etat

Les boutons d’action FranceConnect+ sont primordiaux dans l’usage du service. Il est obligatoire d’utiliser l’un des boutons proposés et aucun autre visuel pour la connexion des usagers.

Téléchargements :

* [FranceConnect-Plus-Boutons.zip](FranceConnect-Plus-Boutons.zip)


## Règles d'intégration du bouton FranceConnect+

Les règles suivantes doivent être respectées. Vous pouvez également les retrouver dans les [Guideline FranceConnect+](../images/technique/guidelines-fc%2B.png)

### Couleurs, Design du bouton

Le bouton FranceConnect+ est déclinable pour un affichage sur fond clair ou sombre. Veillez à utiliser celle adaptée au contraste. 

![theme clair et sombre FranceConnect+](../images/technique/technique-guidelines-fc%2B-themes.png)

Le design, les couleurs et le label du bouton FranceConnect+ ne peuvent pas être modifiés. L'état au survol doit être implémenté.

### Dimensions

La taille recommandée pour une utilisation optimale est de 60 pixels de haut par 245 px de large. Le bouton peut être plus grand, mais l'homothétie doit être respectée. 

![Taille de l'image 60 x 245 pixels](../images/technique/technique-guidelines-fc%2B-dimensions.png)

### Textes d'accompagnement

Au dessus du bouton FranceConnect+, il vous sera demandé d'ajouter systématiquement la phrase explicative *FranceConnect+ est la solution proposée par l'État, pour renforcer la sécurité de vos services en ligne les plus sensibles*. 

Sous le bouton FranceConnect+, il vous sera demandé d'ajouter systématiquement un lien avec le texte "Qu'est-ce que FranceConnect+" qui pointera vers le site https://franceconnect.gouv.fr/france-connect-plus. La phrase doit avoir la couleur et le comportement d'un lien et doit être positionnée sous le bouton FranceConnect+ avec un écart de 12 pixels. 

![Lien "Qu'est ce que FranceConnect+ sous le bouton FranceConnect+](../images/technique/technique-guidelines-fc%2B-lien.png)

### Positionnement du bouton FranceConnect+ par rapport aux autres modes d'authentification.

Le bouton FranceConnect+ **doit être distinct de vos moyens de connexion natifs et en première position si vous êtres un service public**. Il est important de dissocier visuellement les différents moyens d’authentification : 
- une séparation visible doit être mise en place entre eux ; 
- la mention "OU" doit également y figurer afin de faire comprendre à l'utilisateur qu'il peut choisir entre FranceConnect+ ou un autre mode de connexion/d'inscription.

![Intégration du bouton FranceConnect+ dans la page](../images/technique/technique-guidelines-fc%2B-position.png)

### Intégration dans votre service. 

Le bouton FranceConnect+ doit être présent dans la section de votre service permettant aux utilisateurs de s'y connecter.

Si votre service propose à vos utilisateurs de s'inscrire, le bouton FranceConnect+ doit être proposé également sur la page d'inscription. 

### À ne pas faire 

Lors de l'intégration du bouton FranceConnect+, il n'est pas autorisé de : 
 - déformer le bouton;
 - changer sa couleur; 
 - modifier son label.

 ![](../images/technique/technique-guidelines-fc%2B-ne-pas-faire.png)

