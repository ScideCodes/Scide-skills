# Telepítés Codexhez (kész szöveggel)

A Codex az OpenAI kódoló asszisztense. A lenti szöveget be kell másolnod a Codexbe, és a Codex magától beállítja a skilleket.

## 1. Codex telepítése (ha még nincs)

Szükséged lesz a [Node.js](https://nodejs.org) telepítésére, aztán a terminálban:
```
npm install -g @openai/codex
codex
```
Első indításkor jelentkezz be az OpenAI-fiókoddal.

## 2. Másold be ezt a szöveget a Codexbe

```
Állítsd be nekem a skilleket ebből a tárolóból: https://github.com/ScideCodes/Scide-skills

Lépések:
1. Olvasd el a README.md fájlt. Ott van a lista a pluginokról és skillekről: caveman, ponytail, design, obsidian-notes, valamint a beépített dokumentum-skillek.
2. A Codex a skilleket innen tölti be: ~/.codex/skills/<név>/SKILL.md. A mappa neve a skill neve. Ha a ~/.codex/skills mappa nem létezik, hozd létre.
3. Minden pluginhoz keresd meg a nyilvános forrástárolót. Ha nem találod, kérdezd meg tőlem az URL-t. Csak a skill-mappákat másold a ~/.codex/skills/ mappába. Hagyd ki a hookokat, a statusline-szkripteket és minden olyat, ami beállításfájlt módosít.
4. A "Csatlakozók" listát hagyd ki, az Claude-fiókhoz kötött. Ha kell hozzá MCP-szerver, a `codex mcp add` paranccsal add hozzá, és kérj tőlem hitelesítő adatot. Kulcsot soha ne írj fájlba.
5. Ne olvasd és ne másold a ~/.claude/.credentials.json és a ~/.claude.json fájlt.
6. A végén írd ki, mit telepítettél és mit hagytál ki, majd mondd meg, hogy indítsam újra a Codexet.
```

## 3. Ellenőrzés

Indítsd újra a Codexet, és kérdezd meg: „Milyen skillek vannak telepítve?" A listában ott kell lennie a telepített skilleknek.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| `npm: command not found` | Telepítsd a Node.js-t: https://nodejs.org |
| A Codex nem találja a plugin forrását | Add meg neki az URL-t, amikor megkérdezi. |
| Egy skill nem jelenik meg | Nézd meg, hogy a `~/.codex/skills/<név>/SKILL.md` fájl létezik-e, és indítsd újra a Codexet. |
