[Documentation Fournisseur de Service](../README.md) > [Je gère un projet d'intégration de FranceConnect+](../README.md#je-g%C3%A8re-un-projet-dint%C3%A9gration-de-franceconnect) > eIDAS

---

# Qu'est ce qu'eIDAS et quels sont les niveaux de garantie de FranceConnect+ ?

## Qu'est ce que le règlement eIDAS ? 

> Le règlement n° 910/2014 sur l'identification électronique et les services de confiance pour les
transactions électroniques au sein du marché intérieur, dit règlement « eIDAS », est un règlement
européen qui a été adopté le 23 juillet 2014 par le Parlement européen et le Conseil de l'Union
Européenne. L'objectif de ce règlement est de mettre en place un cadre juridique propre à
susciter une confiance accrue dans les transactions électroniques au sein du marché intérieur. 
>
> Le règlement eIDAS s'applique à l’identification électronique et aux services de confiance
(faisant respectivement l’objet des chapitres II et III du présent document). Il accorde également
un effet juridique aux documents électroniques.

Source : [FAQ eIDAS de l'ANSSI](https://www.ssi.gouv.fr/uploads/2017/01/eidas_faq_anssi.pdf)

FranceConnect+ est concerné uniquement par le volet identification électronique du règlement. 

## Qu'est ce que les niveaux de garantie eIDAS ?

Le niveau de garantie eIDAS permettre d'apporter une garantie sur l'identité qui est fournie au Fournisseur de Service. Ils sont définis par le règlement eIDAS avec chacun des exigences différentes. 

> * **Faible :** à ce niveau, l’objectif est simplement de réduire le risque d’utilisation abusive ou d’altération de l’identité ;
> * **Substantiel :** à ce niveau, l’objectif est de réduire substantiellement le risque d’utilisation abusive ou d’altération de l’identité ;
> * **Élevé :** à ce niveau, l’objectif est d’empêcher l’utilisation abusive ou l’altération de l’identité.

Source : [Présentation du règlement eIDAS par l'ANSSI](https://www.ssi.gouv.fr/administration/reglementation/confiance-numerique/le-reglement-eidas/#:~:text=Substantiel%20%3A%20%C3%A0%20ce%20niveau%2C%20l,'alt%C3%A9ration%20de%20l'identit%C3%A9.)

Le détail des exigeances est défini par [le règlement d’exécution n°2015/1502 du 8 septembre 2015](http://eur-lex.europa.eu/legal-content/FR/TXT/PDF/?uri=CELEX:32015R1502&from=FR)

## Quels sont les niveaux eIDAS supportés par la plateforme FranceConnect+ ?

FranceConnect+ a été qualifié par l'ANSSI pour le niveau élevé en tant que moyen d'identité électronique, c'est à dire que FranceConnect+ répond aux exigences pour permette d'apporter un niveau de garantie élevé en tant que moyen d'identification électronique. A ce titre, FranceConnect apparait dans la [liste des produits qualifiés par l'ANSSI](https://www.ssi.gouv.fr/uploads/liste-produits-et-services-qualifies.pdf) dans la section *moyen d'identification életronique*.

Cependant, afin de pouvoir garantir un niveau élevé, il faut également que les Fournisseurs d'Identité soit également qualifié pour ce ce niveau. 

Actuellement, FranceConnect+ ne dispose que d'un seul Fournisseur d'Identité, L'identité Numérique La Poste, qui est qualifié pour le niveau substantiel par l'ANSSI. Ainsi, actuellement la plateforme FranceConnect+ ne peut délivrer des identités avec uniquement le niveau de garantie substantiel même s'il FranceConnect+ est déjà prêt pour délivrer des identités avec le niveau de garantie élevé. 

Le tableau ci-dessous récapitule les niveaux supportés par les deux plateformes FranceConnect et FranceConnect+. 

| Niveau de garantie | FranceConnect | FranceConnect+ |
| ------ | ------ | ------ |
| faible |  Oui | Non | 
| substantiel | Non | Oui | 
| élevé | Non | A venir |

## Schéma d'identification européen et passelle d'interopérabilité

Le règlement eIDAS demande aux états membre de se doter d'un schéma d'identification et de le rendre interopérable avec les aux états membre européen. 

Le schéma d'identification est le mécanisme d'un pays qui permet à un usager de s'authentifier et de s'identifier. 

L'objectif est de permettre à un usager d'un état membre d'accéder aux service d'un autre état membre en utilisant le schéma d'identification qu'il utilise habituellement. Cela peut permettre, par exemple, à un usager français d'accéder au service des impots belges.

Actuellement, la France ne dispose que d'un seul schéma d'identification utilisable par les autres états membre, il s'agit de FranceConnect+ combiné avec L'identité Numérique La Poste. Cependant, cela ne concerne que les services des autres états membres. 

Il est possible pour un fournisseur de service d'utiliser les schémas d'identification d'un autre état membre. 

## Quels sont les niveaux de garantie accessible via les schémas d'identification des autres états membre ? 

Les niveaux de garanties utilisables via les schémas d'idenitification des autres états membre sont les niveaux substantiels et élevés. Il n'est pas possible de demandés ou d'obtenir des identités de niveau de garantie faible via les schémas d'identification des autres états membres. 

## Comment utiliser les schémas d'identification des autres états membres ? 

L'accès aux schémas d'identification des autres états membres se fait exclusivement via la plateforme FranceConnect+. C'est la DINUM, qui opère FranceConnect et FranceConnect+, qui est chargé de faire le lien entre la plateforme FranceConnect+ et les schémas d'identification des autres états membre. 

### Comment avoir accès aux autres schémas d'identifications européens pour mon fournisseur de service ?

### Comment l'usager d'un autre état membre doit il faire pour accéder à un autre service


---