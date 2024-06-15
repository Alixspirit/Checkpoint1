# Exercice 1

# Historique des commandes

fdisk -l  
cfdisk /dev/sdb  
dos  
nouvelle  
6G  
primaire 
ecrire oui  
quitter
fdisk /dev/sdb
n  
p  
2  
entrée
entrée
t  
2  
82  
w  
mkswap /dev/sdb2
swapon /dev/sdb2
fdisk -l
mkfs.ext4 -L DATA /dev/sdb1  
mkdir mnt  
cd mnt  
mkdir data  
cd ..  
mount -t ext4 /dev/sdb1 /mnt/data  
df -h  
nano /etc/fstab  
UUID=423d6604-7c92-479e-894e-588b94a168ce /mnt/data ext4 defaults 0 2  
ctrl + x    
o  
entrée  
mount -a  

# Exercice 2 - Script de creation d'utilisateurs en bash

Nom : addUsers.sh

#!/bin/bash  
echo "Total number of arguments:" $#  
echo "Argument values:" $@  
if [ -z "" ]  
then  
echo "Il manque les noms d'utilisateurs en argument - Fin du script"  
exit 0  
else  
echo "Il y a les arguments - Le script continue"  
fi  
while [ -n "$#" ]  
do  
read -p "Entrez votre nom d'utilisateur:" username  
if id "$username" > /etc/passwd  
then    
echo "L'utilisateur $username existe déjà"    
fi  
sudo adduser $username  
if id $username > /etc/passwd   
then   
echo "L'utilisateur $username a ete crée"  
else  
echo "Erreur à la création de l'utilisateur $username"  
fi  
done  

# Exercice 3 - Quizz

1. cat /etc/passwd
2. setfacl -m u:user:rwx g:group:r-- o:other:r-- myfile
3. Créer un fichier .gitignore et ajouter les noms des fichiers pdf dans le fichier .gitignore
4. git merge
5. echo
6. fg
7. Couche 2:  
pont (bridge): permet de relier des reseaux different, materiel actif
commutateur (switch): fonctionne comme un pont multiport, permet de relier plusieurs segments d'un reseau entre eux, materiel actif  
carte reseau  
Couche 3:  
routeur: permet le routage des paquets entre 2 reseaux ou plus afin de determiner le chemin qu'un paquet de données va emprunter, materiel actif
8. cd équivalent à Set-Location, cp équivalent à Copy-Item, mkdir équivalent à New-Item, ls équivalent à Get-ChildItem
9. charge utile
10. Probleme de pénurie d'adresse ip, classes C trop petites et classes D trop peu nombreuses
