# Glossaire

#### **FC_URL:**
URL de FranceConnect+ 

#### **FS_URL:**
Votre URL, en tant que fournisseur de service  

#### **FD_URL:**
URL du fournisseur de données

#### **CALLBACK_URL_DATA:**
le callback du FS, communiqué lors de son inscription auprès de FC 
#### **POST_LOGOUT_REDIRECT_URI:**
L'URL de redirection après la demande de déconnexion FC 

#### **CLIENT_ID:**
Identifiant du FS, communiqué lors de son inscription auprès de FC 

#### **CLIENT_SECRET:**
Le secret du FS, communiqué lors de son inscription auprès de FC 

#### **AUTHZ_CODE:**
Code retourné (dans l'URL) par FC au FS lorsque ce dernier fait un appel sur le endpoint FC_URL/api/v1/authorize. Il est ensuite passé (dans le corps de la requête HTTP POST) lors de l'appel sur le endpoint FC_URL/api/v1/token

#### **ACCESS_TOKEN:**
Token retourné (dans le corps HTTP) par l'appel au endpoint FC_URL/api/v2/token. Il est ensuite passé lors de l'appel au endpoint FC_URL/api/v2/userinfo

#### **SCOPES:**
Liste des scopes demandés séparés par des espaces (donc par %20 au format unicode dans l'URL)  
	
Voici la liste supportée par FranceConnect+ :

    * openid : obligatoire, permet de demander l'identifiant technique de l'utilisateur au format OpenIDConnect
    * profile : obligatoire, permet de récupérer l'essentiel de l'identité pivot. Si disponible, renvoie aussi le preferred_username
    * birth : obligatoire, permet de récupérer la ville et le département de naissance de la personne (identité pivot)
    * email : obligatoire, permet de récupérer l'adresse électronique de la personne

Cette liste de scopes est définie par la norme OpenIDConnect

L'identité pivot complète se récupère soit par le scope identite_pivot, soit en cumulant deux scopes différents (profile + birth) car les informations de ville et de département de naissance de la personne ne font pas partie des données pouvant être renvoyées en soumettant le scope 'profile' seul. Le découpage est fait ici dans un souci de se conformer à la norme.

#### **ID_TOKEN:**
Objet JWT retourné par l'appel au endpoint FC_URL/api/21/token. L'objet JWT est un objet JSON formatté et signé. Le JSON doit contenir ces six clés : aud,exp,iat,iss,sub et nonce.

Exemple de JWT : 

```
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwczovL2ZjcC5kb2NrZXIuZGV2LWZyYW5jZWNvbm5lY3QuZnIiLCJzdWIiOiI0ZDMyN2RkMWU0MjdkYWY0ZDUwMjk2YWI3MWQ2ZjNmYzgyY2NjNDA3NDI5NDM1MjFkNDJjYjJiYWU0ZGY0MWFmdjEiLCJhdWQiOiJhMGNkNjQzNzJkYjZlY2YzOWMzMTdjMGM3NGNlOTBmMDJkOGFkN2Q1MTBjZTA1NDg4M2I3NTlkNjY2YTk5NmJjIiwiZXhwIjoxNjE5NjA0NTE4LCJpYXQiOjE2MTk2MDQ0NTgsIm5vbmNlIjoiY3VzdG9tTm9uY2UxMSIsImlkcCI6IkZDIiwiYWNyIjoiZWlkYXMxIiwiYW1yIjpudWxsfQ.AdbcnBJluh1UZb4ylEM6oSoarHw-Cb_4--kFWfOJre4
```

Exemple de header du JWT :
```json
{
  "typ": "JWT",
  "alg": "HS256"
}
```

Exemple de payload du JWT :

```json
{
  "iss": "https://fcp.docker.dev-franceconnect.fr",
  "sub": "4d327dd1e427daf4d50296ab71d6f3fc82ccc40742943521d42cb2bae4df41afv1",
  "aud": "a0cd64372db6ecf39c317c0c74ce90f02d8ad7d510ce054883b759d666a996bc",
  "exp": 1619604518,
  "iat": 1619604458,
  "nonce": "customNonce11",
  "idp": "FC",
  "acr": "eidas1",
  "amr": null
}
```
Les champs *aud, exp, iat, iss, sub* sont des champs obligatoires de la norme OpenId Connect. Le *nonce* est un  paramètre obligatoirement envoyé lors de l'appel à `/authorization`. Le FS doit impérativement vérifier que la valeur correspond bien à celle qu'il a envoyée, et qui doit être liée à la session de l'utilisateur.

Si vous utilisez une librairie pour transformer le json en JWT, il génèrera une chaîne de caractères constitué de 3 chaînes base64 séparées par un point.

#### **ID_TOKEN_HINT:**
Objet JWT identique au format ID_TOKEN qui a été reçu lors de l'échange avec l'appel à FC_URL/api/v1/token et doit être passé en paramètre lors de l'appel à FC_URL/api/v2/logout

#### **USER_INFO:**
Voir la section identité pivot

#### **STATE:**
Champ obligatoire, généré aléatoirement par le FS, que FC renvoie tel quel dans la redirection qui suit l'authentification, pour être ensuite vérifié par le FS. Il est utilisé afin d’empêcher l’exploitation de failles CSRF

#### **NONCE :**
Champ obligatoire, généré aléatoirement par le FS que FC renvoie tel quel dans la réponse à l'appel à /token, pour être ensuite vérifié par le FS. Il est utilisé pour empêcher les attaques par rejeu

#### **SUB:**
Identifiant technique (unique et stable dans le temps pour un individu donné) fourni par FranceConnect+ au FS. Le SUB est présent dans l'IdToken retourné au FS ainsi que dans les informations d'identité. Le SUB retourné par FranceConnect+ est spécifique à chaque fournisseur de service (i.e: Un usager aura toujours le même SUB pour un Fournisseur de Service donné, en revanche il aura un SUB différent par Fournisseur de Service qu'il utilise).
