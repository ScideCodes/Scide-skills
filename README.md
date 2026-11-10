# Claude / Codex Skill – a Claude és Codex beállításom

Ez a tároló megmutatja, milyen **bővítményeket (pluginokat)**, **skilleket** és **csatlakozókat** használok a Claude és a Codex asztali appjaiban, és segít ugyanezt **egyetlen bemásolt szöveggel** elindítani. A cél az, hogy ugyanazt a beállítást könnyen lehessen átvinni más gépekre és más felhasználókhoz is.

> Ebben a tárolóban **nincs jelszó, kulcs vagy személyes adat**. A saját fiókjaidat te kötöd be.

## Gyors kezdés

1. **Claude asztali app** → [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md): telepítsd az appot, másold be a kész szöveget, és az összes plugin települ.
2. **Codex asztali app** → [CODEX-TELEPITES.md](CODEX-TELEPITES.md): ugyanígy, egy kész szöveggel.
3. **Csatlakozók** (Gmail, Drive stb.) → [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md#3-csatlakozók-bekötése-gmail-drive-stb), a saját fiókoddal.

A skillek teljes listáját a [SKILLEK.md](SKILLEK.md) fájlban találod.

## Mi micsoda? (rövid szótár)

| Fogalom | Magyarul, egyszerűen |
|---|---|
| **Claude Code** | Mesterséges intelligencia a Claude asztali app **Code** fülén, ami kódot ír, fájlokat szerkeszt és kérdésekre válaszol. |
| **Codex** | Az OpenAI hasonló kódoló asszisztense, saját asztali appal. |
| **Skill** | Egy utasításcsomag (`SKILL.md` fájl), ami megtanít az MI-nek egy munkafolyamatot, pl. Word-dokumentum készítését. |
| **Plugin (bővítmény)** | Egy csomag, amiben skillek, parancsok és más kiegészítők vannak. Egy plugin telepítése az összes skilljét behozza. |
| **Marketplace** | Plugin-áruház: egy lista arról, hogy hol találsz telepíthető pluginokat. Egy GitHub-tároló is lehet marketplace. |
| **Csatlakozó (connector / MCP)** | Összeköti az MI-t egy szolgáltatással, pl. Gmaillel vagy Google Drive-val. |

## Pluginok (mind a 14)

A „Skillek” oszlop azt mutatja, hány skillt hoz a plugin. A forrás az a GitHub-tároló, ahonnan a plugin települ.

| Plugin | Mire jó? | Skillek | Forrás | Claude | Codex |
|---|---|---|---|---|---|
| `caveman` | Rövid, lényegre törő válaszok, kevesebb szöveg és költség | 23 | [JuliusBrussee/caveman](https://github.com/JuliusBrussee/caveman) | igen | igen, csak skillek |
| `ponytail` | Kódolásnál a lehető legkisebb megoldást választja | 6 | [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) | igen | igen |
| `mattpocock-skills` | Mérnöki munkafolyamatok: kérdezés, specifikáció, TDD, kódáttekintés | 27 | [mattpocock/skills](https://github.com/mattpocock/skills) | igen | igen |
| `ecc` | Everything Claude Code: ügynökök, skillek és parancsok csapatoknak | 397 | [affaan-m/ECC](https://github.com/affaan-m/ECC) | igen | igen |
| `agent-skills` | Addy Osmani teljes fejlesztési folyamata a specifikációtól az élesítésig | 34 | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | igen | igen |
| `diagram-design` | Szép, szerkesztői minőségű diagramok | 7 | [cathrynlavery/diagram-design](https://github.com/cathrynlavery/diagram-design) | igen | igen |
| `humanizer` | MI-hangzású szöveg átírása természetesre | 1 | [blader/humanizer](https://github.com/blader/humanizer) | igen | igen, csak skill |
| `ui-ux-pro-max` | UI/UX tervezési adatbázis: stílusok, színek, betűk | 7 | [nextlevelbuilder/ui-ux-pro-max-skill](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill) | igen | igen, projektben használható |
| `claude-mem` | Munkamenetek közti memória | 30 | [thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) | igen | opcionális, kézzel |
| `claude-mem-cowork` | A Claude-Mem a Cowork-höz, a felhőbe (cmem.ai) küld adatot | 3 | az app plugin-böngészője | igen | nem |
| `claude-code-setup` | Javaslatok Claude Code automatizálásokra | 1 | Anthropic | igen | nem |
| `design` | Dizájn-értékelés, akadálymentesség-ellenőrzés, UX-szövegek | 7 | Anthropic | igen | nem |
| `obsidian-notes` | Jegyzetmappák rendezése és ellenőrzése Obsidianhoz | 1 | Anthropic | igen | nem |
| `plugin-management` | Saját pluginok készítése és testreszabása | 2 | Anthropic | igen | nem |

Az Anthropic-pluginokat és a `claude-mem-cowork`-ot csak Claude használja, ezeknek nincs Codex-változata.

### Beépített skillek (a Claude-előfizetéssel járnak, nem kell telepíteni)

`docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research` (mélyebb kutatás), `skill-creator` (saját skill készítése), `google-workspace`, `import-memory`, `morning`, `setup-writing-skill`, `web-search`.

### Csatlakozók (a saját fiókoddal kell bejelentkezned)

Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl, GitHub.

## Fontos tudnivalók

- A **jelszavaidat és kulcsaidat soha ne oszd meg** senkivel, és ne tedd fel GitHubra. Ha egy fájlban `token`, `key` vagy `password` szerepel, ne másold tovább.
- A pluginok **idegen fejlesztők kódját** futtatják a gépeden, és egyesek (pl. `ecc`, `claude-mem`) hookokat is beállítanak, vagyis a munkád közben automatikusan lefutó parancsokat. Telepítés előtt ellenőrizd a forrást.
- A `claude-mem` és a `claude-mem-cowork` rögzíti, mit csinálsz a munkamenetekben. A Cowork-változat az adatot a cmem.ai szolgáltatásnak küldi. Ha ez nem kell, hagyd ki őket.
- Elakadtál? Nézd meg a hibaelhárítást: [Claude](CLAUDE-TELEPITES.md#hibaelhárítás), [Codex](CODEX-TELEPITES.md#hibaelhárítás).
