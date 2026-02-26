# Opracowanie tematów na egzamin inżynierski 2026

## 1. Złożoność czasowa i pamięciowa algorytmów

### Pojęcie złożoności algorytmu

Złożoność algorytmu określa, jak wydajny jest algorytm, ile musi on wykonać operacji w zależności ilości danych oraz ile potrzebuje do tego pamięci. Często zdarza się, że dany problem algorytmiczny można rozwiązać kilkoma metodami, czyli algorytmami o różnej złożoności obliczeniowej.

Nie ma znaczenia tutaj sprzęt na jakim jest to wykonywane, tylko sam algorytm oraz jego zachowanie w zależności od danych wejściowych.

### Złożoność czasowa

Określa ile podstawowych operacji musi wykonać alogrytm, aby rozwiązać dany problem dla **n** danych wejściowych.

W przypadku większej ilości danych wejściowych jest to suma poszczególnych części.

### Złożoność pamięciowa

Określa ilość potrzebnej pamięci do obsłużenia algorytmu na podstawie danych wejściowych **n**.

Często algroytmy bardziej optymalne czasowo są bardziej złożone pamięciowo i odwrotnie.

### Notacje asymptotyczne

Złożoności alogrytmów wyraża się za pomocą notacji asymptotycznych. Stosuje się je zarówno do czasu jak i pamięci.

Notacja duże O &rarr; O(f(n)) (pesymistyczne szacowanie)
: Określa ograniczenie funkcji z góry. Asymptotycznie funkcja nie większa niż, algorytm nie działa wolnej niż.

Notacja duże Omega &rarr; Ω(f(n)) (optymistyczne szacowanie)
: Określa ograniczenie funckji z dołu. Asymtotycznie nie mniejsza, algorytm działa przynajmniej tak długo

Notacja duże Theta &rarr; Θ(f(n))
: Określa ograniczenie ścisłe, dolne i górne. Dokładne oszacowanie złożoności algorytmu.

Najczęściej używaną notacją jest duże O ze względu na bezpieczeństwo skalowaności. Zakłada najgorszy przypadek wykoania, więc jest w stanie dokładnie określić czego możemy się spodziewać po algorytmie mimo jednostronnego ogarniczenia funkcji.

### Klasy złożoności algorytmu

Najprościej mówiąc, jest to rodzaj funckji otrzymany po wyznaczeniu liczby operacji wykonywanych przez analizowany algorytm.

Złożoności posortowane od najszybszej

|Klasa           |Opis złożoności      |Przykładowy algorytm w klasie                                  |
|-----------     |---------------------|---------------------------------------------------------------|
|$$O(1)$$        |Stała                |Dostęp do elementu tablicy                                     |
|$$O(log_{n})$$  |Logarytmiczna        |Wyszukiwanie binarne [^1]                                      |
|O(n)            |Liniowa              |Przeszukanie tablicy element po elemencie                      |
|$$O(nlog_{n})$$ |Liniowo-logarytmiczna|Algorytmy typu dziel i zwyciężaj (merge sort)                  |
|$$O(n^{2})$$    |Kwadratowa           |Bubble sort (wynika z zagnieżdżenia dwóch pętli)               |
|$$O(n^{3})$$    |Sześcienna           |Mnożenie macieży 2-wymiarowych                                 |
|$$O(2^{n})$$    |Wykładnicza          |Problem wież Hanoi (przeniesienie n krążków to 2^n^ - 1 ruchów)|
|$$O(n!)$$       |Silnia               |Generowanie permutacji zbioru                                  |

[^1]: Znalezienie konktretnego elementu w posortowanej tablicy. Przykładowo sprawdzanie środkowego elementu tablicy następnie szukanie w jednej z połówek i tak do uzyskania szukanego elementu.

## 2. Podstawowe struktury danych i algorytmy do ich przetwarzania

Struktura danych to sposób organizacji i przechowywania danych w pamięci komputera, umożliwiający efektywne wykonywanie operacji na tych danych. Struktury danych są zwykle implementowane przy użyciu typów prostych.

Typ prymitywny (prosty) &rarr; przechowuje jedną wartość.
Struktura danych &rarr; organizuje wiele wartości oraz definiuje operacje, które można na nich wykonywać.

UUżycie odpowiedniej struktury danych i algorytmu umożliwia optymalizację czasową, i pamięciową. Każda struktura danych ma swoje zalety i wady, a jej wybór ma kluczowe znaczenie dla wydajności algorytmów.

### Przykładowe struktury danych

#### Tablica

Ciąg elementów przechowywanych w ciągłym obszarze pamięci zedefiniowanym wcześniej, z dostępem przez indeks.

Podstawowwe operacje na tablicach:

| Operacja                                   | Złożoność czasowa|
| ------------------------------------------ | ---------------- |
| Dostęp po indeksie                         | $$O(1)$$         |
| Wyszukiwanie liniowe                       | $$O(n)$$         |
| Wyszukiwanie binarne (posortowana)         | $$O(log_{n})$$   |
| Wstawienie                                 | $$O(n)$$         |
| Usuwanie                                   | $$O(n)$$         |

Algorytmy sortowania tablic:

| Algorytm                            | Złożoność czasowa        | Pamięciowa     |
| ----------------------------------- | ------------             |-------------   |
| Bubble                              | $$O(n^{2})$$             | $$O(1)$$       |
| Merge Sort                          | $$O(nlog_{n})$$          | $$O(n)$$       |
| Quick Sort                          | $$O(nlog_{n})$$          | $$O(log_{n})$$ |
| Heap Sort                           | $$O(nlog_{n})$$          | $$O(1)$$       |

#### Lista powiązana

Lista powiązana to struktura danych składająca się z węzłów, gdzie każdy węzeł zawiera dane oraz wskaźnik do następnego (i opcjonalnie poprzedniego) węzła. Nie posiada stałej wielkości, ani indeksowania elementów. W teorii jest to jakiś przypadek grafu.

Podstawowwe operacje na listach powiązanych:

| Operacja                                   | Złożoność czasowa|
| ------------------------------------------ | ---------------- |
| Dostęp                                     | $$O(n)$$         |
| Wstawienie na początek                     | $$O(1)$$         |
| Wstawienie między znane węzły              | $$O(1)$$         |
| Usuwanie                                   | $$O(n)$$         |

Algorytmy sortowania list powiązanych:

| Algorytm                            | Złożoność czasowa    | Pamięciowa     |
| ----------------------------------- | ------------         |-------------   |
| Odwracanie listy                    | $$O(n)$$             | $$O(1)$$       |
| Merge Sort                          | $$O(nlog_{n})$$      | $$O(log_{n})$$ |
| Znajdowanie środka listy            | $$O(n)$$             | $$O(1)$$       |

#### Stos

Stos to struktura danych działająca na zasadzie LIFO (Last In, First Out), gdzie elementy są dodawane i usuwane z tego samego końca. Jest on powiązany z listą ponieważ to na niej opiera się jego najprostrza implementacja.

Podstawowwe operacje na stosie:

| Operacja                                   | Złożoność czasowa|
| ------------------------------------------ | ---------------- |
| Dodanie                                    | $$O(1)$$         |
| Podgląd ostatniego elementu                | $$O(1)$$         |
| Usuwanie                                   | $$O(1)$$         |

Algorytmy wykorzystujące stos (V - vertices [wierzchołki w grafie], E - edges [krawędzie]):

| Algorytm                            | Złożoność czasowa    | Pamięciowa     |
| ----------------------------------- | ------------         |-------------   |
| Sprawdzanie poprawności nawiasów    | $$O(n)$$             | $$O(n)$$       |
| Przeszukiwanie grafu w głąb (DFS)   | $$O(V * E)$$         | $$O(V)$$       |

#### Kolejka

Kolejka to struktura danych działająca na zasadzie FIFO (First In, First Out), gdzie elementy są dodawane na końcu i usuwane z początku. Jest również powiązana z listą ponieważ na niej jest najprostrza implementacja.

Podstawowwe operacje na kolejce:

| Operacja                                   | Złożoność czasowa|
| ------------------------------------------ | ---------------- |
| Dodanie na koniec                          | $$O(1)$$         |
| Usuwanie usuwanie z początku               | $$O(1)$$         |
| Przeszukanie całej                         | $$O(n)$$         |

Algorytmy wykorzystujące kolejkę:

| Algorytm                            | Złożoność czasowa | Pamięciowa     |
| ----------------------------------- | ----------------- |--------------- |
| Przeszukiwanie grafu w szerz (BFS)  | $$O(V * E)$$      | $$O(V)$$       |

#### Graf

Grafy to struktury danych składające się z wierzchołków i krawędzi (połączeń) między nimi. Mogą być skierowane lub nieskierowane, ważone lub nieważone. Każdy wierzchołek może mieć wiele krawędzi. Standardowe oznaczenia to V - vertices (wierzchołki w grafie) oraz E - edges (krawędzie). Może być implementowany na macierzy sąsiedzwa (tablica 2-wymiarowa), liście sąsiedztwa lub liście krawędzi. Zależnie od implementacji różnią się koszty postawowych operacji.

Podstawowwe operacje na grafie zależnie od implemetacj (złożoność czasowa):

| Reprezentacja      | Dodawanie wierzchołka | Dodawanie krawędzi | Sprawdzanie istnienia krawędzi |
| ------------------ | --------------------- | ------------------ | ------------------------------ |
| Macierz sąsiedztwa | $$O(1)$$              | $$O(1)$$           | $$O(1)$$                       |
| Lista sąsiedztwa   | $$O(1)$$              | $$O(1)$$           | $$O(deg(V))$$                  |
| Lista krawędzi     | $$O(1)$$              | $$O(1)$$           | $$O(E)$$                       |

Algorytmy bazujące na grafach:

| Algorytm                    | Złożoność czasowa                  | Pamięciowa |
| --------------------------- | -----------------                  | ---------- |
| Przeszukiwanie wszerz (BFS) | $$O(V + E)$$                       | $$O(V)$$   |
| Przeszukiwanie w głąb (DFS) | $$O(V + E)$$                       | $$O(V)$$   |
| A*                          | $$O(E * log_{V})$$                 | $$O(V)$$   |
| Dijkstra                    | $$O((V + E)log_{V})$$ $$O(V^{2})$$ | $$O(V)$$   |

#### Tablicje asocjacyjne (hash table/map) (słowniki)

Struktura przechowująca pary klucz–wartość, wykorzystująca funkcję haszującą do wyznaczania klucza/indeksu dla danych.

Podstawowwe operacje na tablicy asocjacynej:

| Operacja                                   | Złożoność czasowa    |
| ------------------------------------------ | ----------------     |
| Dostęp po kluczu                           | $$O(1)$$             |
| Wstawienie                                 | $$O(1)$$             |
| Usuwanie                                   | $$O(1)$$             |
| Ponowne hashowanie                         | $$O(n)$$             |

Algorytmy bazujące na tablicach asocjacyjnych:

| Algorytm                                 | Złożoność czasowa  | Pamięciowa     |
| -----------------------------------      | -----------------  |--------------- |
| Grupowanie anagramów (k - długość słowa) | $$O(nk*log_{k})$$  | $$O(n)$$       |
| Dwa elementy których suma = X            | $$O(n)$$           | $$O(n)$$       |

## 3. Nowoczesne platformy programowania obiektowego

### Co to jest programowanie obiektowe?

Programowanie obiektowe (OOP - object orientet programing) to paradygmat programowania, który organizuje kod wokół obiektów, które łączą dane i zachowania (metody) operujące na tych danych. Kluczowa idea to stan (dane) + zachowanie (metody) są połączone w jedną jednostkę - obiekt. Zawierają się też w tym klasy które są abstrakcyjnym opisem / szablonem tworzenia obiektów i zbiorem ich zachowań. Klasa zawiera też ewentualne realcje z innymi klasami.

#### Filary programowania obiektowego

Abstrakcja - Ukrywanie złożoności obiektów poprzez defioniowanie interfejsów oraz klas.
Enkapsulacja (hermertyzacja) - Ograniczanie dostępu do danych obiektu, dostęp jedynie przez publiczne interfejsy. Kontrola oraz bezpieczństwo stanów.
Dziedziczenie - Tworzenie nowych klas na bazie istniejących, dziedzicząc ich metody oraz własności. Rozszerzalność funkcjonalności oraz współdzielenie kodu.
Polimorfizm - Możliwość użycia tych samych metod / zachowań dla różnych kontekstów.

#### Minusy / ograniczenia programowania obiektowego

- trudności w współbierzności / równoległowości, możliwe przypadki "race condition" częściej niż w innych paradygmatach ze względu na większe współdzielenie
- złożoność hierarchiczna przy dziedziczeniu, możliwe głębokie i trudne w utrzymaniu hierarchie
- nadmierna abstrakcja, wielowarstwowość, trudny do zrozumienia kod
- większy koszt pamięciowy / wydajnościowy względem podejścia proceduralnego

### Czym są nowoczesne palatformy programowania obiektowego?

Nowoczesne platformy programowania obiektowego to kompleksowe środowiska programistyczne umożliwiające tworzenie, uruchamianie i zarządzanie aplikacjami w paradygmacie obiektowym, obejmujące język, środowisko wykonawcze, biblioteki oraz narzędzia wspierające rozwój oprogramowania. Nowoczesne platformy często integrują się z innymi technologiami, takimi jak bazy danych (ORM - Object-Relational Mapping), usługi webowe (REST - Representational State Transfer) czy narzędzia zarządzania wersjami (GIT).

#### Najważniejsze cechy nowoczesnych platform programowania obiektowego

- Modularność i skalowalność - podział aplikacji na moduły, komponenty, ułatwiające utrzymanie i rozwój naszego kodu
- Wsparcie dla współbieżności - wielowątkowość, synchronizacja, jak i również asynchroniczność
- Środowisko uruchomieniowe (runtime) - kontrola wykonania programu, obsługa wyjątków, dynamiczne łądowanie klas oraz bezpieczństwo wykonania
- Automatyczne zarządzanie pamięcią - tak zwany "Garbage Collection", minimalnizacja wycieków pamięci, automatyczne zwalnianie nieużywanej pamięci, przypisanie wolnych wskaźników
- Bogate biblioteki wbudowane - zawierające obsługę plików, sieci, struktur danych czy architektur typu REST i mikroserwisów
- Niezależność systemowa oraz platformowa - kod działa na różnych systemach operacyjnych poprzez maszyny wirtualne lub warstwy pośredniczące umożliwiając tworzenie aplikacji dla wielu systemów jednoscześnie

### Pełnoprawne platformy programowania obiektowego

#### .NET

Jest to platforma programowania obiektowego rozwiajana przez frimę Microsoft, umożliwia tworzenie różnych aplikacji w kilku wspieranych językach. Działa na wspólnym środowisku uruchomieniowym CLR - common language runtime. Posiada automatyczne zarządzanie pamięcią, pełne wsparcie dla OOP i wieloplatformowość.

Platforma ta umożliwia pisanie w językach takich jak VB&period;NET, C# oraz F#. Jej nowoczesność pozwala na pisanie kodu zawierającego cechy również funkcyjne dzięki językowi F#. Jej głównym językiem jest C# wszechstronnie używany do tworzenia różnej maści programów od aplikacji webowych przez desktopowe, mobline a również gry komputerowe ze wsparciem języka Unity.

Platforma posia szeroką bibliotekę klas podstawowych umożliwającą interakcje z systemem operacyjnym, sprzętem wejscia-wyjścia, siecią, współbierznością czy bazą danych.

Kod źródłowy kompilowany jest na tak zwany język pośredni możliwy do wykonania przez CLR. Tutaj pomocny staje się JIT - just in time compilator w środowisku uruchomieniowym, który kompiluje język pośredni (IL - intermediate language) na kod maszynowy. Dzięki JIT kod nie jest kompilowany w całości na raz jednak tylko wtedy kiedy jest potrzebny, generuje to opóźnienia przy pierwszym wykonaniu danych metod jednak przyspiesza całościowe wykonanie.

##### Nowości techniczne .NET

Platforma niedawno przeszła unifikacje. Połączone zostały jej częsci .NET Framework oraz .NET core do zunifikowanej platformy .NET teraz będącą otwartoźródłową oraz multiplatformową w pełni. Kolejną nowością jest rozszerzenie platformy o kolejny element ułatwiający pracę .NET MAUI (Multi-platform App UI) łączący środowisko do tworzenia oraz testowania aplikacji na systemach Linux, Windows oraz wsparcie dla systemów firmy Apple.

#### Java / JVM

Jest to platforma programoawia obiektowego rozwijana przez firmę Oracle, umożliwia tworzenie aplikcji w kilku językach programowania. Działa na wspólnym środowisku uruchomieniowym JVM - Java Virtual Machine. Posiada automatyczne zarządzanie pamięcią, pełne wsparcie dla OOP i wieloplatformowość.

Platforma umożliwia pisanie w językach takich jak Java, Kotlin oraz Scala.

Kod źródłowy jest kompilowany na coś w rodzaju języka pośredniego zwanego bytecode następnie następuje ładowanie klas oraz weryfikacja poprawności potem przechodzi to do JIT gdzie kompilacja następuje wtedy kiedy jest potrzebna na kod maszynowy.

##### Nowości techniczne Java

W najnowszej wersji LTS Java wprowadza jedną z większych zmian z ostatnich lat jaką są wirtualne wątki dla JVM, niezależne od sytemu operacyjnego. Upraszcza to współbieżność oraz ułatwia skalowalność JVM.
Jedną z nowszych usprawnień jest również wprowadzenie tak zwanych sealed classes, czyli klas zamkniętych które mają ograniczenia co do dziedziczenia i dzięki temu zachowujemy większą kontrolę nad hierarchią oraz bezpieczeństwem typów.

## 4. Porównanie sieci LAN i WAN

### Co to jest sieć komputerowa?

Sieć komputerowa to zbiór składający się z co najmniej dwóch połączonych ze sobą urządzeń (komuter, drukarka, laptop, router), umożliwiając wymianę danych i współdzielanie zasobów za pomocą mediów transmisyjnych (przewodów lub Wi-Fi).

#### Podział sieci komputerowych

##### Zasięg geograficzny

1. Sieć LAN - Local Area Network - sieć komputerowa obejmująca niewielki obszar geograficzny, taki jak dom czy biuro, charakteryzuje się niskimi opóźnieniami oraz wysoką prędkością transmisji danych.
2. Sieć CAN - Campus Area Network - sieć łącząca pare sieci LAN zwykle w obrębie uczelni, fabryki lub dużej firmy gdzie potrzebne jest połaczenie paru budynków, zachowuje prędkości transmisji sieci LAN oraz niskie opóźnienia.
3. Sieć MAN - Metropolitan Area Network - sieć obejmująca obszar miasta albo aglomeracji, łączy ona sieci LAN oraz CAN wykorzystując głównie szybkie łącza światłowodowe poprowadzone po całych miastach. MAN zwykle jest używana przez firmy telekomunikacyjne oferujące możliwości transmisji danych oraz dostęp do Internetu.
4. Sieć WAN - Wide Area Network - sieć komputerowa obejmująca rozległy obszar geograficzny (kraj, kontynent), często łącząca ogromne ilości sieci LAN. Charakteryzuje się niższą prędkością transmisji danych i większymi opóźnieniami w porównaniu do LAN ze względu na odległości geograficzne oraz ilość urządzej pośredniczących w ruchu sieciowym.

Największą siecią WAN jest Internet, zrzeszający miliardy urządzeń umożliwiając wymianę danych oraz zasobów na całym świecie.

##### Topologia

1. Magistrala (bus) - wszystkie urządzenia są podłączone do jednego głównego kabla (tzw. magistrali lub szkieletu). Zaleta: łatwa budowa; Wada: awaria głównego kabla unieruchamia całą sieć.
2. Topologia pierścienia (ring) - urządzenia są połączone w zamknięty okrąg. Dane krążą w jednym kierunku, a każde urządzenie działa jak wzmacniacz sygnału.
3. Topologia siatki (mesh) - urządzenia są połączone ze sobą bezpośrednio na wiele sposobów. Wyróżniamy siatkę pełną (każdy z każdym) oraz częściową. Zapewnia wysoką bezawaryjność (redundancja połączeń).
4. Topologia gwiazdy (star) - najpopularniejsza obecnie topologia LAN. Wszystkie urządzenia są połączone za pomocą kabli z jednym centralnym punktem dostępu – przełącznikiem (switch) lub koncentratorem (hub). Zaleta: awaria jednego kabla nie wpływa na inne stacje; Wada: awaria centralnego urządzenia wyłącza całą sieć.

##### Technologia

1. Ethernet - najpopularniejsza, przewodowa technologia lokalnych sieci komputerowych (LAN), standaryzowana jako IEEE 802.3. Umożliwia stabilną, szybką transmisję danych (od 10 Mb/s do 100 Gb/s) między urządzeniami za pomocą kabli miedzianych (skrętka) lub światłowodów. Jest fundamentem infrastruktury sieciowej w biurach, serwerowniach i domach.
2. Wi-Fi - technologia bezprzewodowej łączności sieciowej, oparta na standardach IEEE 802.11, która umożliwia urządzeniom (komputerom, smartfonom, telewizorom, IoT) łączenie się z lokalną siecią (WLAN - Wireless LAN) oraz dostępem do Internetu za pomocą fal radiowych, bez konieczności stosowania kabli. Jest to obecnie wiodąca technologia bezprzewodowa, zarządzana przez organizację Wi-Fi Alliance.
3. Bluetooth - technologia bezprzewodowej komunikacji radiowej krótkiego zasięgu, która w kontekście sieci komputerowych funkcjonuje głównie jako technologia WPAN (Wireless Personal Area Network - bezprzewodowa sieć osobista). Umożliwia ona bezpośrednie połączenie między urządzeniami (ad-hoc) bez konieczności stosowania routerów czy punktów dostępowych, najczęściej w paśmie 2.4 GHz.

##### Model komunikacji

1. Klient-server - fundamentalna architektura sieciowa, w której klient (np. przeglądarka) wysyła żądanie o zasoby lub usługi, a serwer (maszyna o większej mocy) przetwarza je i odsyła odpowiedź. Komunikacja odbywa się w modelu żądanie-odpowiedź (request-response) przez protokoły takie jak HTTP, FTP czy SMTP.
2. Peer-to-Peer - rozproszona architektura, w której każde urządzenie (węzeł) działa jednocześnie jako klient i serwer. Uczestnicy bezpośrednio wymieniają zasoby (pliki, dane) bez centralnego serwera, co zwiększa niezawodność, skalowalność i autonomię użytkowników, a także eliminuje pojedyncze punkty awarii.

### Porównanie LAN i WAN

Porównanie dwóch rodzajów sieci o różniącym się zasięgu geograficznym można wykonać bazując na ich cechach oraz zastosowaniach.

Porównanie cech:

| Cecha          | LAN               | WAN              |
| -------------- | ----------------- | ---------------- |
| Zasięg         | lokalny           | globalny         |
| Prędkość       | bardzo wysoka     | niższa           |
| Opóźnienia     | niskie            | wysokie          |
| Koszt          | niski             | wysoki           |
| Własność       | jedna organizacja | wielu operatorów |
| Bezpieczeństwo | relatywnie łatwe  | złożone          |

Porównanie zastosowań:

| LAN                                             | WAN                                                 |
| ----------------------------------------------- | -----------------------------------                 |
| Połączenie komputerów w domu lub biurze         | Eduroam                                             |
| Udostępnianie zasobów lokalnych                 | Dostęp do Internetu                                 |
| Gry sieciowe lokalne                            | Komunikacja między siedzibami międzynarodowej firmy |

## 5. Metody dostępu do medium transmisyjnego w lokalnych sieciach komputerowych

### Definicja metody dostępu do medium

Metody dostępu do medium transmisyjnego to zasady i mechanizmy określające, w jaki sposób urządzenia w sieci lokalnej mogą korzystać ze wspólnego medium transmisyjnego, aby przesyłać dane.

Medium transmisyjne może być:

- przewodowe (skrętka, światłowód)
- bezprzewodowe (fale radiowe)

Ponieważ wiele urządzeń korzysta z tego samego medium, konieczne są mechanizmy kontrolujące:

- kto może nadawać w danym momencie
- jak unikać kolizji
- reakcje na konflikt transmisji

### Po co definiuje się metody dostępu?

Metody dostępu do medium transmisyjnego potrzebne są, aby:

- zapobiegać koliziom
- zapewnić sprawiedliwy dostęp do medium
- zwiększyć wydajność sieci
- zapewnić stabilość i porządek transmisji

Bez mechanizmów definiujących dostęp urządzenia nadawałyby jednoczenie powodując zakłucenia, kolizje oraz utratę danych.

### Klasyfikacja metod dostępu

Metody rywalizacyjne / losowe - urządzenia same decydują, kiedy nadawać. Może dojść do kolizji.

1. CSMA/CD (Carrier Sense Multiple Access with Colision Detection) - stacje nasłuchują medium transmisyjne przed nadaniem wiadomości, jeżeli jest wolne stacja rozpoczyna transmisję, jeżeli zostanie wykryta kolizja, urządzenie przerywa i ponawia transmisje po danym czasie. Metoda ta była stosowana w technologii Ethernet (half-duplex), przy obecnym full-duplex nie jest stosowana.
2. CSMA/CA (Colision Avoidance) - stacje nasuchują medium przed nadawaniem, jeżeli jest wolne wysłany zostaje sygnał rezerwacyjny (RTS - Request to Send), odbiorca odpowiada sygnałem (CTS - Clear to Send), stacja rozpoczyna transmisję po otrzymaniu sygnału CTS. Metoda jest dalej stosowana w sieciach bezprzewodowych takich jak Wi-FI, gdzie wykrwanie kolizji jest turdniejsze.

Metody deterministyczne / bezkolizyjne - Dostęp do medium jest ściśle kontrolowany dzięki temu kolizje nie występują. Stacje mają przydzielony czas lub kolejkę do nadawania.

1. Token passing - stacje są połączone w topologii pierścienia (ring), tylko stacja posiadająca aktualnie token może nadawać, po zakończeniu transmisji token przekazywany jest dalej. Metoda stosowana była w sieciach typu Token Ring.
2. Polling (odpytywanie) - stacje połączone są do urządzenia nadrzędnego, które cyklicznie sprawdza stan stacji podrzędnych i nadaje prawo transmisji. Metoda stosowana w sieciach o topologii gwiazdy działające w systemie host-terminal, gdzie urządzenie centralne jest przykładowo urządzeniem typu mainframe. Wi-Fi posiada swój zbliżony mechanizm PCF - Point Coordination Function, gdzie punt dostępu może przydzieli stacji czas nadawania (rzadko używany).
3. Time Division Multiple Access (TDMA) - metoda dostępu do medium, w której czas transmisji dzielony jest na równe szczeliny czasowe (time slots). Każdemu urządzeniu przydzielona jest konkretna szczelina czasu, w której może nadawać dane. Po zakończeniu cyklu szczeliny powtarzają się w ustalonej kolejności. Umożliwia to brak kolizji, stałe opóźnienie w transmisji oraz przewidywalny czas dostępu. Metoda stosowana w łączności satelitarnej oraz w sieciach o wysokiej jakości usług i gwarantowanym czasie transmisji.

### Wspólczesne sieci komputerowe

Nowoczesne sieci Ethernet wykorzystują miszane topologie działając w trybie full-duplex, co niweluje kolizje i sprawia że metody wykrywające kolizje stają się zbędne. W większości ruchem zarządzają również przełączniki. Co umożliwia pracę w trybie zbliżonym do bezkolizyjnego.

Sieci Wi-Fi nadal wykorzystują metodę CSMA/CA unikania kolizji i ich wydajność zależy od liczby urządzeń oraz ilości zakłuceń radiowych. W środowiskach o podwyższonej liczbie użytkowników metoda dostępu ma duży wpływ na jakość połączenia.

## 6. Infrastruktura klucza publicznego – architektura oraz sposoby wykorzystania

### Czym jest infrastruktura klucza publicznego (PKI - Public Key Infrastructure)

Infrastruktura klucza publicznego to zbiór technologii, procedur i polityk służących do zarządzania kluczami kryptograficznymi, certyfikatami cyfrowymi oraz zapewnienia poufności, integralności i uwierzytelniania w sieciach komputerowych.

#### Elementy infrastruktury

1. Urząd certyfikacji (CA - Certification Authority) - jest to najważniejszy element systemu, odpowiedzialny za wystawianie certyfikatów cyfrowych, podpisywanie ich własnym kluczem prywatnym, potwierdzanie tożsamości podmiotów.
2. Urząd rejestracji (RA - Registration Authority) - odpowiedzialny za weyfikacje tożsamości przed wystawieniem certyfikatu i następnie przekazanie informacji do CA.
3. Repozytorium certyfikatów - przechowuje wydane certyfikaty, udostępnia listy unieważnionych certyfikatów (CRL - Certificate Revocation List).
4. Certyfikat cyfrowy - Dokument elektroniczny łączący tożsamość z kluczem publicznym, podpisany przez CA.

Jest wiele urzędów certyfikacji oraz jeden nazywany głownym Root CA. Przeglądarki internetowe posiadają wbudowane listy urzędow certyfikacji.
Najczęsciej stotsowanym standardem certyfikatu jest X.509, standart ten wymusza zawarcie danych właściciela, klucza publicznego, oresu ważności certyfikatu oraz podpisu cyfrowego CA.

#### Zastosowania PKI

- Bezpieczeństwo stron internetowych potrzeby protokołu HTTPS - PKI umożliwia działanie protokołów TLS/SSL, zapewnia szyfrowanie połączeń, uwierzytelnienie serwera i integralność danych.
- Podpisy elektroniczne - infrastruktura daje możliwość podpisywania dokuemntów, werfikacje ich autora, jest wykorzystywany w Polsce w e-administracji, systemach bankowych oraz innych systemach rządowych.
- Szyfrowanie poczty elektronicznej - podpisywanie e-maili cyfrowo, szyfrownie treści. Ma to zastosowanie w systemach firmowych oraz (S/MIME - Secure/Multipurpose Internet Mail Extensions).
- Uwierzytelnianie w firmach - połączenia do VPN, Wi-Fi typu enterprice, logowanie bez haseł, autoryzacja urządzeń.
- Bezpieczeństwo urządzeń IOT - zabezpieczenie komunikacji maszyna do maszyny, identyfikacja urządzeń.

#### Zasada działania szyfrowania asymetrycznego

Szyfrowanie asymetryczne wykorzystuje parę kluczy: klucz publiczny i klucz prywatny. Klucz publiczny jest udostępniany innym użytkownikom, podczas gdy klucz prywatny jest przechowywany w tajemnicy przez właściciela.

Wiadomość zaszyfrowana kluczem publicznym może być odszyfrowana tylko za pomocą odpowiadającego klucza prywatnego i odwrotnie. Co umożliwia bezpieczną wymianę informacji, uwierzytelnianie nadawcy oraz zapewnienie integralności danych.

## 7. Podać różnice w implementacji obiektowości w kilku wybranych językach programowania

### Definicja programowania obiektowego

Programowanie obiektowe (OOP - object orientet programing) to paradygmat programowania, który organizuje kod wokół obiektów, które łączą dane i zachowania (metody) operujące na tych danych. Kluczowa idea to stan (dane) + zachowanie (metody) są połączone w jedną jednostkę - obiekt. Zawierają się też w tym klasy które są abstrakcyjnym opisem / szablonem tworzenia obiektów i zbiorem ich zachowań. Klasa zawiera też ewentualne realcje z innymi klasami.

#### Filary OOP

Abstrakcja - Ukrywanie złożoności obiektów poprzez defioniowanie interfejsów oraz klas.
Enkapsulacja (hermertyzacja) - Ograniczanie dostępu do danych obiektu, dostęp jedynie przez publiczne interfejsy. Kontrola oraz bezpieczństwo stanów.
Dziedziczenie - Tworzenie nowych klas na bazie istniejących, dziedzicząc ich metody oraz własności. Rozszerzalność funkcjonalności oraz współdzielenie kodu.
Polimorfizm - Możliwość użycia tych samych metod / zachowań dla różnych kontekstów.

#### Minusy programowania obiektowego

- trudności w współbierzności / równoległowości, możliwe przypadki "race condition" częściej niż w innych paradygmatach ze względu na większe współdzielenie
- złożoność hierarchiczna przy dziedziczeniu, możliwe głębokie i trudne w utrzymaniu hierarchie
- nadmierna abstrakcja, wielowarstwowość, trudny do zrozumienia kod
- większy koszt pamięciowy / wydajnościowy względem podejścia proceduralnego

### Implementacja obiektowości w klasyczynch językach OOP

#### Java

Charakterystyka:

- silne oraz statyczne typowanie
- praktycznie wszystko uważane jest jako obiekt
- podstawową jednostką abstrakcji klasa i jest ona obowiązkowa (abstrakcja) (pojedyńcze dziedziczenie)
- brak wielodziedziczenia klas, tutaj zastosowanie interfejs (abstrakcja) (dziedziczenie)
- kontrola dostępu (private, protected, public) (enkapsulacja)
- automatyczne zarządzanie pamiecią

#### C-sharp

Charakterystyka:

- silne, statyczne typowanie
- praktycznie wszystko uważane jest jako obiekt
- abstrakcja realizowana przez klasy oraz interfejsy (abstrakcja) (dziedziczenie)
- brak wielodziedziczenia klas
- kontrola dostępu (enkapsulacja)
- automatyczne zarządzanie pamiecią

### Implementacja obiektowości w językach wspierających OOP

#### C++

Charakterystyka:

- wsparcie dla programowania proceduralnego jak i obiektowego
- manualne zarządzanie pamięcią
- wielokrotne dziedziczenie klas - możliwy problem diamentu (rozwiązany słowem kluczowym virutal) (dziedziczenie) (abstrakcja)
- klasy wirutalne pełniące role interfejsów (dziedziczenie) (abstrakcja)
- statyczne typowanie
- przeciążanie operatorów (polimorfizm operatorów)
- kontrola dostępu (public, private) (enkapsulacja)

#### Python

Charakterystyka:

- dynamiczne typowanie
- wszystko jest obiektem
- wielodziedziczenie (problem diamentu rozwiązany MRO - Method Resolution Order)
- automatyczne zarządzanie pamięcią
- elsatyczne modele klaswowe
- brak kontroli dostępu (konwecja _nazwa jednak to nic nie blokuje)

## 8. Cykle życia oprogramowania (modele wytwarzania oprogramowania)

### Co to jest cykl życia oprogramowania?

Cykl życia oprogramowania (SDLC = Software Development Life Cycle) - to strukturalne podejście do tworzenia oprogramowania, obejmujące wszystkie etapy od początkowej koncepcji aż po wdrożenie i utrzymanie systemu informatycznego. Celem modeli wytwarzania oprogramowania jest uporządkowanie procesu, redukcja ryzyka, poprawa jakości końcowego produktu.

#### Podstawowe etapy cyklu życia oprogramowania

1. Analiza wymagań (Requirements) - określenie potrzeb, wymagań oraz efektów działania systemu
2. Projektowanie (Design) - architektura systemu, projekt wstępny
3. Implementacja/Tworzenie (Development) - na podstawie projektu oraz wymagań tworzenie systemu
4. Testowanie (Testing) - weryfikacja zgodności z wymaganiami oraz projektem, sprawdzenie poprawności działania
5. Wdrożenie (Deployment) - uruchomienie systemu w środowisku docelowym
6. Utrzymanie i rozwój (Maintenance) - utrzymanie systemu w stanie działjącym i wprowadzanie poprawek

### Modele wytwarzania oprogramowania

#### Model kaskadowy (waterfall)

Jest modelem liniowym gdzie każdy etap musi być zakończony przed rozpoczęciem następnego. Jest prosty i czytelny, łatwy do zarządzania i zapewnia dobrą dokumentacje. Sprawdza się w sytuacjach, kiedy wymagania sytemowe są stałe i jasno ustalone. Nie pozwala na powrót do wcześniejszych etapów, nie zapewnia elastyczności (jeżeli coś zostało ustalone tak będzie zrobione), błędy są wykrywane na późnym etapie życia, a niepoprawne założenia mogą zostać odkryte dopiero przy testach.

Prosta wizualizacja:
Requirements &rarr; Design &rarr; Development &rarr; Testing &rarr; Deployment &rarr; Maintenance

#### Model V (V-Model)

Jest to model rozwijający klasyczne podejście kaskadowe, naprawiając jego błędy związane z brakiem testów we wczesnych etapach. W tym modelu każdy etap projektowy ma odpowiadający mu etap testowy, dzięki czemu niweluje błędy przy założeniach czy projektowaniu systemu. Sprawdza się w systemach wymagających wysokiej niezawodności, przy systemach wbudowanych czy projektach przemysłowych ze względu na zwiększenie zaangażowania testerskiego.

Przykładowe działanie modelu etapami można opisać następująco.

Rozpoczynając pierwszą fazę czyli analizę wymagań po stonie testerskiej rozpoczynamy liczne przeglądy oraz analizy tych wymagań i budujemy na podstawie tego testy akceptacyjne.

Przechodząc do kolejnej fazy projektu systemu zespół ustala jak system będzie wyglądał jego struktura i jak będzie działał, strona testerska przeprowadza przeglądy i analizy, aby jak najnszybciej wyłapać błędy oraz buduje przypadki testowe do testów systemowych.

Następie w fazie projektu architektury zespół ustala techniczne oraz finansowe potrzeby, podział systemu na moduły i funkcje, a strona testerska przeprowadza przeglądy, analizy i buduje przypadki testowe do testów intergracyjnych.

W kolejnej fazie projektowania modułów zespół ustala wewnętrzny projekt dla każdego modulu, a strona testerska przeprowadza przeglądy, analizy i buduje testy jednostkowe.

W ostatniej fazie programistycznej następuje zbudowanie systemu zgodnie z wymogami oraz dokumentacją stworzoną w poprzednich etapach.

Następnie po zakończeniu tej fazy zespół testerski rozpoczyna testy od najmniejszych kawałków, zaczynając od testów modułowych/jednostkowych, następie testy integracyjne, testy systemowe a na koniec na środowisku docelowym przeprowadzane są testy akceptacyjne.

#### Model iteracyjny / przyrostowy

Jest to model bazujący na cyklach, iteracjach. Każda iteracja powinna dostarczać działjącą część systemu. System dzięki temu powstaje stopniowo. Zwiększa to jednak złożoność planowania i zarządzania takim projektem. Jednak umożliwia dostosowywanie się do zmiennych lub niejasnych wymagań systemowych, zapewnia wczesne testowanie każdej iteracji i zmniejsza ryzyko projektowe.

Wizulalizacja działania:
Przyrost 1: Plan &rarr; Design &rarr; Develop &rarr; Test &rarr; Działający inkrement / przyrost v1
&darr;
Przyrost 2: Plan &rarr; Design &rarr; Develop &rarr; Test &rarr; Działający inkrement / przyrost v2
&darr;
...Konytuacja aż system zostanie ukończony...
&darr;
Produkt końcowy - w pełni działjący system spełniający wszystkie wcześniejsze wymagania

#### Model zwinny (agile, scrum)

Model ten opiera się na krótkich iteracjach nazywanych sprintami, najczęsciej od tygodnia do czterech długosci. Zakłda częste dostarczanie działajacych elementów systemu i stałą współpracę z klientem. Daje dużą elastyczność, pozwala reagować na zmiany oraz dopasowywuje się do użytkownika końcowego. Załozenia nie muszą być znane od początku. Jednak przez to wymaga dużego zaangażowania klienta w budowe systemu, średnio skaluje się przy większych zespołach i nie jest w stanie podać jednoznaczenego harmonogramu prac. Jego zastosowania to projekty wymagające dużej elastyczności i szybkiego dostarczania wartości o zmiennych lub nieprecyzyjnych wymaganiach.

Kluczowe elementy tego modeulu (struktura 3-5-3):

Role (Scrum Team):

- Product Owner (Właściciel Produktu): Reprezentuje interesy klienta, definiuje wizję i zarządza priorytetami w Product Backlogu.
- Scrum Master: Wspiera zespół, dba o przestrzeganie zasad Scruma i usuwa przeszkody.
- Zespół programistyczny (Developers): Interdyscyplinarna grupa osób realizująca zadania w ramach sprintu.

Zdarzenia (Events - spotkania):

- Sprint: Iteracja (1-4 tygodnie), podczas której powstaje przyrost produktu.
- Sprint Planning (Planowanie): Określenie celów i zadań na nadchodzący sprint.
- Daily Scrum (Codzienne spotkanie): 15-minutowe spotkanie synchronizujące pracę zespołu.
- Sprint Review (Przegląd): Prezentacja wypracowanego przyrostu interesariuszom.
- Sprint Retrospective (Retrospektywa): Analiza minionego sprintu w celu ulepszenia procesu pracy.

Artefakty (Artifacts - efekty pracy):

- Product Backlog: Lista zadań i funkcji, uporządkowana przez Product Ownera.
- Sprint Backlog: Zbiór zadań wybranych na dany sprint.
- Increment (Przyrost): Gotowa, działająca część produktu po zakończeniu sprintu.

### Współczesne podejście

Obecniej najczęsciej stosowaną metodyką jest model zwinny, rozszerzony o podejście DevOps (itegracja dev - development [programowanie] z ops - operations [wdrażaniem]) dającą możliwości wprowadzenia systemu typu CI/CD - Continous Integration / Continous Deployment, umożliwiający ciągłą integracje zmian oraz wdrażanie ich.

### Porównanie modeli

| Model      | Elastyczność  | Ryzyko                        | Dokumentacja                   |
| ---------- | ------------- | ----------------------------- | ------------------------------ |
| Kaskadowy  | niska         | wysokie przy zmianach założeń | duża                           |
| V-Model    | niska         | kontrolowane                  | bardzo duża                    |
| Iteracyjny | średnia       | mniejsze                      | umiarkowana                    |
| Agile      | bardzo wysoka | niskie mimo zmian             | mniejsza (nie wpisana w model) |

## 9. Zasady modelowania dla konstrukcji relacyjnych baz danych

### Co to jest relacyjna baza danych?

Relacyjna baza danych to system przechowywania danych oparty na modelu relacyjnym, w którym dane są organizowane w postaci tabel składających się z wierszy i kolumn, a relacje między danymi realizowane są za pomocą kluczy.

Kluczowe cechy takiej bazy:

1. Dane przechowywane w tabelach
2. Jednoznaczna identyfikacja rekordów
3. Powiązania między tabelami
4. Operacje na danych wykonywane w języku zapytań (SQL)

Przykłady systemów zarządzania takimi bazami danych (SZBZ - System Zarządzana Bazą Danych, DBMS - Database Managment System):

- MySQL
- PostgreSQL
- Microsoft SQL Server (MSSQL)
- SQLite

## 10. Opis wybranej metodyki wytwarzania oprogramowania

### V-Model (model V)

Jest to model rozwijający klasyczne podejście kaskadowe, naprawiając jego błędy związane z brakiem testów we wczesnych etapach. W tym modelu każdy etap projektowy ma odpowiadający mu etap testowy, dzięki czemu niweluje błędy przy założeniach czy projektowaniu systemu. Sprawdza się w systemach wymagających wysokiej niezawodności, przy systemach wbudowanych czy projektach przemysłowych ze względu na zwiększenie zaangażowania testerskiego oraz dokumentacje na każdym etapie.

Przykładowe działanie modelu etapami można opisać następująco.

Rozpoczynając pierwszą fazę czyli analizę wymagań po stonie testerskiej rozpoczynamy liczne przeglądy oraz analizy tych wymagań i budujemy na podstawie tego testy akceptacyjne.

Przechodząc do kolejnej fazy projektu systemu zespół ustala jak system będzie wyglądał jego struktura i jak będzie działał, strona testerska przeprowadza przeglądy i analizy, aby jak najnszybciej wyłapać błędy oraz buduje przypadki testowe do testów systemowych.

Następie w fazie projektu architektury zespół ustala techniczne oraz finansowe potrzeby, podział systemu na moduły i funkcje, a strona testerska przeprowadza przeglądy, analizy i buduje przypadki testowe do testów intergracyjnych.

W kolejnej fazie projektowania modułów zespół ustala wewnętrzny projekt dla każdego modulu, a strona testerska przeprowadza przeglądy, analizy i buduje testy jednostkowe.

W ostatniej fazie programistycznej następuje zbudowanie systemu zgodnie z wymogami oraz dokumentacją stworzoną w poprzednich etapach.

Następnie po zakończeniu tej fazy zespół testerski rozpoczyna testy od najmniejszych kawałków, zaczynając od testów modułowych/jednostkowych, następie testy integracyjne, testy systemowe a na koniec na środowisku docelowym przeprowadzane są testy akceptacyjne.

#### Zaledy i wady tego modelu

##### Zalety

- dokumentacja na każdym etapie życia produktu
- łatwy w zarządzaniu, łatwe ustalenie jasnego harmonogramu prac
- wysoka dyscyplina działania, każdy z etapów wymaga zakończenia poprzedniego
- szybkie oraz dokładne testowanie na każdym etapnie, zaczynające się już od pierwszego dokumentu

##### Wady

- liniowość modelu znacząco utrudnia elastyczność, zmiana założeń ustalonych na wczesnych etapach wymaga sprawdzenia wszystkich innych etapów
- czasochłonność ze względu na liczne dokumentacje oraz testy na każdym etapie
- pierwsze działajace części systemu są gotowe dopiero po zakończeniu większości etapów

## 11. Rola i algorytmy mechanizmu szeregowania zadań w jądrze systemu operacyjnego

## 12. Modele barw w grafice komputerowej

## 13. Poziomy testowania w cyklu życia oprogramowania

## 14. Klasy języków programowania na wybranych przykładach

## 15. Zasady budowy interfejsów użytkownika systemów informatycznych

## 16. Techniki komunikacji międzyprocesowej

## 17. Główne techniki zwiększania wydajności współczesnych procesorów

## 18. Charakterystyka modeli przetwarzania w Internecie

## 19. Otwarte systemy agentowe: definicja, problemy konstrukcyjne i metody ich rozwiązywania

## 20. Metody pozyskiwania danych przestrzennych

## 21. Metody klasyfikacji obrazów satelitarnych

## 22. Zastosowania formalizmu i metod teorii grafów

## 23. Paradygmat programowania strukturalnego

## 24. Metody kompresji stratnej obrazów i dźwięku

## 25. Rodzaje filtrów oraz ich zastosowanie w przetwarzaniu obrazów
