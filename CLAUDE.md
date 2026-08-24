## Co je tenhle projekt

Jednostránkový web pro britského auto detailera. Vzniká jako
mockup, který se posílá majiteli firmy dřív, než si ho objedná.

## Architektura — čti dřív, než něco změníš

- **Není tu build.** Žádný npm, žádný webpack, žádný package.json.
- `.jsx` soubory se načítají přímo v `index.html` přes
  `<script type="text/babel">` a překládají se v prohlížeči.
- React a ReactDOM se stahují z unpkg CDN.
- `_ds_bundle.js` je knihovna komponent (Button, Card, Input).
  Do ní nesahej.
- Sekce se skládají v `App()` uvnitř `index.html`.

## Co se nikdy nesmí

- **Nepřejmenovávej `window.ReviveRefineDesignSystem_38ca5a`.**
  Stránka by zbělala.
- Nezaváděj build krok, npm ani bundler.
- Neměň názvy souborů v `assets/images/`. Jsou napevno v kódu:
  `logo.png`, `hero.jpg`, `services-feature.jpg`, `benefits.jpg`,
  `gallery-full-valet.jpg`, `gallery-0.jpg`, `gallery-ceramic.jpg`,
  `gallery-interior.jpg`
- Neměň `<title>` na obecný text. Musí obsahovat název firmy
  a město, protože se zobrazuje v náhledu odkazu na Instagramu.

## Barvy

Jsou to CSS proměnné v `:root` v `styles.css`. Rodina proměnných
se jmenuje `mongoose` a je to akcentní barva.

**Barvy pro nového klienta se přidávají jako blok na konec
souboru.** Co je v CSS níž, přebije to nad sebou. Nepřepisuj
původní hodnoty.

Sekce mají třídy `scheme-1` (tmavá) a `scheme-3` (světlá).

## Animace

- Skrytý stav nasazuje JavaScript v `useLayoutEffect`, **nikdy
  CSS**. Kdyby se skript nenačetl, stránka musí být vidět.
- Komponenty, které se animují, musí být definované **mimo**
  rodičovskou funkci. Jinak je React při každém překreslení
  vytvoří znovu a animace se přehraje podruhé.
- Hover řeš v CSS, ne přes React state. Překreslení spouští
  animaci znovu.
- Vždy respektuj `prefers-reduced-motion`.
- Tlačítka v heru nesmí mít zpoždění větší než 200 ms.

## Obsah — pravidla, která nesmíš porušit

- **Nikdy nevymýšlej recenze, jména zákazníků, počty klientů,
  roky na trhu ani certifikace.** Když data nemám, napiš
  `[PLACEHOLDER]` a upozorni mě.
- **Nikdy nevymýšlej ceny.** Když je neznám, řekni mi to.
- Nabízej jen služby, které ten klient opravdu dělá. Když
  šablona obsahuje něco jiného, vymaž to.
- Britská angličtina, hovorově. Zakázané: unlock, elevate,
  transform your vehicle, take it to the next level.
- **Nikdy nepoužívej em dash (—) ani en dash (–).** Čárka,
  tečka, dvojtečka.
- Klientovy vlastní slogany přebírej za obsah, ale oprav
  pravopis.

## Rezervace

Sekce `Newsletter` v `Sections.jsx` je poslední na stránce
a obsahuje inline embed z Cal.com. Slug a username jsou
v konstantách nahoře v souboru.

## Jak chci, abys pracoval

- Než něco změníš, řekni mi, co chceš udělat, a počkej na ano.
- Neupravuj víc souborů, než je potřeba.
- Žádné hromadné nahrazování v celém souboru.
- Když si nejsi jistý, na co se koukám nebo co klient dělá,
  zeptej se místo hádání.
- Po změně mi řekni, co přesně jsi udělal, ne co jsi chtěl.
