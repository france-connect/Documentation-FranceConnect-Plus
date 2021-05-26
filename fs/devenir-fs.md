[Documentation Fournisseur de Service](README.md) > Devenir Fournisseur de Service FranceConnect+ 

---

# Je veux devenir Fournisseur de Service FranceConnect+

## Quelles sont les étapes pour devenir Fournisseur de Service ? 

1. Vous consultez les conditions d'éligibilité à FranceConnect. Les conditions juridiques, de sécurité et de qualité de service sont détaillées dans nos [conditions générales d'utilisation](https://partenaires.franceconnect.gouv.fr/cgu). Le cadre d'implémentation et d'intégration est détaillé dans nos [spécifications ergonomiques](https://partenaires.franceconnect.gouv.fr/fcp/fournisseur-service#acceptance) **TODO** *mettre à jour le lien* .

2. Vous soumettez une demande d'habilitation  via [datapass.api.gouv.fr](https://datapass.api.gouv.fr/) et vous transmettez toutes les informations nécessaires à la validation de votre demande (respect du RGPD, contact du responsable technique, niveau de garantie eIDAS souhaité, données d'identité recueillies, etc). Votre demande est validée par le service juridique de la DINUM dans un délai moyen de 5 jours ouvrés.

3. ~~Si votre demande est acceptée, votre responsable technique reçoit un mail lui donnant accès à l'[espace partenaire](https://partenaires.franceconnect.gouv.fr/login). Cet espace vous permettra d'accéder aux ressources de développement et de test~~.

*Actuellement, notre espace partenaire n'est pas disponible pour FranceConnect+, pour cela, nous vous invitons à vous rapprocher du support partenaire pour accéder à vos ressources de développement et de test FranceConnect+* 

4. Vous présentez vos développements pour une qualification par l'équipe FranceConnect. La durée de cette phase de qualification dépend du [respect des prérequis ](https://partenaires.franceconnect.gouv.fr/monprojet/recetter/)(techniques, sécurité, fonctionnels, UX...). N'hésitez pas à soumettre vos maquettes de parcours en amont pour une pré-qualification fonctionnelle et UX anticipée.

5. Si votre implémentation est validée par notre équipe, vous recevez vos secrets pour passer en production.

## Quels sont les différences entre FranceConnect et FranceConnect+

La principale différences entre FranceConnect et FranceConnect+ est le niveau de garantie eIDAS supporté par la plateforme. Pour rappel, le règlement eIDAS prévoit trois niveau de garantie :

> - Faible : à ce niveau, l’objectif est simplement de réduire le risque d’utilisation abusive ou d’altération de l’identité ;
> - Substantiel : à ce niveau, l’objectif est de réduire substantiellement le risque d’utilisation abusive ou d’altération de l’identité ;
> - Élevé : à ce niveau, l’objectif est d’empêcher l’utilisation abusive ou l’altération de l’identité.

[[plus d'infos](https://www.ssi.gouv.fr/administration/reglementation/confiance-numerique/le-reglement-eidas/)]


La plateforme FranceConnect  supporte uniquement le niveau de garantie faible. C'est la plateforme FranceConnect+ qui assurent les niveaux de garantie supérieur, c'est à dire les niveaux de garantie Substantiel et Élevé. 


## Je suis déjà Fournisseur de Service pour FranceConnect, que dois je faire en plus pour devenir Fournisseur de Service pour FranceConnect+ ? 

FranceConnect+ étant une plateforme différente de FranceConnect, il est nécessaire de réaliser une intégration de FranceConnect+, en complément de l'intégration de FranceConnect. Vous devez donc suivre l'ensemble des étapes pour devenir Fournisseur de Service.

L'intégration de FranceConnect+ en tant que Fournisseur de Service est légèrement différente de celle de FranceConnect car elle nécessite des mesures de sécurités supplémentaires afin de répondre à des exigences de sécurité spécifiques aux niveaux de garantie subtantiel et élevé. Vos équipes de développement devront par conséquent réaliser des évolutions pour pouvoir s'intégrer à FranceConnect+. Les différences principales par rapport à FranceConnect sont les suivants: 

- une plateforme différente, donc 
    - des URLs différentes pour accéder aux environnements; 
    - des secrets différents pour chacun des environnements (intégration, production)
- un chiffrement et un signature sur les jetons transmis
- une utilisation de mode discovery d'OpenId Connect
- une exposition des clés publiques de chiffrement et de signature


Les plateformes FranceConnect et FranceConnect+ reposent toutes les deux sur le même protocole, à savoir OpenId Connect. Hormis les différences cités ci dessus, leur fonctionnement est similaire. Ainsi les intégrations de FranceConnect et FranceConnect+ sont très similaire et ne nécessite pas pour un Fournisseur de Service une charge d'intégration important pour devenir Fournisseur de Service pour FranceConnect+ si vous l'êtes déjà pour FranceConnect. 

---

Pages similaires : 
- [Acteurs à impliquer](pilotage-demarches-acteurs.md)
