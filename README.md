# Wichtelo-Mat 🎄

Familien-Wichteln 2026: Jede Person trägt ihren Wunschzettel ein, danach zieht jede/r auf dem eigenen Gerät ein Los. Die Seite ist eine einzelne `index.html`, die Daten liegen in einer kostenlosen Firebase Realtime Database.

## Einrichtung (einmalig, ca. 10 Minuten)

### 1. Firebase-Datenbank anlegen
1. Auf https://console.firebase.google.com mit einem Google-Konto anmelden.
2. **Projekt hinzufügen** → Namen vergeben (z. B. `wichtelomat`) → Google Analytics kann aus bleiben.
3. Links im Menü **Build → Realtime Database** → **Datenbank erstellen**.
4. Standort **Belgien (europe-west1)** wählen.
5. Als Sicherheitsregeln **Im Testmodus starten** wählen und bestätigen.
6. Oben in der Datenbank steht eine URL, z. B. `https://wichtelomat-xxxx-default-rtdb.europe-west1.firebasedatabase.app`. Diese kopieren.

### 2. URL eintragen
In `index.html` ganz oben im Skript die URL bei `DB_URL` einfügen:

```js
const DB_URL = "https://wichtelomat-xxxx-default-rtdb.europe-west1.firebasedatabase.app";
```

Ohne URL läuft die Seite im Demo-Modus (Daten nur im eigenen Browser).

### 3. Mit GitHub Pages veröffentlichen
1. Im GitHub-Repo: **Settings → Pages**.
2. **Source:** *Deploy from a branch*, Branch `main`, Ordner `/ (root)` → **Save**.
3. Nach etwa einer Minute ist die Seite erreichbar unter
   `https://lindix-code.github.io/wichtelomat-2026/`
4. Diesen Link an die Familie schicken.

## Ablauf für die Familie
1. Seite öffnen und den eigenen Namen auswählen (wird auf dem Gerät gemerkt).
2. Wunschzettel schreiben und absenden.
3. Sobald alle 14 Wunschzettel da sind, wird „Jetzt Los ziehen!“ aktiv.
4. Button drücken: Nach einem 5-Sekunden-Countdown erscheint der Wichtel mit Gesicht und Namen. Die Auslosung gilt für alle gleich und bleibt gespeichert.

## Anpassen
- **Teilnehmer:** `familyMembers` im Skript.
- **Wer nicht wen beschenken darf:** `groups` im Skript. Innerhalb einer Gruppe wird nicht untereinander gewichtelt.
- **Gesichter:** Bilder in `gesichter/` ablegen (WebP/PNG mit transparentem Hintergrund) und in `faces` im Skript eintragen. Wer dort fehlt, bekommt ein Emoji.
- **Budget:** Text im Hinweis unter dem Wunschfeld.

## Hinweise
- Es gibt keine PIN: Wer den Link kennt, kann Namen auswählen. Das ist als Vertrauensbasis in der Familie gedacht.
- Den Link nur an die Familie schicken.
- Nach Weihnachten die Firebase-Datenbank (oder das ganze Projekt) löschen.
- Neu auslosen: In der Firebase-Konsole den Eintrag `assignments` löschen.
