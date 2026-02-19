TP : Chiffrement Symétrique sous Linux avec OpenSSL
Ce dépôt contient les travaux pratiques réalisés dans le cadre du module Cybersécurité. L'objectif est de comprendre et de mettre en œuvre les mécanismes de chiffrement et déchiffrement symétrique en utilisant la boîte à outils OpenSSL.
+1

Objectifs du TP
Apprendre à générer des clés de chiffrement aléatoires.

Chiffrer et déchiffrer des fichiers avec l'algorithme AES-256-CBC.
+2

Utiliser des fonctions de dérivation de clé (PBKDF2) avec un mot de passe et un sel (salt).

Étudier l'impact de la longueur des clés sur la sécurité.
+1

 Guide d'Exécution
1. Vérification de l'environnement
Assurez-vous qu'OpenSSL est installé sur votre système Linux:

Bash

openssl version
2. Chiffrement avec une clé générée (Partie I)

Génération de la clé (256 bits/32 octets) : 

Bash

openssl rand -base64 32 > ma_cle.txt

Chiffrement du fichier : 

Bash

openssl enc -aes-256-cbc -salt -in mon_fichier.txt -out mon_fichier_encrypted.txt -pass file:ma_cle.txt

Déchiffrement du fichier : 

Bash

openssl enc -d -aes-256-cbc -in mon_fichier_encrypted.txt -out mon_fichier_decrypted.txt -pass file:ma_cle.txt
3. Chiffrement avec mot de passe et PBKDF2 (Partie III)
Cette méthode renforce la sécurité en utilisant un sel pour éviter les attaques par dictionnaire.


Générer un sel (16 octets) : 

Bash

openssl rand -base64 16 > salt.txt

Saisir le mot de passe (masqué) : 

Bash

read -s -p "Entrez le mot de passe: " password

Chiffrer avec dérivation PBKDF2 : 

Bash

openssl enc -aes-256-cbc -salt -kdf pbkdf2 -in mon_fichier.txt -out mon_fichier_encrypted_with_password.txt -pass "pass:$password" -p -S $(cat salt.txt)
🔬 Concepts Clés abordés

AES-256-CBC : Algorithme de chiffrement symétrique utilisant une clé de 256 bits et le mode d'enchaînement des blocs (CBC).
+1


Salt (Sel) : Valeur aléatoire ajoutée pour augmenter l'entropie et rendre le texte chiffré unique même pour des données identiques.
+1


PBKDF2 : Fonction de dérivation permettant de transformer un mot de passe simple en une clé robuste.
+1


Gestion des clés : L'importance du stockage sécurisé des clés pour protéger l'intégrité des données.

Module : Cybersécurité

Outil : OpenSSL sur Linux
