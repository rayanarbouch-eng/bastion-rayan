# L6 — Le compte qui expire

## Modification du compte

J'ai utilisé la commande :

`sudo chage -E 2026-12-31 stagiaire`

Elle permet de définir la date d'expiration du compte stagiaire au 31 décembre 2026.

## Vérification

J'ai utilisé :

`sudo chage -l stagiaire`

Résultat :
- Date d'expiration du compte : 31 décembre 2026.
- Le mot de passe n'expire pas.

## Pourquoi une entreprise utilise cette fonction ?

Une entreprise peut faire expirer un compte lorsqu'un stagiaire termine son stage ou lorsqu'un prestataire termine sa mission.

Cela permet de supprimer automatiquement l'accès au compte à la date prévue et de limiter les accès inutiles.

## Conclusion

Le compte stagiaire est configuré pour expirer le 31 décembre 2026.
