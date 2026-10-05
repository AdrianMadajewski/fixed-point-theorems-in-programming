# Twierdzenia o punktach stałych w programowaniu

[![Kompilacja referatu](https://github.com/AdrianMadajewski/fixed-point-theorems-in-programming/actions/workflows/build-latex.yml/badge.svg)](https://github.com/AdrianMadajewski/fixed-point-theorems-in-programming/actions/workflows/build-latex.yml)

Referat (LaTeX) przygotowany na Wydziale Matematyki i Informatyki UAM w Poznaniu.
Autor: **Adrian Madajewski**.

📄 **Aktualna wersja PDF:** [`pdf/referat.pdf`](pdf/referat.pdf) — generowana automatycznie
przy każdej zmianie `referat.tex`.

## O czym jest referat

Semantyka denotacyjna przypisuje programom obiekty matematyczne — funkcje ze stanów
w stany. Dla większości konstrukcji języka definicja jest bezpośrednia, ale pętla
`while` prowadzi do *równania rekurencyjnego* `W = F(W)`, w którym szukana denotacja
występuje po obu stronach. Referat pokazuje, jak nadać temu równaniu ścisły sens
i wybrać właściwe rozwiązanie — **najmniejszy punkt stały**.

Zawartość:

1. **Język IMP** — składnia (BNF) i semantyka denotacyjna wyrażeń oraz instrukcji;
   sformułowanie problemu pętli `while`.
2. **Równania stałopunktowe** — punkty stałe, kolejne przybliżenia.
3. **Zbiory łańcuchowo zupełne** — porządek informacyjny, łańcuchy, kresy górne,
   porządek płaski, porządek poziomy i pionowy w zbiorach funkcji, izomorfizm
   `A ⇀ B ≅ A → B⊥`.
4. **Funkcje ciągłe** — monotoniczność, ciągłość, przestrzeń funkcji ciągłych,
   funkcje na zbiorach płaskich.
5. **Twierdzenie Kleenego** — `lfp(f) = ⊔ fⁱ(⊥)`; zastosowanie do denotacji pętli
   `while` oraz rekurencyjnej definicji silni.
6. **Podejście alternatywne** — metryki częściowe Matthewsa, porządek indukowany
   przez metrykę częściową, ciągi Cauchy'ego i zupełność, twierdzenie Matthewsa
   o punkcie stałym kontrakcji oraz porównanie obu podejść.

## Kompilacja lokalna

Wymagany TeX Live lub MiKTeX z pakietami `babel` (polski), `lmodern`, `amsmath`,
`mathtools`, `stmaryrd`, `mathrsfs`, `tikz`, `hyperref`, `comment`, `float`, `enumitem`.

```bash
latexmk -pdf referat.tex
# lub
pdflatex referat.tex && pdflatex referat.tex
```

## Automatyczna kompilacja

Workflow [`.github/workflows/build-latex.yml`](.github/workflows/build-latex.yml):

- uruchamia się przy każdym pushu zmieniającym `referat.tex` na gałęzi `main`
  (oraz ręcznie z zakładki **Actions**),
- kompiluje referat w pełnym TeX Live (`latexmk` + `pdflatex`),
- zapisuje wynik jako artefakt oraz zatwierdza go w repozytorium jako `pdf/referat.pdf`.

## Struktura repozytorium

| Plik | Opis |
|------|------|
| `referat.tex` | źródło referatu (jedyny plik edytowany ręcznie) |
| `pdf/referat.pdf` | PDF generowany automatycznie przez GitHub Actions |
| `.github/workflows/build-latex.yml` | konfiguracja kompilacji |
| `.gitignore` | dopuszcza do repozytorium tylko powyższe pliki |

## Literatura

- M. J. C. Gordon, *The Denotational Description of Programming Languages: An Introduction*, Springer, 1979.
- S. G. Matthews, *Partial Metric Topology*, Annals of the New York Academy of Sciences 728 (1994), 183–197.
- S. C. Kleene, *Introduction to Metamathematics*, North-Holland, 1952.
- *Denotational Semantics* — Harvard CS 152 (wykład 6), Cornell CS 4110 (wykład 8).
