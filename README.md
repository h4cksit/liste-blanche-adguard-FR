# Liste blanche AdGuard / Pi-hole — FR

Après plusieurs années d'utilisation d'AdGuard et Pi-hole, j'ai constitué 
cette liste blanche pour résoudre deux problèmes récurrents sur les réseaux 
domestiques fortement filtrés :

- Services bancaires en ligne inaccessibles ou dégradés
- Smartphones Android/iOS qui basculent sur la 4G au lieu du Wi-Fi
  (captive portal detection bloquée par les filtres DNS)

---

## Utilisation

**AdGuard Home**
Filtres → Listes blanches → Ajouter une liste → coller l'URL raw du fichier

**Pi-hole**
Whitelist → Ajouter les domaines manuellement ou via script

---

## Contenu de la liste

### Détection connectivité réseau (captive portal)
Indispensable pour que les smartphones restent sur le Wi-Fi.
- Google, Android, Samsung, Apple, Microsoft, Ubuntu, GNOME

### Microsoft / Azure / Office 365
- Telemetry, Speech, Cognitive Services, NEL, Edge, Copilot

### Google / Firebase / Android
- APIs Google, Firebase, Analytics, Crashlytics, FCM (push notifications)

### Apple / iOS
- Captive portal, iTunes, App Store, métriques système

---

### Banques françaises

#### Caisse d'Épargne / BPCE
- Web, mobile, MFA, Secur'Pass, S-money
- APIs communes BPCE, push, authentification

#### BNP Paribas / Hello Bank
- Web, mobile, auth, MFA, push, CDN

#### Société Générale
- Web, mobile, OTP, auth, CDN

#### Crédit Agricole / LCL
- Web, mobile, auth, push

#### Crédit Mutuel / CIC
- Web, mobile, auth, sécurité

#### La Banque Postale / La Poste
- Web, mobile, auth, push, suivi colis

#### Boursorama / BoursoBank
- Web, mobile, auth, CDN

#### Fortuneo
- Web, mobile, auth

#### N26
- Web, mobile, auth, CDN

#### Revolut
- Web, mobile, auth, CDN

#### Lydia / Sumeria
- Mobile, API, auth

#### PayPal
- Web, mobile, paiements sécurisés

---

### Opérateurs / FAI français

#### Orange / Sosh
- Portail, auth, mobile, push, CDN

#### Bouygues Telecom / Bbox
- Web, auth, mobile, push, CDN

#### Free / Free Mobile / Iliad
- Web, mobile, Freebox, auth

#### SFR / RED by SFR
- Web, mobile, auth, push, apps

---

### Stockage cloud
- **pCloud** : CDN, landing
- **Internxt** : auth, drive, CDN

### Ecosystème mobile constructeurs
- **Samsung** : Cloud Solution, Knox, connectivité
- **Xiaomi / MIUI** : Mi Cloud, DNS
- **Nintendo** : push, mise à jour
- **PlayStation** : notifications

### Amazon / streaming
- Amazon Video, Netflix logs

### Domotique & matériel
- OctoPrint, Meethue (Philips Hue), Tuya, Jabra, Bosch

### Services & outils
- GitHub, Sentry, Matomo, Cloudflare DNS

### Divers
- WhatsApp, Spotify, Batch, Amplitude
---
## Entrées spécifiques par client
Certaines règles sont limitées à une IP spécifique (`$client='192.168.1.19'`)
pour éviter d'ouvrir globalement des domaines publicitaires ou de tracking
nécessaires uniquement sur un appareil précis (TV, box Android, etc.).
---
## Avertissement
Certains domaines sont basés sur des patterns standards observés.
Si un service reste bloqué, consultez les logs AdGuard/Pi-hole pour 
identifier le domaine exact et ouvrez une issue.
---
## Contribution

Les PR et issues sont les bienvenues.
Si un service est bloqué chez vous, ouvrez une issue avec :
- Le service concerné
- Le domaine bloqué identifié dans les logs AdGuard/Pi-hole
- L'appareil concerné (Android, iOS, TV, etc.)

---

## Licence

MIT
