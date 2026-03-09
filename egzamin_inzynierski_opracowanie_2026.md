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

|Klasa           |Opis złożoności      |Przykładowy algorytm w klasie                                     |
|-----------     |---------------------|---------------------------------------------------------------   |
|$$O(1)$$        |Stała                |Dostęp do elementu tablicy                                        |
|$$O(log_{n})$$  |Logarytmiczna        |Wyszukiwanie binarne [^1]                                         |
|O(n)            |Liniowa              |Przeszukanie tablicy element po elemencie                         |
|$$O(nlog_{n})$$ |Liniowo-logarytmiczna|Algorytmy typu dziel i zwyciężaj (merge sort)                     |
|$$O(n^{2})$$    |Kwadratowa           |Bubble sort (wynika z zagnieżdżenia dwóch pętli)                  |
|$$O(n^{3})$$    |Sześcienna           |Mnożenie macieży 2-wymiarowych                                    |
|$$O(2^{n})$$    |Wykładnicza          |Problem wież Hanoi (przeniesienie n krążków to $$2^n - 1$$ ruchów)|
|$$O(n!)$$       |Silnia               |Generowanie permutacji zbioru                                     |

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
| Przeszukiwanie grafu w głąb (DFS)   | $$O(V \cdot E)$$     | $$O(V)$$       |

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
| Przeszukiwanie grafu w szerz (BFS)  | $$O(V \cdot E)$$  | $$O(V)$$       |

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
| A*                          | $$O(E \cdot log_{V})$$             | $$O(V)$$   |
| Dijkstra                    | $$O((V + E)log_{V})$$ $$O(V^{2})$$ | $$O(V)$$   |

#### Tablicje asocjacyjne (hash table/map) (słowniki)

Struktura przechowująca pary klucz-wartość, wykorzystująca funkcję haszującą do wyznaczania klucza/indeksu dla danych.

Podstawowwe operacje na tablicy asocjacynej:

| Operacja                                   | Złożoność czasowa    |
| ------------------------------------------ | ----------------     |
| Dostęp po kluczu                           | $$O(1)$$             |
| Wstawienie                                 | $$O(1)$$             |
| Usuwanie                                   | $$O(1)$$             |
| Ponowne hashowanie                         | $$O(n)$$             |

Algorytmy bazujące na tablicach asocjacyjnych:

| Algorytm                                 | Złożoność czasowa      | Pamięciowa     |
| -----------------------------------      | -----------------      |--------------- |
| Grupowanie anagramów (k - długość słowa) | $$O(nk \cdot log_{k})$$| $$O(n)$$       |
| Dwa elementy których suma = X            | $$O(n)$$               | $$O(n)$$       |

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

Java 8 - interfejsy funkcjonalne oraz lambda.

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
4. Topologia gwiazdy (star) - najpopularniejsza obecnie topologia LAN. Wszystkie urządzenia są połączone za pomocą kabli z jednym centralnym punktem dostępu - przełącznikiem (switch) lub koncentratorem (hub). Zaleta: awaria jednego kabla nie wpływa na inne stacje; Wada: awaria centralnego urządzenia wyłącza całą sieć.

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

## 6. Infrastruktura klucza publicznego - architektura oraz sposoby wykorzystania

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

#### C&num;

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

### Dlaczego modeluje się bazy?

Modelując baze danych staramy się uzyskać strukturę tabel oraz zależności, tak aby dane były spójne i jednoznaczne, logicznie uporządkowane, pozbawione redundancji, łatwe do utrzymania i rozwoju. Modelowanie bazy odbywa się przed implemetacją takiej bazy w jednym z sytemów zarządzania.

### Zasady

1. Zasada jednoznacznej identyfikacji (klucz główny) - każda tabela powinna posiadać swój klucz główny który jednoznaczenie identyfikuje każdy rekord, nie może on być NULLem, powinien być stabilny (niezmienny po utworzeniu rekordu). Przykłady: id_klienta, numer_zamowienia.
2. Zasada minimalnej redundancji (normalizacja) - celem tej zasady jest eliminacja powialania się danych, zmniejszenie ryzyka niespójności, ułatwienie aktualizacji danych oraz zapobieganie anomaliom (wstawiania, usuwania, modyfikacji). Ta zasada ma w sobie tak zwane formy normalne:
    - 1NF - wartości atomowe (niepodzielne)
    - 2NF - brak zależności częściowych (wszystkie atrybuty niekluczowe muszą zależeć od całego klucza podstawowego a nie tylko jego części)
    - 3NF - brak zależności przechodnich (tabele nie mogą między sobą być w relacji przechodniej [A -> B, B -> C to C -> A])
3. Zasada integralności danych - zapewnia spójność danych w bazie
    - integralność encji - klucz główny nie może być NULL
    - integralność referencyjna - klucz obcy musi wskazywać istniejący rekord w tabeli nadrzędnej
    - integralność dziedzinowa - wartości muszą być zgodne z określonymi typami i zakresami
    - ograniczenia unikalności - wartości muszą być unikalnem, jedna tabela jeden typ obiektu

### Etapy modelowania bazy danych

Wyróżniamy trzy etapy modelowania:

1. Model pojęciowy / koncepcyjny (ERD - Entity-Relationship Diagram) - diagram związków, atrybutów i encji
2. Model logiczny - tabele, klucze i zależności
3. Model fizyczny - implementacja w systemie zarządzania, typy danych, indeksowanie i optymalizacja

#### Model pojęciowy / koncepcyjny

Zrozumienie co ma być przechowywane, bez wchodzenia w technikalia implementacji. Zwykle realizowane przez diagram encjowo-relacyjny. Nie wchodzimy tutaj w typy danych, ani to jakim kluczem powiązane są tabele tylko przykładowo "klient składa zamówienie".

Podstawowe elementy:

- Encje - obiekty świata rzeczywistego (klient, zamówienia), tabele
- Atrybuty - cechy encji (numer_zamowienia, imie_klienta), kolumny
- Relacje - powiązania między encjami

##### Rodzaje relacji

- 1:1 (jeden do jednego)
- 1:N (jeden do wielu)
- N:M (wiele do wielu) - wymaga tabeli pośredniczącej (asocjacyjnej)

#### Model logiczny

Przejście z modelu pojęciowego na opis struktur, która będzie zgodna z teorią baz, tutaj dbamy o normalizacje i definujemy klucze. Określamy nazwy kolumn i ogólne typy przykładowo to będzie jakiś tekst. Zamieniamy tutaj relacje typu wiele do wielu na tabele oraz tabele asocjacyjną (łączącą).

#### Model fizyczny

Tutaj kończy się teoria, przechodzimy z wcześniej opisanej logiki na konkretny system zarządzania bazą danych, biorąc pod uwagę jego zalety, wady, ogarniczenia. Celem tego etapu jest implementacja i optymalizacja. Przechodzimy też z specyfiki typów "jakiś tekst" na VARCHAR(255) lub TEXT, zamiast "liczba" to INT, BIGINT. Szacujemy, które kolumny będą najczęściej przeszukiwane aby je indeksować i przyspieszyć bazę. Tutaj też definiujemy ogaraniczenia dla atrybutów przykładowo UNIQUE - wymaganie unikatowych danych.

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

### Czym jest szeregowanie zadań?

Szeregowanie zadań (CPU scheduling) to mechanizm systemu operacyjnego polegający na wyborze procesu lub wątku, który w danym momencie otrzyma dostęp do procesora (CPU).

Jest to podstawowa funkcja jądra systemu operacyjnego, realizowana przez tzw. scheduler. Scheduler to część jądra systemu operacyjnego odpowiedzialna za wybór procesu/wątku, który otrzyma CPU, przełączanie kontekstu między procesami, zapewnienie sprawiedliwego podziału czasu procesora, optymalizację wydajności i responsywności systemu.

### Dlaczego potrzebne jest szeregowanie zadań?

Szeregowanie jest potrzebne, ponieważ procesor może w danym momencie obsłużyć jeden wątek (procesor jednordzeniowy) lub jeden wątek na rdzeń (procesor wielordzeniowy). Jednocześnie w systemie działa wiele procesów, które potrzebują dostępu do procesora. Scheduler decyduje, co wykona się teraz i jak długo, kiedy nastąpi przełączenie.

### Cele mechanizmu szeregowania

- maksymalne wykorzystanie CPU
- minimalizację czasu oczekiwania procesów
- szybkie reakcje systemu (responsywność)
- obsługę wielu procesów jednocześnie (wielozadaniowość)
- realizację priorytetów procesów
- przewidywalność w systemach czasu rzeczywistego

### Stany procesów w systemach operacyjnych

#### Model 5-stanowy

Wyróżna 5 różnych stanów procesu:

- new
- ready
- running
- waiting
- terminated

Przejścia między stanami oraz ich przyczyny:

| Z jakiego stanu | Do jakiego | Co powoduje przejście                     |
| --------------- | ---------- | ----------------------------------------- |
| New             | Ready      | utworzenie procesu zakończone (admission) |
| Ready           | Running    | przydział CPU przez scheduler             |
| Running         | Waiting    | żądanie I/O / oczekiwanie na zdarzenie    |
| Waiting         | Ready      | zakończenie I/O / zdarzenie wystąpiło     |
| Running         | Ready      | wywłaszczenie (koniec kwantu czasu)       |
| Running         | Terminated | zakończenie procesu                       |

#### Model 7-stanowy

Wyróżnia 5 stanów z poprzedniego modelu oraz dwa dodatkowe:

- new
- ready
- running
- waiting
- terminated
- ready suspended
- blocked suspended

Przejścia między stanami nie opisanymi w poprzednim modelu:

| Z jakiego stanu   | Do jakiego        | Co powoduje przejście               |
| ----------------- | ----------------- | ----------------------------------- |
| Ready             | Ready Suspended   | brak pamięci RAM (swap out)         |
| Waiting           | Blocked Suspended | brak pamięci RAM                    |
| Ready Suspended   | Ready             | przywrócenie do RAM (swap in)       |
| Blocked Suspended | Waiting           | przywrócenie do RAM                 |
| Blocked Suspended | Ready Suspended   | zakończenie I/O podczas zawieszenia |

### Wywłaszczanie

Wywłaszczanie to mechanizm, w którym system operacyjny może przerwać wykonywanie aktualnego procesu i przydzielić CPU innemu procesowi, nawet jeśli ten pierwszy nie zakończył jeszcze swojej pracy.

#### Jak działa wywłaszczanie?

System operacyjny wykorzystuje zegar systemowy. Bazując na tym zegarze działa tak zwane przerwanie (interrupt). Dzieli ono czas na kwanty, które określają fragmenty czasu procesora. Podczas przerwania obecne procesy tracą swój czas procesora a scheduler wybiera jaki proces otrzyma teraz dostęp.

#### Dlaczego jest potrzebne wywłaszczanie?

Proces wywłacszczania umożliwa sprawiedliwy podział czasu procesora, szybkie regowanie na zdarzenia (kliknięcie przycisku myszy), obsługę priorytetyzacji procesów w trakcie trwania innych procesów. Bez wywłaszczania proces mógłby zajmować CPU dowolnie długo, system mógłby być mało responsywny, a aplikacje interaktywne wydawałyby się zbyt wolne.

### Algorytmy szeregowania zadań

#### FCFS (First Come, First Served)

Bardzo prosty algorytm zakładający że pierwszy proces nie zależnie od czasu wykonania jest wykonywany jako pierwszy. Jego główną zaletą jest prostota jednak posiada wady zależne od długości wykonywanych procesów. Jeżeli pierwszy proces jest bardzo długi a kolejne krótkie to długi proces potrafi zablokować te krótkie, powstanie tak zwany efekt konwoju. Ten algorytm jest uważany za mało responsywny.

#### SJF (Shortest Job First)

Algorytm zakładający, że procesy z najkrótszym czasem wykonania mają pierwszeństwo wykonania. Minimalizuje to średni czas oczekiwanian na wykonanie, jednak jego wadą jest wymóg znajomości czasu wykonania oraz ryzyko zagłodzenia długich procesów jeżeli krótkie ciągle dochodzą.

#### Round Robin (RR)

Algorytm pracujący na kwantach czasu. Każdy proces otrzymuje z góry ustalony kawałek czasu po jego upłynięciu następuje przełączenie i inny proces dostaje kwant czasu. Ten algorytm zakłada sprawiedliwość i jest uważany za dobry dla systemów wymagających responsywności i interaktywności. Jego wady mogą wynikać z doboru kwantów czasu. Jeżeli kwant czasu będzie zbyt krótki przełączanie kontekstu procesora jest większe, a zbyt długi kwant zmniejsza responsywność systemu.

#### Szeregowanie priorytetowe

Algorytm zakładający priorytetyzacje każdego procesu. Im wyższy priorytet tym wcześniej zostanie wykonany proces. Umożliwia realizacje ważnych zadań o wiele wcześniej. Jednak posiada ryzyko zagłodzenia procesów o niskim priorytecie. Ta wada jest jednak możliwa do załagodzenia mechanizmem podnoszenia priorytetów dla starszych procesów (aging).

#### Rozwiązania wielopoziomowe

##### Kolejki wielopoziomowe (Multilevel Queue Scheduling,  Multilevel Feedback Queue)

Procesy podzielone są na różne kolejny według ich kategorii. Każda kolejka może mieć własny algorytm szergowania przykładowo RR dla interaktywnych żeby zachować responsywność a FCFS dla wsadowych. Umożliwa to różnorodność i dopasowanie algorytmów do typu procesu jaki będą obsługiwać. Jednak zwiększa to złożoność całości.

Oprócz powyższego mechanizmu znany jest również multilevel feedback queue polegający na większej adapcyjności do zachowania procesów. Dany proces może zmienić kolejke w zależności od jego czasu wykonania albo tego jakie elementy wejścia-wyjścia musi użyć. Jego wadą jest wysoka złożoność implementacji i zarządzania.

## 12. Modele barw w grafice komputerowej

Model barw to matematyczny sposób opisu koloru za pomocą zestawu liczb (składowych).
Definiuje on, jak reprezentować kolor w systemie komputerowym lub urządzeniu. Kolor w informatyce nie jest „barwą” samą w sobie - jest wektorem liczb w określonej przestrzeni. Różne modele barw są używane w różnych kontekstach, takich jak wyświetlanie na ekranie, drukowanie czy przetwarzanie obrazów.

### Model RGB (Red, Green Blue)

Jest to addytywny model barw, polegającym na dodawaniu składowych światała aby uzyskać dany kolor. Brak jakiejkolwiek barwy (0,0,0) jest kolorem czarnym, a maksimum we wszystkich składowych to biały (255,255,255). Zawiera 3 składowe zawarte w nazwie, kolory czerowny, zielony i niebieski. Standatrdowo każdy znich ma zakres 8 bitów (0-255). W grafice komuterowej najczęsciej jest to model zapisu obrazu rastrowego. Najczęsciej wykorzystywany jest w ekranach (monitory, telewizory, telefony). Ten model dostał również rozszerzenia. Tak zwany RGBA to model RGB rozszerzony o kanał Alfa oznaczający przezroczystość oraz rozszerzenie wartości na 16 lub 32 bity na kanał w grafice profesjonalnej.

### Model CMYK (Cyan, Magenta, Yellow, Key (black))

Jest to subtraktywny model braw, polegający na pochłanianiu światla zamiast dodawania. Kolory są tworzone przez mieszanie składowych cyjan, magenta oraz żółty, a dzięki dodatkowej składowej jako czarny jest stworzony idealnie do druku.

### Model HSL/HSV (Hue, Saturation, Lightness / Value)

Jest to model opartny na percepcji ludzkiego oka. Baazuje na trzech składowych odcień (hue) - określa kolor na wykresie kołowym 0-360, nasycenie (saturation) 0-100% definiuje jak bardzo nasycony jest dany kolor, jasność/wartość (lightness/value) 0-100% określa jak jasny jest ten kolor. Wykorzystywany jest głównie w projektowaniu interfejsów użytkownia, czy w przetwarzaniu obrazów (przykładowo sprawdzenie czy zdjęcie ma kolor czerwony nie zależnie od cieni).

### Model YCbCr (Luma, Chorma blue, Chroma red)

Model który jest bardzi uważany za podmodel RGB. Został stworzony jako ukłon dla oszczędności danych. Jest on często wykorzystywany w produkcji wideo. Dzięki niemu filmy na platformach VOD działają płynnie przy minimalnych prędkościach łączy. Polega na rozdzieleniu jasności oraz koloru wykorzystując wadę ludzkiego oka. Człowiek świetnie rozróżnia jasność jednak detal w kolorze jest problemem. Ten model jest idealny do kompresji danych ze względu na możliwość samplowania kanałów. Można przykładowo przesłać pełny kanał janości a dla koloru tylko część. Pozwala na różne poziomy kompresji zależnie od propocji przekazania kanałów.

### Konwersja między modelami barw

Jest możliwa konwersja między modelami barwowymi, ale przez cechy każdego z modeli bardzo łatwo stracić niektóre informacje. Przejścia typu CMYK &rarr; RGB &rarr; CMYK nigdy nie dają efektu początkowego. Aby zachować wybrany kolor najlepiej korzystać z modelu w którym był wybrany.

## 13. Poziomy testowania w cyklu życia oprogramowania

### Poziomy testowania

Okreslają na jakim etapie i jaką część oprogramowania sprawdzamy. Każdy poziom skupia się na innych częściach i szuka innych błędów. Definiuje się 4 podstawowe poziomy testów w cyklu życia oprogramowania.

#### Testy jednostkowe (Unit testing)

Ten poziom skupia się na najmniejszych fragmentach oprogramowania. Sprawdza konkretne moduły, metody, klasy. Polega na sprawdzeniu czy dany pojedyńczy element działa poprawnie będąc wyizolowanym od reszty oprogramowania. Na tym poziomie testów zwykle stosowana jest technika białoskrzynkowa (white-box testing), polegająca na analizie kodu pod różnymi kątami. Uwzględnia analizę statyczną, testy pokrycia instrukcji lub gałęzi. Często są automatyzowane i wykonywane przez programistów ze względu na ich prostote oraz niewielki zakres. Ich celem jest wyeliminowanie błędów logicznych, warunków czy brzegowych przy zakresach. Czesto pozwalają też wykryć martwy lub zbędny kod oprogramowania (warunki, które nigdy nie zachodzą).

#### Testy integracyjne (Integration Testing)

Ten poziom skupia się na testowaniu czy najmniejsze moduły współpracują ze sobą poprawnie, sprawdzane są interfejsy i przepływy danych. Czasami sprawdzane są również integracje systemów, które są rozdzielone w danym oprogramowaniu przykładowo czy baza danych poprawnie zapisuje dane wpisane przez interfejs lub przekazane z innej części systemu. Przy testach integracji modułów jest wykorzystywana technika białoskrzynkowa tak jak w testach jednostkowych. Czesto ten poziom testów rozdzielany jest na itegracjen modułów oraz integracje systemów, gdzie pierwszy typ wykonują również programiści, a drugi typ testerzy. Głownie polega na wykrywaniu błędów komunikacji między modułami/systemami, coś może działać samodzielnie natomiast w parze z innym modułem już nie.

#### Testy systemowe (System Testing)

Ten poziom zawiera w sobie testy całegop systemu. Zwykle jest wykonywany przez zespół testerski. Opiera się na wymaganiach funkcjonalnych oraz niefunkcjonalnych. Najczęściej na tym poziomie testuje się technikami czarnoskrzynkowymi (black-box testing), polega to na testach systemu bez wglądu w kod oprogramowania, zakładając system jako czarna skrzynia, która ma się zachować zgodnie z założeniami. Przy testach funkcjonalnych bazuje na scenariuszach biznesowych, przypadkach użycia lub na samych wymaganiach funkcjonalnych. Przy testach niefunkcjonalnych sprawdzamy wydajność, bezpieczeństwo, niezawodność oraz kompatybilność z różnymi urządzeniami uruchomieniowymi. Na tym poziome wykrywamy różne rodzaje błędów ze względu na duży zakres testów.

#### Testy akceptacyjne (Acceptance Testing)

Ten poziom zwykle jest ostatnim krokiem przed oddaniem systemu do użytku przez użytkownika końcowego. Sprawdza czy system jest w pełni zgodny z oczekiwaniami użytkownika końcowego, czy działa na środowisku docelowym oraz czy jest gotowy do użycia. Zależnie od użytkownika końcowego wykonywany jest przez klienta, zespół testerski lub product ownera. Sprawdza scenariusze biznesowe systemu, historie użytkownika, zgodności elementów z ustaleniami oraz pełne procesy operacyjne.

### Testy wykonywane na różnych poziomach

Testy te nie są uzależnione od danych poziomów testowania.

#### Retesty (confirmation testing, retesting)

Po zgloszeniu awarii lub defektu na jednym z poziomów musi zostać on poprawiony. Zazwyczaj zgłaszający dostaje poprawiony element do tak zwanytch retestów. Ponownego sprawdzenia tego samego scenariusza lub działania po wprowadzonych poprawkach. Przy przeglądach lub analizach statycznych samo ponone sprawdzenie czy poprawka została wprowadzona w kodzie / dokumencie jest również uważana za retest.

#### Testy regresyjne (regression testing)

Tak jak retesty odnoszą się do sprawdzania elementów oprogramowania po wprowadzeniu poprawek lub po wprowadzeniu nowych funkcjonalności, czy kolejnego elementu integrującego się z poprzednimi. Podczas progresowania z rozbudową lub naprawianiem oprogramowania przypadkowo można doprowadzić do regresu / regresji. Testy te mają wykryć czy w częsciach lub systemach, które wcześniej działały poprawnie nie pojawiły się awarie bądź defekty. Regresja występuje tylko wtedy jeżeli przykładowo dany przypadek testowy nie wykazał błędów a po dalszych zmianach w systemie ten sam przypadek wykrył błąd.

## 14. Klasy języków programowania na wybranych przykładach

### Po co języki programowania są klasyfikowane?

Języki programowania są klasyfikowane według różnych kryteriów, aby można było zrozumieć możliwości oraz ogarniczenia każdego z nich i porównać sposoby tworzenia oprogramowania. Mając takie informacje możemy łatwiej dobrać język programowania do problemu, który chcemy rozwiązać.

### Klasyfikacja języków programowania

#### Paradygmaty programowania

- programowanie obiektowe - opiera się na obiektach, które łącza dane i metody w klasy. Kluczowe cechy to hermetyzacja, dziedziczenia i polimorfizm. Przykłady: Java, C&num;
- programowanie proceduralne - opiera się na procedurach lub funkcjach (zbiorze procedur) wykonywanych sekwencyjnie. Przykłady: C, Pascal
- programowanie funkcyjne - program opartny na funkcjach zwykle matematycznych, zwykle nie powoduje zmiany danych. Zamiast pętli korzysta z rekurencji. Przykład: Haskell

#### Poziomy abstrakcji

- niskiego poziomu - języki te charakteryzują się bliskim działaniem ze sprzętem i bezpośrednią jego kontrolą. Cechują się wysoką wydajnością jednak są zależne od architektury sprzętu. Przykłady: Asembler, Embedded C (jako podzbiór C), C (manualne zarządzanie pamięcią)
- wysokiego poziomu - zapewniają wysoką abstrakcje i łatwość programowania, bardziej zbliżone do języka naturalnego, automatycznie zarządzają pamięcią i zasobami systemowymi. Łatwe w przenoszczeniu (działają prawie na każdym sprzęcie) Przykłady: Python, Java, C&num;

#### Typowanie

- satyczne - typy zmiennych są określane podczas kompilacji kodu. Przykłady Java, C++, C&num;
- dynamiczne - typy zmiennych określane są podczas wykonania programu. Przykłady Python, JavaScripy

#### Sposób wykonania

- kompilowalne - kod źródłowy tłumaczony jest na kod maszynowy przed uruchomieniem programu. Przykłady C, C++, Java, C&num;
- interpretowalne - kod źródłowy wykonywany jest przez interpreter języka. Przykłady Python, JavaScript

## 15. Zasady budowy interfejsów użytkownika systemów informatycznych

### Co nazywamy interfejsem użytkownika?

Interfejs użytkownika (UI - user interface) to warstwa systemu informatycznego, umożliwiająca komunikację między użytkownikiem a oprogramowaniem, prezentuje dane oraz umożliwia wykonanie akcji. Może to być graficzny interfejs (GUI - graphical user interface), interfejs tekstowy, terminal (CLI - command line interface), czy rozwinięcie graficznego o gesty przykładowo w interfejsach na smartfonach. Jakość takiego interfejsu bezpośrednio wpływa na jego użyteczność, efektywność oraz satysfakcje z użycia.

### Zasady użyteczności Jacoba Nielsena (Heurystyki Nielsena)

#### Stan systemu powinien być widoczny (Visibility of system status)

Użytkownik powinien być zawsze informowany o tym, co się dzieje w danej chwili. Paski ładowania czy inne animacje, komunikaty, podświetlanie sekcji menu, w której użytkownik przebywa oraz informowanie szczególnie przy płatnościach o każdym etapie.

#### Zgodność systemu z rzeczywistościa (Match between system and the real world)

Interfejs użytkownika powinien korzystać z języka zrozumiałego dla użytkownika. Wykorzystywać proste zwroty jak kosz na usunięte rzeczy. Unikanie języka technicznego jest tutaj plusem nie minusem. Zamiast błędu 404 "not found" lepiej przetłumaczyć to na każdy język, który system wykorzystuje i napisać „Nie znaleziono strony”.

#### Kontrola i swoboda użytkownika (User control and freedom)

Użytkownik powienien mieć możliwość cofnięcia każdej jego operacji (undo), czy anulowania działań lub powrotu krok do tyłu. Brak takich możliwości powoduje poczucie braku kontroli.

#### Standardy i spójność (Consistency and standards)

Interfejs powinien być przewidywalny, zgodny z konwencjami branżowymi (typu umiejscowienie menu). Powinien zawierać jednolitą terminologię i dane elementy powinny działać tak samo na każdym widoku.

#### Zapobieganie błędom (error prevention)

Interfejs użytkownika powinien być programowany tak, aby zapobiegać błędom. Znacznie łatwiej jest zapobiec pomyłkom niż je odwrócić. Potwierdzenia przez usunięciem, czy walidacja pól formularza przed wysłaniem zamiast samo wyświetlanie komunikatu błędu przed wysłaniem. Dezaktywacja przycisku, gdy dane nie zostały wpisane lub są niepoprawne. Listy rozwijane zamiast pól tekstowych tam, gdzie się da.

#### Rozpoznawanie/pokazywanie zamiast przypominania (Recognition rather than recall)

Interfejs powinien minimalizować wymóg obciążenia pamięci użytkownika. Wszystkie opcje oraz informacje powinny być ekpsonowane na ekranie tam gdzie są potrzebne. Jeżeli użytkownik musi wpisać swoje dane przy składaniu zamówienia pokażmy mu je ponownie na koniec, aby nie musiał cofać się lub pamiętać czy dobrze wpisał.

#### Elastyczność i efektywność użytkowania (Flexibility and efficiency of use)

Interfejs powinien być prosty do użycia przez początkujących jednak wydajny dla zaawansowanych użytkowników. Przykładowo skróty klawiszowe dla przyspieszenia pracy, prosta personalizacja interfejsu oraz automatyczne uzupełnianie danych.

#### Estetyka i minimalizm (Aesthetic and minimalist design)

Aby interfejs był prosty i przyjazny w użyciu należy zadbać aby nie miał zbędnych elementów rozpraszających oraz rywalizujących o uwagę użytkownika. Każdy dodatkowy element może zwiększyć obciążenie poznawcze. Należy unikać nadmiaru kolorystycznego oraz przeładowania ekranu.

#### Pomoc w rozpoznawaniu i naprawianiu błędów (Help users recognize, diagnose, and recover from errors)

Jeżeli pojawia się błąd należy go zakomunikować użytkownikowi jasno i prezejżyście w prostym języku oraz z sugestią rozwiązania. Zaleca się unikać informacji typu "Error 0x80004005" i zastępować je jasnym opisem: "Nie można zapisać pliku - brak uprawnień. Sprawdź ustawienia dostępu".

#### Pomoc i dokumentacja (Help and documentation)

Nawet jeżeli system jest intuicyjny i prosty, czasami potrzebna jest pomoc. Systemy i interfejsy powinny oferować łatwo dostępną pomoc, dokumentacje i odpowiedzi na często zadawane pytania. Dokumentacja powinna być wpełni zorientowana na użytkownika i jasno opisywać działanie.

### Skrócony opis

Interfejs użytkownika powinien być prosty oraz minimalistyczny. Powinien zawierać tyko niezbędne elementy jasno pokazane na ekranie. Powinien być spójny na każdym widoku lub spójny z platformą na której pracuje. Jednolitość kolorystyczna, czcionkowa oraz przewidywalne działanie elementów interaktywnych. Stan systemu powinien być zawsze widoczny i pokazujący co się dzieje w danym czasie oraz czy zakończyło się to sukcesem czy błędem. Interfejs powinien zwracać jak najwięcej informacji na akcje użytkownika, podświetlanie przycisków, komunikaty o błędach, animacje sugerujące działanie. Interfejs powinien zapobiegać błędom, walidowanie pól formularzy, ograniczenie możliwości wprowadzenia błędów oraz potwierdzanie operacji krytycznych jak usuwanie. Czytekność, dostępność i ergonomia - intefejs powinien być dostępny i czytelny dla każdego, powinien zawierać logiczne rozmiezczenie elementów oraz dostosowanie do ekranu na którym jest wyświetlany.

## 16. Techniki komunikacji międzyprocesowej

### Komunikacja międzyprocesowa (IPC - Inter-Process Communication)

Komunikacja międzyprocesowa to mechanizmy systemu operacyjnego umożliwiające wymianę danych oraz synchronizację między niezależnymi procesami. Procesy są izolowane w przestrzeni adresowej pamięci, dlatego IPC jest niezbędne do współpracy aplikacji. Główne cele IPC to przesyłanie danych, koordynacja pracy procesów, zapewnienie spójności i bezpieczeństwa oraz zwiększenie wydajności systemu wieloprocesowego.

### Techniki IPC

#### Mechanizmy oparne na przesyłaniu komunikatów

##### Potoki (pipes)

Jest to jednokierunkowy kanał komunikacji, najczęsciej stosowany między procesami spokrewnionymi. Są popularne w systemach operacyjnych UNIX/Linux i dzielą się na nazwane oraz nienazwane. Nienazwane potoki działają głównie między procesem rodzicem a potomnym. Za to potoki nazwane umożliwiąją komunikację między dowolnymi procesami i są zdefiniowane w systemie plików. Jest to bardzo prosty mechanizm jednak ograniczony do komunikacji jednkierunkowej bez użycia większej ilości potoków.

##### Kolejki komunikatów (Message Queues)

Asynchroniczny sposób wymiany informacji. Proces może zarejestrować kolejkę w menadżerze kolejek, na której będzie nasłuchiwał przychodzących wiadomości, oraz wysyłać wiadomości na kolejki innych procesów. Wiadomości będą czekać w kolejce aż do odczytania. Różne implementacje określają limit „czasu życia” wiadomości oraz limit wiadomości w kolejce. Zaltą tego rozwiązania jest brak potrzeby synchronizacji jednak wadą jest ograniczenie rozmiaru komunikatów.

##### Gniazda (Sockets)

Gniazdo jest pojęciem abststrakcyjnm rezprezentującym dwukierunkowy punkt końcowy połączenia. Umożiwiają komunikacje między procesami poprzez sieć jak i lokalnie. Wykorzystują protokoły sieciowe takie jak TCP czy UDP. Działają w modelu klient-serwer. Najczęściej są wykorzystywane w aplikacjach sieciowych lub do komunikacji między różnymi systemami.

#### Mechanizmy oparne na współdzielaniu pamięciu

Pamięć współdzielona (shared memory) to najszybsza metoda IPC. Kilka procesów korzysta z tej samej puli pamięci. Jej minusy to potencjalne problemy z bezpieczeństwem skoro jeden proces ma dostęp do pamięci drugiego oraz wymóg synchornizacji korzysając z mechanizmów synchronizacji.

##### Mechanizmy synchronizacji

Semafory - mechanizm synchronizacji dostępu do zasobów wspóldzielnych. Wyróżnia się semafory binarne oraz zliczające. Stosowane są aby zapobiegać zakleszczeniom (deadlock). Chociaż nie zawsze są w stanie to zrobić - problem ucztujących filozofów. Semafor jest kontrolą dostępu wspierającą współdzielanie zasobów takich jak pamięć.

#### Sygnały

Jedna z najstarszych metod IPC używanych w systemach Unix. Sygnały używane są do powiadamiania procesu o asynchronicznych wydarzeniach. Procesy mogą określać sposób, w jaki obsługują dany sygnał, lub pozwolić systemowi zająć się jego obsługą. Przykłaty to SIGINT, SIGKILL.

## 17. Główne techniki zwiększania wydajności współczesnych procesorów

### Procesor (CPU - Central Procesing Unit)

Główny układ komputera odpowiedzialny za wykonywanie instrukcji programu oraz sterowanie pracą całego systemu. Realizuje operacje arytmetyczne, logiczne i kontrolne sekwencyjnie pracując zgodnie z zegarem. Jego głownymi parametrami jest taktowanie zegara wyrażane współcześnie w GHz, liczba rdzeni, liczba wątków oraz wielkości pamięci cache różnych poziomów.

### Współczesne sposoby optymalizacji w porównaniu do hisorycznych

Kiedyś najprostrzym sposobem zwiększenia wydajności procesora było zwiększanie częstotliwości takotania zegara do ograniczeń fizycznych, energetycznych i termalnych tematych czasów. Kolejnym sposobem było zwiększanie liczby tranzystorów w procesorze, jednak prawo Moore'a znacznie zwolniło ze względu na zbliżenie się do granic fizycznych i wielkości atomowych.

Obecnie większość procesorów pracuje blisko swoich limitów energetycznych i termalnych, mają nawet mechanizmy zapobiegające przegrzewani blokujące moc procesora przy danej temperaturze (przykładowo 95 stopni). Przez to też nastapiło przejście na optymaizacje opierające się głownie na równolegowości i wykonaniu instruckji sprzętowo oraz logicznie zmieniając architekturę i organizacje wykoania.

### Techniki zwiększania wydajności

#### Techniki zrównoleglania wykonywania instrukcji (ILP - Instruction-level parallelism)

##### Potokowość (pipelineing)

Jest to podział wykonywania instrukcji na etapy podstawowe (fetch, decode, execute, write back). Każdy z tych etapów jest wykonywany niezależnie, więc pozwala to na przetwarzanie wielu instrukcji na raz z przesunięciem o jeden etap. Zwiększa to przepustowość pod kątem instrukcji na jednostkę czasu.

```markdown
I1: F D E W
I2:   F D E W
I3:     F D E W
```

##### Wykonywanie poza kolejnością (Out-of-Order Execution)

Jest to wykonywanie instrukcji nie trzymając się kolejności w programie, a uzależniając kolejność wykonywania od dostępności danych. W efekcie lepsze wykorzystanie jednostek wykonawczych i zmniejszenie opóźnień.

##### Przewidywanie skoków (branch prediction)

Procesor przewiduje wynik instrukcji warunkowych. Pozwala na kontynuowanie potokowanie bez czekania na wynik skoku. Zmniejsza czas wykonania instrukcji skoku. Jednak błędna predykcja może spowodowac spadek wydajności.

##### Very Long Instruction Word (VLIW)

Procesory składające się z kilku (zwykle czterech lub ośmiu) jednostek obliczeniowych. Po normalnej kompilacji programu, kompilator VLIW porządkuje kod na ścieżki, które wprost nie posiadają jakichkolwiek zależności. Następnie są one dzielone na cztery lub więcej części (jeden dla każdej jednostki obliczeniowej CPU) i pakowane razem w większe instrukcje z dodatkową informacją odnośnie do jednostki, na której ma być wykonywana.

#### Wielordzeniowość i wielowątkowość

##### Wielordzeniowość (multi-core)

Prawdziwa równoległość zadaniowa, procesor posiada wiele rdzeni i każdy z nich może wykonywać osobne zadanie.

##### Wielowątkowość

Każdy fizyczny rdzeń procesora potrafi obsługiwać dwa wątki jednocześnie korzystając z podziału fizycznych rdzeni na dwa logiczne. Firma AMD tą technologię nazwała SMT - Simultaneous Multithreading, natomiast Intel posiada swój odpowienik nazywający się HT - Hyper-Threading.

#### Pamięć podręczna (Cache)

Hierarchicznie strukturyzowana pamięć typu SRAM (statyczna, nieulotna) o którtkim czasie dostępu. Zlokalizowana bespośrednio w procesorze. Umożliwia ona zmniejszenie czasu dostępu do najważniejszych danych. Dzięki niej procesor może przechować część danych w zdecydowanie szybszej pamięci, niż wysyłać je do RAMu.
Wyróżniamy trzy poziomy pamięci cache:

1. L1 cache - pamięć podręczna pierwszego poziomu, zwykle znajduje się fizycznie bezpośrednio obok rdzenia proesora, działa z prędkością procesora przechowując najważniejsze intrukcje / dane.
2. L2 cache - poziom drugi, zwykle zlokalizowany wewnątrz układu procesora ale poza rdzeniem, wolniejsza niż L1, ale dalej szybsza niż RAM, funkcjonuje jako bufor pamięciowy między L1 a L3 lub RAM.
3. L3 cache - poziom trzeci, zwykle zlokalizowana również na układzie procesora, ale wspólna dla wszystkich jego rdzeni, najwolniejsza z pamięci podręcznych, jednak wciąż o wiele szybsza niż RAM, synchronizuje ona działanie rdzeni i przechowuje dane, które nie zmieściły się w L2 lub L1.

#### Turbo/boost mode

Wraz ze zwiększeniem liczby rdzeni jednak brakiem wielordzeniowości aplikacji pojawił się problem poboru mocy takich procesorów z tego powodu też pierwsze wielordzeniowe procesory miały niższe taktowanie. Rozwiązaniem stało się wyłączanie nieużywanych rdzeni i wykorzystanie mocy na podniesienie taktowania rdzenia, który tego wymaga.

## 18. Charakterystyka modeli przetwarzania w Internecie

### Czym są modele przetwarzania?

Modele przetwarzaia w Internecie są to opisy spsobów rozmieszczania zasobów obliczeniowych, komunikacji między nimi oraz podziały odpowiedzialności za przetwarzanie danych. Te modele przechodziły różne ewolucje związane z rozwojem całej sieci jaką jest teraz Internet, wzrostem liczby użytkowników i zapotrzebowaniem na wydajność i skalowalność.

### Model klient-serwer

Najbardziej klasyczny model przetwarzania w Internecie. Występują w nim dwa typy urządzeń klient oraz serwer.

Urządzenie typu klient wysyła zapytania do serwera o udostępnienie jakiegoś zasobu danych, a jego zadaniem jest prezentacja tych danych lub proste przetwarzanie części aplikacyjnych.

Urządzenie typu serwer zwykle cechuje się dużą wydajnością aby przetwarzać dane, sprawdzać czy klient może mieć dostęp oraz wysyłać je na prośby wielu klientów jednocześnie.

Zaletą takiego rozwiązania jest centralne zarządzanie danymi, łatwa kontrola dostępu oraz admnistracja, jednak posiada też wady. Skalowalność tego modelu jest ogarniczona jeżeli nie chcemy zwiększać ilości urządzeń typu serwer, a awaria jednego z takich urządzeń lub jedynego może doprowadzić do utraty usługi.

Przykłady korzystające z tego rozwiązania to poczta elektroniczna, repozytoria plików lub struktura WWW.

#### Model chmury obliczeniowej (Cloud Computing)

Model chmurowy jest rozwinięciem modelu klient-serwer zeskalowanym na potrzeby wielu różnych usług. Zwykle cechuje się ogromną ilością serwerów zawartych w centrach danych i modelowanych tak, aby dynamicznie dzieić się mocą obliczeniową tam gdzie jest potrzebna. Jest to dalej model klient-serwer gdzie klientem zwykle jest urządzenie końcowe typu przeglądarka a serwery posiadają aplikacje i bazy danych.

Zalety tego rozwiązania to elastyczność, wielka skala możliwa do podziału, redukcje kosztów infrastruktury, dostępność z dowolnego miejsca, a wadami tego rozwiązania jest kompletna zależność od dostawcy usług serwerowych (zarządzających centrami, serwerowniami) oraz problem prywatności i bezpieczeństwa takich serwerów.

Przykładami zastosowania tego modelu są usługi typu SaaS (Software as a Service) oprogramownie jako usługa lub aplikacje internetowe. Przykładowo google workspace (gmail, docs, drive).

### Model peer-to-peer (P2P)

Model zapewniający działanie typu równy z równym. Każde urządzenie w tym modelu może pracować jako klient oraz jako serwer. Nie ma centralizacji, komunikacja odbywa się bezpośrednio między urządzeniami.

Zaletami tego rozwiązania jest wysoka skalowalność, kazdy nowy klient jest również serwerem, odporność na awarie całości usługi oraz efektywne wykorzystanie zasobów wielu urządzeń. Jednak istniją również wady tego rozwiązania. Ciężko zarządzać taką siecią, nie jesteśmy w stanie zagwarantować bezpieczeństwa każdego z urządzeń oraz jakość usług jest zmienna.

Najczęstrze zastosowanie takiego rozwiązania to udpostępnianie plików. Przykładowo BitTorrent. Komunikator Skype na wczesnych etapach swojego rozwoju opierał się na P2P do obsługi swoich rozmów.

### Model przetwarzania rozproszonego

W tym modelu zadania obliczeniowe są podzielone między wiele, urządzń pracujących w tej samej sieci. Duże zadanie jest dzielone na mniejsze części i równolegle wykonywane przez wiele urządzeń. Zasada działania jest zbliżona do jednego logicznego organizmu. Nie ma tutaj centralnego zarządzania.

Zaletami tego rozwiązania jest odporność na awarię, łatwa skalowalność oraz duża wydajność obliczeniowa, jednak posiada też wady. Pojawiają się opóźnienia wynikające z komunikacji sieciowej tych urządzeń oraz trudna jest synchronizacja danych między dużą ilością urządzeń

Najczęstrze zastosowanie takiego modelu to wyszukiwarki internetowe, systemy finansowe i bankowe oraz symulacje naukowe.

#### Model edge computing

Jest rozszerzeniem przetwarzania rozproszonego jednak przy założeniu, że obliczenia wykonywane są najbliżej miejsca powstania danych. Jak nazwa wskazuje na tak zwanej "krawędzi sieci". Zamiast rozsyłać dane do innych części sieci wykonywane są na danych urządzeniu lub na paru najbliższych.

Zaletami tego roziwązania są mniejsze opóźniania niż w bazowym modelu, ograniczenie ruchu sieciowego. Wady tego rozwiązania to ograniczenie mocy obliczeniowej.

Zastosowania to autonomiczne pojazdy lub internet rzeczy (IoT - Internet of Things).

## 19. Otwarte systemy agentowe: definicja, problemy konstrukcyjne i metody ich rozwiązywania

### System agentowy

System agentowy to system informatyczny składający się z jednego lub wielu agentów, które działają autonomicznie w określonym środowisku, postrzegają je za pomocą mechanizmów percepcji oraz podejmują działania w celu realizacji określonych zadań lub celów. Agenci w takim systemie mogą komunikować się, współpracować lub konkurować ze sobą, a ich zachowanie jest zazwyczaj oparte na regułach, wiedzy lub mechanizmach podejmowania decyzji.

### Otwarty system agentowy (OMAS - Open Multi-Agent System)

Otwarte systemy agentowe to systemy informatyczne składające się z wielu autonomicznych agentów, którzy mogą dołączać do systemu, opuszczać go oraz wchodzić w interakcje z innymi agentami bez pełnej kontroli jednego centralnego podmiotu i w trakcie działania systemu.

Agent to autonomiczny podmiot, posiadający zdolności percepcyjne, decyzyjne i wykonawcze. Cechuje go samodzielność, zdolność do reakcji na zmiany w otoczeniu, zdolność do komunikacji z innymi agentami.

Przykładowe zastosowania takiego systemu to wyszukiwanie informacji w sieci, zarządzanie sieciami telekomunikacyjnymi, różnego rodzaju symulacje - rynku, ruchu czy innych rzeczy.

### Główne problemy konstrukcyjne

#### Koordynacja agentów

Agenci realizują własne cele, działania mogą się wzajemnie blokować.

Rozwiązanie: protokoły negocjacji, kontrakty (Contract Net Protocol),mechanizmy konsensusu.

#### Komunikacja między agentami

Brak wspólnego języka, różne protokoły i formaty danych.

Rozwiązanie: wspólne języki komunikacyjne, formalne protokoły interakcji.

#### Bezpieczeństwo i zaufanie

Agenci mogą działać nieuczciwie lub być złośliwi.

Rozwiązanie: mechanizmy reputacji, systemy certyfikatów, monitorowanie zachowań.

#### Skalowalność

Wzrost liczby agentów zwiększa złożoność, ryzyko przeciążenia komunikacji.

Rozwiązanie: hierarchiczne struktury, podział na grupy, lokalne interakcje.

#### Konflikty i sprzeczne cele

Agenci mogą mieć cele sprzeczne z innymi agentami.

Rozwiązanie: mechanizmy rozwiązywania konfliktów, mediacja, negocjacje.

#### Tabela podsumowująca

| Problem      | Metoda rozwiązania       |
| ------------ | ------------------------ |
| Koordynacja  | protokoły negocjacji     |
| Komunikacja  | standaryzacja            |
| Zaufanie     | reputacja                |
| Skalowalność | architektura rozproszona |
| Konflikty    | mediacja                 |

## 20. Metody pozyskiwania danych przestrzennych

### Dane przestrzenne

Dane przestrzenne (geograficzne) to dane opisujące położenie, kształt oraz właściwości obiektów znajdujących się na powierzchni Ziemi lub w przestrzeni geograficznej. Umożliwiają one określenie, gdzie dany obiekt się znajduje oraz jakie posiada cechy.

Dane przestrzenne są wykorzystywane głównie w systemach informacji geograficznej (GIS), kartografii, geodezji, planowaniu przestrzennym oraz nawigacji.

### Przechowywanie danych przestrzennych

W systemach informacji geograficznej (GIS) dane przestrzenne mogą być zapisywane w dwóch podstawowych modelach: rastrowym i wektorowym. Modele te określają sposób przedstawiania obiektów i zjawisk występujących na powierzchni Ziemi.

#### Model rastrowy

Model rastrowy przedstawia przestrzeń w postaci regularnej siatki komórek (pikseli). Każda komórka ma określony rozmiar i zawiera jedną wartość opisującą cechę danego fragmentu powierzchni. Dokładność danych jest ściśle powiązana z rodzielczością rastra.

Zaletami tego rozwiązania jest prosta struktura danych, dobre odwzorowanie zjawisk ciągłych takich jak wysokość czy temperatura oraz łatwe wykonywanie analiz przestrzennych. Jednak przy dużej dokładności czyli przy wysokiej rozdzielczości pliki robią się bardzo duże, granice obiektów nie są idealnie odwzorowane ze względu na podział komórkowy oraz obiekty liniowe mają podobny problem jak granice.

#### Model wektorowy

Model wektorowy przedstawia obiekty przestrzenne za pomocą figur geometrycznych opisanych współrzędnymi. Podstawowymi elementami tego modelu są punkty, które reprezentują obiekty o małych rozmiarach. Linię, które reprezentują obiekty wydłużone przykładowo drogi czy linie energetyczne. Poligony (obszary), które reprezentują obiekty poiwerzchniowe przykładowo działki, czy granice administracyjne.

Zaletami tego rozwiązania jest bardzo dokładne odwzorowanie kształtów obiektów i ich granic, mniejsze rozmiary plików przy danych obiektowych oraz łatwe powiązanie z bazą danych zawierającą atrybuty terenu. Jednak jest to bardziej złożona struktura danych, będąca bardziej skomplikowana do analizy powierzchniowej oraz przedstawienia zjawisk ciągłych.

#### Porównanie modeli w tabelce

| Cecha             | Model rastrowy                     | Model wektorowy                |
| ----------------- | ---------------------------------- | ------------------------------ |
| Sposób zapisu     | siatka komórek (piksele)           | punkty, linie, poligony        |
| Typ zjawisk       | ciągłe (np. temperatura, wysokość) | obiekty o wyraźnych granicach  |
| Dokładność granic | niższa                             | bardzo wysoka                  |
| Rozmiar danych    | często duży                        | zwykle mniejszy                |
| Zastosowania      | teledetekcja, modele terenu        | mapy geodezyjne, sieci drogowe |

### Pozyskiwanie danych

#### Pomiary terenowe (bezpośrednie)

Polega na zbieraniu danych bezpośrednio w terenie przy użyciu specjalistycznych urządzeń pomiarowych. Znane też jako pomiary geodezyjne. Wykorzystują takie narzędzia jak tachimetry lub niwelatory. Cechują się bardzo wysoką dokładnością pomiaru i bezpośrednim kontaktem z obiektem mierzonym. Dane zwykle zapisywane sa jako dane wektorowe. Stosowane często w budownictwie lub kartografii.

#### Systemy GNSS / GPS [^2]

[^2]: GNSS - Global Navigation Satellite System - zbiór globalnych systemów nawigacji satelitarnej. Obejmuje amerykański GPS, europejski Galileo, rosyjski Glonass oraz chiński BeiDou, zapewniając większą dokładkość niż sam GPS.
GPS - global positioning system - stworzony przez departamet obrony stanów zjednoczonych, system do wyzaczania położenia użytkownika i ułatwiania nawigacji.

Globalne systemy satelitarne umożliwiające szybkie pozywskiwanie współżęnych. Cechują się szerokim zasięgiem działania, wysoką moblinością oraz relatywnie niskimi kosztami operacyjnymi. Ograniczone są przez warunki atmosferyczne, zakłucenia sygnałów czy przeszkody terenowe takie jak lasy czy budynki. Najczęściej wykorzystywane są do nawigacji.

#### Fotogrametria

Jest to technika pozyskiwania precyzyjnych informacji przestrzennych o obiektach i terenie na podstawie zdjęć (lotniczych, naziemnych, satelitarnych). Pozwala na zdalne tworzenie modeli 3D, ortofotomap [^3] i chmur punktów. Najczęsciej zapisywana w modelu rastrowym, ale jest możliwość stworzenia wektorywch danych. Wykorzystywana jest między innymi w geodezji, budownictwie i archeologii.

[^3]: Ortofotomapa - cyfrowa (rastrowa) mapa powstała z przetworzonych zdjęć lotniczych lub satelitarnych, która dzięki specjalnej obróbce (ortorektyfikacji) eliminuje zniekształcenia i jest odwzorowana w rzucie ortogonalnym (prostopadłym do ziemi), co pozwala na precyzyjne pomiary odległości, powierzchni i kątów.

#### Teledetekcja

Technika pozyskiwania danych bazująca na bezkontaktowym zbieraniu informacji o obiektach, zjawiskach czy obszarach za pomocą sensorów umieszczonych na satelitach, samolotach czy dronach. Sensory (kamery, skanery, radary - mikrofalowe skanowanie, lidary - laserowe skanowanie) rejestrują promienowanie, które nie jest dostępne dla ludzkiego oka przykłądowo podczerwień. Co pozwala na wykrycie różnych cech obiektów. Zaletom tego rozwiązania zwykle jest wysoka precyzja w czasie rzeczywistym, jednak operacja z takim sprzętem wiąże się zwykle z dużymi kosztami uzyskania i potem przetwarzania danych. Przykładowo chmura punktów z LiDAR [^4] wymaga potężnych mocy obliczeniowych do dlaszego przetwarzania.

[^4]: LiDAR - Light Detection and Ranging, działą na zasadzie radaru wykorzystując wiązki laserowe, pozwalając na dokładne określenie kształtów i odległosci.
RaDAR - Radio Detection and Ranging.

#### Dane wtórne oraz digitalizacja

Polega na pozyskiwaniu danych z istniejących źródeł, takich jak papierowe dokumenty czy mapy, lub rozproszone bazy danych zawierające informacje geograficzne. Recznie lub automatycznie digitalizowane są mapy oraz dokumenty fizyczne uzupełniając bądź tworząc nowe warstwy informacji w systemach GIS.

### Aktualne podejście

Współcześnie systemy GIS często łączą różne metody pozyskiwania oraz przechowywania danych przestrzennych, aby uzuskać peły oraz coraz bardziej dokładny obraz rzeczywistości.

## 21. Metody klasyfikacji obrazów satelitarnych

Klasyfikacja obrazów satelitarnych polega na przypisywaniu pikselom obrazu określonych klas tematycznych na podstawie ich właściwości spektralnych. Dzięki temu możliwe jest rozpoznanie różnych typów pokrycia terenu, takich jak lasy, woda, zabudowa czy pola uprawne. Obrazy satelitarne składają się z wielu pikseli, z których każdy zawiera informację o odbitym promieniowaniu w różnych zakresach spektrum elektromagnetycznego. Analiza tych wartości pozwala określić, jaki typ powierzchni reprezentuje dany piksel.

### Podział metod klasyfikacji

- Klasyfikacja nadzorowana - wymaga danych treningowych dla algorytmów rozpoznawania.
- Klasyfikacja nienadzorowana - algorytm rozpoznawania działa bez danych treningowych.
- Klasyfikacja obiektowa - analiza grup pikseli tworzących obiekty zamiast pojedyńczych pikseli.

#### Klasyfikacja nadzorowana

Klasyfikacja nadzorowana polega na tym, że użytkownik wskazuje przykładowe obszary należące do określonych klas pokrycia terenu. Na tej podstawie algorytm uczy się rozpoznawać podobne piksele na całym obrazie.

Przykładowe algorytmy działające na podstawie danych testowych od użytkownika to metoda największego prawdopodobieństwa (maximum likelihood) i minimalna odległość (minimum distance).

Zaletami tego rozwiązania jest większa kontrola nad wynikiem klasyfikacji oraz wyższa dokładność jednak wymaga przygotwania danych treningowych i wiedzy o analizowanym obszarze.

#### Klasyfikacja nienadzorowana

Klasyfikacja nienadzorowana polega na automatycznym grupowaniu pikseli o podobnych właściwościach spektralnych bez wcześniejszego wskazywania klas przez użytkownika. Algorytm sam tworzy grupy pikseli (tzw. klastry), które następnie są interpretowane przez użytkownika.

Przykładowe algorytmy stosowane w tej klasyfikacji to K-means oraz ISODATA.

Zaletami tego rozwiązania jest brak potrzeby danych treningowych i szybkie przetwarzanie dużych zbiorów danych, jednak klasy powstałe w wyniku tej analizy nie zawsze odpowiadają rzeczywistości i wymagają dodatkowej interpretacji przez użytkownika.

#### Klasyfikacja obiektowa

W klasyfikacji obiektowej najpierw przeprowadza się segmentację obrazu na jednorodne obiekty, a następnie klasyfikuje się całe obiekty zamiast pojedynczych pikseli. Wykorzystuje się nie tylko cechy spektralne, ale również teksturę, kształt czy relacje przestrzenne. Podejście to jest szczególnie efektywne przy obrazach wysokiej rozdzielczości, na przykład z satelitów takich jak Sentinel-2 czy Landsat 8.

Zaletami tego rozwiązania jest lepsza interpretacja złożonych struktur i redukcja szumów, jednak wymaga to segmentacji obrazu oraz jest bardziej złożona obliczeniowo.

#### Uczenie głębokie / maszynowe

Obecnie coraz większe zainteresowanie mają metody oparte na uczeniu maszynowym, wykorzystujące sieci neuronowe, które automatycznie uczą się relacji klas z danymi.

Zaletą tego rozwiązania jest wysoka skuteczność automatycznego klasyfiktowania, jednak wymaga dużych zbiorów danych w celu nauki oraz znaczynhcb zasobów obliczeniowych.

## 22. Zastosowania formalizmu i metod teorii grafów

### Teoria grafów

Teoria grafów to dział matematyki i informatyki badający struktury składające się z wierzchołków (ang. vertices) oraz krawędzi (edges) łączących te wierzchołki zwanych grafami.

#### Podstawowe typy grafów

- grafy proste - brak pętli (krawędzi prowadzącej do tego samego wierzchołka), brak krawędzi wielokrotnych
- multigrafy (grafy złożone) - może zawierać pętle, może zawierać krawędzie wielokrotne
- grafy skierowane - kierunek krawędzi ma znaczenie
- grafy nieskierowane - kierunek krawędzi nie jest oznaczony (nie ma znaczenia)
- grafy ważone - krawędzie mają przypisane wagi (koszty, odległości)
- grafy nieważone - krawędzie nie mają przypisanych wag
- grafy cykliczne - zawierają w sobie cykle (zamknięta droga taka że ostatni wierzchołek jest tym samym co pierwszy)
- grafy acykliczne - nie posiadające cyklu
- drzewa - specjalny rodzaj grafu acyklicznego
- grafy spójne - każda para wierzchołków jest połączona jakąś scieżką
- grafy niespójne - nie każda para wierzchołków posiada ścieżkę

### Formalizm grafów

Formalizm w teorii grafów to sposób przedstawiania rzeczywistych sytuacji za pomocą abstrakcyjnych struktur, takich jak zbiory punktów (wierzchołków) i łączących je linii (krawędzi). Pozwala na modelowanie relacji, analizę zależności i optymalizację rozwiązań.

### Metody teorii grafów

Metody to systematyczne procedury i algorytmy opracowane w celu rozwiązywania konkretnych problemów optymalizacyjnych i strukturalnych w tych grafach. Kluczową cechą dobrych metod (algorytmów) jest ich efektywność, co oznacza, że liczba kroków potrzebnych do rozwiązania problemu jest ograniczona funkcją wielomianową względem liczby wierzchołków i krawędzi.

### Zastosowania

#### Nawigacja

Tutaj grafy formalizują problemy nawigacji między wieloma miastami, skrzyżowaniami (wierzchołkami) czy innymi punktami i ich połączeniami (krawędziami). Wykorzytując grafy skierowane, nieskierowane, i często ważone. Pojawia się tutaj znany problem najkrótszej ścieżki między dwoma wierzchołkami, dokładniej przy grafach ważonych tam gdzie suma wag krawędzi jest minimalna.

Znanymi metodami rozwiązującymi te problemy jest algorytm Dijkstry, który krokowo buduje drzewo najkrótszych ścieżek, etykietując wierzchołki ich aktualną odległością od źródła. Bardziej zaawansowaną wersją jest algorytm A*, który wykorzystuje heurystykę (szacowanie pozostałego dystansu), aby przeszukiwać graf bardziej efektywnie w kierunku celu.

Przykład systemów wykorzystujących takie rozwiązania aktualnie jest to Google Maps, które korzysta głównie z algorytmu A* jednak nie wykluczając algorytmu Dijkstry. System przetwarza miliony danych w czasie rzeczywistym uzwlędniając ruch drogowy oraz historyczne wzorce, ważąc trasy pod kątem czasu przejazdu.

#### Sieci komputerowe

Formalizując sieci komputerowe na grafach definujemy urządzenia jako wierzchołki i krąwędzie jako połączenia sieciowe między nimi. Wykorzystywane są tutaj grafy nieskierowane do modelowania połączeń fizycznych. Grafy skierowane do modelowania przepływów danych. Grafy ważone jako kolejny etap przykładowo fizycznych połączeń, gdzie waga jest opóźnieniem, odległością, kosztem przesyłu. Wykorzystywane są tutaj również drzewa w takich protokołach jak STP (Spanning Tree Protocol), aby eliminować pętle w sieciach Ethernet.

Znanymi metodami używanymi w sieciach jest również algorytm Dijkstry wykorzystywany w protokołach RIP oraz OSPF, aby znajdować najkrótsze ścieżki połączeń fizycznych między dwoma użądzeniami. Wykorzystywane są również algorytmy znajdujące minimalne drzewa rozpinające takie jak Kruskal czy Prim do zapobiegania cyklom.

Przykładami systemów wykrorzystujących te roziwązania w sieciach to przełączniki (switch) w sieciach komputerowych gdzie wykorzystywane są algorytmy minimalnych drzew rozpinających jako protokół STP czy jego rozwinięcia. Kolejnym przykładem są routery gdzie wykorzystywane są algorytmy najkrótszych scieżek w protokołach RIP oraz OSFP.

#### Relacje społeczne

Relacje społeczne można formalizować z wykorzystaniem grafów. Osoby stają się wierzchołkami a relacja jest krawędzią. Stopień wierzchołka jest liczbą znajomych takiej osoby a ścieżki pozwalają zdefiniować znajomych znajomych i definiować osobiste sieci kontaktów.

#### Oddzielanie substacji chemicznych, które reagują między sobą w magazynie

Firma chemiczna musi przechowywać substancje w przedziałach tak, aby niekompatybilne związki (które mogłyby wybuchnąć przy kontakcie) znajdowały się osobno. Buduje się graf, gdzie wierzchołkami są chemikalia, a krawędzie łączą te, które ze sobą reagują. Liczba chromatyczna tego grafu określa minimalną liczbę bezpiecznych przedziałów potrzebnych w magazynie. Formalizm kolorowania grafów tutaj był pomocny.

## 23. Paradygmat programowania strukturalnego

### Czym jest programowanie strukturalne?

Paradygmat programowania strukturalnego to sposób tworzenia programów komputerowych polegający na organizowaniu kodu w uporządkowaną, logiczną strukturę z wykorzystaniem jasno określonych konstrukcji sterujących. Celem tego podejścia jest zwiększenie czytelności, łatwości utrzymania oraz niezawodności programów.

Pojawił się jako odpowiedź na problemy wynikające z chaotycznego używania instrukcji skoków bezwarunkowych typu "goto", które utrudniały analizę i rozwój.

Cechy tego paradygmatu:

- Brak lub silne ograniczenie instrukcji goto
- Podział programu na procedury i funkcje
- Hierarchiczną strukturę kodu (stos wywołań)
- Modularność (każdy moduł (funkcja) realizuje określone zadanie)

### Podstawowe struktury sterujące

1. Strukura sekwencyjna (sekwencja)
Instrukcje wykonwywane są jedna po drugiej w ustalonej kolejności.
2. Struktura warunkowa (selekcja)
Pozwala na wykonanie różnych fragmentów programu w zależności od spełnienia warunku.
3. Struktura iteracyjna (pętla)
Umożliwia wielokrotne wykonywanie tych samych instrukcji.

### Zalety oraz ograniczenia programowanie strukturalnego

Zalety:

- Wysoka czytelność
- Łatwe debugowanie
- Dobra podstawa do nauki programowania
- Logiczny przepływ sterowania

Ogarniczenia:

- Słabe wsparcie dla bardzo dużych systemów,
- Brak naturalnego modelowania obiektów świata rzeczywistego,
- Trudniejsza rozbudowa bez dodatkowych paradygmatów.

Wszystkie ogarniczenia rozwiazane zostały przez inne paradygmaty dlatego też większość współczesnych języków jest wieloparadygmatowa.

### Języki wykorzytujące ten paradygmat

- C (jeżeli unikane jest goto)
- Python (pisany tylko nieobiektowo lub wewnątrz metod)
- Java (wewnątrz metod)

Kontrprzykładem jest Asembler, który posiada pełne wsparcie skoków bezwarunkowych.

## 24. Metody kompresji stratnej obrazów i dźwięku

### Czym jest kompresja stratna?

Kompresja stratna to technika redukcji rozmiaru plików multimedialnych (obrazów, dźwięków) poprzez usunięcie części informacji, które są mniej istotne dla ludzkiej percepcji. Stratna w tym przypadku ponieważ nieodwracalnie rezygnujemy z części danych, efektem zmniejszając rozmiar pliku.

Wyróżniamy też kompresje bezstratną, która nie traci żadnych danych, jednak zmniejsza wielkość pliku nieznacznie.

### Ograniczenia percepcji u człowieka

Wzork człowieka jest bardzo precyzyjnym urządzeniem, jednak ma swoje ograniczenia. Składa się z około 120 milionów pręcików, które są wrażliwe na zmiany jasności, ale już tylko około 6 milionów czopków, które umożliwiają nam rozróżnianie kolorów. Z tego powodu ludzkie oko jest bardziej podatne na zmiany jasności niż koloru.

Słuch człowieka podobnie wyłapuje ogrom informacji, jednak traci cześć z tych informacji w obecności innych. Przykładowo nie jest w stanie usłyszeć wysokich częstotliwości lub cichych dźwięków w obecności innych głośnych dźwięków.

Kopresja danych wykorzystuje te ogarniczenia pozwalając na ucięcie niektórych informacji z ścieżek wideo bądź audio w celu zmniejszenia wielkości plików.

### Metody kompresji stratnej obrazu

- Redukcja dokładności kwantyzacji (Least Significant Bits Truncation) - obcinanie najmniej znaczących bitów reprezentujących kolor
- Redukcja rozdzielczości (pruning) - zastępowanie grup pikseli jednym pikselem
- Redukcja palety barw - zmniejszenie liczby dostępnych kolorów
- Redukcja chrominancji (color subsampling) - konwersja RGB &rarr; YCbCr / YUV i zmniejszenie rozdzielczości informacji o kolorze
- Transformacja kosinusowa (DCT) - przekształcenie bloków pikseli do domeny częstotliwościowej, zamienia informacje o położeniu pikseli na informacje o zmianach jasności, co pozwala łatwo usunąć mało istotne szczegóły obrazu.
- Kwantyzacja - kluczowy etap stratny, zaokrąglanie współczynników po DCT
- Kodowanie entropijne - dalsza redukcja rozmiaru poprzez wykrywanie powtarzających się wzorców (bezstratna część)

#### Efekty uboczne kompresji obrazu

- Artefakty blokowe
- Utrata detali
- Rozmycie krawędzi

#### Etapy kompresji na przykładzie JPEG - Joint Photographic Experts Group

**Kodowanie**:

1. Wyizoluj informacje o kolorze. Problem, jeśli chodzi o format JPEG, polega na tym, że informacje o jasności obrazu są równomiernie rozłożone w kanałach R, G i B. Pamiętaj, że jasność jest ważniejsza niż kolor, więc będziemy chcieli izolować jasność na podstawie informacji o kolorze, dzięki czemu możemy zająć się tym osobno. Aby to zrobić, JPEG wykorzystuje pewne obliczenia matematyczne do konwersji obrazu z modelu kolorów z RGB do YCbCr. Obraz YCbCr również ma trzy kanały, ale przechowuje wszystkie informacje o jasności w jednym kanale (Y), dzieląc jednocześnie informacje o kolorze pomiędzy pozostałe dwa (Cb i Cr).
2. Wyrzuć kilka informacji o kolorze. Zanim zajmiemy się czymkolwiek innym, JPEG usuwa część informacji o kolorze, zmniejszając tylko kanały Cb i Cr (kolor), zachowując jednocześnie pełny rozmiar ważnego kanału Y (jasność). Ściśle rzecz biorąc, ten krok jest opcjonalny.
3. Konwersja do dziedziny częstotliwości. Aby wykorzystać drugą obserwację dotyczącą ludzkiej percepcji wzrokowej, zaczynamy od podzielenia każdego z kanałów Y, Cb i Cr na 8×8 bloków pikseli. Przekształcimy każdy z tych bloków z domeny przestrzennej do domeny częstotliwości. Wartość w lewym górnym rogu bloku będzie reprezentować informację o najniższej częstotliwości, a wartość w prawym dolnym rogu bloku będzie reprezentować informację o najwyższej częstotliwości. To transformacja domeny jest realizowana przy użyciu odrobiny matematycznej sztuczki zwanej 2D Dyskretna transformacja kosinusowa (DCT).
4. Suwak jakości (kwantyzacja). Następnym krokiem jest selektywne usunięcie części informacji o częstotliwości. Jeśli kiedykolwiek zapisałeś obraz JPEG i wybrałeś wartość jakości, tutaj właśnie ten wybór wchodzi w grę. Działa to w ten sposób: zacznij od dwóch tabel liczb całkowitych 8×8, zwanych tabelami kwantyzacji. Jedna tabela zawiera informacje o jasności, a druga o kolorze. Liczby te zostaną użyte w każdym z bloków 8×8 w danych obrazu poprzez podzielenie wartości częstotliwości w danych obrazu przez odpowiadającą jej liczbę w tabeli kwantyzacji. Zatem lewy górny róg każdego bloku 8×8 w kanale częstotliwości Y zostanie podzielony przez liczbę w lewym górnym rogu tabeli kwantyzacji jasności i tak dalej. Wynik każdego podziału zaokrągla się do najbliższej liczby całkowitej, a części ułamkowe odrzuca się.
5. Bezstratna kompresja danych. W postaci RLE [^5] albo Huffmana, w formie “zig-zag”. To wyświetla wartości dla każdego bloku 8×8 w zygzakowatym wzorze, który porządkuje liczby od najniższej częstotliwości do najwyższej. Oznacza to, że najbardziej skwantowane części (z największymi dzielnikami) znajdują się obok siebie, tworząc ładne, powtarzalne wzory małych liczb.

[^5]: RLE (Run length encoding) to bardzo prosta metoda kompresji bezstratnej polegająca na zastępowaniu sekwencji powtarzających się wartości informacją o liczbie ich wystąpień. Zamiast zapisywać dane w postaci „AAAAAB”, zapisuje się je jako „5AB”. Metoda ta działa najlepiej wtedy, gdy w danych występują długie ciągi identycznych elementów (np. zera po kwantyzacji w JPEG), natomiast przy dużej zmienności sygnału nie daje znaczących oszczędności, a czasem może nawet zwiększyć rozmiar danych.

**Dekodowanie**:

1. Dekompresja. Pierwszym krokiem jest dekompresja skwantowanych (podzielonych i zaokrąglonych) danych częstotliwości. Ponieważ dane te zostały skompresowane bezstratnie, wynik będzie dokładnie taki sam, jak w kroku 5 powyżej.
2. Rekonstrukcja na podstawie skwantowanych danych. Następnie musimy odwrócić proces kwantyzacji. Stosujemy tę samą procedurę co poprzednio, ale zamiast dzielić przez liczby w tabelach, mnożymy.
3. Konwersja z powrotem do domeny przestrzennej. Gdy zrekonstruowaliśmy informacje o częstotliwości, musimy przekształcić je z powrotem z dziedziny częstotliwości do dziedziny przestrzennej. To nie problem. Transformata, której użyliśmy podczas kodowania, ma odwrotność to spełnia swoje zadanie.
4. Wypełnij brakujące informacje o kolorze. Aby połączyć kanały z powrotem w jeden obraz, musimy skalować dwa kanały kolorów Cb i Cr z powrotem do ich pierwotnego rozmiaru. Ale informacje, które wyrzuciliśmy, zniknęły, więc będziemy musieli je przybliżyć interpolacja. Uzupełnimy brakujące piksele, biorąc średnią z otaczających pikseli, które nadal tam są.
5. Konwersja z powrotem do RGB. W tym momencie mamy kompletny obraz, ale nadal znajduje się on w przestrzeni kolorów YCbCr, której komputer nie może wyświetlić bezpośrednio. Musimy przekształcić go z powrotem w przestrzeń kolorów RGB, od której zaczęliśmy.

### Metody kompresji stratnej dźwięku

- Podział sygnału na ramki - dzielenie sygnału audio na krótkie fragmenty czasowe
- Transformacja do dziedziny częstotliwości - przekształcenie sygnału za pomocą FFT lub MDCT, uzyskanie informacji o amplitudach poszczególnych częstotliwości
- Maskowanie psychoakustyczne - Usunięcie dźwięków, które są niesłyszalne w obecności innych, głośniejszych dźwięków.
- Redukcja precyzji - zmniejszenie liczby bitów opisujących amplitudy częstotliwości
- Kodowanie entropijne - redukcja rozmiaru poprzez wykrywanie powtarzających się wzorców (bezstratna część)

#### Efekty uboczne kompresji dźwięku

- zniekształcenia wysokich tonów
- metaliczne brzmienie
- utrata dynamiki sygnału

#### Etapy kompresji na przykładzie MP3

1. Podziel sygnał audio na ramki czasowe. Sygnał zapisany w postaci próbek PCM jest ciągły w czasie, dlatego na początku dzieli się go na krótkie fragmenty (ok. 25 ms). Dzięki temu można analizować lokalne właściwości dźwięku i przetwarzać każdą część niezależnie, co umożliwia adaptacyjną kompresję.
2. Konwersja do dziedziny częstotliwości. Aby analizować zawartość widma, każda ramka jest przekształcana z domeny czasu do domeny częstotliwości przy użyciu banku filtrów oraz transformacji MDCT. Otrzymujemy zestaw współczynników opisujących energię w różnych zakresach częstotliwości.
3. Podział na pasma częstotliwości. Widmo dźwięku dzieli się na podpasmowe zakresy odpowiadające czułości ludzkiego słuchu (np. kilkadziesiąt pasm). Skrajne lub słabo słyszalne zakresy mogą być redukowane, ponieważ mają niewielkie znaczenie percepcyjne.
4. Model percepcji słuchu (maskowanie). Wykorzystywane są właściwości ludzkiego słuchu: silne dźwięki maskują słabsze w pobliżu częstotliwości oraz w czasie. Na tej podstawie obliczany jest próg słyszalności i określane są informacje, które mogą zostać uproszczone lub usunięte.
5. Przydział bitów dla pasm. Każdemu pasmu częstotliwości przydziela się liczbę bitów proporcjonalną do jego znaczenia percepcyjnego - istotne pasma zachowują większą dokładność, mniej istotne są reprezentowane oszczędniej.
6. Dostosowanie do ograniczeń przepływności. Całkowita liczba bitów dostępnych dla ramki jest ograniczona przez zadany bitrate (np. CBR - Constant Bitrate). Jeśli zapotrzebowanie jest większe, redukowana jest dokładność najmniej ważnych danych.
7. Kwantyzacja (kompresja stratna). Współczynniki częstotliwościowe są skalowane i zaokrąglane, co powoduje utratę części informacji. Wykorzystywane są techniki takie jak maskowanie czasowe czy joint stereo, aby zmniejszyć ilość danych przy minimalnym wpływie na odbiór.
8. Bezstratna kompresja danych. Skwantyzowane współczynniki są dodatkowo kodowane statystycznie (np. metodą Huffmana [^6]), co zmniejsza rozmiar danych bez dalszej utraty jakości.
9. Pakowanie ramek w strumień MP3. Do każdej ramki dodawane są nagłówki zawierające informacje sterujące, a wszystkie ramki są łączone w końcowy strumień danych tworzący plik MP3.

[^6]: Kodowanie Huffmana to bezstratna metoda kompresji statystycznej, która przypisuje krótsze kody bitowe częściej występującym symbolom, a dłuższe rzadkim. Na podstawie częstości występowania symboli budowane jest drzewo binarne, z którego wyznaczane są jednoznaczne (prefiksowe) kody. Dzięki temu średnia długość zapisu symbolu maleje, co redukuje rozmiar danych bez utraty informacji - technika ta jest powszechnie stosowana między innymi w JPEG i MP3 jako końcowy etap kompresji.

## 25. Rodzaje filtrów oraz ich zastosowanie w przetwarzaniu obrazów


