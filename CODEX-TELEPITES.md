# Telepítés a Codex asztali appba (kész szöveggel)

A Codex az OpenAI kódoló asszisztense. A lenti szöveget be kell másolnod a Codex appba, és a Codex magától telepíti a pluginokat és a skilleket. Terminált nem kell megnyitnod.

A Claude-oldali pluginokról és a miértekről a [README.md](README.md) szól, a skillek listája a [SKILLEK.md](SKILLEK.md) fájlban van.

## 1. A Codex app telepítése (ha még nincs)

1. Töltsd le a Codex appot macOS-re vagy Windowsra innen: https://developers.openai.com/codex/app. Intel-alapú Macen az Intel verziót válaszd.
2. Telepítsd, nyisd meg, és jelentkezz be a ChatGPT-fiókoddal (vagy egy OpenAI API-kulccsal).

A plugin-parancsokhoz **Codex 0.122 vagy újabb** kell. Ha a telepítés közben a Codex azt írja, hogy ismeretlen a `codex plugin` parancs, frissítsd az appot.

## 2. Másold be ezt a szöveget a Codexbe

Nyiss egy új szálat (thread) az appban, és illeszd be ezt. A Codex minden parancs előtt engedélyt kérhet, ezeket hagyd jóvá.

```
Telepítsd nekem az alábbi pluginokat és skilleket a Codexbe. Ha egy lépés hibázik, ne állj meg: ugord át, folytasd a következővel, és a végén jelezd.

A) Natív pluginok. Mindegyikhez futtasd le a két parancsot:
- codex plugin marketplace add DietrichGebert/ponytail
  codex plugin add ponytail@ponytail
- codex plugin marketplace add mattpocock/skills
  codex plugin add mattpocock-skills@mattpocock
- codex plugin marketplace add affaan-m/ECC
  codex plugin add ecc@ecc
- codex plugin marketplace add addyosmani/agent-skills
  codex plugin add agent-skills@agent-skills
- codex plugin marketplace add cathrynlavery/diagram-design
  codex plugin add diagram-design@diagram-design

B) Csak skillek (ezeknek nincs natív Codex-pluginjuk):
- npx skills add JuliusBrussee/caveman -g -a codex
- npx skills add blader/humanizer -g -a codex
Ha az npx nem érhető el vagy hibázik, használd a beépített $skill-installer skillt, vagy klónozd a tárolót egy ideiglenes mappába, és másold a skill-mappákat ide: $HOME/.agents/skills/<skill neve>/SKILL.md. A mappa neve a skill neve. Ha a $HOME/.agents/skills mappa nem létezik, hozd létre.

C) ui-ux-pro-max:
- npm install -g ui-ux-pro-max-cli, majd a megnyitott projektmappában: uipro init --ai codex
Ez csak az adott projektmappába telepít. Kérdezd meg tőlem, melyik projektbe kérem. Ha minden projektben kell, a letöltött skill-mappát másold a $HOME/.agents/skills alá.

D) A claude-mem telepítőjét hagyd ki. Interaktív, külön eszközöket (Bun) telepít, és rögzíti a munkámat. Ha kell, majd külön kérem.

Szabályok:
- Ha egy plugin hookot kér engedélyezni (a /hooks menüben), ne engedélyezd helyettem. Írd ki, mit kér, és én döntök.
- Az ecc-t és az agent-skillst ne telepítsd más módszerrel is ugyanarra a gépre (pl. másoló szkripttel), mert minden skill kétszer jelenne meg.
- A Claude-hoz kötött dolgokat (design, obsidian-notes, plugin-management, claude-code-setup, claude-mem-cowork, valamint a Csatlakozók) hagyd ki. Ha MCP-szerver kell valamihez, kérdezz, és mondd meg, hol adhatom hozzá a Codex app beállításaiban. Kulcsot vagy jelszót soha ne írj fájlba.
- Ne olvasd és ne másold a ~/.claude/.credentials.json és a ~/.claude.json fájlt.
- A végén írd ki, mit telepítettél és mit hagytál ki, majd mondd meg, hogy indítsam újra a Codex appot és nyissak új szálat.
```

## 3. Ellenőrzés

Zárd be és nyisd meg újra a Codex appot, nyiss új szálat, és kérdezd meg: „Milyen skillek vannak telepítve?" A listában ott kell lennie a telepített skilleknek.

Ha a skillek fájljait is látni szeretnéd, a Codex a felhasználói skilleket innen tölti be: `$HOME/.agents/skills`. A projektekhez tartozó skillek a projekt `.agents/skills` mappájában vannak. A pluginok skilljeit a Codex a plugin-gyorsítótárból tölti be, ezeket nem találod a fenti mappában. A skilleket `@` jellel hívhatod meg, pl. `@spec-driven-development`.

## Mire figyelj

- A pluginok **idegen fejlesztők kódját** futtatják a gépeden. Telepítés előtt nézd át a plugin GitHub-oldalát, a linkek a [README.md](README.md) táblázatában vannak.
- Az `ecc` nagy csomag (397 skill és parancs). Ha nem kell, ne telepítsd, vagy telepítés után kapcsold ki.
- Egy skillt egy módszerrel telepíts, mert különben kétszer jelenik meg a listában.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| Nem találom a Codex appot | Töltsd le innen: https://developers.openai.com/codex/app. Macen és Windowson is elérhető. |
| A `codex plugin` parancs ismeretlen | Frissítsd a Codex appot a legújabb verzióra (0.122 vagy újabb kell). |
| A Codex nem találja egy plugin forrását | Add meg neki a GitHub-tároló URL-jét a [README.md](README.md) táblázatából, amikor megkérdezi. |
| Egy skill nem jelenik meg | Nézd meg, hogy a `$HOME/.agents/skills/<név>/SKILL.md` fájl létezik-e, és indítsd újra a Codex appot. A régi `~/.codex/skills` mappát a Codex már nem olvassa. |
| Az `npx` nem működik | Használd a beépített `$skill-installer` skillt, vagy másold a skill-mappát kézzel a `$HOME/.agents/skills` alá. |
| Egy plugin hookot kér | Olvasd el, mit futtatna. Ha nem bízol benne, ne engedélyezd, a skillek hook nélkül is működnek. |
