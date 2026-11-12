# Bilan individuel — Rayan

**Machine :** rayan-Laptop-12-13th-Gen-Intel-Core  
**Date :** 12 novembre 2026  
**Système :** Ubuntu 26.04.1 LTS  
**Score final du bastion :** 100/100

## Sécurisation réalisée

- Système mis à jour.
- Mises à jour de sécurité automatiques activées.
- Pare-feu UFW actif : entrées refusées par défaut.
- Compte root verrouillé.
- Compte stagiaire sans droits sudo.
- Dossier personnel protégé.
- SSH configuré avec authentification par clé.
- Connexion root par SSH interdite.
- Fail2ban installé et configuré.
- Journaux conservés après redémarrage.

## Spécialités

| Guilde | Résultat |
|---|---|
| Clés | 2/3 — contrôle sudo non détecté |
| Rempart | 3/3 |
| Porte | 3/3 |
| Veilleurs | 3/3 |
| Ondes | 3/3 |

## Borne Wi-Fi

- Score : 100/100.
- Wi-Fi principal : Bastion-Mercator-3.
- Chiffrement : WPA2/WPA3.
- Réseau invité isolé.
- Administration depuis Internet désactivée.
- Sauvegarde de configuration réalisée.

## Combat contre le Glitch

9 attaques repoussées sur 9.

## Point restant à signaler

Le paramètre `timestamp_timeout=5` est configuré dans `/etc/sudoers.d/delai`. La syntaxe est validée par `sudo visudo -c`, mais le script de spécialités ne détecte pas ce paramètre.
