# BlitzPredict — strona projektu

Statyczny landing page projektu BlitzPredict publikowany przez GitHub Pages pod adresem
https://blitzpredict.info.

Repozytorium strony jest oddzielone od prywatnego repozytorium aplikacji
byczekbyczek/BlitzPredict.

## Technologia

- pojedynczy plik index.html,
- CSS osadzony w dokumencie,
- brak JavaScriptu aplikacyjnego,
- brak frameworka, bundlera i zewnętrznych zależności,
- GitHub Pages z domeną z pliku CNAME.

## Co pokazuje obecna strona

Treść odpowiada stanowi aplikacji po scaleniu PR #31:

- lokalna wersja rozwojowa dla Windows,
- GUI i CLI oparte na wspólnym serwisie analizy,
- jawny, jednorazowy przechwyt klatki z wybranego okna gry w Windows,
- stały fallback przez ręczny wybór JPG, PNG lub WebP,
- dla klatki przechwyconej z okna: fail-closed preflight ekranu ładowania przed OCR i zapytaniami API,
- adaptacyjna geometria dwóch składów po siedem osób,
- obsługa układu matchmakingu preferencyjnego i standardowego,
- lokalny EasyOCR,
- konserwatywne dopasowanie kont: tylko jednoznaczny exact match jest zaufany,
- kontrolowany klient oficjalnego API Wargaming,
- generowanie i eksport HUD,
- testy na Windows i Ubuntu dla Pythona 3.11–3.13,
- deterministyczny benchmark offline,
- prywatne, agregatowe audyty geometrii i realnego OCR,
- walidacja wewnętrznej paczki portable Windows.

Strona jasno oddziela gotowe elementy od planów. Nie przedstawia ciągłego
watchera, automatycznego wykrywania bitwy, live overlay, hooków wejścia, automatyzacji
rozgrywki, chmury, subskrypcji, aplikacji mobilnej ani publicznej podpisanej paczki
jako ukończonych funkcji.

## Prywatność materiałów demonstracyjnych

Landing page nie publikuje screenów z gry ani prawdziwych nicków. Widok produktu
jest syntetycznym mockupem zbudowanym wyłącznie w HTML i CSS, z wymyślonymi
nazwami i wartościami.

Starsze pliki demo-input.* i demo-output.* zostały usunięte z bieżącego drzewa
publikacji. Historia Git zachowuje wcześniejsze wersje repozytorium.

## Pliki

- index.html — treść, style, semantyka i syntetyczny mockup produktu,
- assets/favicon.svg — favicon,
- CNAME — domena blitzpredict.info,
- robots.txt — reguły indeksowania,
- sitemap.xml — mapa strony,
- 404.html — prosta strona błędu,
- CHANGELOG.md — historia publicznych zmian.

## Kontrola przed publikacją

Przed scaleniem zmian należy sprawdzić:

1. poprawność składni HTML,
2. poprawność JSON-LD,
3. unikalność wszystkich atrybutów id,
4. istnienie celu dla każdego lokalnego linku z kotwicą,
5. istnienie wszystkich lokalnych plików wskazanych przez href i src,
6. obecność opisu alt dla ewentualnych obrazów treści,
7. widok desktopowy i mobilny przez lokalny serwer HTTP,
8. wynik git diff --check.

Do szybkiego lokalnego podglądu uruchom w tym katalogu:

    python -m http.server 8080

Następnie otwórz:

    http://127.0.0.1:8080/

## Publikacja

GitHub Pages publikuje zawartość głównej gałęzi repozytorium użytkownika.
Scalenie zmian do main aktualizuje publiczną stronę, dlatego przed merge trzeba
obejrzeć lokalny render na szerokim i wąskim viewportcie.

Po wdrożeniu należy potwierdzić:

- https://blitzpredict.info/ zwraca HTTP 200,
- dokument ma aktualny tytuł i opis,
- favicon, robots.txt oraz sitemap.xml zwracają HTTP 200,
- HTTPS pozostaje aktywny,
- na stronie nie ma surowych screenshotów ani prawdziwych identyfikatorów graczy.

## Kontakt

Publiczny adres projektu:

    karol@blitzpredict.info

Strona opisuje BlitzPredict jako niezależny projekt Karola. Nie deklaruje formy
prawnej działalności; nazwa prawna używana w zewnętrznych formularzach musi
odpowiadać rzeczywistym dokumentom właściciela.
