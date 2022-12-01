[Documentation Fournisseur de Service](../../README.md) > [Devenir Fournisseur de Service FranceConnect+](../../README.md#je-veux-devenir-fournisseur-de-service) > Intégrer FranceConnect+ lorsque je suis déjà Fournisseur de Service pour FranceConnect

---

# Je suis déjà Fournisseur de Service pour FranceConnect, que dois je faire en plus pour devenir Fournisseur de Service pour FranceConnect+ ? 

## Demande d'habilitation

Même si vous êtes déjà fournisseur de service FranceConnect, il est nécessaire de faire une demande d'habilitation spécifique à FranceConnect+ via [datapass](https://datapass.api.gouv.fr/franceconnect/). Lors de votre demande, veuillez à bien indiquer que votre demande FranceConnect+ dans la section *Niveau de garantie attendu par votre service*.


## Intégration 

FranceConnect+ étant une plateforme différente de FranceConnect, il est nécessaire de réaliser une intégration de FranceConnect+, en complément de l'intégration de FranceConnect. Vous devez donc suivre l'ensemble des étapes pour devenir Fournisseur de Service.

L'intégration de FranceConnect+ en tant que Fournisseur de Service est légèrement différente de celle de FranceConnect car elle nécessite des mesures de sécurités supplémentaires afin de répondre à des exigences de sécurité spécifiques aux niveaux de garantie subtantiel et élevé. Vos équipes de développement devront par conséquent réaliser des évolutions pour pouvoir s'intégrer à FranceConnect+. Les différences principales par rapport à FranceConnect sont les suivants: 

- une plateforme différente, donc 
    - des URLs différentes pour accéder aux environnements; 
    - des secrets différents pour chacun des environnements (intégration, production)
- un chiffrement et un signature sur les jetons transmis
- une utilisation de mode discovery d'OpenID Connect
- une exposition des clés publiques de chiffrement et de signature


Les plateformes FranceConnect et FranceConnect+ reposent toutes les deux sur le même protocole, à savoir [OpenID Connect](https://openid.net/connect/). Hormis les différences cités ci dessus, leur fonctionnement est similaire. Ainsi les intégrations de FranceConnect et FranceConnect+ sont très similaire et ne nécessite pas pour un Fournisseur de Service une charge d'intégration important pour devenir Fournisseur de Service pour FranceConnect+ si vous l'êtes déjà pour FranceConnect. 

## Identifiant commun à FranceConnect et FranceConnect+

FranceConnect et FranceConnect+ fournissent un identifiant technique permettant d'identifier de manière unique un utilisateur pour votre service. Par défaut, cette identifiant est différent sur les deux plateforme. Il vous est possible, si vous en avez le besoin, de recevoir le même identifiant pour un même utilisateur pour votre service pour les deux plateformes. 

Pour pouvoir en bénéficier, il suffit de le préciser lors de votre demande de création de votre fournisseur de service. 