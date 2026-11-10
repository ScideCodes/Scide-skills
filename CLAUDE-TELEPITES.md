# Claude bővítmények telepítése – lépésről lépésre

Ez az útmutató akkor való neked, ha a Claude Code bővítményeit szeretnéd telepíteni, de nem vagy fejlesztő. Haladj sorban; ha egy gomb vagy menüpont neve eltér, nézd meg a [hivatalos útmutatót](https://code.claude.com/docs).

> **Biztonság:** a telepítéshez a Claude parancsokat futtathat a gépeden. Olvasd el, mire kér engedélyt, és csak azt hagyd jóvá, amit értesz. A belépési adataidat, jelszavaidat és API-kulcsaidat soha ne másold be.

## 1. Készítsd elő a Claude appot

1. Töltsd le a Claude asztali alkalmazást a [claude.com](https://claude.com) oldalról, és telepítsd.
2. Nyisd meg az appot, majd jelentkezz be a Claude-fiókoddal. A bővítmények használatához megfelelő Claude-előfizetésre lehet szükség.
3. Az appban nyisd meg a **Code** fület. Ez a Claude Code: itt dolgozhat a Claude fájlokkal és kóddal.
4. Indíts **helyi (Local)** munkamenetet, és válassz egy mappát, amellyel dolgozhat. A felhős (Cloud) munkamenetben az itt leírt telepítés nem működik.

## 2. Telepítsd a bővítményeket

### Ajánlott módszer: másold be a kérést a Claude Code-ba

1. A **Code** fülön indíts új helyi munkamenetet.
2. Másold be az alábbi teljes szöveget a Claude-nak.
3. A Claude műveleteket kérhet tőled. Minden kérésnél olvasd el, mit tenne; csak akkor engedélyezd, ha érted és jóváhagyod.
4. Várd meg a Claude összefoglalóját. Ha valamit kihagyott, később megpróbálhatod kézzel telepíteni.

```
Telepítsd nekem a lent felsorolt Claude Code bővítményeket a felhasználói szintre, hogy minden projektemben elérhetők legyenek.

Minden bővítménynél add hozzá a megadott forrást, majd telepítsd a bővítményt. Ha valamelyik lépés hibázik, ne próbálkozz találomra: folytasd a következővel, a végén pedig mondd el, mi sikerült és mi nem.

Forrás | Bővítmény neve
JuliusBrussee/caveman | caveman@caveman
DietrichGebert/ponytail | ponytail@ponytail
affaan-m/ECC | ecc@ecc
addyosmani/agent-skills | agent-skills@addy-agent-skills
cathrynlavery/diagram-design | diagram-design@diagram-design
blader/humanizer | humanizer@humanizer
nextlevelbuilder/ui-ux-pro-max-skill | ui-ux-pro-max@ui-ux-pro-max-skill
thedotmack/claude-mem | claude-mem (ellenőrizd a piactér pontos nevét a listában)
anthropics/claude-plugins-official | mattpocock-skills@claude-plugins-official és claude-code-setup@claude-plugins-official
anthropics/knowledge-work-plugins | design és cowork-plugin-management (a piactér pontos nevét ellenőrizd a listában)

Fontos szabályok:
- Az obsidian-notes, a claude-mem-cowork és minden olyan bővítmény maradjon ki, amelynek nem találod egyértelműen a forrását. Ne találgass; sorold fel ezeket a végén.
- Ne futtasd a claude-mem külön telepítőjét (npx claude-mem install). Ehhez előbb kérdezz meg.
- Ne szerkeszd a beállításfájlokat kézzel, és ne olvasd vagy másold át a ~/.claude/.credentials.json vagy ~/.claude.json fájlt.
- A végén sorold fel, mit telepítettél, mit hagytál ki és miért. Ezután emlékeztess, hogy indítsak új munkamenetet.
```

A `claude-mem` opcionális. Ez rögzítheti a munkamenetek tartalmát, és a teljes működéséhez külön telepítés kell. Ha nem szeretnéd ezt használni, hagyd ki.

### Másik módszer: telepítés az app menüjéből

Ezt válaszd, ha csak egy bővítményt szeretnél, vagy a fenti módszer nem sikerült.

1. Helyi munkamenetben, a **Code** fülön keresd meg a prompt melletti **+** gombot.
2. Válaszd az **Add plugins** (bővítmények hozzáadása), majd a **Browse plugins** (bővítmények böngészése) lehetőséget. A menüpontok neve appverziónként eltérhet.
3. Keresd meg a bővítményt, nyisd meg, és válaszd ki, hogy minden projektedben vagy csak az aktuális projektben legyen elérhető.
4. Ha nem találod, a **Settings → Customize → Plugins → Add marketplace → GitHub repo** menüben add hozzá a forrást `tulajdonos/tároló` alakban. Például: `JuliusBrussee/caveman`.
5. A telepítés után indíts új munkamenetet.

A forrásokat és a bővítmények rövid leírását a [README-ben](README.md) találod. Az Anthropic bővítményeit az app saját piacterén keresd.

## 3. Csatlakoztass külső szolgáltatásokat (ha szeretnél)

A csatlakozó például lehetővé teszi, hogy a Claude egy általad engedélyezett Google Drive-fájlt használjon. Csak a szükséges szolgáltatásokat kapcsold be.

1. Nyisd meg a Claude app **Settings** (Beállítások) oldalát, vagy a [claude.ai](https://claude.ai) oldalt.
2. Keresd meg a **Settings → Connectors** (Beállítások → Csatlakozók) részt.
3. Válaszd ki a szolgáltatást, kattints a **Connect** (Csatlakozás) gombra, majd jelentkezz be a saját fiókoddal.
4. Ellenőrizd, milyen hozzáférést kér a szolgáltatás. Csak akkor engedélyezd, ha megfelel neked.

Példák: Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl és GitHub.

## 4. Ellenőrizd, hogy működik-e

1. Indíts új munkamenetet a **Code** fülön.
2. Írd be például: „Készíts egy rövid Word-dokumentumot a bevásárlólistámról.”
3. Kérd meg a Claude-ot, hogy sorolja fel az elérhető skilleket, például: „Milyen skilleket tudsz használni?”

A **+ → Plugins → Manage plugins** (Bővítmények kezelése) részen ellenőrizheted, illetve kikapcsolhatod a telepített bővítményeket. A teljes skill-lista a [SKILLEK.md](SKILLEK.md) fájlban van.

## Mire figyelj?

- A bővítmények külső fejlesztők kódját futtathatják. Telepítés előtt nézd meg a forrást, és ne engedélyezz ismeretlen parancsot.
- Egyes bővítmények automatikusan futó parancsokat, úgynevezett hookokat állíthatnak be. Ha a Claude ilyenre kér engedélyt, előbb olvasd el a részleteket.
- Az `ecc` nagy csomag: sok skillel és paranccsal jár. Ha nem használod, kapcsold ki a **Manage plugins** részen.
- A `claude-mem` munkamenetadatokat rögzíthet. Csak akkor telepítsd, ha ezt tudatosan szeretnéd.
- Soha ne másold át más gépéről a `~/.claude/.credentials.json` vagy `~/.claude.json` fájlt. Ezek belépési adatokat tartalmazhatnak.

## Hibaelhárítás

| Mi történt? | Mit próbálj meg? |
|---|---|
| Nem látom a **Code** fület. | Frissítsd és indítsd újra a Claude appot. |
| Nem találom a bővítmények menüjét. | Ellenőrizd, hogy helyi (Local) munkamenetben vagy-e, majd frissítsd az appot. |
| A bemásolt kérésnél hiba történt. | Nézd meg a Claude összefoglalójában, melyik bővítmény maradt ki. Azt próbáld meg külön, az app menüjéből telepíteni. |
| Nem találom a keresett bővítményt. | Add hozzá a forrását a **Settings → Customize → Plugins → Add marketplace** menüben, vagy ellenőrizd a [README-ben](README.md) megadott forrást. |
| A `claude plugin` parancs ismeretlen. | Frissítsd az appot. Addig próbáld a kézi, menüből történő telepítést. |
| A csatlakozó nem működik. | Ellenőrizd a bejelentkezést a **Settings → Connectors** részen, majd csatlakoztasd újra. |
| Nem jelenik meg a frissen telepített bővítmény. | Indíts új munkamenetet, vagy zárd be és nyisd meg újra az appot. |
