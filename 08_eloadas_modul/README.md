# 8. előadás – LaTeX-modul

A `diffea8.tex` a differenciálegyenletek-jegyzet 8. előadásának **beilleszthető modulja**. Az eredeti kézirat forrása a `differencialegyenletek.pdf` 27–31. oldala, kizárólag a 2019. 11. 13. (8) és 2019. 11. 20. (9) jelölések közötti szakasz.

## Fájlok

- `diffea8.tex`: a modul, **nem** önálló dokumentum.
- `preamble.tex`: változtatás nélküli másolat a projekt eredeti stílusfájljából.
- `08_forditas_proba.tex`: egyszerű ellenőrző fődokumentum.
- `08_eloadas.pdf`: az ellenőrző fődokumentummal ténylegesen lefordított, 4 oldalas változat.
- `lectures/08_eloadas_abrak/`: üres ábramappa; a kézirat kijelölt részén **0 önálló ábra** található.
- `ellenorzes.md`: oldalankénti egyeztetés, javítások, kéziratos bizonytalanságok és fordítási próbák.

## Beillesztés a teljes jegyzetbe

A jegyzet fő `.tex` fájljában, a `\begin{document}` és a `\end{document}` között:

```latex
\input{diffea4.tex}
\input{diffea5.tex}
\input{diffea6.tex}
\input{diffea7.tex}
\input{diffea8.tex}
```

A fődokumentum preambulumában egyszer szerepeljen:

```latex
\input{preamble.tex}
```

A modul tartalmazza a `\graphicspath{{lectures/08_eloadas_abrak/}}` beállítást, de saját ábrát nem tölt be. A 4–6. előadásnak külön eredeti képfájljai lehetnek; ezeket a meglévő jegyzetben továbbra is biztosítani kell.

## Újrafordítás

A jelen mappában, telepített `pdflatex` segítségével:

```bash
pdflatex -interaction=nonstopmode -halt-on-error -jobname=08_eloadas 08_forditas_proba.tex
pdflatex -interaction=nonstopmode -halt-on-error -jobname=08_eloadas 08_forditas_proba.tex
```

A `preamble.tex` és a 8. előadás fájljai mellett mást nem kell telepíteni a már meglévő LaTeX-telepítés standard csomagjain túl. A csomagolt `08_eloadas.pdf` a fenti paranccsal készült.

## Forráshűségi figyelmeztetés

Néhány eredeti kéziratos jelölés matematikailag hiányosnak tűnik (például a többszörös gyök deriváltfeltétele, a paraméter szerinti deriválás nevezője és a szuperpozíciós képlet `y^n` tagja). Ezeket nem módosítottam hallgatólagosan. A teljes lista és a javasolt értelmezések az `ellenorzes.md` fájlban olvashatók. A 9. előadásnak a próbafüggvény-módszerre vonatkozó folytatása nem része a modulnak.
