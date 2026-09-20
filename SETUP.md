# Fejlesztői környezet

Ezt egyszer kell végigcsinálni, utána minden lecke működik. Ha valami elakad, ne szenvedj
vele sokat egyedül, szólj.

## 1. Kódszerkesztő: VS Code

Töltsd le és telepítsd a [VS Code](https://code.visualstudio.com/)-ot.

Utána telepítsd ezeket a bővítményeket. A VS Code bal oldalán a négyzetes ikonra kattintva
(`Extensions`) keresd rá a nevekre:

| Bővítmény                                                                                                      | Mire jó                                                                | Melyik leckétől |
| -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- | --------------- |
| **[Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)**                   | Egy kattintással kiszolgálja az oldaladat, és frissíti magát mentéskor | 01              |
| **[Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)**                     | Automatikusan rendes formára igazítja a kódot                          | 01              |
| **[Tailwind CSS IntelliSense](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss)** | Kiegészíti a Tailwind osztályneveket, és megmutatja mit csinálnak      | 01              |
| **[Pretty TypeScript Errors](https://marketplace.visualstudio.com/items?itemName=yoavbls.pretty-ts-errors)**   | Olvasható formára hozza a TypeScript hibaüzeneteket                    | 02              |

A 4. leckében az API-nkat nem külön bővítménnyel, hanem **[Bunnal](https://bun.sh/) írt kis szkriptekkel**  
fogjuk piszkálni, így ugyanazt a nyelvet használod a teszteléshez is, amiben a szervert  
írtad.

Amikor először megnyitod a projektet VS Code-ban, fel fogja ajánlani ezeknek a
bővítményeknek a telepítését. Fogadd el.

A beállítások már benne vannak a repóban, a `.vscode/` mappában és a `.prettierrc` fájlban:
mentéskor magától rendbe teszi a kódodat, és a Tailwind osztálynevek kiegészítése is
működik. Nem kell semmit beállítanod.

> Ha mégsem formáz mentéskor: nyisd meg a `View` > `Output` panelt, és a jobb felső
> legördülőből válaszd a `Prettier`-t. Ott leírja, miért hagyta ki a fájlt. A leggyakoribb
> ok az, hogy a saját beállításaid közt szerepel a `prettier.requireConfig: true`, ami miatt
> a Prettier csak olyan projektben dolgozik, ahol van konfigurációs fájl. Ebben a repóban
> van, szóval itt ez nem okozhat gondot.

## 2. Git és GitHub

Szükséged lesz egy [GitHub](https://github.com/) fiókra és a [git](https://git-scm.com/) parancsra.

- GitHub fiók: [https://github.com/signup](https://github.com/signup)
- Git telepítés: [https://git-scm.com/downloads](https://git-scm.com/downloads)

Ellenőrizd egy terminálban:

```bash
git --version
```

Ha kiír egy verziószámot, megvagy.

### A repó forkolása és klónozása

1. Nyisd meg a kurzus repóját GitHubon, és kattints jobb felül a **Fork** gombra. Így
   készül egy saját másolatod, amibe szabadon írhatsz.
2. A forkod oldalán kattints a zöld **Code** gombra, és másold ki a HTTPS linket.
3. Terminálban, abban a mappában, ahol a projektjeidet tartod:

```bash
git clone <ide-a-kimásolt-link>
cd web-tanulas
code .
```

Az utolsó parancs megnyitja a projektet VS Code-ban.

## 3. Bun

A [Bun](https://bun.sh/) futtatja majd a [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) és [TypeScript](https://www.typescriptlang.org/) kódunkat a böngészőn kívül, és ez kezeli a
külső könyvtárakat is. **Az 1. leckéhez még nem kell**, ott elég a böngésző, de
telepítsd most, hogy a 2. leckén ne ezzel menjen az idő.

**Windows** (PowerShell):

```powershell
powershell -c "irm bun.sh/install.ps1 | iex"
```

**macOS / Linux**:

```bash
curl -fsSL https://bun.sh/install | bash
```

Telepítés után **nyiss egy új terminált** (a régi még nem ismeri a parancsot), és
ellenőrizd:

```bash
bun --version
```

Ha itt `command not found` vagy `nem ismeri fel parancsként` jön, akkor a telepítő nem
tudta beállítani az elérési utat. Indítsd újra a gépet, és próbáld megint.

## 4. Böngésző

[Chrome](https://www.google.com/chrome/) vagy [Firefox](https://www.mozilla.org/firefox/). Szükségünk lesz a **fejlesztői eszközökre**, ezt most próbáld ki:

- Nyiss meg egy tetszőleges weboldalt.
- Jobb klikk bárhol → `Vizsgálat` / `Inspect`, vagy nyomj `F12`-t.
- Alul vagy oldalt megjelenik egy panel több füllel: `Elements`, `Console`, `Network`.

Ezt a panelt a kurzus alatt tarts végig nyitva.

## Kész?

Menj a [01-es leckére](leckek/01-html-css-tailwind/).
