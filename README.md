# Claude / Codex skillek – egyszerű útmutató kezdőknek

Ez a tároló egy személyes összeállítás: megmutatja, milyen Claude- és Codex-bővítményeket, skilleket és csatlakozókat használok. Az útmutatók segítenek a telepítésben akkor is, ha még nem használtál hasonló eszközt.

> **Fontos:** a telepítés külső fejlesztők bővítményeit teszi elérhetővé. Mindig nézd meg, mit telepítesz, és csak azt hagyd jóvá, amiben megbízol. Jelszót, belépési kódot vagy API-kulcsot ne másolj be az MI-nek, és ne tölts fel a tárolóba.

## Melyik útmutatót válasszam?

- Claude-ot használsz? Nyisd meg a [Claude telepítési útmutatóját](CLAUDE-TELEPITES.md).
- Codexet használsz? Nyisd meg a [Codex telepítési útmutatóját](CODEX-TELEPITES.md).
- Csak a skillek nevét szeretnéd megnézni? Itt a [skillek teljes listája](SKILLEK.md).

A Claude és a Codex két külön alkalmazás. Nem kell mindkettőt telepítened: válaszd azt az útmutatót, amelyik alkalmazást használod.

## Egyszerű szótár

| Kifejezés | Mit jelent? |
|---|---|
| **Claude Code** | A Claude kódolással és fájlokkal dolgozó módja. |
| **Codex** | Az OpenAI kódolási feladatokra használható asszisztense. |
| **Skill** | Rövid útmutató, amely egy adott feladat elvégzésében segíti az MI-t. |
| **Plugin (bővítmény)** | Telepíthető csomag. Egy csomag több skillt és más kiegészítőt is tartalmazhat. |
| **Marketplace (piactér)** | A bővítmények katalógusa, ahonnan kiválaszthatod és telepítheted őket. |
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

Az Anthropic bővítményei és a `claude-mem-cowork` csak Claude-ban használhatók. Nincs hozzájuk Codex-változat.

### Claude-ban eleve elérhető skillek

Ezeket a Claude-előfizetés tartalmazza, ezért külön telepítésük nem szükséges: `docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research`, `skill-creator`, `google-workspace`, `import-memory`, `morning` és továbbiak.

### Csatlakozók

A példák: Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl és GitHub. Csak azt a szolgáltatást csatlakoztasd, amelyre valóban szükséged van, és mindig a saját fiókoddal jelentkezz be.

## Biztonsági tudnivalók

- A bővítmények kódja a gépeden futhat. Telepítés előtt nézd meg a forrásukat, és ne hagyj jóvá olyan műveletet, amelyet nem értesz.
- Egyes bővítmények automatikusan futó parancsokat (hookokat) is beállíthatnak. A Claude- és Codex-útmutató elmondja, mire figyelj.
- A `claude-mem` rögzítheti a munkamenetek adatait. A Cowork-változat adatot küld a cmem.ai szolgáltatásnak. Ha ezt nem szeretnéd, ne telepítsd.
- A belépési adataid, jelszavaid és API-kulcsaid maradjanak titokban. Ne másold be őket az MI-nek vagy egy nyilvános tárolóba.

## Elakadtál?

A telepítési útmutatók végén egyszerű hibaelhárítási táblázatot találsz: [Claude](CLAUDE-TELEPITES.md#hibaelhárítás) · [Codex](CODEX-TELEPITES.md#hibaelhárítás).
