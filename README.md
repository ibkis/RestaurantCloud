# TP1 Cloud Computing: restaurant


## Summary
Aplication web client/Server heberger sur cloud
les instructions qui suit on étè realiser sur windows 
## Prérequis 
* Compte github - [Creation de Compte](https://github.com)
* Compte sur Openshift - [Creation de Compte](https://manage.openshift.com)

## Outils 

* eclipse oxygene java EE- [Telecharger]( https://www.eclipse.org/downloads/packages/release/oxygen/3a)
* openshift-origin-client-tools [Telecharger](https://github.com/openshift/origin/releases)
* github desktop [telecharger]()
### Installation JBoss

 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss1.png)
 ### Rechercher Jboss
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss2.png)
 ### Selection les Plugin a installer(de preference tous)
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss3.png)
 ### Confirmer
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss4.png)
 ### 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/joss5.png)
 
## Details sur le developpement
L'application client/Server a été realiser sur le framework Spring(projet maven), en utilisant l'architecture de micro-service classic<br>
### le server offre 3 points d'entrer à savoir :
- Obtenir la liste des restaurant(a comme parametre true:par ordre decroissant, false sans ordre) <br>
  en local : http://localhost:9101/restaurants (methode GET)
- Recuperation d'un restaurant en fonction de son identifiant <br> 
  en local: http://localhost:9101/restaurants/1  (methode GET)
- En fin ajouter une evaluation à un restaurant(methode POST)<br>
 en local: http://localhost:9101/addnote<br>
 
 Ainsi tout foie on peut changer le port d'exécution du erver, cela se réalise dans le fichier :
 [server/src/main/resources/application.properties](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/application.properties)
 <br> ou ajouter des restaurant static fichier: [server/src/main/resources/data.sql](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/data.sql)
### Coté Client 
Pour eviter des bugs, il est preferable de lancer le <b>Server</b> et de mettre l'addresse du server dans le ficher [RestaurantProxy.java](https://github.com/karimouseyni/RestaurantCloud/blob/master/client/src/main/java/com/clientui/proxies/RestaurantProxy.java),
,<br>
Ainsi tout foie on peut changer le port d'exécution du Client e réalise dans le fichier :
 [client/ain/resources/application.properties](https://github.com/karimouseyni/RestaurantCloud/blob/master/client/src/main/resources/application.properties)
ainsi le client peut etre lancer 

<U><b>NB:</b></U> le client et le server ne dois pas s'executer sur le meme port

# Demo
Pour executer le projet en local, vous telecharger le git [RestaurantCloud]() et vous importez le dossier Client et Server dans un IDE comme(Eclipse, Intellij,Netbeans,...) sachant qu'ils dispose tout le necessaire pour excecuter un projet Spring(Server web, maven, java EE).

 ### Accueil 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo1.PNG)
### Liste des restaurants  
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo2.PNG)
 ### details d'un restaurant 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo3.PNG)
 ### Noter Un restaurant 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo4.PNG)
 ###  
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo5.PNG)
 ### List ordonné( ordre decroissant des moyen) 
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/demo7.PNG)

# Importation sur github
 ### clonage du repertoire
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/cole1.PNG)
 ### Apres avoir deposer le code remplire( summary et description)  etvalider
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clone2.PNG)
 ### publier les modification resultat
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clon3.PNG)

# Deployement Sur Openshift
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
### Click sur Browws.. pour choisir l'executable openshift client telecharger ci-haut et apply and close
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet4.PNG)
### Next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet6.PNG)
### Choisir le projet et l'environement de deployement et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet7.PNG)
### Url du git(repertoir du git) et nom du projet
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet8.PNG)
### Configuration et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet9.PNG)
### Configuration du port et next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet10.PNG)
### Next
![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/projet10.PNG)
 
