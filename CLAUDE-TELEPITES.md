# Telepítés Claude Code-hoz (lépésről lépésre)

Szükséged lesz egy **Claude-előfizetésre** (Pro vagy Max) és egy terminálra.
Terminál: Windowson a *PowerShell*, Macen a *Terminal* alkalmazás.

## 1. Claude Code telepítése

Másold be a terminálba a rendszeredhez tartozó parancsot, majd nyomj Entert.

**Mac vagy Linux:**
```
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```
irm https://claude.ai/install.ps1 | iex
```

Ha ez nem működik, a hivatalos útmutató mindig naprakész: https://code.claude.com/docs

Indítsd el:
```
claude
```
Első indításkor megnyílik a böngésző, ott jelentkezz be a Claude-fiókoddal.

## 2. Bővítmények (pluginok) telepítése

A Claude Code-on belül írd be:
```
/plugin
```
Megnyílik egy menü. Válaszd a **Discover** fület, keresd meg a bővítményt, nyomj Entert, és válaszd az **Install** lehetőséget.

Ezeket találod meg ott:

| Plugin | Mire jó? |
|---|---|
| `design` | Dizájn-értékelés, UX-szövegek |
| `obsidian-notes` | Obsidian-jegyzetek rendezése |

A `caveman` és a `ponytail` nálam saját piactérből jön. Ha nem látod őket, kérd el tőlem a forrásukat, és add hozzá így:
```
/plugin marketplace add <tulajdonos>/<tároló>
```
Telepítés után indítsd újra a Claude Code-ot: lépj ki a `/exit` paranccsal, majd indítsd el újra a `claude` paranccsal.

Ellenőrzés: írd be a `/plugin` parancsot, és nézd meg, hogy a telepített pluginok mellett ott van-e az „enabled" felirat.

## 3. Csatlakozók bekötése (Gmail, Drive stb.)

Ezt a **böngészőben** végezd el, nem a terminálban:

1. Nyisd meg: https://claude.ai
2. Menj ide: **Settings → Connectors**
3. Minden szolgáltatásnál kattints a **Connect** gombra, és jelentkezz be a **saját** fiókoddal.

Csak azt kösd be, amit tényleg használni akarsz.

## 4. Kész, próbáld ki

Indítsd el a `claude` parancsot, és írd be például: „Készíts egy rövid Word-dokumentumot a bevásárlólistámról." Ha a Claude elkészíti a fájlt, a `docx` skill működik.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| `claude: command not found` | Zárd be és nyisd meg újra a terminált, majd próbáld újra. |
| A `/plugin` parancs nem létezik | Frissítsd a Claude Code-ot: `claude update`. |
| Nem látok egy plugint a listában | Lehet, hogy privát piactérben van. Kérd el a forrást, és használd a `/plugin marketplace add` parancsot. |
| Egy csatlakozó nem enged be | Jelentkezz ki és vissza a claude.ai Settings → Connectors oldalon, majd csatlakoztasd újra. |
| Új plugin nem jelenik meg | Indítsd újra a Claude Code-ot. |

**Soha ne másold át** más gépéről a `~/.claude/.credentials.json` és a `~/.claude.json` fájlt. Ezekben a bejelentkezési adataid vannak.
