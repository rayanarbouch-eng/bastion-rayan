# L5 — Les groupes Linux

## Mes groupes

La commande `id` indique que mon compte `rayan` appartient notamment aux groupes :
- `adm`
- `sudo`
- `plugdev`
- `lpadmin`
- `users`

## Comparaison avec stagiaire

La commande `id stagiaire` montre que cet utilisateur appartient aux groupes :
- `stagiaire`
- `users`

## Rôle des quatre groupes

- `adm` : permet de consulter certains journaux système pour diagnostiquer les problèmes.
- `sudo` : permet d'exécuter des commandes avec les privilèges administrateur, selon la configuration.
- `lpadmin` : permet de gérer les imprimantes et les paramètres d'impression.
- `plugdev` : donne des permissions liées à certains périphériques amovibles ou connectés.

## Pourquoi le groupe adm peut-il lire les journaux ?

Certains fichiers de journaux système appartiennent au groupe `adm`. Les membres de ce groupe peuvent donc les consulter sans être administrateur.

## Conclusion

Les groupes Linux permettent de donner des permissions à plusieurs utilisateurs sans devoir configurer chaque utilisateur séparément.
