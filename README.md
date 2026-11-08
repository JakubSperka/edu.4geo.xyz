# edu.4geo.xyz

**Doplnkové študijné materiály pre geodéziu a kartografiu.**

Zdrojový projekt vzdelávacieho webu pre predmety Katedry globálnej geodézie a geoinformatiky. Stránka sústreďuje materiály podľa tematických oblastí, ktoré môžu zahŕňať viacero nadväzujúcich predmetov.

Web je vytvorený pomocou [Quarto](https://quarto.org/) a pripravený na publikovanie ako statická stránka na [GitHub Pages](https://docs.github.com/en/pages).

## Tematické oblasti

| Oblasť | Aktuálny obsah |
| --- | --- |
| Programovanie | Odkaz na [py4geodesy.xyz](https://py4geodesy.xyz/) s materiálmi k predmetom Programovanie 1 a 2. |
| Spracovanie a analýza meraní | Samostatná stránka; materiály zatiaľ nie sú dostupné. |
| Kozmická geodézia | Samostatná stránka; materiály zatiaľ nie sú dostupné. |

Na úvodnej stránke sú oblasti dostupné cez karty. Horné menu obsahuje položky **Úvod** a **O projekte**.

## Vzhľad a funkcie

- Responzívne rozloženie pre počítače aj mobilné zariadenia.
- Svetlá a tmavá téma s prepínačom a rešpektovaním systémového nastavenia.
- Vyhľadávanie v lokálnom obsahu webu; externé materiály na py4geodesy.xyz nie sú súčasťou indexu.
- Mapové pozadie so súradnicovou mriežkou a dekoratívnymi vrstevnicami.
- Vlastná ikona glóbusu a oranžové akcenty odvodené z jej farebnosti.

Vrstevnice sú ilustračné a nepredstavujú skutočné výškopisné údaje.

## Lokálne spustenie

Potrebná je nainštalovaná aplikácia [Quarto CLI](https://quarto.org/docs/get-started/). Odporúčaná verzia je **1.7 alebo novšia**, ktorá podporuje nastavenie témy podľa systémových preferencií. Súčasná verzia webu nevyžaduje Python ani R.

Stiahnite alebo naklonujte tento repozitár, otvorte terminál v jeho koreňovom priečinku a spustite:

```sh
quarto preview
```

Quarto zobrazí adresu lokálneho náhľadu a priebežne obnovuje stránku pri úpravách zdrojových súborov. Náhľad ukončíte cez `Ctrl+C`.

## Zostavenie

```sh
quarto render
```

Výsledný web vznikne v priečinku `_site/`. Ide o hotové HTML, štýly, obrázky a ďalšie súbory potrebné na publikovanie.

Priečinky `_site/` a `.quarto/` sú v `.gitignore`; zdrojový repozitár ich štandardne nesleduje.

## Publikovanie na GitHub Pages

Projekt používa manuálne publikovanie zostavených súborov. Automatický workflow GitHub Actions zatiaľ nie je súčasťou repozitára.

1. Spustite `quarto render`.
2. Preneste **celý obsah** priečinka `_site/` do publikačnej vetvy alebo samostatného publikačného repozitára. Zachovajte adresárovú štruktúru a zahrňte aj skrytý súbor `.nojekyll`.
3. V GitHub repozitári otvorte **Settings → Pages** a vyberte **Deploy from a branch**.
4. Zvoľte publikačnú vetvu a priečinok `/(root)` alebo `/docs` podľa umiestnenia výstupu. V tomto priečinku musí byť priamo súbor `index.html`.
5. Uložte nastavenie a po dokončení nasadenia otvorte adresu zobrazenú GitHubom.

GitHub Pages pri publikovaní z vetvy neponúka `_site/` ako zdrojový priečinok; kopíruje sa jeho obsah do zvoleného publikačného umiestnenia. Zdrojové súbory Quarto uchovávajte oddelene od výstupu, napríklad v hlavnej vetve a výstup vo vetve `gh-pages`.

Názov projektu neznamená, že vlastná doména je už pripojená. Doménu `edu.4geo.xyz` treba nastaviť v GitHub Pages a v DNS. Pri ďalších manuálnych aktualizáciách zachovajte prípadný súbor `CNAME` v publikačnej vetve.

Podrobnosti: [nastavenie zdroja publikovania GitHub Pages](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

## Štruktúra projektu

```text
.
├── _quarto.yml                 # Konfigurácia, navigácia a témy
├── index.qmd                   # Úvodná stránka a karty oblastí
├── o-projekte.qmd              # Popis, financovanie a vyhlásenie o AI
├── predmety/
│   ├── spracovanie-a-analyza-merani.qmd
│   └── kozmicka-geodezia.qmd
├── assets/                     # Ikona a dekoratívne SVG vrstevnice
├── styles.css                  # Spoločný dizajn a responzívne pravidlá
├── theme-light.scss            # Nastavenia svetlej témy
├── theme-dark.scss             # Nastavenia tmavej témy
├── TEXTY-NA-UPRAVU.md           # Pracovný podklad na redakciu textov
├── .nojekyll                   # Publikovanie bez spracovania Jekyllom
└── README.md
```

## Úprava a dopĺňanie obsahu

Texty stránok sa upravujú v súboroch `.qmd`, ktoré používajú Markdown. Spoločné nastavenia a navigácia sú v `_quarto.yml`.

Pri dopĺňaní materiálov upravte stránku danej oblasti a jej popis či stav na úvodnej stránke. Novú oblasť pridajte ako `.qmd` súbor do priečinka `predmety/` a doplňte odkaz do prehľadu v `index.qmd`.

Súbor [TEXTY-NA-UPRAVU.md](TEXTY-NA-UPRAVU.md) slúži na pripomienkovanie nadpisov a popisov. **Jeho zmeny sa automaticky neprenášajú na web**; treba ich zapracovať do príslušných zdrojových súborov. Tento súbor ani README sa nevykresľujú ako stránky webu.

Pred publikovaním overte náhľad, odkazy a čitateľnosť v oboch témach a znovu spustite `quarto render`.

## Financovanie

Vývoj stránky je financovaný z projektu **„Projekt na zvýšenie úspešnosti študentov v absolvovaní predmetov Programovanie 1 a Spracovanie a analýza meraní 1, 2 prostredníctvom online vzdelávacej platformy a doučovania“**.

Ďakujeme za podporu tvorby a rozvoja online študijných materiálov.

## Použitie umelej inteligencie

Pri tvorbe projektu boli použité nástroje **OpenAI Codex (2026)** na návrh a úpravu kódu, textov a dekoratívnej grafiky a **OpenAI Imagegen (2026)** na vygenerovanie ikony webu. Aj toto README bolo pripravené s pomocou OpenAI Codex.

Rozsah použitia AI a zodpovednosť autora sú opísané na stránke [O projekte](o-projekte.qmd), s odkazom na opatrenie rektora STU č. 1/2024-O. Vyhlásenie sa nevzťahuje na tvorbu obsahu externej stránky py4geodesy.xyz.

## Licencia

Licencia projektu zatiaľ nebola zvolená. Tento repozitár zatiaľ neudeľuje všeobecné oprávnenie na opätovné použitie svojho obsahu ani zdrojového kódu.

Navrhované rozdelenie na rozhodnutie autora:

- **MIT** pre vlastný zdrojový kód webu a programové ukážky.
- **Creative Commons Attribution 4.0 International (CC BY 4.0)** pre vlastné výučbové texty a ilustrácie, ku ktorým má poskytovateľ licencie potrebné práva.

Toto je návrh, nie udelenie uvedených licencií. Po ich zvolení je potrebné doplniť licenčné súbory, určiť držiteľa práv a jasne označiť rozsah platnosti vrátane kódu vloženého do `.qmd` súborov. Materiály tretích strán a externé odkazy sa riadia vlastnými podmienkami.
