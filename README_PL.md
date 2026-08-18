# BlitzPredict site — instrukcja publikacji

Ten pakiet jest przygotowany pod istniejące repozytorium użytkownika GitHub Pages `byczekbyczek.github.io`.

## Co jest już gotowe

- `index.html` — pełna poprawiona strona.
- `assets/demo-input.*` — prawdziwy screenshot wejściowy PoC.
- `assets/demo-output.*` — prawdziwy wynik BlitzPredict.
- `CNAME` — domena `blitzpredict.info`.
- `robots.txt`, `sitemap.xml`, `404.html`, favicon.

## Dwie rzeczy do uzupełnienia przed publikacją

W `index.html` wyszukaj dwukrotnie:

```text
DEMO_URL_HERE
```

Zastąp oba wystąpienia linkiem do niepublicznego filmu YouTube.

Sprawdź również, czy adres kontaktowy pozostaje poprawny:

```text
karol@blitzpredict.info
```

## Zalecana kolejność

1. Najpierw wgraj nowe pliki do repozytorium `byczekbyczek.github.io` i sprawdź stronę pod dotychczasowym adresem GitHub Pages.
2. Zweryfikuj domenę na poziomie konta GitHub.
3. Dodaj `blitzpredict.info` jako Custom domain w ustawieniach Pages repozytorium.
4. Dopiero potem ustaw rekordy DNS u operatora domeny.
5. Po propagacji DNS włącz `Enforce HTTPS`.

GitHub zaleca dodanie domeny do konfiguracji Pages przed skierowaniem DNS na GitHub, aby ograniczyć ryzyko przejęcia domeny.

## Krok 1 — wgranie kodu

W repozytorium `byczekbyczek.github.io`:

1. Zrób kopię obecnego `index.html`.
2. Zastąp pliki w katalogu głównym zawartością tego pakietu.
3. Folder `assets` musi znaleźć się obok `index.html`.
4. Commit, na przykład:

```text
Rebuild BlitzPredict landing page for startup application
```

5. Sprawdź stronę pod adresem `byczekbyczek.github.io`.

## Krok 2 — bezpieczna weryfikacja domeny na GitHubie

Na GitHubie przejdź do ustawień swojego profilu, nie repozytorium:

1. Profile picture → `Settings`.
2. `Pages` w sekcji Code, planning and automation.
3. `Add a domain`.
4. Wpisz `blitzpredict.info`.
5. GitHub pokaże rekord TXT do dodania w DNS domeny.
6. Dodaj ten rekord TXT u operatora i pozostaw go na stałe.
7. Wróć do GitHuba i kliknij `Verify`.

Nie dodawaj wildcard DNS typu `*.blitzpredict.info`.

## Krok 3 — Custom domain w repozytorium

1. Otwórz repozytorium `byczekbyczek.github.io`.
2. `Settings` → `Pages`.
3. W polu `Custom domain` wpisz:

```text
blitzpredict.info
```

4. Kliknij `Save`.

Plik `CNAME` z tego pakietu zawiera już tę samą domenę.

## Krok 4 — DNS domeny

U operatora domeny dodaj cztery rekordy A dla domeny głównej:

| Typ | Nazwa / Host | Wartość |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |

Dodaj również:

| Typ | Nazwa / Host | Wartość |
|---|---|---|
| CNAME | `www` | `byczekbyczek.github.io` |

### Bardzo ważne dla firmowego maila

Nie usuwaj ani nie zmieniaj istniejących rekordów:

- MX,
- SPF,
- DKIM,
- rekordów weryfikacyjnych poczty.

Dodajesz rekordy strony obok rekordów pocztowych. Samo dodanie rekordów A/CNAME nie powinno wyłączyć poczty, o ile nie skasujesz MX/TXT.

DNS może propagować się do 24 godzin.

## Krok 5 — HTTPS

Po poprawnym rozpoznaniu domeny:

1. Repozytorium → `Settings` → `Pages`.
2. Zaznacz `Enforce HTTPS`.

Opcja może pojawić się z opóźnieniem po propagacji DNS.

## Krok 6 — Google for Startups Cloud Program

Przed wysłaniem wniosku sprawdź spójność:

```text
Public website: https://blitzpredict.info
Business email: karol@blitzpredict.info
Google Cloud billing account: konto/dostęp powiązany z tym firmowym adresem
```

Google wymaga, aby firmowy adres użyty we wniosku odpowiadał domenie publicznej strony startupu. Przygotuj również 18-znakowy Billing Account ID.

## Co strona mówi obecnie

### Działa teraz

- ręcznie dostarczony screenshot,
- EasyOCR,
- autorska korekcja i kaskadowe wyszukiwanie kont,
- publiczne Wargaming API,
- WR i average damage,
- team averages,
- wygenerowany HUD w OpenCV.

### Jest planowane

- standalone Android/Windows client,
- kontrolowany backend w Google Cloud,
- cache, monitoring i testy kosztowe,
- prywatny pilot,
- dalsze moduły analityczne i model subskrypcyjny.

Ta granica jest celowo jasna, aby strona nie przedstawiała planów jako gotowej infrastruktury.
