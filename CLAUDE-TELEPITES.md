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

### A) Mindent egyszerre (egy csomag)

A tárolóban van egy `scide-all` nevű csomag, ami egyetlen telepítéssel felteszi a lenti 10 plugint. Ezek: `design`, `cowork-plugin-management`, `caveman`, `ponytail`, `mattpocock-skills`, `agent-skills`, `ecc`, `diagram-design`, `humanizer`, `ui-ux-pro-max`.

**Kattintással az appban:**

1. A Code fülön nyiss egy helyi munkamenetet.
2. Nyisd meg a **Settings → Customize → Plugins** oldalt, kattints az **Add marketplace** gombra, válaszd a **GitHub repo** lehetőséget, és add meg: `ScideCodes/Scide-skills`
3. A **+ → Plugins** menüben keresd meg a `scide-all` csomagot, és kattints az **Install** gombra.

**Vagy szöveggel:** másold be ezt a Code fül helyi munkamenetébe, és küldd el:

```
Telepítsd nekem a Scide Skills pluginjeit. Csak az alábbi két parancsot futtasd, és semmi mást ne módosíts. Ha egy parancs hibát ad, mondd meg a pontos hibaüzenetet, és állj meg. Ha a `claude` parancs nem található, állj meg, és mondd meg, hogy használjam a kattintós módszert. Kulcsot vagy jelszót ne kérj és ne írj fájlba. A végén sorold fel, mi sikerült és mi nem.

claude plugin marketplace add ScideCodes/Scide-skills
claude plugin install scide-all@scide-skills
```

Ezután indíts új munkamenetet, hogy minden betöltődjön.

A `claude-code-setup` (Anthropic) nevét a csomag nem használhatja, ezért azt külön kell felvenni. Ha kéred, ezt is add hozzá a fenti szöveghez:

```
claude plugin marketplace add anthropics/claude-plugins-official
claude plugin install claude-code-setup@claude-plugins-official
```

**Figyelem:** a csomag a pluginokat az eredeti tárolójukból tölti le, rögzített verzió nélkül, tehát a szerzők későbbi változtatásai is bekerülnek. Ezek idegenek kódját futtatják a gépeden (hookok, szkriptek), és az `ecc` nagyon sok skillt hoz. Ha nem akarod az egészet, használd a B) módszert, és csak a kellőket telepítsd. A pluginok és skillek listája: [SKILLEK.md](SKILLEK.md).

Ebben **nincs** benne az `obsidian-notes` (az Anthropic könyvtárából jön, a B) módszerrel telepítsd), és nincs benne a `claude-mem` és a `claude-mem-cowork` sem. Ezek rögzítik, mit csinál a Claude, és az utóbbi a leírása szerint a cmem.ai-nak is küld adatot. Ha kéred őket, a B) módszerrel add hozzá a `thedotmack` piacteret (`thedotmack/claude-mem`), és olvasd el előtte, mit gyűjtenek.

### B) Egyenként, kattintással

1. A Code fülön nyiss egy helyi munkamenetet.
2. Kattints a **+** gombra, és válaszd a **Plugins** menüpontot. Megnyílik a bővítménybrowser.
3. Keresd meg a bővítményt, és kattints az **Install** gombra.

Ha egy plugint nem találsz a listában, valamelyik másik piactérben van. Add hozzá az appban:

1. Nyisd meg a **Settings → Customize → Plugins** oldalt (a bal alsó sarokban a fiókmenüből érhető el a Settings).
2. Kattints az **Add marketplace** gombra, és válaszd a **GitHub repo** lehetőséget.
3. Add meg a forrást `<tulajdonos>/<tároló>` formában (például `JuliusBrussee/caveman`), majd telepítsd belőle a bővítményeket. A források a `.claude-plugin/marketplace.json` fájlban vannak.

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
