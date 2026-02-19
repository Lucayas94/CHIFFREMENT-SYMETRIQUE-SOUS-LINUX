# TP : Chiffrement Symétrique sous Linux avec OpenSSL

[cite_start]Ce dépôt contient les travaux pratiques réalisés dans le cadre du module **Cybersécurité**[cite: 1]. [cite_start]L'objectif est de comprendre et de mettre en œuvre les mécanismes de chiffrement et déchiffrement symétrique en utilisant la boîte à outils **OpenSSL** sous un environnement Linux[cite: 3, 4, 6].

##  Objectifs du TP
* [cite_start]Comprendre le mécanisme de chiffrement et déchiffrement symétrique[cite: 4].
* [cite_start]Apprendre à utiliser la boîte à outils cryptographique `openssl`[cite: 4].
* [cite_start]Générer des clés de différentes longueurs (128, 192, 256 bits) et comparer leur impact[cite: 47].
* [cite_start]Mettre en œuvre le chiffrement avec mot de passe via la fonction de dérivation **PBKDF2**.

---

##  Guide d'Exécution

### 1. Vérification de l'environnement
[cite_start]Vérifiez que la commande `openssl` est installée sur votre système[cite: 10]:
```bash
openssl version
