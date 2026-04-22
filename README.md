# 🤖 Mineflayer Random Bot

Ein Minecraft-Bot der deinem Server joint und zufällige Bewegungen macht.

---

## ⚙️ Konfiguration

Erstelle Umgebungsvariablen (`.env` lokal, oder im Hosting-Dashboard):

| Variable | Beschreibung | Standard |
|---|---|---|
| `MC_HOST` | Server IP/Domain | `localhost` |
| `MC_PORT` | Server Port | `25565` |
| `MC_USERNAME` | Bot-Name (Cracked) oder E-Mail (Premium) | `RandomBot` |
| `MC_PASSWORD` | Passwort (nur Premium) | leer |
| `MC_AUTH` | `offline` (Cracked) oder `microsoft` (Premium) | `offline` |
| `MC_VERSION` | z.B. `1.20.1`, oder leer für Auto-Detect | auto |

---

## 🚀 Lokal testen

```bash
npm install
MC_HOST=dein.server.de MC_PORT=25565 node bot.js
```

---

## ☁️ Hosting auf Railway.app (empfohlen, kostenlos)

> ⚠️ **Netlify funktioniert NICHT** für dauerhaft laufende Prozesse.
> Railway.app ist die einfachste Alternative!

**Schritte:**

1. Gehe auf [railway.app](https://railway.app) und melde dich an (GitHub-Login)
2. Klicke auf **"New Project" → "Deploy from GitHub Repo"**
3. Lade den Bot-Code auf GitHub hoch (oder nutze Railway's CLI)
4. Setze die **Umgebungsvariablen** im Railway-Dashboard:
   - `MC_HOST` = deine Server-IP
   - `MC_PORT` = 25565
   - `MC_USERNAME` = RandomBot
   - `MC_AUTH` = offline
5. Railway startet den Bot automatisch!

**Mit Railway CLI:**
```bash
npm install -g @railway/cli
railway login
railway init
railway up
railway variables set MC_HOST=dein.server.de MC_USERNAME=RandomBot MC_AUTH=offline
```

---

## ☁️ Andere Hosting-Optionen

### Render.com
1. New → Web Service
2. Verbinde GitHub Repo
3. Start Command: `node bot.js`
4. Environment Variables setzen

### Fly.io
```bash
fly launch
fly secrets set MC_HOST=dein.server.de MC_AUTH=offline
fly deploy
```

---

## 🎮 Bot-Verhalten

Der Bot führt alle 5-15 Sekunden zufällig eine dieser Aktionen durch:
- 🚶 In zufällige Richtung laufen (1-3 Sekunden)
- 👀 Zufällig umschauen
- 🦘 Springen
- 🤫 Schleichen
- 🛑 Stillstehen
- 👋 Arm schwingen

Der Bot verbindet sich automatisch neu wenn er kicked wird oder die Verbindung verliert.

---

## 📝 Cracked vs. Premium Server

**Cracked/Offline Server:**
```
MC_AUTH=offline
MC_USERNAME=IrgeneinName
```

**Premium Server (Microsoft-Account):**
```
MC_AUTH=microsoft
MC_USERNAME=deine@email.de
MC_PASSWORD=deinPasswort
```
