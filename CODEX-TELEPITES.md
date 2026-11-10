# Codex bővítmények telepítése – lépésről lépésre

Ez az útmutató megmutatja, hogyan telepíthetsz skilleket és bővítményeket az OpenAI Codex asztali alkalmazásába. A parancsokat bemásolhatod a Codexbe; nem kell külön terminált megnyitnod.

> **Biztonság:** telepítés közben a Codex engedélyt kérhet parancsok futtatására. Olvasd el, mit tenne, és csak azt hagyd jóvá, amit értesz. Jelszót, belépési adatot vagy API-kulcsot ne másolj be.

## 1. Telepítsd és nyisd meg a Codexet

1. Töltsd le a Codex asztali alkalmazást a [hivatalos oldalról](https://developers.openai.com/codex/app). macOS-re és Windowsra érhető el.
2. Telepítsd, nyisd meg, és jelentkezz be a fiókoddal.
3. A plugin-parancsok használatához **Codex 0.122-es vagy újabb verzió** szükséges. Ha a Codex azt jelzi, hogy nem ismeri a `codex plugin` parancsot, frissítsd az alkalmazást.

## 2. Másold be a telepítési kérést

1. Nyiss egy új beszélgetést (a Codexben ez lehet „thread” vagy „szál”).
2. Másold be az alábbi teljes kérést.
3. Ha a Codex engedélyt kér egy parancs futtatására, olvasd el a kérést, és csak akkor hagyd jóvá, ha érted.
4. A végén kérd meg, hogy mondja el, mi sikerült, és mi maradt ki.

```
Telepítsd nekem az alábbi bővítményeket és skilleket a Codexbe. Ha egy lépés hibázik, ne állj meg: hagyd ki azt a lépést, folytasd a következővel, és a végén mondd el, mi történt.

A) Codex-bővítmények. Mindegyiknél add hozzá a piacteret, majd telepítsd a bővítményt:
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

B) Csak skillként telepíthető elemek:
- npx skills add JuliusBrussee/caveman -g -a codex
- npx skills add blader/humanizer -g -a codex
Ha az npx parancs nem működik, ne próbálj találomra más parancsokat futtatni. Jelezd a hibát, és mondd el, hogy a beépített $skill-installer vagy a kézi telepítés lehet a következő lépés.

C) ui-ux-pro-max:
- Ezt csak akkor telepítsd, ha megmondom, melyik projekthez kérem.
- A telepítési parancs: npm install -g ui-ux-pro-max-cli, majd a kiválasztott projekt mappájában: uipro init --ai codex.
- Ez projektmappába telepít. Mielőtt bármit futtatnál, kérdezd meg, melyik projektet használjam.

D) A claude-mem telepítését hagyd ki. Külön telepítője van, további eszközöket telepíthet, és munkamenetadatokat rögzíthet. Majd külön kérem, ha szükségem lesz rá.

Biztonsági szabályok:
- Ha egy bővítmény hook vagy automatikus parancs engedélyezését kéri, ne engedélyezd helyettem. Mondd el, mit kér, és várd meg a döntésemet.
- Az ecc-t és az agent-skills elemet ne telepítsd másik módszerrel is ugyanarra a gépre, mert a skillek többször jelenhetnek meg.
- A Claude-hoz tartozó bővítményeket (design, obsidian-notes, plugin-management, claude-code-setup és claude-mem-cowork) hagyd ki. A csatlakozókat se állítsd be; azokat külön, a saját fiókjaimmal intézem.
- Ne olvasd és ne másold a ~/.claude/.credentials.json vagy ~/.claude.json fájlt.
- A végén sorold fel, mit telepítettél, mit hagytál ki és miért. Ezután emlékeztess, hogy indítsam újra a Codexet, és nyissak új beszélgetést.
```

A `ui-ux-pro-max` opcionális, és csak egy kiválasztott projektbe települ. Ha nem tudod, melyik mappát válaszd, hagyd ki.

## 3. Indítsd újra és ellenőrizd

1. Zárd be, majd nyisd meg újra a Codexet.
2. Nyiss új beszélgetést.
3. Kérdezd meg: „Milyen skillek érhetők el?”
4. A felhasználói skillek mappája általában `$HOME/.agents/skills`. A projekthez telepített skilleket az adott projekt `.agents/skills` mappájában találod.

A teljes skill-lista a [SKILLEK.md](SKILLEK.md) fájlban van.

## Mire figyelj?

- A bővítmények külső fejlesztők kódját futtathatják. Telepítés előtt nézd meg a forrást; a hivatkozásokat a [README-ben](README.md) találod.
- Az `ecc` nagy csomag, sok skillt és parancsot tartalmaz. Ha nincs rá szükséged, ne telepítsd.
- Ugyanazt a skillt ne telepítsd több módszerrel, mert többször jelenhet meg.
- A telepítés vagy beállítás során megjelenő engedélykéréseket mindig olvasd el.

## Hibaelhárítás

| Mi történt? | Mit próbálj meg? |
|---|---|
| Nem találom a Codex appot. | Töltsd le a [hivatalos oldalról](https://developers.openai.com/codex/app); macOS-re és Windowsra érhető el. |
| A `codex plugin` parancs ismeretlen. | Frissítsd az appot legalább a 0.122-es verzióra, majd próbáld újra. |
| A Codex nem találja a bővítmény forrását. | Ellenőrizd a forrás nevét a [README-ben](README.md), és csak megbízható forrást adj hozzá. |
| Egy skill nem jelenik meg. | Indítsd újra a Codexet. Ellenőrizd, hogy a skill a `$HOME/.agents/skills` vagy az adott projekt `.agents/skills` mappájába került-e. |
| Az `npx` parancs hibázik. | Állj meg, és olvasd el a hibaüzenetet. Kérj segítséget a beépített `$skill-installer` használatához vagy a kézi telepítéshez; ne futtass ismeretlen parancsot. |
| Egy bővítmény automatikus műveletet (hookot) kér. | Ne engedélyezd automatikusan. Olvasd el, mit futtatna, és csak akkor dönts, ha érted. |
| A bővítmény nem jelenik meg telepítés után. | Indíts új beszélgetést, vagy zárd be és nyisd meg újra a Codexet. |
