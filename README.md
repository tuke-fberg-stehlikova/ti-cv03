# cv03: Bootstrap

Stránka týždňa s teóriou a ukážkami: https://beata.stehlikova.website.tuke.sk/ti/04.html

## Odovzdávaš

V repository *cv03* na GitHub a vo svojom webovom priestore na sigma (`ti/cv03`):

- `index.html` a `form.html` prerobené na Bootstrap,
- `css/style.css` len s tým, čo Bootstrap nerieši,
- `img/` s obrázkom.

## Hodnotenie

1 bod. Web z *cv02* je prerobený na Bootstrap a úlohy sú splnené. Commit a push najneskôr do nasledujúceho cvičenia. Po každom push sa spustia automatické testy; výsledok nájdeš podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 6.

## Prompt pre AI

```text
Prerob môj web na Bootstrap 5.3 (z CDN jsdelivr). Posielam ti svoje súbory
index.html, form.html a css/style.css. Tému, texty a názvy súborov nemeň.

STRÁNKY
- Do oboch stránok pripoj Bootstrap CSS a až za ním môj css/style.css.
  Pred </body> pripoj bootstrap.bundle.min.js. Nechaj meta viewport.
- Menu prerob na navbar (navbar-expand-md, fixed-top), rovnaký na oboch
  stránkach, s triedou active pri odkaze na aktuálnu stránku.
- Hlavný obsah daj do <main class="container">; v nav a vo footer daj
  <div class="container"> dovnútra. Obsah v main rozdeľ na <section> s id.
- Na index.html použi mriežku (row, col-md-6, col-lg-4) a aspoň tri karty (card).
- Pridaj tabuľku s triedami table a table-striped v obale table-responsive.
- Obrázku daj triedu img-fluid.

FORMULÁR (form.html)
Formulár neskôr spracuje PHP, preto ho oprav presne podľa týchto pravidiel:
- <form method="get" action="">.
- Každé pole má atribút name: malé písmená, bez diakritiky a bez medzier,
  slová spojené podčiarkovníkom (napr. rok_od). Každé name je iné.
  Ak moje pole name už má, nechaj ho.
- Každé pole má id a vlastný <label for="..."> s tým istým id.
- select: prvá možnosť je <option value="">-- vyber --</option>.
  Každá ďalšia možnosť má atribút value s krátkou hodnotou bez diakritiky
  a bez medzier; text medzi značkami je pre človeka.
- radio: všetky v skupine majú rovnaké name, každé má vlastné value a
  vlastné id, jedno má checked. Skupina je vo <fieldset> s <legend>.
- skupina checkboxov, z ktorých sa dá vybrať viac: name končí hranatými
  zátvorkami (napr. zaujem[]), každý má vlastné value a id.
- samostatný checkbox (súhlas): má value="ano".
- Povinné polia majú required. Číselné pole má min a max.
- Tlačidlo je <button type="submit">.
- Triedy Bootstrap: form-label, form-control, form-select, form-check,
  form-check-input, form-check-label, okolo každého poľa <div class="mb-3">,
  na <legend> trieda fs-6.

CSS
V css/style.css nechaj len to, čo Bootstrap nerieši (moje farby, trieda
.zvyraznene, :hover) a pridaj odsadenie body zhora kvôli fixed-top.
Ostatné zmaž a na začiatok súboru napíš v komentári, čo si zmazal a prečo.
Žiadne inline štýly, žiadna značka <style>, žiadny vlastný JavaScript.

KOMENTÁRE
Ku každému bloku HTML napíš krátky slovenský komentár, ktoré triedy
Bootstrap používa a čo robia.

Na konci vypíš tabuľku všetkých polí formulára: name, typ poľa a aké
hodnoty môže poslať.

Tu sú moje súbory:
[VLOŽ obsah index.html, form.html a css/style.css]
```

## Úlohy

**Úloha 4.1: Príprava Kubeflow.** Priprav si Kubeflow podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 1: v Explorer je hore WEB, dole na stavovej lište je **Go Live**. Ak tam nie je, rozšírenia vráti tento príkaz v termináli:

```bash
code-server --install-extension Natizyskunk.sftp --install-extension yandeu.five-server --install-extension bmewburn.vscode-intelephense-client --install-extension mblode.twig-language-2
```

Potom `F1`, **Developer: Reload Window**. Nastavenie pripojenia na sigma zostáva.

**Úloha 4.2: Zadanie a kópia minulého týždňa.** Prijmi zadanie *cv03* v Classroom 50 (link je vyššie) a repository naklonuj do `~/web/ti/cv03` podľa návodu 04, časti 2 a 3. Potom do neho prekopíruj svoj web z minulého týždňa:

```bash
cd ~/web/ti
rsync -a --exclude .git --exclude .github --exclude README.md cv02/ cv03/
ls cv03
```

Vo výpise musí byť `index.html`, `form.html`, `css`, `img` a `README.md`. Pokračuješ vo svojej téme z *cv02*. Priečinok `cv02` zostáva tak, ako si ho odovzdal.

**Úloha 4.3: Bootstrap cez AI.** Prompt z Ukážky 6 vlož do AI a na koniec vlož obsah svojich troch súborov z `cv03`. Výsledok ulož do tých istých súborov v `cv03`. Stránky si pozri cez Five Server (pravý klik do súboru, **Open with Five Server**). **Prečítaj komentáre v kóde: každú triedu musíš vedieť prečítať.** Ak výsledok nie je dobrý, spusti znova príkaz `rsync` z úlohy 4.2 a začni od čistej kópie.

**Úloha 4.4: Mriežka.** Zmeň rozloženie kariet na notebooku z troch v riadku na dve. Pridaj jednu novú kartu.

**Úloha 4.5: Navbar.** Pridaj do menu jednu položku, napríklad odkaz na sekciu s `id` na stránke `index.html`. Over, že trieda `active` je na každej stránke pri správnom odkaze.

**Úloha 4.6: Formulár.** Skontroluj tabuľku polí, ktorú AI vypísala: každé pole má `name`, každá možnosť má `value`. Pridaj jedno nové pole s triedami Bootstrap, s `label`, `name` a `id`. Odošli formulár a v adresnom riadku nájdi hodnoty `value`.

**Úloha 4.7: Odstupy a farby.** Jednej časti stránky zmeň pozadie a odstupy iba triedami Bootstrap. Do `style.css` pri tejto úlohe nezasahuj.

**Úloha 4.8: Vlastné CSS.** V `style.css` nastav menu svoju farbu. V F12 nájdi jedno prečiarknuté pravidlo a zisti, ktoré pravidlo ho prebilo.

**Úloha 4.9: Mobil.** Cez F12 a ikonu mobilu skontroluj obe stránky: menu sa rozbalí, karty idú pod seba, obrázok a tabuľka nepretečú mimo stránku.

**Úloha 4.10: Commit a push.** Commit a push podľa návodu [04 Odovzdávanie](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), časť 5. Urob commit po každej hotovej úlohe, nie jeden na konci. Výsledok automatických testov si pozri podľa časti 6. Pri červenom ✕ si prečítaj názov testu s `FAIL`, oprav to a pushni znova.

**Úloha 4.11: Upload Folder a kontrola na sigma.** Podľa návodu 04, časť 7: klikni pravým na priečinok `cv03` a v menu úplne dole zvoľ **Upload Folder**. Over v prehliadači `https://sigma.tuke.sk/student/meno.priezvisko/ti/cv03/`: obe stránky aj obrázok.

**Hodnotenie:** 1 bod. V repository *cv03* na GitHub aj na sigma je tvoj web z *cv02* prerobený na Bootstrap a úlohy sú splnené. Commit a push najneskôr do nasledujúceho cvičenia.

---

# cv03: Bootstrap

The week page with theory and examples: https://beata.stehlikova.website.tuke.sk/ti/04.html

## What you submit

In the repository *cv03* on GitHub and in your web space on sigma (`ti/cv03`):

- `index.html` and `form.html` rebuilt with Bootstrap,
- `css/style.css` with only what Bootstrap does not handle,
- `img/` with the image.

## Grading

1 point. The website from *cv02* is rebuilt with Bootstrap and the tasks are done. Commit and push by the next lab at the latest. Automatic tests run after every push; find the result following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 6.

## AI prompt

```text
Rebuild my website with Bootstrap 5.3 (from the jsdelivr CDN). I am sending you
my files index.html, form.html and css/style.css. Do not change the topic, the
texts or the file names.

PAGES
- Attach the Bootstrap CSS to both pages and only after it my css/style.css.
  Attach bootstrap.bundle.min.js before </body>. Keep the meta viewport.
- Turn the menu into a navbar (navbar-expand-md, fixed-top), the same on both
  pages, with the active class on the link to the current page.
- Put the main content into <main class="container">; in nav and footer put
  <div class="container"> inside. Divide the content in main into <section>s with ids.
- On index.html use the grid (row, col-md-6, col-lg-4) and at least three
  cards (card).
- Add a table with the classes table and table-striped inside a
  table-responsive wrapper.
- Give the image the class img-fluid.

FORM (form.html)
The form will later be processed by PHP, so fix it exactly by these rules:
- <form method="get" action="">.
- Every field has a name attribute: lowercase, no accents, no spaces, words
  joined by an underscore (e.g. rok_od). Every name is different.
  If my field already has a name, keep it.
- Every field has an id and its own <label for="..."> with the same id.
- select: the first option is <option value="">-- select --</option>.
  Every other option has a value attribute with a short value without accents
  and spaces; the text between the tags is for people.
- radio: all in a group share one name, each has its own value and its own id,
  one has checked. The group is in a <fieldset> with a <legend>.
- a group of checkboxes where several can be ticked: the name ends with square
  brackets (e.g. zaujem[]), each has its own value and id.
- a single checkbox (agreement): has value="ano".
- Required fields have required. A number field has min and max.
- The button is <button type="submit">.
- Bootstrap classes: form-label, form-control, form-select, form-check,
  form-check-input, form-check-label, <div class="mb-3"> around every field,
  and the class fs-6 on <legend>.

CSS
Keep in css/style.css only what Bootstrap does not handle (my colours, the
.zvyraznene class, :hover) and add top padding to body because of fixed-top.
Delete the rest and write a comment at the top of the file saying what you
deleted and why. No inline styles, no <style> tag, no custom JavaScript.

COMMENTS
Add a short comment to every HTML block saying which Bootstrap classes it uses
and what they do.

At the end print a table of all form fields: name, field type and which values
it can send.

Here are my files:
[PASTE the content of index.html, form.html and css/style.css]
```

## Tasks

**Task 4.1: Getting Kubeflow ready.** Get Kubeflow ready following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 1: Explorer shows WEB at the top, the status bar at the bottom shows **Go Live**. If it does not, this terminal command brings the extensions back:

```bash
code-server --install-extension Natizyskunk.sftp --install-extension yandeu.five-server --install-extension bmewburn.vscode-intelephense-client --install-extension mblode.twig-language-2
```

Then `F1`, **Developer: Reload Window**. The sigma connection settings stay.

**Task 4.2: The assignment and a copy of last week.** Accept the assignment *cv03* in Classroom 50 (the link is above) and clone the repository into `~/web/ti/cv03` following guide 04, parts 2 and 3. Then copy your website from last week into it:

```bash
cd ~/web/ti
rsync -a --exclude .git --exclude .github --exclude README.md cv02/ cv03/
ls cv03
```

The listing must contain `index.html`, `form.html`, `css`, `img` and `README.md`. You continue with your own topic from *cv02*. The `cv02` folder stays as you submitted it.

**Task 4.3: Bootstrap with AI.** Paste the prompt from Example 6 into an AI and paste the content of your three files from `cv03` at the end. Save the result into the same files in `cv03`. View the pages with Five Server (right click in the file, **Open with Five Server**). **Read the comments in the code: you must be able to read every class.** If the result is not good, run the `rsync` command from task 4.2 again and start from a clean copy.

**Task 4.4: The grid.** Change the card layout on a laptop from three per row to two. Add one new card.

**Task 4.5: Navbar.** Add one item to the menu, for example a link to a section with an `id` on the `index.html` page. Check that the `active` class is on the right link on each page.

**Task 4.6: The form.** Check the table of fields the AI printed: every field has a `name`, every option has a `value`. Add one new field with Bootstrap classes, a `label`, a `name` and an `id`. Submit the form and find the `value` values in the address bar.

**Task 4.7: Spacing and colours.** Change the background and the spacing of one part of the page with Bootstrap classes only. Do not touch `style.css` in this task.

**Task 4.8: Your own CSS.** Set your own colour for the menu in `style.css`. In F12 find one crossed-out rule and find out which rule overrode it.

**Task 4.9: Phone.** With F12 and the phone icon check both pages: the menu unfolds, the cards go below each other, the image and the table do not overflow the page.

**Task 4.10: Commit and push.** Commit and push following guide [04 Submitting](https://beata.stehlikova.website.tuke.sk/navody/04-odovzdavanie.html), part 5. Make a commit after every finished task, not one at the end. Look at the result of the automatic tests following part 6. With a red ✕ read the name of the test marked `FAIL`, fix it and push again.

**Task 4.11: Upload Folder and the check on sigma.** Following guide 04, part 7: right-click the `cv03` folder and choose **Upload Folder** at the very bottom of the menu. Check in the browser `https://sigma.tuke.sk/student/name.surname/ti/cv03/`: both pages and the image.

**Grading:** 1 point. The repository *cv03* on GitHub and on sigma contains your website from *cv02* rebuilt with Bootstrap, and the tasks are done. Commit and push by the next lab at the latest.
