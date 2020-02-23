# tp2-Groupe-1_DIOP

# Exercice 1. Variables d’environnement

1. Dans quels dossiers bash trouve-t-il les commandes tapées par l’utilisateur?
 Dans les dossiers suivants: 
 /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

2.Quelle variable d’environnement permet à la commande cd tapée sans argument de vous ramener dans votre répertoire personnel?
Variable HOME

3.Explicitez le rôle des variablesLANG,PWD,OLDPWD,SHELLet_.
Lang: la variable d’environnement LANG détermine la langue que les logiciels utilisent pour communiquer avec l’utilisateur
PWD: permet de déterminer le répertoire courant
OLDPWD: Contient le répertoire avant le dernier cd
SHELL: interpréteur de commande

4.Créez une variable locale MY_VAR(le contenu n’a pas d’importance). Vérifiez que la variable existe
MY_VAR=”coucou”
Cette variable locale est connu du shell courant uniquement et donc seulement pour la session en cours.

5.Tapez ensuite la commande bash. 
Que fait-elle?
La commande bash nous fait changer  de prompt.
 La variable  MY_VAR existe-t-elle?
Non elle n’existe pas
 Expliquez. 
On a changé de prompt or la variable est locale donc on peut pas la retrouver dans ce nouveau prompt.
 A la fin de cette question, tapez la commande exit pour revenir dans votre session initiale.

6.Transformez MY_VAR en une variable d’environnement et recommencez la question précédente. Expli-quez.
On ajoute export MY_VAR=HELLO à la fin du fichier /home/diop/.bashrc
On peut maintenant retrouver la variable dans le prompt bash. 

7.Créer la variable d’environnement NOMS ayant pour contenu vos noms de binômes séparés par un espace. Aﬀicher la valeur de NOMS pour vérifier que l’affectation est correcte.

8.Ecrivez une commande qui aﬀiche ”Bonjour à vous deux, binôme1 binôme2!” (où binôme1 et binôme2sont vos deux noms) en utilisant la variableNOMS.
Image question 7 et 8
![GitHub Image](/images/image.png)
Format: ![Alt Text](url)

9.Quelle différence y a-t-il entre donner une valeur vide à une variable et l’utilisation de la commande unset?
unset : Supprime la varible d'environnement alors que dans l'autre cas c'est juste le contenu qui est vide mais existe.

10.Utilisez la commande echo pour écrire exactementl a phrase :$HOME =chemin(où chemin est votre dossier personneld ’après bash
echo $HOME=/home/diop

# Programmation Bash

# Exercice 2. Contrôle de mot de passe

```
#!/bin/bash

   PASSWORD='motdepasse'
   
   echo -n -e "Tapez votre mot de passe :\n"
   read -s
   mdp="$REPLY"
   
   if test "$PASSWORD" = "$mdp"
   	then echo -n -e "Bon mot de passe\n"
   else 
   	echo -n -e "Mauvais mot de passe\n"
   fi
   
   exit 0
 ```

# Exercice 3. Expressions rationnelles

```
#!/bin/bash

  function is_number()
  {
  	re='^[+-]?[0-9]+([.][0-9]+)?$'

  	if ! [[ $1 =~ $re ]] ; then
  		return 1
  	else
  		return 0
  	fi
  }

  is_number $1

  if [ $? -eq 0 ] ; then
  	echo  "nombre reel"
  else
  	echo  "pas un nombre reel. ERREUR"
  fi
```

# Exercice 5. Factorielle
```
#/bin/bash
fact ()
{ 
n=$1
        if [ $n -eq 0 ]
         then
                echo 1
         else 
                echo  $((n *`fact $((n-1))`))
        fi
}

echo `fact $1`
```
