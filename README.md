# github-vpn-tunnel

# GitHub Runner VPN via Tailscale (SOCKS Proxy)

Ce dépôt vous permet de créer un tunnel VPN temporaire vers un GitHub runner distant gratuitement, sans carte bancaire.

---

## 🔧 Prérequis

- Compte GitHub
- Compte Tailscale (gratuit)
- Navigateur ou logiciel capable d’utiliser un proxy SOCKS5

---

## 🚀 Instructions

### 1. Générez une clé Tailscale

- Allez sur https://login.tailscale.com/admin/settings/keys
- Générez une `auth key` (cochez "Ephemeral")

---

### 2. Ajoutez la clé dans GitHub

- Dépôt > Settings > Secrets > Actions
- Nom : `TAILSCALE_AUTHKEY`
- Valeur : votre clé Tailscale

---

### 3. Lancez le tunnel

- Onglet **Actions** > `Tailscale Proxy Runner` > `Run workflow`
- Le runner se connectera à Tailscale avec le nom `github-runner`

---

### 4. Récupérez son IP privée Tailscale

- Connectez-vous sur l’appli Tailscale (ou https://tailscale.com/admin)
- Trouvez `github-runner`, notez son IP : `100.x.x.x`

---

### 5. Configurez votre navigateur

- Proxy SOCKS5 : `100.x.x.x:1080`

---

### ✅ Résultat

- Vous naviguez sur Internet avec l’IP d’un GitHub runner distant (USA ou Europe)
- Aucun VPS, aucune carte bancaire, 100% gratuit

⚠️ Le tunnel s'arrête après 60 minutes (limite GitHub Actions)
