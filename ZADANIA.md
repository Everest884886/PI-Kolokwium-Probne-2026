# Kolokwium — instrukcja i punktacja

**Czas: 45 minut. Maksimum: 10 punktów.** Dozwolone: terminal, `man`, `--help`, dotychczasowe prezentacje i własne notatki. Zasady korzystania z pomocy innych osób / AI określa prowadzący przed rozpoczęciem sprawdzianu.

**Zacznij od wykonania forka** publicznego repozytorium prowadzącego na własne konto GitHub, a potem sklonuj *swój* fork (nie oryginał). Pracuj w katalogu forka. Pliki w `dane/` są materiałem wejściowym — nie wolno ich modyfikować.

## A. Strumienie, filtry i potoki — 2 pkt

1. (1 pkt) Utwórz `raporty/bledy.txt` zawierający **wszystkie** wiersze rozpoczynające się od `ERROR;` ze wszystkich `dane/*.log`, posortowane alfabetycznie. Wykorzystaj `grep`, `sort` i przekierowanie `>`.
2. (1 pkt) Utwórz `raporty/ile_bledow.txt` zawierający **jedną liczbę**: liczbę wierszy z `raporty/bledy.txt`. Użyj `wc -l` i przekierowania (można skorzystać z `<`).

## B. Prawa i archiwum — 2 pkt

3. (1 pkt) Nadaj `src/analiza.sh` uprawnienia **750** (`rwxr-x---`).
4. (1 pkt) Utwórz archiwum `raporty/oddanie.tar.gz` obejmujące katalog `dane/`, katalog `src/` i plik `README.md`. Nie pakuj całego repozytorium ani katalogu `.git`.

## C. Skrypt Bash — 4 pkt

Uzupełnij istniejący plik `src/analiza.sh`. Uruchomienie: `bash src/analiza.sh dane`.

5. (1 pkt) Przyjmij katalog logów z pierwszego argumentu (`$1`); jeżeli brak argumentu, użyj `dane`. Jeśli katalog nie istnieje, wypisz komunikat na **stderr** i zakończ kodem **2**. Użyj `if` i testu `-d`.
6. (1 pkt) Użyj **pętli `for`** do przejścia po `*.log` i wyświetl po jednej linii dla każdego pliku w formacie `nazwa.log;liczba_ERROR;STATUS`. Liczbę `ERROR` licz przez `grep` (liczą się wyłącznie linie zaczynające się od `ERROR;`). Jeśli nie ma logów, skrypt nie powinien wypisywać nieistniejącej nazwy `*.log`.
7. (2 pkt) Dla danego pliku wpisz `ALARM`, gdy **Liczba wpisów ERROR w danym pliku jest większa lub równa 2.** W przeciwnym wypadku wpisz `OK`. Zrealizuj to w `if`. Zwracana liczba w drugim polu to **zawsze liczba wpisów ERROR**, niezależnie od warunku alarmu.

Nie dodawaj nagłówka, dodatkowych komentarzy ani spacji w wierszach wyniku. Testuj: `bash src/analiza.sh dane` oraz `bash src/analiza.sh /nie_ma`.

## D. Git i GitHub — 2 pkt

8. (1 pkt) Wykonaj **minimum dwa własne commity** po rozdzielnych etapach pracy, np. po A+B i po C. Nadaj im zrozumiałe komunikaty. Sprawdź `git log --oneline`.
9. (1 pkt) Opublikuj rozwiązanie (`git push`) **we własnym publicznym forku** i prześlij prowadzącemu URL tego forka. Repozytorium musi zawierać pliki `raporty/` i zmodyfikowany skrypt.

## Co oddajesz?

Jedno **publiczne repozytorium GitHub (Twój fork)**. Upewnij się, że `git status` jest czysty, a pliki widać w przeglądarce na Twoim profilu. Jeśli GitHub jest niedostępny, zastosuj procedurę awaryjną wskazaną przez prowadzącego — nie publikuj kluczy prywatnych.
