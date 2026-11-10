# Telepítés a Claude asztali appba (lépésről lépésre)

Szükséged lesz egy **Claude-előfizetésre** (Pro vagy Max) és a **Claude asztali appra** (Windowson és Macen is elérhető). Terminálra nincs szükség.

## 1. A Claude asztali app telepítése

1. Töltsd le az appot a https://claude.com oldalról, és telepítsd a rendszeredre.
2. Nyisd meg, és jelentkezz be a Claude-fiókoddal.
3. Az app tetején válaszd a **Code** fület. Itt működik a Claude Code, vagyis az, ami fájlokkal és kóddal dolgozik a gépeden.
4. Válassz egy mappát a gépeden (új munkamenet indításakor), ebben fog dolgozni a Claude.

A hivatalos útmutató mindig naprakész: https://code.claude.com/docs

## 2. Bővítmények (pluginok) telepítése

A bővítményeket a **Code** fülön, helyi (Local) munkamenetben tudod telepíteni. Felhős (cloud) munkamenetben nem érhető el a bővítménybrowser.

1. A Code fülön nyiss egy helyi munkamenetet.
2. Kattints a **+** gombra, és válaszd a **Plugins** menüpontot. Megnyílik a bővítménybrowser.
3. Keresd meg a bővítményt, és kattints az **Install** gombra.

Ezeket találod meg ott:

| Plugin | Mire jó? |
|---|---|
| `design` | Dizájn-értékelés, UX-szövegek |
| `obsidian-notes` | Obsidian-jegyzetek rendezése |

A `caveman` és a `ponytail` nálam saját piactérből jön. Ha nem látod őket, kérd el tőlem a forrásukat, és add hozzá az appban:

1. Nyisd meg a **Settings → Customize → Plugins** oldalt (a bal alsó sarokban a fiókmenüből érhető el a Settings).
2. Kattints az **Add marketplace** gombra, és válaszd a **GitHub repo** lehetőséget.
3. Add meg a forrást `<tulajdonos>/<tároló>` formában, majd telepítsd belőle a bővítményeket.

Telepítés után indíts új munkamenetet a Code fülön, hogy a bővítmények biztosan betöltődjenek.

Ellenőrzés: a **+ → Plugins → Manage plugins** oldalon látnod kell a telepített pluginokat bekapcsolva. Itt tudod később kikapcsolni vagy eltávolítani őket.

A menüpontok nevei az app verziójától függően kicsit eltérhetnek. Ha nem találod valamelyiket, nézd meg a hivatalos útmutatót.

## 3. Csatlakozók bekötése (Gmail, Drive stb.)

1. Nyisd meg az asztali app **Settings** oldalát, vagy a https://claude.ai oldalt a böngészőben.
2. Menj ide: **Settings → Connectors**
3. Minden szolgáltatásnál kattints a **Connect** gombra, és jelentkezz be a **saját** fiókoddal.

Csak azt kösd be, amit tényleg használni akarsz.

## 4. Kész, próbáld ki

Nyiss egy új munkamenetet az appban, és írd be például: „Készíts egy rövid Word-dokumentumot a bevásárlólistámról." Ha a Claude elkészíti a fájlt, a `docx` skill működik.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| Nem látom a **Code** fület | Frissítsd az asztali appot a legújabb verzióra, majd indítsd újra. |
| Nem látom a **Plugins** menüpontot | Helyi (Local) munkamenetben próbáld, felhős munkamenetben nem érhető el. Frissítsd az appot is. |
| Nem látok egy plugint a listában | Lehet, hogy privát piactérben van. Kérd el a forrást, és add hozzá a **Settings → Customize → Plugins → Add marketplace** oldalon. |
| Egy csatlakozó nem enged be | Jelentkezz ki és vissza a Settings → Connectors oldalon, majd csatlakoztasd újra. |
| Új plugin nem jelenik meg | Indíts új munkamenetet, vagy indítsd újra az appot. |

**Soha ne másold át** más gépéről a `~/.claude/.credentials.json` és a `~/.claude.json` fájlt. Ezekben a bejelentkezési adataid vannak.
