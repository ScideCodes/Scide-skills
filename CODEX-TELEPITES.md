# Telepítés a Codex asztali appba (kész szöveggel)

A Codex az OpenAI kódoló asszisztense. A lenti szöveget be kell másolnod a Codex appba, és a Codex magától beállítja a skilleket.

## 1. A Codex app telepítése (ha még nincs)

1. Töltsd le a Codex appot macOS-re vagy Windowsra innen: https://developers.openai.com/codex/app. Intel-alapú Macen az Intel verziót válaszd.
2. Telepítsd, nyisd meg, és jelentkezz be a ChatGPT-fiókoddal (vagy egy OpenAI API-kulccsal).

Terminálra és Node.js-re nincs szükség.

## 2. Másold be ezt a szöveget a Codexbe

Nyiss egy új szálat (thread) az appban, és illeszd be ezt:

```
Állítsd be nekem a skilleket ebből a tárolóból: https://github.com/ScideCodes/Scide-skills

Lépések:
1. Olvasd el a README.md és a SKILLEK.md fájlt. A telepítendő pluginok forrásai (GitHub, tulajdonos/tároló): anthropics/knowledge-work-plugins (design, cowork-plugin-management mappa), JuliusBrussee/caveman, DietrichGebert/ponytail, mattpocock/skills, addyosmani/agent-skills, affaan-m/ECC, cathrynlavery/diagram-design, blader/humanizer, nextlevelbuilder/ui-ux-pro-max-skill. A claude-mem pluginokat és az obsidian-notes-t hagyd ki, hacsak nem kérem.
2. A Codex a skilleket innen tölti be: ~/.codex/skills/<név>/SKILL.md. A mappa neve a skill neve. Ha a ~/.codex/skills mappa nem létezik, hozd létre.
3. Minden pluginhoz használd a fenti forrást. Ha nem találod, kérdezd meg tőlem az URL-t. Csak a skill-mappákat másold a ~/.codex/skills/ mappába. Hagyd ki a hookokat, a statusline-szkripteket és minden olyat, ami beállításfájlt módosít.
4. A "Csatlakozók" listát hagyd ki, az Claude-fiókhoz kötött. Ha kell hozzá MCP-szerver, kérdezd meg tőlem, és mondd meg, hol adhatom hozzá a Codex app beállításaiban. Kulcsot vagy jelszót soha ne írj fájlba.
5. Ne olvasd és ne másold a ~/.claude/.credentials.json és a ~/.claude.json fájlt.
6. A végén írd ki, mit telepítettél és mit hagytál ki, majd mondd meg, hogy indítsam újra a Codex appot.
```

## 3. Ellenőrzés

Zárd be és nyisd meg újra a Codex appot, nyiss új szálat, és kérdezd meg: „Milyen skillek vannak telepítve?" A listában ott kell lennie a telepített skilleknek.

## Hibaelhárítás

| Probléma | Megoldás |
|---|---|
| Nem találom a Codex appot | Töltsd le innen: https://developers.openai.com/codex/app. Macen és Windowson is elérhető. |
| A Codex nem találja a plugin forrását | Add meg neki az URL-t, amikor megkérdezi. |
| Egy skill nem jelenik meg | Nézd meg, hogy a `~/.codex/skills/<név>/SKILL.md` fájl létezik-e, és indítsd újra a Codex appot. |
