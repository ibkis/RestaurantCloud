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
 ### Apres avoir deposer le code valider
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clone2.PNG)
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/clon3.PNG)
 
- importation du projet sur github en utilisant Github Desktop
- Creation d'un projet openshift sous eclipse :
- type de server : Openshift 3
- server : https://console.starter-ca-central-1.openshift.com
- creer un token en avec le compte openshift
- clique sur advanced : choisir l'executable  openshift-origin-client-tool
- clique sur next
- creer un projet si aucun projet n'est crée au paravant
- choisir l'enviroment de developpement, dans notre cas de jboss,tomcat
- url du git repository et le reference s'il existe plusieur projet dans le meme repository
- next
- laisser les parametre pardefaut et next
- utiliser un port et next





