[Documentation Fournisseur](../README.md) > [J'intègre FranceConnect+ dans mon service en ligne](../README.md#jintègre-franceconnect-dans-mon-service-en-ligne) > Comment intégrer le bouton FranceConnect+ à mon service ?

---

# Comment intégrer le bouton FranceConnect+ à mon service ?

En fonction du type de service, il existe deux intégration possible du bouton FranceConnect+ :  

## Intégration du Systeme de Design de l'Etat

Votre service doit utiliser le [systeme de Design de l'Etat](https://www.systeme-de-design.gouv.fr/). Celui-ci intègre directement un bouton FranceConnect+. Vous pouvez consulter directement dans la documentation du composant [Bouton FranceConnect](https://www.systeme-de-design.gouv.fr/elements-d-interface/composants/bouton-franceconnect).

## Intégration hors du systeme de Design de l'Etat

Les boutons d’action FranceConnect+ sont primordiaux dans l’usage du service. Il est obligatoire d’utiliser l’un des boutons proposé et aucun autre visuel pour la connexion des usagers.

Pour les boutons en svg, lors de l'utilisation d'une image veuillez préciser la taille du bouton.

Téléchargements :

* [FranceConnect-Plus-Boutons.zip](FranceConnect-Plus-Boutons.zip)

## Règles d'intégration du bouton FranceConnect+

Les règles suivantes doivent être respectées:

- le design, les couleurs et le label du bouton FranceConnect+ ne peuvent pas être modifiés,
- le bouton bleu FranceConnect+ est à utiliser en priorité,
- l'état au survol doit être implémenté,
- la taille recommandée pour une utilisation optimale est de 60 pixels de haut par 230 px de large,
- le bouton FranceConnect+ doit être positionné en premier mode d'authentification,
- il doit être présent dans les sections connexion et inscription (si applicable) du site,
- il doit être séparé des autres modes de connexion/d'inscription:

    Il est important de dissocier visuellement les différents moyens d’authentification : une séparation visible doit être mise en place entre eux.
    La mention "OU" doit également y figurer afin de faire comprendre à l'utilisateur qu'il peut choisir entre FranceConnect+ ou un autre mode de connexion/d'inscription.
    

- Au dessus du bouton FranceConnect+, il vous sera demandé d'ajouter systématiquement la phrase explicative "FranceConnect+ est la solution proposée par l'État, pour renforcer la sécurité de vos services en ligne les plus sensibles". 
- sous le bouton FranceConnect+, il vous sera demandé d'ajouter systématiquement un lien avec le texte "Qu'est-ce que FranceConnect+" qui pointera vers le site https://franceconnect.gouv.fr/france-connect-plus.
