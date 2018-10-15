# TP1 Cloud Computing: restaurant


## Summary
Application web client/Server heberger sur cloud
Les instructions qui suivent on été réaliser sur Windows 
## Prérequis 
* Compte github - [Création de Compte](https://github.com)
* Compte sur Openshift - [Création de Compte](https://manage.openshift.com)

## Outils 

* eclipse oxygen java EE- [Télécharger] ( https://www.eclipse.org/downloads/packages/release/oxygen/3a)
* Open shift-origin-client-tools [Télécharger](https://github.com/openshift/origin/releases)
* GitHub desktop [Télécharger]()
# Installation JBoss

 ### Eclipse Mark place
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss1.png)
 ### Rechercher Jboss
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss2.png)
 ### Sélection les Plugin à installer (de préférence tous)
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss3.png)
 ### Confirmer
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss4.png)
 ### 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/joss5.png)
 
## Détails sur le développement
L'application client/Server a été réaliser sur le Framework Spring(projet maven), en utilisant l'architecture de micro-service classic <br>
### Le server offre 3 points d'entrer à savoir :
- Obtenir la liste des restaurant (supporte un paramètre true:par ordre décroissant, false sans ordre) <br>
  En local : http://localhost:9101/restaurants (méthode GET)
- Récupération d'un restaurant en fonction de son identifiant <br> 
  En local : http://localhost:9101/restaurants/1  (méthode GET)
- En fin ajouter une évaluation à un restaurant (méthode POST)<br>
 En local : http://localhost:9101/addnote<br>
 
 Ainsi tout foie on peut changer le port d'exécution du server, cela se réalise dans le fichier : [server/src/main/resources/application.properties](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/application.properties)
```xml
spring.application.name=microservice-restaurant

server.port:9101

#Configurations H2
spring.jpa.show-sql=true
spring.h2.console.enabled=true

#défini l'encodage pour data.sql
spring.datasource.sql-script-encoding=UTF-8
 ```

 <br> ou ajouter des restaurant static fichier : [server/src/main/resources/data.sql](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/data.sql)
```
INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG ) VALUES (0, 'Restaurant1', 'Spectialité poulet', 10.0, 10.0, 10.0, 10.0,'0.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG) VALUES (1,  'Restaurant2', 'Spectialité patte', 10.0, 10.0, 10.0, 10.0,'1.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG ) VALUES (2, 'Restaurant2', 'Spectialité Brochette', 10.0, 10.0, 10.0, 10.0,'2.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG) VALUES (3, 'Restaurant3', 'Spectialité Parisien', 10.0, 10.0, 10.0, 10.0,'3.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG ) VALUES (4, 'Restaurant4', 'Spectialité Chinois', 10.0, 10.0, 10.0, 10.0,'4.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG ) VALUES (5, 'Restaurant5', 'Spectialité pizza', 10.0, 10.0, 10.0, 10.0,'5.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE ,IMAG) VALUES (6, 'Restaurant6', 'Spectialité riz', 10.0, 10.0, 10.0, 10.0,'6.jpg');

INSERT INTO RESTAURANT (ID, NOM,DESCRIPTION , MOYEN,QNOURITURE , QSALLE, QSERVICE,IMAG ) VALUES (7 , 'Restaurant7', 'Spectialité mechou', 5.0, 10.0, 10.0, 10.0,'7.jpg');
 ```

### Coté Client 
Pour éviter des bugs, il est préférable de lancer le <b>Server</b> et de mettre l'adresse du server dans le ficher [RestaurantProxy.java](https://github.com/karimouseyni/RestaurantCloud/blob/master/client/src/main/java/com/clientui/proxies/RestaurantProxy.java),
```java
…
@FeignClient(name = "microservice-restaurant", url = "localhost:9101")

public interface RestaurantProxy {
….
 ```

,<br>
Ainsi tout foie on peut changer le port d'exécution du Client e réalise dans le fichier :
 [client/ain/resources/application.properties](https://github.com/karimouseyni/RestaurantCloud/blob/master/client/src/main/resources/application.properties)
```
spring.application.name=restaurant-clientui
server.port:9102

 ```

Ainsi le client peut être lancé 

<U><b>NB :</b></U> le client et le server ne dois pas s'exécuter sur le même port

# Démo
Pour exécuter le projet en local, vous télécharger le git [RestaurantCloud]() et vous importez le dossier Client et Server dans un IDE comme(Eclipse, Intellij,Netbeans,...) sachant qu'ils dispose tout le nécessaire pour exécuter un projet Spring(Server web, maven, java EE).

 ### Accueil 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo1.PNG)
### Liste des restaurants  
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo2.PNG)
 ### détails d'un restaurant 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo3.PNG)
 ### Noter Un restaurant 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo4.PNG)
 ###  
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo5.PNG)
 ### List ordonné (ordre décroissant des moyens) 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo7.PNG)

# Importation sur github
 ### Clonage du répertoire
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/cole1.PNG)
 ### Apres avoir déposer le code remplir ( summary et description)  et valider
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clone2.PNG)
 ### publier les modifications résultat
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clon3.PNG)


# Déploiement Sur Openshift
### Projet Openshift
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet1.PNG)
### Click sur retrieve
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet6.PNG)
### Login
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet2.PNG)
### Click sur retrieve
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet3.PNG)
### Click sur Workspace OC Sttings
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet6.PNG)
### Click sur Browws.. pour choisir l'exécutable openshift client télécharger ci-haut et apply and close
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet4.PNG)
### Next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet6.PNG)
### Choisir le projet et l'environnement de déploiement et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet7.PNG)
### Url du git(répertoire du git) et nom du projet
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet8.PNG)
### Configuration et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet9.PNG)
### Configuration du port et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet10.PNG)
### Next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet10.PNG)
