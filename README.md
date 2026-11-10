# Scide Skills – a Claude és Codex beállításom

Ez a tároló megmutatja, milyen **bővítményeket (pluginokat)**, **skilleket** és **csatlakozókat** használok a Claude és a Codex asztali appjaiban, és lépésről lépésre segít ugyanezt beállítani nálad is. Nem kell hozzá programozni tudni.

> Ebben a tárolóban **nincs jelszó, kulcs vagy személyes adat**. A saját fiókjaidat te kötöd be.

## Gyors kezdés (3 lépés)

1. **Telepítsd a Claude asztali appot** → [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md), 1. lépés
2. **Telepítsd az összes bővítményt egyetlen szöveg bemásolásával** → ugyanott, 2. lépés
3. **Kösd be a csatlakozókat** (Gmail, Drive stb.) → ugyanott, 3. lépés

Codexet használsz? → [CODEX-TELEPITES.md](CODEX-TELEPITES.md): telepítsd a Codex asztali appot, és egy kész szöveget kell bemásolnod, a többit a Codex elvégzi.

## Mi micsoda? (rövid szótár)

| Fogalom | Magyarul, egyszerűen |
|---|---|
| **Claude Code** | Mesterséges intelligencia a Claude asztali app **Code** fülén, ami kódot ír, fájlokat szerkeszt és kérdésekre válaszol. |
| **Skill** | Egy utasításcsomag (`SKILL.md` fájl), ami megtanít az MI-nek egy munkafolyamatot, pl. Word-dokumentum készítését. |
| **Plugin (bővítmény)** | Egy csomag, amiben skillek, parancsok és más kiegészítők vannak. Pár kattintással telepíthető az appban. |
| **Marketplace** | Plugin-áruház: egy lista arról, hogy hol találsz telepíthető pluginokat. |
| **Csatlakozó (connector / MCP)** | Összeköti az MI-t egy szolgáltatással, pl. Gmaillel vagy Google Drive-val. |

## Amit én használok

### Pluginok
Az **egyszerre telepítő szöveg** (lásd [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md), 2. lépés) az első 11 pluginot teszi fel. Minden skill neve a [SKILLEK.md](SKILLEK.md) fájlban van.

| Plugin | Honnan? | Mire jó? |
|---|---|---|
| `claude-code-setup` | Anthropic | Projektelemzés, automatizálási ajánlások. |
| `design` | Anthropic | Dizájn-kritika, akadálymentesség, UX-szövegek, kutatás. |
| `cowork-plugin-management` | Anthropic | Pluginok készítése és testreszabása. |
| `caveman` | Julius Brussee | Rövid, lényegre törő válaszok, kevesebb költség. |
| `ponytail` | Dietrich Gebert | Kódolásnál a lehető legkisebb, legegyszerűbb megoldás. |
| `mattpocock-skills` | Matt Pocock | Tervezés, spec, jegyek, TDD, kódáttekintés. |
| `agent-skills` | Addy Osmani | Teljes fejlesztési folyamat a specifikációtól a kiadásig. |
| `ecc` | Affaan Mustafa | Nagy csomag: kb. 311 skill, ügynökök, parancsok, hookok. |
| `diagram-design` | Cathryn Lavery | Sokféle diagram HTML-, SVG- és PNG-formátumban. |
| `humanizer` | blader | MI-szerű szöveg átírása természetesre. |
| `ui-ux-pro-max` | nextlevelbuilder | UI/UX tervezés, stílusok, paletták, betűpárok. |
| `obsidian-notes` | Anthropic könyvtár | Obsidian-jegyzetek rendezése. Az app bővítménybrowserében telepítsd. |
| `claude-mem`, `claude-mem-cowork` | Alex Newman, CMEM | Munkamenetek közti memória. **Nem** része az egyszerre telepítésnek, mert adatot rögzítenek és küldhetnek külső szolgáltatásnak. |

### Beépített skillek (a Claude-előfizetéssel járnak, nem kell telepíteni)
`docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research` (mélyebb kutatás), `skill-creator` (saját skill készítése), `google-workspace`, `import-memory`, `morning`, `setup-writing-style`.

### Csatlakozók (a saját fiókoddal kell bejelentkezned)
Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl, GitHub.

## Fontos tudnivalók

- A **jelszavaidat és kulcsaidat soha ne oszd meg** senkivel, és ne tedd fel GitHubra. Ha egy fájlban `token`, `key` vagy `password` szerepel, ne másold tovább.
- A közösségi pluginok **idegenek kódját** futtatják a gépeden (hookok, szkriptek). Telepítés előtt nézd át a forrásukat, főleg az `ecc` és a memória pluginok esetében.
- Elakadtál? Nézd meg a [hibaelhárítást](CLAUDE-TELEPITES.md#hibaelhárítás).
