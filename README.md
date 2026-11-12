# Bastion de la guilde Rayan

## Membres et rôles

| Membre | Rôle | Pseudo GitHub |
|---|---|---|
| Rayan | Chef, Forgeron, Gardien et Veilleur | À compléter |

## Notre spécialité : sécurité du bastion et des ondes

Notre objectif est de protéger le poste informatique et le réseau Wi-Fi contre les accès non autorisés. Nous renforçons les comptes, le pare-feu, SSH, les journaux et la borne Wi-Fi.

### Recette de sécurisation

1. Mettre le système à jour :
   ```bash
   sudo apt update
   sudo apt upgrade -y
   ```
2. Activer le pare-feu :
   ```bash
   sudo ufw default deny incoming
   sudo ufw default allow outgoing
   sudo ufw enable
   ```
3. Renforcer SSH et utiliser une authentification par clé.
4. Installer et configurer Fail2ban pour protéger SSH.
5. Vérifier les services et les ports ouverts :
   ```bash
   sudo ss -tlnp
   ```
6. Vérifier les spécialités :
   ```bash
   sudo ./scripts/specialites.sh
   ```

## Nos bastions

| Membre | Bilan lundi | Bilan mardi | Bilan jeudi | Tampons |
|---|---|---|---|---|
| Rayan | Non documenté | 100/100 | 100/100 | Rempart, Porte, Veilleurs, Ondes |
## Notre borne Wi-Fi

- Wi-Fi principal : Bastion-Mercator-3
- Wi-Fi invité : nom à compléter
- Score du bilan de la borne : 100/100
- Chiffrement : WPA2/WPA3 (sae-mixed)
- Réseau invité : séparé et isolé
- Administration depuis Internet : fermée
- Sauvegarde de la configuration : réalisée

## Le combat contre le Glitch

**Résultat : 9 attaques repoussées sur 9.**

Les neuf attaques ont été repoussées :
- La porte de service
- Le mot de passe deviné
- Le trône de root
- La rafale
- Les portes oubliées
- Le vieux bug
- Le mot de passe d'usine
- Les ondes ouvertes
- L'invité indiscret

Aucune attaque n'a été signalée comme réussie dans le bilan.

## Remarque technique

La configuration sudo est réglée sur 5 minutes dans `/etc/sudoers.d/delai`. Le script de spécialités ne détecte pas ce réglage avec sa vérification actuelle, bien que `visudo -c` confirme que la configuration est valide.
