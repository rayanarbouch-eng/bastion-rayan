# Bilan du bastion : rayan-Laptop-12-13th-Gen-Intel-Core, 12/11/2026 09:35

Score : **80 / 100** (VERT)

| État | Point | Points |
|---|---|---|
| A faire | Système à jour (15 paquets en attente) : sudo apt update puis sudo apt upgrade (quête 3) | 0 / 15 |
| OK | Mises à jour de sécurité automatiques | +10 |
| OK | Pare-feu actif, entrées refusées par défaut | +15 |
| OK | Compte root verrouillé | +5 |
| OK | Aucun compte sans mot de passe | +5 |
| OK | Un seul administrateur : toi | +10 |
| OK | Verrouillage automatique de l'écran (10 min au plus) | +5 |
| OK | Dossier personnel fermé aux autres comptes (750) | +5 |
| OK | Serveur SSH durci (clé seulement, pas de root) | +15 |
| OK | Aucun port TCP ouvert au réseau, sauf SSH | +10 |
| A faire | fail2ban surveille SSH : sudo apt install fail2ban, puis la prison sshd (quête 9) | 0 / 5 |
| Info | AppArmor actif : chaque programme protégé reste dans sa cage | |
| Info | Disque non chiffré : on n'y touche pas cette semaine, à signaler au maître du jeu | |
