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
L'application client/Server a été realiser sur le framework Spring, en utilisant l'architecture de micro-service classic<br>
### le server offre 3 points d'entrer à savoir :
- Obtenir la liste des restaurant(a comme parametre true:par ordre decroissant, false sans ordre) <br>
  en local : http://localhost:9101/restaurants (methode GET)
- Recuperation d'un restaurant en fonction de son identifiant <br> 
  en local: http://localhost:9101/restaurants/1  (methode GET)
- En fin ajouter une evaluation à un restaurant(methode POST)
 en local: http://localhost:9101/addnote
 
 Ainsi toute foie on peut changer le port d'execution sur Server, cela se realise dans le fichier :
 [server/src/main/resources/application.properties](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/application.properties)
 <br> ou ajouter des restaurant static fichier: [server/src/main/resources/data.sql](https://github.com/karimouseyni/RestaurantCloud/blob/master/server/src/main/resources/data.sql)
### Coté CLient 

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

# Demo



