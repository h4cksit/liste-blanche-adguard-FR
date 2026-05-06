# Liste blanche AdGuard / Pi-hole — FR

Après plusieurs années d'utilisation d'AdGuard et Pi-hole, j'ai constitué 
cette liste blanche pour résoudre deux problèmes récurrents sur les réseaux 
domestiques fortement filtrés :

- Services bancaires en ligne inaccessibles ou dégradés
- Smartphones Android/iOS qui basculent sur la 4G au lieu du Wi-Fi  
  (captive portal detection bloquée par les filtres DNS)

**332 domaines validés** par résolution DNS depuis un réseau résidentiel FR (mai 2026).

---

## Utilisation

**AdGuard Home**  
Filtres → Listes blanches → Ajouter une liste → coller l'URL :
```
https://raw.githubusercontent.com/h4cksit/liste-blanche-adguard-FR/main/allowlist.txt
```

**Pi-hole**
```
https://raw.githubusercontent.com/h4cksit/liste-blanche-adguard-FR/main/allowlist.txt
```

---

## Contenu de la liste

### Détection connectivité réseau (captive portal)
Indispensable pour que les smartphones restent sur le Wi-Fi.  
Couvre Google, Android, Samsung, Apple, Microsoft, Ubuntu, GNOME.

### Microsoft / Azure / Office 365
Telemetry, Speech, Cognitive Services, NEL, Edge, Copilot.

### Google / Firebase / Android
APIs Google, Firebase, Analytics, Crashlytics, FCM (push notifications).

### Apple / iOS
Captive portal, iTunes, App Store, métriques système.

---

### Banques françaises

| Banque | Couverture |
|---|---|
| Caisse d'Épargne / BPCE | Web, mobile, MFA, Secur'Pass |
| BNP Paribas / Hello Bank | Web, mobile |
| Société Générale | Web, mobile |
| Crédit Agricole / LCL | Web, mobile |
| Crédit Mutuel / CIC | Web, mobile |
| La Banque Postale | Web, mobile |
| Boursorama / BoursoBank | Web, mobile |
| Fortuneo | Web, mobile |
| N26 | Web, mobile |
| Revolut | Web, mobile |
| Lydia / Sumeria | Mobile, API |
| PayPal | Web, mobile, paiements |

---

### Opérateurs / FAI français

| Opérateur | Couverture |
|---|---|
| Orange / Sosh | Portail, auth, mobile, CDN |
| Bouygues Telecom / Bbox | Web, auth, mobile |
| Free / Free Mobile | Web, mobile, Freebox |
| SFR / RED by SFR | Web, mobile |

---

### Lecteurs multimédias & TV connectées
NVIDIA Shield, Google Chromecast, Amazon Fire TV, Apple TV,  
Xiaomi Mi Box, Sony Bravia, LG webOS, Samsung Smart TV.

### Constructeurs mobiles
Samsung, Xiaomi, Huawei, OnePlus/OPPO, Sony Mobile, Motorola, Nokia.

### Domotique & maison connectée
Philips Hue, Tuya, IKEA Tradfri, Sonos, Netatmo, Somfy, Legrand,  
Fibaro, Shelly, OctoPrint, Jabra, Bosch.

### Outils self-hosted & homelab
Home Assistant, Grafana, Proxmox, Nextcloud, Portainer, Vaultwarden,  
Pi-hole, AdGuard, Uptime Kuma, Matomo, Infomaniak, Sentry.

### Stockage cloud
pCloud, Internxt.

### Streaming & médias
Netflix, OQEE (Free), Spotify, Amazon Video.

### Écosystème mobile constructeurs
Samsung Cloud, Xiaomi Mi Cloud, Nintendo, PlayStation, Amazon.

### Services & outils
GitHub, Cloudflare DNS (1.1.1.1), Sentry, Matomo, Amplitude, Batch,  
WhatsApp, Telemetry InfluxDB.

---

## Personnalisation par appareil (lecteurs multimédias)

Certains appareils de type lecteur multimédia nécessitent des domaines  
de tracking ou d'analytics pour fonctionner correctement  
(lecture vidéo, DRM, mises à jour, activation des services).

Dans le fichier `allowlist.txt`, ces règles sont ouvertes globalement  
avec `$important`. Si vous souhaitez les restreindre à un seul appareil,  
modifiez-les directement dans AdGuard Home en remplaçant `$important`  
par `$client='IP_DE_VOTRE_APPAREIL'`.

**Exemple pour une NVIDIA Shield à l'IP 192.168.1.50 :**
```adguard
@@||events.gfe.nvidia.com^$client='192.168.1.50'
@@||prod.otel.kaizen.nvidia.com^$client='192.168.1.50'
```

---

## Méthode de validation

Chaque entrée est validée par résolution DNS (A / AAAA) via Quad9 (9.9.9.9),  
depuis un réseau résidentiel français, à l'aide d'un script Python dédié.  
Les domaines NXDOMAIN confirmés sont supprimés à chaque mise à jour.

Dernière validation : **mai 2026** — 95 entrées inexistantes supprimées.

---

## Avertissement

Si un service reste bloqué, consultez les logs AdGuard/Pi-hole pour  
identifier le domaine exact et ouvrez une issue.

Cette liste n'a pas vocation à débloquer des trackers publicitaires  
de manière globale. Les entrées sont documentées et justifiées  
par un besoin fonctionnel identifié.

---

## Contribution

Les PR et issues sont les bienvenues.  
Si un service est bloqué chez vous, ouvrez une issue avec :
- Le service concerné
- Le domaine bloqué identifié dans les logs AdGuard/Pi-hole
- L'appareil concerné (Android, iOS, TV, console, etc.)

---

## Licence

MIT
