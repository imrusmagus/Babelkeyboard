# Babelkeyboard
A macOS menu bar app that draws your keyboard exactly as it lights up in the dark — and reveals every hidden Shift/Option/Shift+Option symbol on it.


A macOS menu bar app that draws your keyboard exactly as it lights up in the dark — and shows you every hidden **Shift**, **Option**, and **Shift+Option** symbol on it, so you never have to Google "how do I type €" again.

## Why

Every Mac keyboard secretly hides dozens of symbols behind modifier keys — currency signs, typographic quotes, math symbols, accented letters. Babel Keyboard puts them all in front of you, on a realistic, backlit-style drawing of your actual keyboard.

## Features

- **Realistic dark keyboard** — drawn key by key, matching your real MacBook's layout (ANSI or ISO, including the correct L-shaped Enter key).
- **Shift / Option / Shift+Option toggles** — show only what you need.
- **Live mode** — hold Shift or Option on your physical keyboard and watch the matching symbols light up in real time (requires granting Input Monitoring access for it to work outside this app's own window).
- **Search** — type a symbol's name ("star", "at sign") and jump straight to it.
- **Favorites** — pin the symbols you use often.
- **Click to copy** — click any symbol to copy it and add it to your recents.
- **7 built-in layouts** — Hungarian, US, British/GB, Norwegian, French, Italian, Romanian.
- **Record your own layout** — don't see your layout in the list? Switch your Mac to it in System Settings, then use the built-in recorder: press through 4 phases (base, Shift, Option, Shift+Option) and Babel Keyboard builds the layout for you, saved permanently on your Mac.
- **English & Hungarian UI** — switch anytime from the menu bar.

## Requirements

- macOS 26 (Tahoe) or later — the frosted "Liquid Glass" panels use an API only available from macOS 26 onward.
- No Xcode required to build — just the free Command Line Tools.

## Building from source

Babel Keyboard is a plain Swift Package (no `.xcodeproj`).

```bash
git clone <this-repo-url>
cd BabelKeyboard
swift build
swift run
```

### Packaging as a double-clickable app

```bash
./make_app.sh
```

This builds a release binary, generates `AppIcon.icns` from `AppIcon.png`, and produces `Babel Keyboard.app`.

### Building a drag-to-install DMG

```bash
./make_dmg.sh
```

(Run `make_app.sh` first — the DMG just wraps the existing `.app`.)

> The app isn't notarized with an Apple Developer ID, so on first launch, right-click the app → **Open** → **Open** again to get past Gatekeeper.

## Adding a layout manually

If you'd rather hand-edit layout data instead of using the in-app recorder, layouts live in `Sources/BabelKeyboard/Data/EmbeddedLayouts.swift`. Each key has a `base`, `topLeft` (Shift), `bottomLeft` (Option), and `bottomRight` (Shift+Option) value plus a human-readable combo string.

## Support

If Babel Keyboard saved you a Google search or two, you can [buy the developer a coffee ☕](https://buymeacoffee.com/nanasiimreu).

## Credits

Developed by **imrusmágus**.

## License

All rights reserved — see [LICENSE](LICENSE). This repository is public for demonstration purposes only; it is **not** open source, and reuse without permission isn't allowed.






# ⌨️ Babel Keyboard

*[English description → README.md](README.md)*

Egy macOS menüsáv-alkalmazás, ami pontosan úgy rajzolja ki a billentyűzetedet, ahogy sötétben világít — és megmutatja rajta az összes elrejtett **Shift**, **Option** és **Shift+Option** jelet, hogy soha többé ne kelljen Google-özni, hogy "hogyan írok €-t".

## Miért

Minden Mac billentyűzet több tucat jelet rejt a módosító billentyűk mögé — pénznem-jeleket, tipográfiai idézőjeleket, matematikai szimbólumokat, ékezetes betűket. A Babel Keyboard mindezt eléd teszi, a valódi billentyűződ realisztikus, háttérvilágításos rajzán.

## Funkciók

- **Realisztikus, sötét billentyűzet** — gombonként megrajzolva, a valódi MacBook-kiosztásodhoz igazítva (ANSI vagy ISO, a helyes L-alakú Enter gombbal).
- **Shift / Option / Shift+Option kapcsolók** — csak azt mutatja, amire szükséged van.
- **Live mód** — tartsd lenyomva a Shiftet vagy az Optiont a valódi billentyűzeteden, és a megfelelő jelek élőben felvillannak (az app ablakán kívüli működéshez Bemenet-figyelés engedély kell).
- **Keresés** — írd be egy jel nevét ("csillag", "kukac"), és az app egyből odaugrik.
- **Kedvencek** — tűzd ki a gyakran használt jeleidet.
- **Kattintás = másolás** — bármelyik jelre kattintva vágólapra kerül, és bekerül a "legutóbbi" közé.
- **7 beépített kiosztás** — Magyar, US, British/GB, Norvég, Francia, Olasz, Román.
- **Saját kiosztás felvétele** — nincs a listában a tiéd? Válts át rá a Rendszerbeállításokban, majd használd a beépített felvevőt: 4 fázison (alap, Shift, Option, Shift+Option) végigmenve az app felépíti neked a kiosztást, és tartósan elmenti a gépeden.
- **Angol és magyar felület** — bármikor váltható a menüsávból.

## Rendszerkövetelmény

- macOS 26 (Tahoe) vagy újabb — az "üveges" (Liquid Glass) paneleket egy csak macOS 26-tól elérhető API adja.
- Nem kell hozzá Xcode a fordításhoz — elég az ingyenes Command Line Tools.

## Fordítás forrásból

A Babel Keyboard egy sima Swift Package (nincs `.xcodeproj`).

```bash
git clone <ennek-a-repónak-az-url-je>
cd BabelKeyboard
swift build
swift run
```

### Dupla-kattintható app csomagolása

```bash
./make_app.sh
```

Ez lefordítja a release buildet, legenerálja az `AppIcon.icns`-t az `AppIcon.png`-ből, és elkészíti a "Babel Keyboard.app"-ot.

### Húzd-és-dobd DMG telepítő készítése

```bash
./make_dmg.sh
```

(Előtte fusson le a `make_app.sh` — a DMG csak becsomagolja a már meglévő `.app`-ot.)

> Az app nincs hivatalos Apple fejlesztői aláírással ellátva, így első indításkor jobb klikk az app-ra → **Megnyitás** → még egyszer **Megnyitás**, hogy a Gatekeeper átengedje.

## Kiosztás kézzel hozzáadása

Ha az appon belüli felvevő helyett inkább kézzel szerkesztenéd az adatokat, a kiosztások a `Sources/BabelKeyboard/Data/EmbeddedLayouts.swift` fájlban élnek. Minden gombnak van egy `base`, `topLeft` (Shift), `bottomLeft` (Option) és `bottomRight` (Shift+Option) értéke, plusz egy ember által olvasható kombó-szöveg.

## Támogatás

Ha a Babel Keyboard megspórolt neked egy-két Google-keresést, [meghívhatod a fejlesztőt egy kávéra ☕](https://buymeacoffee.com/nanasiimreu).

## Készítette

**imrusmágus**

## Licenc

Minden jog fenntartva — lásd: [LICENSE](LICENSE). Ez a tár csak bemutatási célból nyilvános; **nem** nyílt forráskódú, engedély nélküli felhasználása nem megengedett.
