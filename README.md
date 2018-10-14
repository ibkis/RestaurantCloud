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
- Installer Jboss a travers Eclipse Marketplace wizard et rechercher jboss version 18
 
 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss1.png)
 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss2.png)
 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss3.png)
 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss4.png)
 ### Eclipse Markplace
 ![Alt text](https://github.com/karimouseyni/RestaurantCloud/blob/master/img/jboss5.png)
 
## Configurantions

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



