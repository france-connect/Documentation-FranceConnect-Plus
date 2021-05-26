[Documentation Fournisseur de Service](README.md) > [Devenir Fournisseur de Service FranceConnect+](../README.md#je-veux-devenir-fournisseur-de-service) > Intégrer FranceConnect+ lorsque je suis déjà Fournisseur de Service pour FranceConnect

---

# Je suis déjà Fournisseur de Service pour FranceConnect, que dois je faire en plus pour devenir Fournisseur de Service pour FranceConnect+ ? 

FranceConnect+ étant une plateforme différente de FranceConnect, il est nécessaire de réaliser une intégration de FranceConnect+, en complément de l'intégration de FranceConnect. Vous devez donc suivre l'ensemble des étapes pour devenir Fournisseur de Service.

L'intégration de FranceConnect+ en tant que Fournisseur de Service est légèrement différente de celle de FranceConnect car elle nécessite des mesures de sécurités supplémentaires afin de répondre à des exigences de sécurité spécifiques aux niveaux de garantie subtantiel et élevé. Vos équipes de développement devront par conséquent réaliser des évolutions pour pouvoir s'intégrer à FranceConnect+. Les différences principales par rapport à FranceConnect sont les suivants: 

- une plateforme différente, donc 
    - des URLs différentes pour accéder aux environnements; 
    - des secrets différents pour chacun des environnements (intégration, production)
- un chiffrement et un signature sur les jetons transmis
- une utilisation de mode discovery d'OpenId Connect
- une exposition des clés publiques de chiffrement et de signature


Les plateformes FranceConnect et FranceConnect+ reposent toutes les deux sur le même protocole, à savoir OpenId Connect. Hormis les différences cités ci dessus, leur fonctionnement est similaire. Ainsi les intégrations de FranceConnect et FranceConnect+ sont très similaire et ne nécessite pas pour un Fournisseur de Service une charge d'intégration important pour devenir Fournisseur de Service pour FranceConnect+ si vous l'êtes déjà pour FranceConnect. 