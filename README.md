# 🛡️ Bastion de la guilde Rayan

## 1. Présentation du projet

Le projet **Bastion** a pour objectif de sécuriser un poste informatique Linux et un réseau Wi-Fi contre les accès non autorisés et les mauvaises configurations.

Notre travail consiste à renforcer la sécurité du système, à contrôler les connexions réseau, à protéger les accès administrateur et à vérifier que les services importants fonctionnent correctement.

Nous avons travaillé sur plusieurs aspects :
- La sécurisation du système Linux.
- La protection des comptes utilisateurs et des droits administrateur.
- La configuration du pare-feu.
- La sécurisation des connexions SSH.
- La surveillance des services et des journaux.
- La protection du réseau Wi-Fi.
- La sauvegarde de la configuration de la borne.
- La vérification des résultats avec les scripts du projet.
- La documentation et le partage du travail avec Git et GitHub.

## 2. Membres et rôles

| Membre | Rôle | Pseudo GitHub |
|---|---|---|
| Rayan | Chef, Forgeron, Gardien et Veilleur | À compléter |

En tant que membre principal de la guilde, j'ai participé à la sécurisation du poste, à la protection du réseau Wi-Fi, aux vérifications techniques et à la rédaction des comptes rendus.

## 3. Notre spécialité : sécurité du bastion et des ondes

Notre spécialité est de protéger deux éléments importants : le poste informatique et le réseau sans fil.

### A. Sécurisation du poste Linux

**1. Mise à jour du système**

Commandes utilisées :

```bash
sudo apt update
sudo apt upgrade -y
```

Explications :
- `sudo` permet d'exécuter une commande avec les droits administrateur.
- `apt update` actualise la liste des paquets disponibles.
- `apt upgrade -y` installe les mises à jour disponibles.

Les mises à jour permettent notamment de corriger des bugs et des failles de sécurité.

**2. Configuration du pare-feu**

Commandes utilisées :

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw enable
sudo ufw status
```

Explications :
- `ufw` est un outil qui permet de gérer le pare-feu Linux.
- `default deny incoming` bloque les connexions entrantes par défaut.
- `default allow outgoing` autorise les connexions sortantes par défaut.
- `enable` active le pare-feu.
- `status` affiche son état et ses règles.

Le pare-feu limite les connexions entrantes non autorisées et réduit les possibilités d'accès au poste.

**3. Protection des connexions SSH**

SSH permet de se connecter à distance à une machine Linux de manière sécurisée.

Dans notre projet, nous avons travaillé sur l'utilisation de clés SSH afin de privilégier une authentification par clé plutôt qu'une authentification reposant uniquement sur un mot de passe.

Sur la borne Wi-Fi, l'accès SSH au routeur est configuré avec une authentification par clé.

Cela renforce la protection des accès à distance.

**4. Protection contre les tentatives de connexion**

Nous avons travaillé avec Fail2ban.

Fail2ban surveille certains journaux et peut bloquer temporairement des adresses IP qui effectuent trop de tentatives de connexion suspectes.

Cela permet de limiter certaines tentatives répétées de connexion, notamment sur SSH.

**5. Vérification des ports ouverts**

Commande utilisée :

```bash
sudo ss -tlnp
```

Explications :
- `ss` affiche des informations sur les connexions réseau.
- `-t` affiche les connexions TCP.
- `-l` affiche les ports en écoute.
- `-n` affiche les numéros sans résolution des noms.
- `-p` affiche les processus associés lorsque les informations sont disponibles.

Cette commande permet de repérer les services qui écoutent sur le réseau et de vérifier qu'aucun service inutile n'est exposé.

**6. Vérification des services**

Commandes utiles :

```bash
systemctl status fail2ban
systemctl --failed
```

- `systemctl status` permet de consulter l'état d'un service.
- `systemctl --failed` affiche les services qui ont échoué.

Les journaux peuvent aussi être consultés avec :

```bash
sudo journalctl -u fail2ban
```

Cela permet de comprendre le fonctionnement d'un service et de rechercher les erreurs éventuelles.

## 4. Protection des comptes et des droits administrateur

La protection des comptes est une partie importante du bastion.

Nous avons notamment vérifié plusieurs éléments :
- Le compte root est verrouillé.
- Aucun compte sans mot de passe n'a été signalé par le bilan.
- Les droits administrateur sont contrôlés.
- La configuration de sudo est vérifiée.

### Réglage du délai sudo

Nous avons configuré le fichier :

```text
/etc/sudoers.d/delai
```

Avec la ligne :

```text
Defaults timestamp_timeout=5
```

Cette option règle à cinq minutes la durée pendant laquelle l'authentification sudo reste considérée comme récente.

Nous avons ensuite vérifié la syntaxe avec :

```bash
sudo visudo -c
```

Le résultat a confirmé que la configuration était correctement analysée.

**Remarque technique :** le script de spécialités ne détecte pas ce réglage avec sa méthode de vérification actuelle. Le contrôle `sudo -l` utilisé pendant nos vérifications n'a pas affiché le paramètre attendu. Il faut donc distinguer la validation de la configuration par `visudo -c` de la détection du réglage par le script.

## 5. Vérification des spécialités

Commande utilisée :

```bash
sudo ./scripts/specialites.sh
```

Ce script permet de vérifier les différents éléments liés aux spécialités du projet et d'afficher les résultats obtenus.

### Résultats des spécialités

| Spécialité | Résultat |
|---|---:|
| Clés | 2/3 |
| Rempart | 3/3 |
| Porte | 3/3 |
| Veilleurs | 3/3 |
| Ondes | 3/3 |

La spécialité Clés n'a pas obtenu tous ses points parce que le script ne détecte pas le réglage `timestamp_timeout`, même si `visudo -c` confirme que la configuration sudo est valide.

## 6. Historique des bilans du bastion

Nous avons effectué plusieurs vérifications pour améliorer progressivement la sécurité du poste.

### Mardi 10 novembre 2026

| Vérification | Résultat |
|---|---:|
| Première vérification | 68/100 |
| Deuxième vérification | 84/100 |
| Bilan final | 100/100 |
| Vérifications suivantes | 100/100 |

Cette progression montre que plusieurs corrections ont été effectuées entre les premières vérifications et le résultat final.

### Jeudi 12 novembre 2026

| Vérification | Résultat |
|---|---:|
| Première vérification | 84/100 |
| Deuxième vérification | 80/100 |
| Bilan final | 100/100 |

Le dernier bilan enregistré indique un résultat de 100/100.

### Tableau récapitulatif

| Membre | Bilan lundi | Bilan mardi | Bilan jeudi |
|---|---|---|---|
| Rayan | Non documenté | 100/100 | 100/100 |

Le bilan du lundi n'a pas été retrouvé dans les éléments disponibles. Nous avons donc indiqué « Non documenté » au lieu d'inventer un résultat.

## 7. Notre borne Wi-Fi

Une autre partie importante du projet concerne la sécurisation de la borne Wi-Fi.

### Configuration générale

| Élément | Configuration ou résultat |
|---|---|
| Wi-Fi principal | Bastion-Mercator-3 |
| Wi-Fi invité | Nom à compléter |
| Score du bilan | 100/100 |
| Chiffrement | WPA2/WPA3 (sae-mixed) |
| Réseau invité | Séparé et isolé |
| Administration depuis Internet | Fermée |
| Accès SSH au routeur | Authentification par clé |
| Interface Web | HTTPS |
| Sauvegarde | Réalisée |
| Version OpenWrt | 25.12.6 |

### Explication des protections

**1. Chiffrement WPA2/WPA3**

Le chiffrement protège les communications sans fil et limite les connexions aux personnes autorisées.

La configuration `sae-mixed` permet de prendre en charge WPA2 et WPA3.

**2. Réseau invité isolé**

Le réseau invité est séparé du réseau principal.

Cela permet d'accueillir des appareils extérieurs sans leur donner automatiquement accès aux équipements du réseau principal.

**3. Administration depuis Internet fermée**

L'administration du routeur n'est pas accessible directement depuis Internet.

Cela réduit les possibilités d'accès extérieur à l'interface d'administration.

**4. Administration SSH par clé**

L'accès SSH au routeur utilise une authentification par clé.

Cela renforce la protection de l'administration à distance.

**5. Interface Web en HTTPS**

HTTPS chiffre les échanges entre le navigateur et l'interface d'administration.

**6. Sauvegarde de la configuration**

Une sauvegarde a été réalisée afin de conserver une copie de la configuration de la borne.

Elle peut être utile pour restaurer les paramètres en cas de problème.

### Résultat

Le bilan de la borne Wi-Fi a obtenu **100/100**.

Ce résultat indique que les contrôles prévus par le bilan de la borne ont été validés.

## 8. Le combat contre le Glitch

Dans le projet, nous avons également réalisé un exercice de sécurité appelé « Le combat contre le Glitch ».

L'objectif était de vérifier la résistance du bastion face à plusieurs situations représentant des faiblesses de sécurité.

### Résultat obtenu

**9 attaques repoussées sur 9.**

Les neuf attaques recensées dans le bilan sont :

1. La porte de service.
2. Le mot de passe deviné.
3. Le trône de root.
4. La rafale.
5. Les portes oubliées.
6. Le vieux bug.
7. Le mot de passe d'usine.
8. Les ondes ouvertes.
9. L'invité indiscret.

Aucune attaque n'a été signalée comme réussie dans le bilan.

Ce résultat montre que les neuf situations testées ont été repoussées selon le compte rendu de l'exercice.

## 9. Organisation du projet avec Git et GitHub

Nous avons utilisé Git pour suivre les modifications du projet et GitHub pour partager le dépôt.

### Dépôt local

Le projet est organisé dans le répertoire :

```bash
~/kit-bastion
```

### Organisation des fichiers

```text
kit-bastion/
│
├── README.md
│
├── scripts/
│   └── specialites.sh
│
└── rapports/
    ├── Rayan-bilan.md
    ├── Rayan-bilan-lundi.md
    ├── Rayan-bilan-mardi.md
    ├── Rayan-bilan-jeudi.md
    └── Rayan-wifi.md
```

Le README présente le projet, les rôles, les résultats et les principales informations techniques.

Le dossier `rapports` contient les comptes rendus des bilans et de la borne Wi-Fi.

### Commandes Git utilisées

**1. Vérifier l'état du dépôt**

```bash
git status
```

Cette commande permet de voir les fichiers modifiés, les fichiers non suivis et l'état de la branche.

**2. Ajouter les fichiers**

```bash
git add README.md rapports/
```

Cette commande prépare les modifications pour le prochain commit.

**3. Vérifier les modifications préparées**

```bash
git diff --cached --check
```

Cette commande permet notamment de repérer des espaces inutiles en fin de ligne.

Lors d'une vérification, des avertissements concernant des espaces en fin de ligne ont été affichés dans certains rapports. Ils ne bloquaient pas la création du commit.

**4. Créer un commit**

```bash
git commit -m "Ajout des bilans et organisation du README"
```

Un commit permet d'enregistrer un ensemble de modifications dans l'historique Git.

Le commit créé porte l'identifiant :

```text
fd0df7c
```

**5. Envoyer les modifications vers GitHub**

```bash
git push origin main
```

Cette commande envoie les commits locaux vers la branche `main` du dépôt distant `origin`.

**6. Vérifier la synchronisation**

```bash
git status
```

Le dernier résultat indiquait :

```text
Sur la branche main
Votre branche est à jour avec 'origin/main'.
rien à valider, la copie de travail est propre
```

Cela signifie que les modifications locales étaient enregistrées et que la branche locale était synchronisée avec la branche distante.

## 10. Les difficultés rencontrées et les vérifications

Pendant le projet, plusieurs vérifications ont été nécessaires.

- Certains contrôles du script ne détectaient pas immédiatement les réglages réalisés.
- La configuration sudo a nécessité une vérification spécifique avec `visudo -c`.
- Certains rapports contenaient des espaces inutiles signalés par Git.
- Nous avons dû organiser les bilans pour distinguer les résultats réellement disponibles des informations manquantes.

Ces difficultés nous ont permis de comprendre qu'un résultat affiché par un script doit être interprété et vérifié, et qu'une configuration correcte ne signifie pas toujours que tous les contrôles automatiques la détectent.

## 11. Conclusion générale

Ce projet m'a permis de travailler sur plusieurs domaines de la sécurité informatique.

J'ai appris à :
- Mettre à jour un système Linux.
- Configurer et vérifier un pare-feu.
- Comprendre le fonctionnement de SSH.
- Renforcer les accès administrateur.
- Vérifier les ports et les services actifs.
- Comprendre l'utilité de Fail2ban.
- Sécuriser un réseau Wi-Fi.
- Isoler un réseau invité.
- Vérifier une configuration et consulter les journaux.
- Utiliser Git et GitHub pour organiser et partager mon travail.
- Rédiger des rapports techniques et expliquer les résultats obtenus.

Les derniers bilans disponibles indiquent 100/100 pour le bastion et 100/100 pour la borne Wi-Fi. L'exercice Glitch indique également neuf attaques repoussées sur neuf.

**Mon objectif était de construire un bastion mieux protégé, de comprendre les protections mises en place et de pouvoir expliquer chaque action réalisée.**
