# Skillek pluginonként

Egy **plugin** több **skillet** tartalmaz. A telepítést a [CLAUDE-TELEPITES.md](CLAUDE-TELEPITES.md) írja le. Itt az van, hogy melyik plugin milyen skilleket ad.

## Anthropic pluginok

**claude-code-setup**: elemzi a projektet, és ajánl hozzá automatizálást (hookok, skillek, MCP-szerverek, subagentek).
`claude-automation-recommender`

**design**: dizájn-kritika, rendszer, UX-szöveg, akadálymentesség, kutatás, átadás a fejlesztőknek.
`accessibility-review`, `design-critique`, `design-handoff`, `design-system`, `research-synthesis`, `user-research`, `ux-copy`

**cowork-plugin-management**: pluginok készítése és testreszabása.
`cowork-plugin-customizer`, `create-cowork-plugin`

**obsidian-notes**: jegyzetmappa rendezése és ellenőrzése Obsidianhoz (hibás linkek, árva jegyzetek, hiányzó indexek). Az Anthropic könyvtárából jön, ezért nincs benne az egyszerre telepítő szövegben. Telepítsd az app bővítménybrowserében.
`obsidian-notes`

## Beépített skillek (nem kell telepíteni)

A Claude-előfizetéssel járnak: `docx` (Word), `xlsx` (Excel), `pptx` (PowerPoint), `pdf`, `docs`, `deep-research`, `skill-creator`, `google-workspace`, `import-memory`, `morning`, `setup-writing-style`.

## Közösségi pluginok

**caveman** (Julius Brussee): rövid, lényegre törő válaszok, kevesebb költség.
`caveman`, `ultracave`, `megacave`, `cavecrew`, `caveman-commit`, `caveman-compress`, `caveman-discover`, `caveman-evidence-review`, `caveman-explore`, `caveman-help`, `caveman-init`, `caveman-learn`, `caveman-manage`, `caveman-optimize`, `caveman-review`, `caveman-setup`, `caveman-stats`, `investigate-first`, `lean-build`, `migration`, `safe-refactor`, `surgical-patch`, `verify-and-stop`

**ponytail** (Dietrich Gebert): a lehető legkisebb, legegyszerűbb megoldás.
`ponytail`, `ponytail-audit`, `ponytail-debt`, `ponytail-gain`, `ponytail-help`, `ponytail-review`

**mattpocock-skills** (Matt Pocock): tervezés, spec, jegyek, TDD, kódáttekintés.
`ask-matt`, `code-review`, `codebase-design`, `diagnosing-bugs`, `domain-modeling`, `grill-me`, `grill-with-docs`, `grilling`, `handoff`, `implement`, `implement-spec`, `improve-codebase-architecture`, `pr`, `prototype`, `research`, `retro`, `setup-matt-pocock-skills`, `tdd`, `teach`, `to-questionnaire`, `to-spec`, `to-tickets`, `triage`, `wait-what`, `wayfinder`, `wizard`, `writing-for-agents`

**agent-skills** (Addy Osmani): a teljes fejlesztési folyamat a specifikációtól a kiadásig.
`api-and-interface-design`, `browser-testing-with-devtools`, `build`, `ci-cd-and-automation`, `code-review-and-quality`, `code-simplification`, `code-simplify`, `constraint-driven-development`, `constraints`, `context-engineering`, `debugging-and-error-recovery`, `deprecation-and-migration`, `documentation-and-adrs`, `doubt-driven-development`, `frontend-ui-engineering`, `git-workflow-and-versioning`, `idea-refine`, `incremental-implementation`, `interview-me`, `observability-and-instrumentation`, `performance-optimization`, `plan`, `planning-and-task-breakdown`, `review`, `security-and-hardening`, `ship`, `shipping-and-launch`, `source-driven-development`, `spec`, `spec-driven-development`, `test`, `test-driven-development`, `using-agent-skills`, `webperf`

**ecc** (Affaan Mustafa): nagy csomag, kb. 311 skill, ügynökök, parancsok és hookok. Itt nem sorolom fel mindet. A teljes lista a tárolóban van (https://github.com/affaan-m/ECC), telepítés után pedig az `ecc-guide` skill is megmondja, mi van benne.

**diagram-design** (Cathryn Lavery): sokféle diagram HTML-, SVG- és PNG-formátumban.
`diagram-design`, `doctor`, `export-diagram`, `import-drawio`, `import-excalidraw`, `import-mermaid`, `profile`

**humanizer** (blader): az MI-szerű szöveget úgy írja át, hogy a te hangodon szóljon.
`humanizer`

**ui-ux-pro-max** (nextlevelbuilder): UI/UX tervezés, stílusok, színpaletták, betűpárok.
`banner-design`, `brand`, `design`, `design-system`, `slides`, `ui-styling`, `ui-ux-pro-max`

## Memória pluginok (csak ha kéred, az egyszerre telepítés nem teszi fel)

**claude-mem** és **claude-mem-cowork** (Alex Newman, CMEM): munkamenetek közti emlékezet. Hookokkal rögzítik, mit csinál a Claude, és a `claude-mem-cowork` a leírása szerint a cmem.ai szolgáltatásnak is küld adatot. Telepítés előtt olvasd el, mit gyűjtenek.

- `claude-mem`: `agent-cost-report`, `babysit`, `backup-setup`, `build`, `build-and-release`, `ccs-align`, `childhood`, `cloud-sync`, `design-is`, `do`, `handoff`, `how-it-works`, `knowledge-agent`, `learn-codebase`, `make-plan`, `mem-search`, `mode-creator`, `oh-my-issues`, `owner-goals`, `pathfinder`, `release`, `request-progress`, `screenpipe`, `smart-explore`, `standup`, `timeline-report`, `version-bump`, `weekly-digests`, `what-the`, `wowerpoint`
- `claude-mem-cowork`: `agent-cost-report`, `mem-search`, `mem-setup`
