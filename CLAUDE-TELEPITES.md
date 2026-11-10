# Telepítés a Claude asztali appba (lépésről lépésre)

Szükséged lesz egy **Claude-előfizetésre** (Pro vagy Max) és a **Claude asztali appra** (Windowson és Macen is elérhető). Terminált nem kell megnyitnod: a parancsokat a Claude futtatja le.

## 1. A Claude asztali app telepítése

1. Töltsd le az appot a https://claude.com oldalról, és telepítsd a rendszeredre.
2. Nyisd meg, és jelentkezz be a Claude-fiókoddal.
3. Az app tetején válaszd a **Code** fület. Itt működik a Claude Code, vagyis az, ami fájlokkal és kóddal dolgozik a gépeden.
4. Indíts **helyi (Local)** munkamenetet, és válassz egy mappát a gépeden. Ebben fog dolgozni a Claude. Felhős (cloud) munkamenetben a pluginok nem telepíthetők.

A hivatalos útmutató mindig naprakész: https://code.claude.com/docs

## 2. Az összes plugin telepítése

### A) Egy bemásolt szöveggel (ajánlott)

Nyiss egy új helyi munkamenetet a **Code** fülön, és másold be ezt a szöveget. A Claude lefuttatja a parancsokat, te csak az engedélykéréseket hagyod jóvá.

```
Telepítsd nekem az alábbi Claude Code pluginokat, user scope-ban (minden projektben elérhető legyen).

Minden pluginhoz két parancsot futtass le:
1. claude plugin marketplace add <forrás>
2. claude plugin install <plugin>@<marketplace neve>

Ha egy marketplace neve eltér a megadottól, nézd meg a "claude plugin marketplace list" kimenetét, és azt használd. Ha egy lépés hibázik, ne állj meg: ugord át, folytasd a következővel, és a végén jelezd.

Forrás | plugin@marketplace
JuliusBrussee/caveman | caveman@caveman
DietrichGebert/ponytail | ponytail@ponytail
affaan-m/ECC | ecc@ecc
addyosmani/agent-skills | agent-skills@addy-agent-skills
cathrynlavery/diagram-design | diagram-design@diagram-design
blader/humanizer | humanizer@humanizer
nextlevelbuilder/ui-ux-pro-max-skill | ui-ux-pro-max@ui-ux-pro-max-skill
thedotmack/claude-mem | claude-mem (a marketplace nevét a list parancs mutatja)
anthropics/claude-plugins-official | mattpocock-skills@claude-plugins-official és claude-code-setup@claude-plugins-official
anthropics/knowledge-work-plugins | design és cowork-plugin-management (ez a "Plugin Management"), a marketplace nevét a list parancs mutatja

Szabályok:
- Az "obsidian-notes", a "Claude mem cowork" és minden, aminek nem találod a forrását, maradjon ki. Ne találgass: a végén sorold fel, melyiket kell nekem kézzel telepítenem az app plugin-böngészőjéből.
- A claude-mem külön telepítőjét (npx claude-mem install) ne futtasd, előbb kérdezz meg.
- Ne szerkeszd kézzel a settings.json fájlt, és ne olvasd a ~/.claude/.credentials.json és a ~/.claude.json fájlt.
- A végén írd ki, mit telepítettél, mit hagytál ki és miért, majd mondd meg, hogy indítsak új munkamenetet.
```

Telepítés után indíts **új munkamenetet** a Code fülön, hogy a pluginok betöltődjenek.

Az `obsidian-notes` és a `claude-mem-cowork` plugint az app saját böngészőjéből telepítsd (lásd lent, B).

### B) Kézzel az appban

Akkor jó, ha az A) mód valamelyik lépése nem sikerült, vagy csak egy-egy plugint szeretnél.

1. A **Code** fülön, helyi munkamenetben kattints a prompt melletti **+** gombra, és válaszd az **Add plugins** menüpontot. Ha ott **Plugins** áll, válaszd azt, majd a **Browse plugins** lehetőséget. Megnyílik a bővítménybrowser.
2. Keresd meg a bővítményt, kattints rá, és válaszd ki, hogy kinek települjön (a **te fiókodnak** minden projektben, vagy csak az adott projektnek).
3. Ha egy plugin nincs a listában, add hozzá a marketplace-ét: **Settings → Customize → Plugins → Add marketplace → GitHub repo**, és írd be a forrást `tulajdonos/tároló` formában.

A lenti forrásokat add hozzá, ha kézzel dolgozol:

| Plugin | Marketplace forrása |
|---|---|
| `caveman` | `JuliusBrussee/caveman` |
| `ponytail` | `DietrichGebert/ponytail` |
| `ecc` | `affaan-m/ECC` |
| `agent-skills` | `addyosmani/agent-skills` |
| `diagram-design` | `cathrynlavery/diagram-design` |
| `humanizer` | `blader/humanizer` |
| `ui-ux-pro-max` | `nextlevelbuilder/ui-ux-pro-max-skill` |
| `claude-mem` | `thedotmack/claude-mem` |
| `mattpocock-skills`, `claude-code-setup` | Anthropic hivatalos piactér, az appban alapból megvan |
| `design`, `plugin-management`, `obsidian-notes`, `claude-mem-cowork` | az app bővítménybrowserében keresd név szerint |

A menüpontok nevei az app verziójától függően kicsit eltérhetnek. Ha nem találod valamelyiket, nézd meg a hivatalos útmutatót: https://code.claude.com/docs/en/discover-plugins

### Ellenőrzés

A **+ → Plugins → Manage plugins** oldalon látnod kell a telepített pluginokat bekapcsolva. Itt tudod később kikapcsolni vagy eltávolítani őket. A skilleket a prompt mezőbe írt `/` jellel is megnézheted: `/<plugin>:<skill>` alakban jelennek meg. A teljes listát a [SKILLEK.md](SKILLEK.md) fájlban találod.

### Mire figyelj

- A pluginok **idegen fejlesztők kódját** futtatják a gépeden. A `ecc` és a `claude-mem` hookokat is beállít, vagyis a munkád közben automatikusan lefutó parancsokat. Telepítés előtt nézd át a plugin GitHub-oldalát.
- Az `ecc` nagy csomag (397 skill és parancs), ezért a Claude ettől lassabb és több tokent fogyaszthat. Ha nem kell az összes, kapcsold ki a **Manage plugins** oldalon.
- A `claude-mem` rögzíti, mit csinálsz a munkamenetekben, és külön telepítőt (Node.js 20+ és Bun) használ a teljes működéshez. Csak akkor telepítsd, ha tudod, mire kell. A hivatalos útmutató: https://docs.claude-mem.ai/installation
- A harmadik féltől származó piacterek automatikus frissítése alapból ki van kapcsolva. A **Marketplaces** fülön tudod bekapcsolni.

## 3. Csatlakozók bekötése (Gmail, Drive stb.)

1. Nyisd meg az asztali app **Settings** oldalát, vagy a https://claude.ai oldalt a böngészőben.
2. Menj ide: **Settings → Connectors**
3. Minden szolgáltatásnál kattints a **Connect** gombra, és jelentkezz be a **saját** fiókoddal.

Csak azt kösd be, amit tényleg használni akarsz. A javasolt lista: Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl, GitHub.

## 4. Kész, próbáld ki

Nyiss egy új munkamenetet az appban, és írd be például: „Készíts egy rövid Word-dokumentumot a bevásárlólistámról." Ha a Claude elkészíti a fájlt, a beépített `docx` skill működik. A pluginokat így próbálhatod ki: írd be, hogy „Mutasd meg, milyen skillek vannak telepítve", vagy a `caveman` pluginnál írd be: `/caveman`.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| Nem látom a **Code** fület | Frissítsd az asztali appot a legújabb verzióra, majd indítsd újra. |
| Nem látom a **Plugins** vagy az **Add plugins** menüpontot | Helyi (Local) munkamenetben próbáld, felhős munkamenetben nem érhető el. Frissítsd az appot is. |
| Az A) mód közben hibát ír egy plugin | Ez normális lehet. A Claude a végén kilistázza a kihagyottakat, ezeket telepítsd a B) móddal. |
| Nem látok egy plugint a listában | Add hozzá a marketplace-ét a **Settings → Customize → Plugins → Add marketplace** oldalon, a fenti táblázat szerint. |
| A `claude plugin` parancs ismeretlen | Frissítsd az asztali appot, majd próbáld újra. Régi Claude Code verzióban nem biztos, hogy léteznek a plugin-parancsok. Addig használd a B) módot. |
| Egy csatlakozó nem enged be | Jelentkezz ki és vissza a Settings → Connectors oldalon, majd csatlakoztasd újra. |
| Új plugin nem jelenik meg | Indíts új munkamenetet, vagy indítsd újra az appot. |
| Túl lassú vagy túl sokat beszél a Claude | Kapcsold ki a **Manage plugins** oldalon a nagyobb csomagokat (`ecc`, `claude-mem`). |

**Soha ne másold át** más gépéről a `~/.claude/.credentials.json` és a `~/.claude.json` fájlt. Ezekben a bejelentkezési adataid vannak.
