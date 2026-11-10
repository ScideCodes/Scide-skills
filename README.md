# Claude / Codex skillek – kezdő útmutató

Szeretnél skilleket telepíteni, de nem tudod, hol kezdd? Kövesd az alábbi lépéseket. **Nem kell mindkét alkalmazást telepítened** — válaszd a Claude vagy a Codex útmutatóját.

> **Biztonság:** csak olyan műveletet engedélyezz, amit értesz. Jelszót, belépési kódot és API-kulcsot soha ne másolj be az MI-nek.

## Kezdés – válaszd ki az alkalmazásodat

### Claude-ot használsz?

1. Nyisd meg a **Claude asztali alkalmazást**, és jelentkezz be.
2. Kattints felül a **Code** fülre.
3. Válaszd a **Local** (helyi) munkamenetet, majd válaszd ki azt a mappát, amellyel dolgozni szeretnél.
4. Indíts egy új munkamenetet.
5. Kattints az alábbi gombra, és kövesd az útmutatót: **[Claude bővítmények telepítése – lépésről lépésre](CLAUDE-TELEPITES.md)**.

Az útmutatóban találsz egy kész szöveget: másold be a Claude Code beszélgetésébe, olvasd el a Claude engedélykéréseit, majd csak azokat hagyd jóvá, amelyeket értesz.

### Codexet használsz?

1. Nyisd meg a **Codex asztali alkalmazást**, és jelentkezz be.
2. Nyiss egy **új beszélgetést** (a Codexben ez „thread” vagy „szál” néven is szerepelhet).
3. Kattints az alábbi gombra, és kövesd az útmutatót: **[Codex bővítmények telepítése – lépésről lépésre](CODEX-TELEPITES.md)**.

Az útmutatóban találsz egy kész szöveget: másold be a Codex beszélgetésébe, olvasd el a parancsokra vonatkozó engedélykéréseket, majd csak azokat hagyd jóvá, amelyeket értesz.

### Csak a skill-listát keresed?

Itt találod: **[Az összes skill listája](SKILLEK.md)**.

## Mi ez a tároló?

Ez a tároló Claude- és Codex-bővítmények, skillek és csatlakozók gyűjteménye. A telepítési útmutatók akkor is végigvezetnek a lépéseken, ha most használod először ezeket az eszközöket.

| Kifejezés | Egyszerű magyarázat |
|---|---|
| **Claude Code** | A Claude fájlokkal és kóddal dolgozó módja. |
| **Codex** | Az OpenAI kódolási feladatokra használható asszisztense. |
| **Skill** | Rövid útmutató, amely egy adott feladat elvégzésében segíti az MI-t. |
| **Bővítmény (plugin)** | Telepíthető csomag, amely több skillt és más kiegészítőt is tartalmazhat. |
| **Piactér (marketplace)** | Katalógus, ahonnan bővítményeket lehet kiválasztani és telepíteni. |
| **Csatlakozó** | Kapcsolat egy másik szolgáltatáshoz, például a Gmailhez vagy a Google Drive-hoz. Bekapcsoláskor a saját fiókoddal kell bejelentkezned. |
| **Helyi munkamenet** | Olyan Claude Code-munkamenet, amely a kiválasztott mappával dolgozik a saját gépeden. |

## A bővítmények listája

A „Skillek” oszlop a bővítményhez tartozó skillek számát jelzi. A számok a készítéskori állapotot mutatják, és a bővítmények frissítésével változhatnak.

| Bővítmény | Mire való? | Skillek | Forrás | Claude | Codex |
|---|---|---:|---|---|---|
| `caveman` | Rövid, lényegre törő válaszok | 23 | [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | igen | igen, csak skillek |
| `ponytail` | Egyszerű, kis méretű kódmegoldások | 6 | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | igen | igen |
| `mattpocock-skills` | Mérnöki munkafolyamatok, például tervezés és kódellenőrzés | 27 | [mattpocock/skills](https://github.com/mattpocock/skills) | igen | igen |
| `ecc` | Fejlesztői eszközök, skillek és parancsok | 397 | [affaan-m/ECC](https://github.com/affaan-m/ECC) | igen | igen |
| `agent-skills` | Fejlesztési folyamatok a tervezéstől a kiadásig | 34 | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | igen | igen |
| `diagram-design` | Diagramok készítése | 7 | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | igen | igen |
| `humanizer` | Természetesebb megfogalmazás | 1 | [blader/humanizer](https://github.com/blader/humanizer) | igen | igen, csak skill |
| `ui-ux-pro-max` | Felülettervezési ötletek és eszközök | 7 | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | igen | igen, projektben |
| `claude-mem` | Munkamenetek közti memória | 30 | [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) | igen | választható, kézi telepítéssel |
| `claude-mem-cowork` | Memória a Claude Coworkhöz; adatot küld a cmem.ai szolgáltatásnak | 3 | az alkalmazás piactere | igen | nem |
| `claude-code-setup` | Javaslatok Claude Code-beállításokhoz | 1 | Anthropic | igen | nem |
| `design` | Dizájn, akadálymentesség és felhasználói élmény | 7 | Anthropic | igen | nem |
| `obsidian-notes` | Obsidian-jegyzetek kezelése | 1 | Anthropic | igen | nem |
| `plugin-management` | Bővítmények készítése és beállítása | 2 | Anthropic | igen | nem |

Az Anthropic bővítményei és a `claude-mem-cowork` csak Claude-ban használhatók, Codex-változatuk nincs.

### Claude-ban eleve elérhető skillek

Ezeket a Claude-előfizetés tartalmazza, ezért külön telepítésük nem szükséges: `docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research`, `skill-creator`, `google-workspace`, `import-memory`, `morning` és továbbiak.

### Csatlakozók

Például Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl és GitHub. Csak azt a szolgáltatást csatlakoztasd, amelyre valóban szükséged van, és mindig a saját fiókoddal jelentkezz be. A Claude-csatlakozók beállítását a [Claude telepítési útmutató](CLAUDE-TELEPITES.md#3-csatlakoztass-külső-szolgáltatásokat-ha-szeretnél) mutatja be.

## Biztonsági tudnivalók

- A bővítmények kódja a gépeden futhat. Telepítés előtt nézd meg a forrásukat, és ne hagyj jóvá olyan műveletet, amelyet nem értesz.
- Egyes bővítmények automatikusan futó parancsokat (hookokat) is beállíthatnak. A telepítési útmutatók elmondják, mire figyelj.
- A `claude-mem` rögzítheti a munkamenetek adatait. A Cowork-változat adatot küld a cmem.ai szolgáltatásnak. Ha ezt nem szeretnéd, ne telepítsd.
- A belépési adataid, jelszavaid és API-kulcsaid maradjanak titokban. Ne másold be őket az MI-nek vagy egy nyilvános tárolóba.

## Elakadtál?

Nézd meg a részletes hibaelhárítást: [Claude útmutató](CLAUDE-TELEPITES.md#hibaelhárítás) · [Codex útmutató](CODEX-TELEPITES.md#hibaelhárítás).
