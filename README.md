# Scide Skills – a Claude és Codex beállításom

Ez a tároló megmutatja, milyen **bővítményeket (pluginokat)**, **skilleket** és **csatlakozókat** használok a Claude és a Codex asztali appjaiban, és lépésről lépésre segít ugyanezt beállítani nálad is. Nem kell hozzá programozni tudni.

> Ebben a tárolóban **nincs jelszó, kulcs vagy személyes adat**. A saját fiókjaidat te kötöd be.

## Gyors kezdés (3 lépés)

1. **Telepítsd a Claude asztali appot** → [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md), 1. lépés
2. **Telepítsd a bővítményeket** → ugyanott, 2. lépés
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
| Név | Mire jó? |
|---|---|
| `caveman` | Rövid, lényegre törő válaszok, kevesebb szöveg és költség. |
| `ponytail` | Kódolásnál a lehető legkisebb, legegyszerűbb megoldást választja. |
| `design` | Dizájn-értékelés, akadálymentesség-ellenőrzés, UX-szövegek. |
| `obsidian-notes` | Jegyzetmappák rendezése és ellenőrzése Obsidianhoz. |

### Beépített skillek (a Claude-előfizetéssel járnak, nem kell telepíteni)
`docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research` (mélyebb kutatás), `skill-creator` (saját skill készítése), `google-workspace`.

### Csatlakozók (a saját fiókoddal kell bejelentkezned)
Gmail, Google Drive, Figma, Brevo, Netlify, Firecrawl, GitHub.

## Fontos tudnivalók

- A **jelszavaidat és kulcsaidat soha ne oszd meg** senkivel, és ne tedd fel GitHubra. Ha egy fájlban `token`, `key` vagy `password` szerepel, ne másold tovább.
- A `caveman` és a `ponytail` az én fiókom saját piacterében van. Ha nem látod őket a listában, írj nekem, és megküldöm a forrásukat.
- Elakadtál? Nézd meg a [hibaelhárítást](CLAUDE-TELEPITES.md#hibaelhárítás).
