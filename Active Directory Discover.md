
# 1. Installation du Service AD DS sur le serveur

![Add AD DS](https://github.com/Fairskip/AD_Decouvrir/blob/main/AD%20DS%20Install.png)
<br><br>
Ajout de rôle et de fonctionnalités > Assistant Ajout de rôles et de fonctionnalités :
* Avant de commencer => suivant
* Type d'installation => par défaut, suivant
* Sélection du serveur => par défaut, suivant
* Rôles de serveur => **Services AD DS**, suivant
  <br><br>
  ![adds](https://github.com/Fairskip/AD_Decouvrir/blob/main/AD%20DS%20Install%202.png)
  <br><br>
* ... jusqu'à la fin => par défaut, suivant / installer  

<br>

# 2. Configuration de AD DS : Promouvoir ce serveur.   

1 -  Gestionnaire de serveur => Cliquer sur le drapeau jaune   

2 - Drapeau Jaune => Cliquer sur **Promouvoir ce Serveur**
  
<br>

![Promouvoir ce serveur](https://github.com/Fairskip/AD_Decouvrir/blob/main/Promouvoir%20ce%20serveur.png)

<br>
3 - Assistant configuration des services de domaine Active Directory :  
  
* Configuration de déploiement :
    
→ Sélectionner l'opération de déploiement =>  Ajouter une nouvelle forêt

→ Nom de domaine racine => wilders.lan

→ suivant

![wilders](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%201.png)
	
* Options du contrôleur de domaine => défaut  
  
  → Taper le mot de passe du mode de restauration des services d'annuaire (DSRM) => Mettre un mot de passe
  
  → suivant

![mdp](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%202.png)  
    
	
  * Option DNS => défaut sans tenir compte du message dans le ruban jaune, suivant.    


![ignore](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%203.png)
  
<br>		
     
  * Options supplémentaires => défaut, suivant

![wilders](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%204.png)  

   
* Défaut et suivant / Installer pour toutes les autres étapes de la configuration des services de domaine AD  

![pass](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%205.png)  
   
	
4 - La VM redémarre.  
  
![restart](https://github.com/Fairskip/AD_Decouvrir/blob/main/ADDS%20config%206.png)  

   <br>	
   
# 3. Mettre le PC Host from Workgroup to Domaine.  

Après avoir vérifier que le serveur et le Host soient dans le même server et que le IPv4 du DHCP est activé :  

* Explorateur de fichier > ce PC > (clic droit) Propriété > Modifier.
![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%201.png)

* Modification du nom ou du domaine de l'ordinateur => Cliquer Membre d'un Domaine.
* Membre d'un Domaine => WILDERS
* Ok

![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%202.png)

* Entrer le nom et le mot de passe d'un compte autorisé à joindre le domaine, Ok.

![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%203.png)    

* Le PC est désormais membre du Domaine Wilder.

![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%204.png)


* La Machine redémarre une fois que le domaine a été prise en compte.
* On a désormais une session **Autre Utilisateur** pour ce PC Host.

![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%205.png)


* Et dans Utilisateurs et ordinnateurs Active Directory > wilders.lan > Computer, on a le PC Hosty enregistré dans le domaine.

![host domaine](https://github.com/Fairskip/AD_Decouvrir/blob/main/Host%20Domaine%206.png)
