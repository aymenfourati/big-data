## Compte rendu du TP n° 1 : Le traitement Batch avec Hadoop HDFS et Map Reduce

### Réalisé par Fourati Aymen & Helali Eya



#### Objectifs du TP : 
Initiation au framework hadoop et au patron MapReduce, utilisation de docker pour lancer un cluster hadoop de 3 noeuds.


# Préparation de l'environement
![image](./hadoop-cluster-docker.png)
``` 
Creation et lancement des trois contenaires :
Hadoop Master 
Hadoop slave 1 
Hadoop slave 2 
```
![image](./0.jpg)
``` 
Lancement de hadoop et yarn
```
![image](./1.jpg)
``` 
Affichage du contenu du fichier purchases.txt
```
![image](./2.jpg)
# Interfaces web pour Hadoop

![image](./13.jpg)
# Wordcount
## Tester Map Reduce en local
``` 
Creation d'une configuration de type application
```
![image](./11.jpg)
``` 
output : 
```
![image](./12.jpg)
## Lancer Map Reduce sur le cluster

``` 
Creation d'un configuration Maven avec une ligne de commande : 
package install 
```
![image](./10.jpg)
``` 
Copie du fichier target/wordcount-1.jar vers hadoop-master:/root
```
![image](./9.jpg)
``` 
Lancement du job map reduce
```
![image](./3.jpg)
``` 
Affichage des dernières lignes du chier généré output/part-r-00000,
```
![image](./4.jpg)
![image](./5.jpg)
``` 
Affiche de la Page web de monitoring des Jobs Map Reduce
```
![image](./6.jpg)
![image](./6.1.jpg)
``` 
Affichage des interfaces webs des noeuds esclaves pour analyzer leurs comportements :
```
![image](./7.jpg)

![image](./8.jpg)
# Application
### Écrire un Job Map Reduce permettant, à partir du chier purchases initial, de déterminer le total des ventes par magasin
``` 
Création d'un module tn.insat.application dans lequel nous avons definis trois classes :
- TokenizerMapper : le mapper de notre job qui est tres similaire a celui du job wordcount
- MagasinReducer : Le reducer chargé du parsing des champs dans le fichier purchases.txt afin de pouvoir en tirer les valeurs des redondances de chaque magasin.
- ProductCounter : Notre classe main
```
![image](./16.jpg)
```
Le reducer : 
```
![image](./18.jpg)
```
La configuration maven atravers laquel nous avons copier le fichier .jar vers notre contenaire master et lancer notre job evidement apres nombreux testes locaux
```
![image](./17.jpg)
```
Output : 
```
![image](./15.jpg)
![image](./14.jpg)