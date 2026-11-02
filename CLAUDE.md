# Reguli de lucru — Symy Poetry

Proiect simplu: Manuel aduce poezii ale unui prieten (autorul), Claude le rafinează, autorul
aprobă printr-un Pull Request. **Tot ce scrii este în limba română**: mesaje de commit,
titlul și descrierea PR-ului, răspunsurile către Manuel. Nu construi automatizări, workflow-uri
GitHub sau scripturi; procesul este manual și rămâne așa.

## Principii

- **Vocea autorului primează.** Nu rescrie în stilul tău. Păstrează rima, ritmul, regionalismele
  și licențele poetice, chiar dacă par greșeli. Dacă nu ești sigur că ceva e greșeală, nu
  schimba; întreabă autorul în PR.
- **Nimic nu se schimbă fără aprobarea autorului.** Totul trece prin PR; autorul poate refuza
  orice modificare.
- **Originalul se păstrează exact.** Cum a venit de la Manuel, inclusiv diacriticele greșite
  și spațiile; corecturile se fac doar în PR, ca autorul să le vadă pe toate.

## Formatul unei poezii

Fișierul `poezii/<slug>.md` (slug = titlul fără diacritice, cu litere mici și cratime):

```
---
titlu: Titlul poeziei
tema: [natura, dor]
---

Primul vers
al doilea vers

A doua strofă
```

- `tema` este lista temelor poeziei; Manuel o spune sau o propui tu (spune-i lui Manuel că e doar o propunere).
  Pe ea se bazează cărțile de la final.
- Opțional, `sursa:` cu linkul postării de pe Facebook, dacă Manuel îl dă.
- Versurile și strofele rămân exact ca în original: o linie pe vers, rând gol între strofe.

## Pașii pentru o poezie (sau mai multe, la un loc)

1. **Original.** Salvează textul primit, neschimbat, în `poezii/<slug>.md`. Commit direct pe
   `main`: `Original: <Titlu>`. Push. (Originalul ajunge întâi pe `main` ca PR-ul să arate
   *doar* modificările, nu tot fișierul ca adăugat.)
2. **Rafinare.** Creează ramura `rafinare/<slug>` (pentru mai multe poezii: `rafinare/<tema>`),
   modifică fișierul și fă commit: `Rafinare: <Titlu>`. Push.
3. **Pull Request** către `main`, în română:
   - titlu: `Rafinare: <Titlu>`;
   - o scurtă introducere (ce am verificat, ce impresie generală);
   - tabel cu **fiecare** modificare, numerotată: `nr | înainte | după | tip | motiv`;
   - secțiunea **Întrebări pentru autor** pentru ce nu am schimbat, dar merită discutat;
   - un rând la final: *„Comentează la rândul respectiv sau după număr. Ce nu îți place,
     refuzi și revenim la original.”*
4. Dă-i lui Manuel **linkul PR-ului** și nimic mai mult de făcut pe partea lui.
5. **Comentarii.** Când Manuel revine, citește comentariile PR-ului
   (`gh pr view <nr> --comments` și `gh api repos/{owner}/{repo}/pulls/<nr>/comments`),
   propune răspunsurile, aplică ce s-a hotărât, fă commit și push pe aceeași ramură.
   Manuel rezolvă conversațiile și îmbină PR-ul.
6. **Cărți.** La cerere, adună poeziile pe o temă în `carti/<titlu-carte>.md` (cuprins, apoi
   poeziile în ordinea hotărâtă împreună cu Manuel), tot printr-un PR.

## Ce verifici la rafinare

**Corecturi** (se aplică, se explică scurt în tabel):
- ortografie și greșeli de tipar;
- diacritice: `ș` și `ț` cu virgulă (nu `ş`/`ţ` cu sedilă), `ă`, `â`, `î` corecte (regula
  `â`/`î` din ortografia curentă, cu excepțiile ei);
- gramatică: acord, forme verbale, cratime, virgule evidente;
- litere mari la început de vers doar dacă autorul o face constant (urmează convenția lui);
- spații duble, spații la capăt de rând, semne de punctuație lipite.

**Sugestii** (se aplică moderat și se marchează „sugestie” în tabel, ca autorul să le poată
refuza ușor):
- cuvinte mai potrivite, repetiții, rime sau ritm care șchioapătă;
- sunt acceptate doar dacă păstrează sensul și tonul autorului. Alternativele mai îndrăznețe
  merg la „Întrebări pentru autor”, nu în text.

## GitHub

- Depozitul: `Manu-APO/symy-poetry`, ramura principală `main`.
- Dacă `gh` nu este autentificat, nu inventa un PR: pregătește ramura, apoi dă-i lui Manuel
  linkul de creare `https://github.com/Manu-APO/symy-poetry/compare/main...<ramura>?expand=1`
  împreună cu textul descrierii, gata de lipit.
- Nu face push forțat și nu șterge ramuri fără să întrebi.
- Platforma veche, complicată (workflow-uri, AI automat, export) a rămas, nefolosită, doar
  pe ramura `feature/editorial-platform`.
