# Liste blanche AdGuard / Pi-hole — FR

Après plusieurs années d'utilisation d'AdGuard et Pi-hole, 
j'ai constitué cette liste blanche pour résoudre deux problèmes 
récurrents sur les réseaux domestiques fortement filtrés.

## Problèmes résolus

- Services bancaires en ligne inaccessibles ou dégradés
- Smartphones Android/iOS qui basculent sur la 4G 
  au lieu du Wi-Fi (captive portal detection bloquée)

## Utilisation

Dans AdGuard Home :
Filtres → Listes blanches → Ajouter une liste → coller l'URL raw

Dans Pi-hole :
Whitelist → Ajouter les domaines manuellement ou via script

## Contenu

La liste est maintenue à partir de retours terrain.
Elle évolue en fonction des services testés.

## Contribution

Les PR et issues sont les bienvenues.
Si un service est bloqué chez vous, ouvrez une issue avec :
- Le service concerné
- Le domaine bloqué identifié dans les logs

## Licence

MIT
