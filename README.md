# Symy Poetry

Poezii românești, rafinate împreună cu autorul și adunate, la final, în cărți.

## Cum merge

1. Autorul alege o poezie (de pe Facebook).
2. Manuel o copiază aici, în Claude, exact așa cum este.
3. Claude o salvează **neschimbată** în `poezii/`, apoi pregătește o variantă rafinată
   (ortografie, diacritice, gramatică, eventual sugestii de cuvinte) pe o ramură separată
   și deschide un **Pull Request**.
4. Autorul citește Pull Request-ul și lasă comentarii: ce acceptă, ce nu.
5. Claude aplică ce s-a hotărât, Manuel rezolvă comentariile, iar PR-ul se îmbină.
6. Când sunt destule poezii pe o temă, Claude le adună într-o carte în `carti/`.

## Foldere

| Folder | Ce conține |
|---|---|
| `poezii/` | Câte un fișier pe poezie, `nume-poezie.md` |
| `carti/` | Cărțile finale, adunate pe teme |

Regulile după care lucrează Claude sunt în [CLAUDE.md](CLAUDE.md).
