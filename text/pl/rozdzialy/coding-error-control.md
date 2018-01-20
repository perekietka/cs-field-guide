# Kodowanie - Kontrola błędów

## What's the big picture?

{panel type="teacher-note" summary="Pokazanie sztuczki z parzystością w klasie"}
Magiczna sztuczka z użyciem parzystości może stanowić ciekawy wstęp do idei korekcji błędów i zalecamy jej użycie na początku uczenia tego tematu. Trzeba ją wypróbować zawczasu, a dla uczniów szkół średnich zalecamy siatkę o wymiarach około 7x7 lub 8x8, żeby wywarła odpowiednie wrażenie. Szczegóły znajdują się w sekcji [Magia przewracania kart](http://csunplugged.org/error-detection) [strony CS Unplugged](http://csunplugged.org/).
{panel end}

{video url="https://www.youtube.com/embed/OXz64qCjZ6k?rel=0"}

Magiczna sztuczka z parzystością (na powyższym filmie) umożliwia magikowi wykrycie, która z dziesiątek kart została odwrócona gdy nie patrzył.
Magia tej sztuczki to w rzeczywistości informatyka, wykorzystująca tę samą technikę, której używają komputery do wykrywania i korygowania błędów danych. Pokażemy jak to działa w następnej sekcji.

To samo dzieje się z danymi przechowywanymi na komputerach - gdy ty (lub komputer) ich nie obserwujesz, niektóre z nich mogły się przypadkowo zmienić z powodu drobnej usterki.
Nie chcielibyśmy, żeby komputer tak po prostu użył nieprawidłowych wartości kiedy już je odczyta.
Chcielibyśmy żeby przynajmniej wykrył, że coś poszło nie tak, a najlepiej by było, gdyby zrobił to, co magik, czyli naprawił.

W tym rozdziale chodzi o ochronę przed błędami w danych w różnych postaciach - w danych przechowywanych na dysku twardym, na dysku CD, dyskietce, dysku SSD (na przykład w telefonie komórkowym, aparacie lub odtwarzaczu mp3), danych znajdujących się w danej chwili w pamięci RAM (szczególnie na serwerach, w których poprawność danych jest niezwykle ważna), danych przepływających pomiędzy pamięcią RAM i dyskiem twardym lub między zewnętrznym dyskiem twardym a wewnętrznym dyskiem twardym, danych przetwarzanych właśnie w procesorze, czy danych przesyłanych przez sieci przewodowe lub bezprzewodowe, na przykład z twojego komputera na serwer po drugiej stronie świata. Obejmuje takie dane, jak kody kreskowe wydrukowane na produktach czy numery na kartach kredytowych.

Jeśli nie wykryjemy, że dane zostały zmienione przez jakiś problem fizyczny (na przykład małą rysę na płycie CD lub uszkodzony obwód w pamięci flash), niepoprawna informacja zostanie po prostu użyta. Bardzo źle napisany system bankowy może potencjalnie doprowadzić do zmiany salda twojego rachunku, gdyby tylko jeden z bitów w liczbie został zmieniony przez promień kosmiczny, wpływając na wartość w pamięci komputera! Jeśli kod paskowy na paczce czipsów zakupionej w sklepie zostanie zeskanowany nieprawidłowo, może zostać naliczona opłata za szampon. Jeśli prześlesz plik muzyczny z laptopa do odtwarzacza mp3, a kilka bitów zostało przesłanych nieprawidłowo, odtwarzacz mp3 może odtworzyć muzykę z irytującymi usterkami. Kody kontroli błędów chronią przed tym wszystkim, więc (zwykle) wszystko po prostu działa i nie musimy się obawiać takich błędów.

Dane mogą zostać przypadkowo zmienione z wielu przyczyn. Sieci, które mają dużo "szumu" (spowodowanego złą jakością okablowania, zakłóceniami elektrycznymi lub - w przypadku sieci bezprzewodowych - zakłóceniami z innych sieci). Bity na dyskach są bardzo małe, a niedoskonałości na powierzchni mogą w końcu spowodować uszkodzenie pamięci. Powierzchnie na dyskach kompaktowych i DVD są odsłonięte i mogą być łatwo uszkodzone podczas przechowywania (na przykład w wysokiej temperaturze lub wilgotności) lub używania (na przykład przez zadrapania albo kurz). Błędy mogą również wystąpić przy wpisywaniu liczb, na przykład przy wprowadzaniu numeru konta bankowego w celu dokonania płatności lub numeru kontenera, który jest ładowany na statek. Kody kreskowa na produktach mogą być lekko zarysowane lub poplamione na czarno, albo opakowanie może być zgięte lub nie można go prawidłowo odczytać, ponieważ zbyt szybko przesunięto nad nim skaner. Zmiana bitów w pamięci trwałej (takiej jak dyski twarde, dyski optyczne i dyski półprzewodnikowe) jest czasami nazywana gniciem danych, a [strona Wikipedii o gniciu danych](https://en.wikipedia.org/wiki/ Data_degradation) zawiera listę innych sposobów w jaki mogą wystąpić te błędy.

Nikt nie chce komputera, który nie jest wiarygodny i nie robi tego, co powinien robić z powodu zmian bitów! Jak więc poradzić sobie z tymi problemami?

Kodowanie korekcyjne służy do wykrywania kiedy te błędy występują, a jeśli jest to praktyczne i możliwe, poprawianie danych tak, aby wróciły do niezmienionej postaci.

Niektóre schematy kontroli błędów zawierają wbudowane kody korekcji błędów, takie jak metoda parzystości, którą krótko wprowadzono na początku tej sekcji. Być może nie zrozumiałeś jeszcze, jak działała sztuczka z parzystością, ale po odwróceniu karty magik *wykrył*, która karta została przewrócona, i mógł ją *poprawić*.

Inne schematy kontroli błędów, takie jak te, które działają przy wysyłaniu danych z serwera za granicą do twojego komputera, wysyłają dane w bardzo małych fragmentach zwanych pakietami (mówi o tym rozdział o protokołach sieciowych) i każdy pakiet ma dodane informacje o wykryciu błędu.

Wykrywania błędów używa się również przy numerach kodów kreskowych na zakupionych produktach, a także unikalnego numeru ISBN (International Standard Book Number), który mają wszystkie książki, a nawet 16-cyfrowego numeru na karcie kredytowej. Jeśli którykolwiek z tych numerów zostanie wpisany lub zeskanowany niepoprawnie, istnieje duża szansa, że ​​błąd zostanie wykryty, a użytkownik może zostać poproszony o ponowne wprowadzenie danych.

Pod koniec tego rozdziału powinieneś zrozumieć podstawową ideę kodowania kontroli błędów, powody, dla których tego wymagamy, różnice między algorytmami, które mogą wykrywać błędy, a tymi, które mogą zarówno wykrywać, jak i korygować błędy, a także niektóre z nich. stosuje się kodowanie sterujące, w szczególności parzystość (skupiając się na sztuczce parzystości) i cyfry kontrolne używane do zapewnienia prawidłowego wprowadzania numerów książek, numerów kodów kreskowych i numerów kart kredytowych.

## The Parity Magic Trick

Jeśli nigdy wcześniej nie widziałeś sztuczki z parzystością, obejrzyj wideo w sekcji "Jaki jest ogólny obraz?" powyżej. Zakładamy w tej sekcji, że wiesz, co to znaczy sztuczka z parzystością, ale teraz wyjaśnimy, jak ona działa!

{image filename="parity-trick-cartoon.jpg" alt="Sztuczka z parzystością"}

Magik poprosi obserwatora, aby ułożył dwustronne karty w kwadracie, a następnie magik powie, że uczyni zadanie nieco trudniejszym, dodając do kwadratu dodatkową kolumnę i rząd. Magik odwraca się, a obserwator odwraca jedną z kart. Magik znowu się odwraca i mówi obserwatorowi, która karta została odwrócona!

Teraz pytanie brzmi: skąd magik wiedział, która karta została przewrócona, nie oglądając odwróconej karty, ani nie zapamiętując układu?! Krótka mówiąc, odpowiedzią jest korekcja błędów. Przyjrzyjmy się temu bliżej...

### Wykonywanie sztuczki z parzystością

W tym programie interaktywnym komputer ma kwadrat 7x7 z czarno-białych kart. Musisz wybrać kolor dodatkowej karty dla każdego rzędu (po prawej) i kolumny (na dole), tworząc kwadrat kart 8x8. Każda dodatkowa karta powinna zostać wybrana tak, aby każdy rząd i kolumna miały parzystą liczbę czarnych kart (ponieważ jest 8 kart, liczba białych kart będzie również parzysta).
Kartę w prawym dolnym rogu można wybrać na podstawie jej wiersza lub kolumny; powinny dać ten sam kolor.

Kiedy uznasz, że wszystko jest dobrze, powinieneś powiedzieć komputerowi, aby odwrócił kartę. Przez kilka sekund będzie pokazywana animacja, a następnie karty pojawią się ponownie z jedną odwróconą kartą (cała reszta będzie taka sama jak poprzednio). Twoim zadaniem jest zidentyfikowanie odwróconej karty. Powinieneś być w stanie to zrobić *bez* zapamiętania układu kart. Pamiętasz wzorzec, według którego dodawałeś dodatkowe karty? To on jest kluczem. Gdy uznasz, że zidentyfikowałeś kartę, kliknij ją, aby sprawdzić, czy masz rację. Program interaktywny poprowadzi cię przez te instrukcje. Jeśli całkowicie utknąłeś podczas identyfikacji odwróconej karty, w programie interaktywnym pojawi się podpowiedź, chociaż powinieneś najpierw spróbować ją znaleźć. Upewnij się, że dodajesz dodatkowe karty poprawnie; komputer nie powie ci, jeśli źle je ustawisz i prawdopodobnie nie będziesz w stanie zidentyfikować odwróconej karty, jeśli dodatkowe karty nie zostaną ustawione poprawnie.

{interactive name="parzystość" type="cała strona" text="Program interaktywny sztuczki z parzystością"}

Pamiętasz, jak ustawiałeś karty tak, aby każda kolumna miała parzystą liczbę czarnych kart? Kiedy karta zostaje odwrócona, powoduje to, że w wierszu i kolumnie znajduje się nieparzysta liczba czarnych kart. Wszystko, co musisz zrobić, to zidentyfikować rząd i kolumnę, które mają nieparzystą liczbę czarno-białych kart, a wtedy karta, która znajduje się na ich przecięciu, musi być tą, która została odwrócona!

To, co zobaczyliśmy powyżej, to prosty algorytm korekcji błędów, znany jako *2-wymiarowa parzystość*.

### Jaki jest związek sztuczki z parzystością z kodami korekcji błędów?

Karty reprezentują bity, przy czym ich dwa stany to czerń i biel (w rozdziale "prezentacja danych" analizowaliśmy, jak bit może być przechowywany przez cokolwiek, co może być w jednym z dwóch stanów: błyszczący/matowy, namagnesowany/nienamagnesowany , wysokie napięcie/niskie napięcie, czerń/biel itp.). Karty w kracie 7x7, które komputer dla ciebie przygotował, mogą być jakimiś danymi, na przykład tekstem reprezentowanym za pomocą bitów, obrazem lub jakimiś liczbami.
Chociaż są one rozmieszczone na kracie, na komputerze wiersze bitów będą przechowywane i przesyłane jeden po drugim (jako 8 partii po 8 bitów każda).

Dodatkowe, dodane przez ciebie karty są nazywane *bitami parzystości*. [Parzystość](https://pl.wikipedia.org/wiki/Parzysto%C5%9B%C4%87_liczb)
oznacza po prostu, czy liczba jest parzysta czy nieparzysta (słowo pochodzi od tego samego rdzenia co "para"). Dodając dodatkowe karty w taki sposób, aby zapewnić równą liczbę czarnych kart w każdym rzędzie i kolumnie, zapewniłeś, aby wiersze i kolumny miały tzw. własność *parzystości*.

Odwrócenie karty symulowało błąd w danych (np. kawałek kurzu lądujący na dysku CD lub promień kosmiczny zmieniający bit na dysku twardym lub zakłócenia elektryczne zmieniające bit wysyłany przez kabel sieciowy). Ponieważ wiedziałeś, że w każdym wierszu i kolumnie powinna znajdować się parzysta liczba białych i czarnych kart, byłeś w stanie stwierdzić, że wystąpił błąd na podstawie faktu, że w kolumnie i szeregu była nieparzysta liczba czarnych kart. Oznacza to, że algorytm jest w stanie wykryć błędy, czyli była to **detekcja błędów**. Konkretna karta, która została odwrócona, znajdowała się na przecięciu wiersza i kolumny z nieparzystą liczbą czarnych kart i białych kart, a ponieważ byłeś w stanie dokładnie określić, która karta została przewrócona, byłeś w stanie poprawić błąd, czyli był to też algorytm **korekcji błędów**.

Gdybyś nie dodał bitów parzystości, nie byłbyś w stanie nawet stwierdzić, że wystąpił błąd, chyba że zapamiętałeś cały układ kart!
A co by było, gdyby odwrócono więcej niż jedną kartę? Rozważymy to później.

{panel type="project" summary="Bycie magikiem czyli używanie sztuczki z parzystością jako sztuczki magicznej!"}
Teraz, gdy już nauczyłeś się, jak działa sztuczka z parzystością, możesz wypróbować ją z fizycznym zestawem kart, jak magik w filmie, albo możesz użyć dowolnych obiektów z dwoma różnymi stronami, takimi jak monety lub kubki. Możesz używać kart do gry, ale oznaczenia mogą rozpraszać, a karty z dwoma kolorami są najłatwiejsze (możesz je wykonać, tnąc dwukolorowe arkusze tektury, albo jednokolorowy arkusz z naklejkami, albo zamalowany na jednej stronie).

Możesz znaleźć szczegóły i wiele pomysłów związanych ze sztuczką [tutaj](http://csunplugged.org/error-detection) lub postępować zgodnie z tymi instrukcjami:

1. Poproś znajomego, aby rozłożył 25 kart w siatce 5 na 5, starając się mieć w miarę losową mieszankę czarnych i białych (to mniej niż w programie interaktywnym, ale łatwiej jest zaczynać z mniejszą liczbą kart, aby uniknąć błędów w następnym kroku!)
2. Weź wszystkie pozostałe karty, a następnie powiedz, że w sumie 5 na 5 jest zbyt łatwe, więc zamierzasz przerobić je na 6 na 6. Zamiast dodawać losowo nowy wiersz i kolumnę, dodajesz je w taki sposób, w jaki robiłeś to w programie interaktywnym (z parzystością). Zrób to tak szybko, jak tylko potrafisz, nie popełniając błędów (może to wyglądać bardzo naturalnie, jeśli to poćwiczysz, mimo że karty są starannie dobierane).
3. Powiedz swojemu przyjacielowi, że się odwrócisz i chciałbyś, aby odwrócił jedną kartę, kiedy nie będziesz patrzył. Upewnij się, że odwrócił dokładnie jedną kartę.
4. Odwróć się ponownie po odwróceniu karty, przejrzyj wiersze i kolumny, identyfikując wiersz, a następnie kolumnę zawierającą nieparzystą liczbę czarnych kart. Odwrócona karta będzie na przecięciu tego rzędu i kolumny. Odwróć tę kartę z powrotem.

Trzeba trochę ćwiczeń żeby móc dodać więcej kart i zidentyfikować odwróconą kartę tak, żeby obserwator nie zauważył, że długo się nad tym zastanawiasz. Przy odrobinie praktyki powinieneś być w stanie to robić, swobodnie prowadząc rozmowę. Kiedy już to opanujesz, będziesz mieć świetną sztuczkę na imprezy.

Aby uczynić ją bardziej efektowną, możesz udawać, że czytasz w myślach, machając rękami nad kartami. Szczególnie imponujące może być wprowadzenie asystenta do pokoju po odwróceniu karty; nawet jeśli nie widział wcześniej konfiguracji kart, i tak będzie w stanie wykryć błąd.
{panel end}

### Analizowanie sztuczki parzystości

{panel type="teacher-note" summary="Ta sekcja zawiera materiał rozszerzony"}
Ta sekcja jest rozszerzeniem skierowanym do zapalonych studentów. Dzieci w szkole podstawowej były w stanie zrozumieć wiele z tych pomysłów, choć tak naprawdę zależy to od zaangażowania uczniów w materiał.
{panel end}

W tym momencie powinieneś być w stanie wykonać sztuczkę z parzystością na tyle dobrze, że możesz pokazać, że ją rozumiesz. Pozostała część tego rozdziału skupia się na dalszym badaniu pomysłów dotyczących korekcji błędów, związanych ze sztuczką z parzystością.

Najlepszym rozwiązaniem byłoby posiadanie fizycznych kart parzystości, które można rozmieścić przed sobą i przestawiać w trakcie rozważania postawionych pytań.

{comment}
.. xhtml5 (niski priorytet) Czy moglibyśmy zapewnić program interaktywny, która byłby po prostu piaskownicą ze sztuczką z parzystością?
{comment end}

Algorytm korekcji błędów często łatwiej wykrywa błędy, niż je poprawia. Błędy na wielu bitach mogą czasami nawet pozostać zupełnie niewykryte. Co się stanie, jeśli komputer (lub twój przyjaciel, jeśli byłeś magikiem z prawdziwymi kartami parzystości), był sprytny i odwrócił dwie karty zamiast jednej? Możesz zacząć od namówienia przyjaciela lub kolegi z klasy, aby to zrobił. Powtórz to kilka razy. Czy zawsze potrafisz poprawić błędy, czy też czasem źle zgadujesz?

Pamiętaj, że aby *wykryć* błędy za pomocą tego algorytmu, wystarczy zauważyć że jeden lub więcej wierszy i / lub kolumn ma nieparzystą liczbę czerni i bieli - wtedy musi istnieć co najmniej jeden błąd. Aby *poprawić* błędy, trzeba wskazać konkretne karty, które zostały odwrócone.

Czy zawsze jesteś w stanie wykryć, kiedy wystąpił błąd, jeśli zostały odwrócone 2 karty? Czemu? Czy zawsze jesteś w stanie poprawić błąd? A co gdyby były to 3 karty?

Okazuje się, że zawsze można wykryć błąd po odwróceniu 2 kart (tj. błąd 2-bitowy), ale system nie może naprawić błędu większego niż 1-bitowy. Kiedy dwie karty są odwrócone, będą co najmniej dwie opcje jak przerzucić dwie kart w celu przywrócenia parzystości, a ty nie będziesz wiedział, która z nich jest właściwa. Przy 3-bitowym błędzie (przerzucone 3 karty) zawsze będzie można wykryć błąd (nieparzystą liczbę czarnych bitów w co najmniej jednym rzędzie lub kolumnie), ale znowu nie można dokonać korekty. Przy odwracaniu 4 kart jest możliwe (choć niezbyt prawdopodobne), że błąd może pozostać niewykryty.

W rzeczywistości istnieje sposób na odwrócenie 4 kart, w których błąd jest *niewykryty*, co oznacza, że algorytm nie będzie w stanie wykryć błędu. Czy jesteś w stanie znaleźć sposób jak to zrobić?

Dzięki większej liczbie kart parzystości możemy wykryć i ewentualnie poprawić więcej błędów. Przyjrzyjmy się bardzo prostemu systemowi z minimalnymi liczbą kart parzystości. Możemy mieć siatkę z danymi 7x7 i tylko jedną kartę parzystości. Ta karta parzystości sprawia, że w całym układzie znajduje się parzysta liczba czarnych kart (w tym karta parzystości). Jak można tego użyć do wykrywania błędów? Czy jesteś w stanie kiedykolwiek poprawić błędy w tym systemie? W jakich sytuacjach błędy pozostają niezauważone (pomyśl, co się dzieje kiedy masz wiele błędów, tzn. przerzucono więcej niż jedną kartę).

Przy użyciu tylko jednej dodatkowej karty do sprawdzania parzystości, można wykryć błąd pojedynczego bitu (całkowita liczba czarnych kart stanie się nieparzysta), ale 2-bitowy błąd nie zostanie wykryty, ponieważ liczba czarnych kart będzie ponownie parzysta. Zostanie wykryty 3-bitowy błąd, ale ogólnie rzecz biorąc, ten system jest dość zawodny.

Wracając do powyższej sztuczki z parzystością, w której była siatka 7 na 7 i 15 kart parzystości, aby uzyskać 8 na 8, warto zauważyć, że potrzebna była tylko 1 dodatkowa karta do wykrycia, że wystąpił błąd, ale 15 dodatkowych do poprawienia błędu. Jeśli rozważymy koszt algorytmu, widać, że w tym algorytmie znacznie więcej miejsca kosztuje możliwość poprawiania błędów, niż po prostu ich wykrywanie!

Co się dzieje, gdy używamy siatki o różnych rozmiarach? Siatka nie musi mieć parzystej liczby czarnych kart *i* parzystej liczby białych kart, po prostu tak akurat jest, że jeśli mamy siatkę o boku parzystej wielkości z dodanymi bitami parzystości (np. o najczęściej w tej sekcji używanym rozmiarze 8x8) i parzystą liczbę czarnych kart, to będzie też parzysta liczba białych, co sprawia, że łatwiej się we wszystkim połapać.

Wypróbuj siatkę 6x6 z dodatkiem kart parzystości, aby uzyskać 7x7. Karty parzystości po prostu muszą sprawić, że każdy rząd i kolumna mają parzystą liczbę czarnych kart (w tym przypadku zawsze będzie nieparzysta liczba białych kart w każdym rzędzie i kolumnie). Wykrywanie błędów polega na szukaniu wierszy i kolumn zawierających nieparzystą liczbę czarnych kart (ale parzysta liczbę białych kart). Co ciekawe, siatka nie musi nawet być kwadratem! Możesz użyć 4x7 i też będzie działać!

Nie ma również ograniczeń rozmiaru. Możesz utworzyć siatkę 10x10 (100 kart) i nadal możesz wykryć, która karta została przewrócona. Większe siatki czynią magiczną sztuczkę jeszcze bardziej imponującą.

## Cyfry kontrolne na kodach kreskowych i innych numerach

Prawdopodobnie nie byłbyś zadowolony, gdybyś kupił książkę przez Internet, wpisując numer ISBN (International Standard Book Number), i wysłano Ci niewłaściwą książkę, lub jeśli kilka dni po jej zamówieniu otrzymałbyś e-mail z informacją, że podany numer karty kredytowej nie należał do Ciebie, tylko miał jedną zmienioną cyfrę, a inny posiadacz karty kredytowej poskarżył się na bezprawne obciążenie jego karty. Albo gdybyś poszedł do sklepu kupić puszkę napoju, a skaner odczytał ją jako droższy produkt. Czasami skaner nawet nie odczytuje kodu kreskowego, a operator kasy ręcznie musi wprowadzić numer do komputera - ale jeśli nie wprowadzi go dokładnie tak, jak widnieje na kodzie kreskowym, może się okazać, że zostanie naliczona opłata za niewłaściwy produkt. Wszystko to są przykłady sytuacji, którym korekcja błędów może zapobiec.

Numery kodów kreskowych, numery kart kredytowych, numery kont bankowych, numery ISBN, numery PESEL, etykiety wysyłkowe (kody kontenerów wysyłkowych - SSCC) i numery podatkowe zawierają kody korekcji błędów, aby zmniejszyć ryzyko ich wystąpienia. Niektóre cyfry w takich numerach to cyfry kontrolne, które uzyskuje się, wykonując specjalne obliczenia na wszystkich pozostałych cyfrach w numerze. Jeśli na przykład wpiszesz numer karty kredytowej w formularzu internetowym, aby coś kupić, zostanie obliczone jaka powinna być 16. cyfra, przy użyciu pierwszych 15 cyfr i specjalnego sposobu (w numerach kart kredytowych jest 16 cyfr). Jeśli oczekiwana 16-ta cyfra nie jest cyfrą, którą wprowadziłeś, można stwierdzić, że wystąpił błąd po wprowadzeniu numeru i zostaniesz powiadomiony, że numer karty kredytowej jest nieprawidłowy.

W tej sekcji najpierw przyjrzymy się jednemu z najczęściej używanych formatów kodów kreskowych używanych w większości produktów kupowanych w supermarketach i innych sklepach. Później rozpatrzymy numery kart kredytowych. Nie musisz rozumieć *dlaczego* obliczenia działają tak dobrze (jest to zaawansowana matematyka i nie jest to ważne dla zrozumienia ogólnej idei) i chociaż dobrze jest wiedzieć, jakie są obliczenia, nie jest to niezbędne. Więc jeśli matematyka jest dla ciebie wyzwaniem i cię niepokoi, nie panikuj za bardzo, ponieważ to, co oglądamy w tej sekcji, nie jest wcale tak trudne, jak mogłoby się początkowo wydawać!

### Cyfry kontrolne na kodach kreskowych produktów

Większość produktów, które można kupić w sklepie, ma kod kreskowy z 13-cyfrowym "globalnym numerem handlowym" (zwanym GTIN-13).
Pierwsze 12 cyfr to rzeczywisty numer identyfikacyjny produktu, 13. to cyfra kontrolna wyliczana z pozostałych 12.
Nie wszystkie kody kreskowe to GTIN-13, istnieje kilka innych typów.
Jeśli jednak kod kreskowy zawiera 13 liczb, to prawie na pewno jest to GTIN-13.

{image filename="isbn-barcode.png" alt="Obraz 13-cyfrowego kodu kreskowego"}

Ostatnia cyfra tych liczb jest wyliczana z pierwszych 12.
Jest to bardzo ściśle związane z bitem parzystości, który rozważaliśmy powyżej, gdzie ostatni bit rzędu jest "wyliczany" z wcześniejszych bitów.
Kod GTIN-13 pozwala nam wykryć, czy jedna z cyfr nie została wprowadzona niepoprawnie.

Następujący program interaktywny sprawdza kody kreskowe GTIN-13. Wprowadź pierwsze 12 cyfr kodu kreskowego do programu interaktywnego, a on powie ci, jaka powinna być ostatnia cyfra!
Możesz zacząć używając numeru kodu kreskowego "9 300675 036009".

{interactive name="checksum-calculator-gtin-13" type="in-page"}

{panel type="teacher-note" summary="Pozyskiwanie większej ilości kodów kreskowych"}
Możesz przynieść różne opakowania, które mają kody kreskowe, żeby klasa mogła je ocenić, albo przynieść zdjęcia kodów kreskowych.
{panel end}

Co się stanie, jeśli popełnisz błąd podczas wpisywania 12 cyfr (spróbuj zmienić jedną cyfrę)?
Czy to pozwala wykryć, że popełniono błąd?

{panel type="teacher-note" summary="Solution"}
Jeśli zmieni się tylko jedna cyfra, cyfra kontrolna będzie zawsze nieprawidłowa, a błąd zostanie wykryty.
{panel end}

Znajdź inny produkt z kodem kreskowym, np. artykuł spożywczy z obiadu lub przedmiot papierniczy.
Zauważ, że niektóre kody kreskowe są trochę inne --- upewnij się, że kody kreskowe, których używasz, mają 13 cyfr (chociaż możesz też dowiedzieć się, jak działa cyfra kontrolna na innych kodach).
Czy program interaktywny zawsze jest w stanie określić, czy poprawnie wpisałeś kod kreskowy?

Jeden z następujących numerów produktów zawiera jedną niepoprawną cyfrę. Czy możesz stwierdzić, który z produktów miał nieprawidłowo wpisany numer?

- 9 400550 619775
- 9 400559 001014
- 9 300617 013199

{panel type="teacher-note" summary="Solution"}
Ostatni kod zawiera literówkę; powinno być 9 300617 003199. Uczniowie powinni być w stanie wykryć, że jest nieprawidłowy, ale nie da się ustalić, jaka jest właściwa wartość.
{panel end}

Gdybyś skanował powyższe kody kreskowe w supermarkecie, niepoprawny musiałby zostać ponownie przeskanowany, a system może stwierdzić, że jest to zła liczba, bez konieczności wyszukiwania w spisie.
Zwykle byłoby to spowodowane uszkodzeniem samego kodu kreskowego (np. trochę lodu na zamrożonym produkcie, powodujące nieprawidłowy odczyt).
Jeśli zostanie wykryty błąd, skaner zwykle wydaje dźwięk ostrzegawczy, aby ostrzec kasjera.

Możesz spróbować wymienić się numerami kodów kreskowych z kolegami z klasy, ale przed podaniem numeru rzuć monetą i jeśli wyjdzie orzeł, zmień jedną z cyfr kodu kreskowego, zanim go podasz.
Czy uda im się ustalić, że dostali błędny kod kreskowy?

Jeśli jedna cyfra jest niepoprawna, to wyliczona cyfra kontrolna da inną wartość niż ma cyfra w kodzie, co zasygnalizuje błąd. Tak więc błędy jednocyfrowe *zawsze* zostaną wykryte, ale co jeśli dwie cyfry ulegną zmianie --- czy zawsze błąd zostanie wykryty?

{panel type="teacher-note" summary="Solution"}
Jeśli zostaną zmienione dwie cyfry, błąd może pozostać niewykryty; na przykład zmiana 9 400559 001014 na 6 500559 001014 nadal będzie generować sumę kontrolną 4, która wydaje się być zgodna. Jednak jest mało prawdopodobne, że dwa błędy będą tak się zniosą (uczniowie mogą zbadać, jak często to się dzieje).
{panel end}

Co jeśli błąd występuje w samej sumie kontrolnej, ale nie w innych cyfrach - czy zostanie wykryty?

{panel type="teacher-note" summary="Solution"}
Niektórzy uczniowie mogą się martwić, że wystąpi problem, jeśli to suma kontrolna zostanie zmieniona, ale oczywiście jeśli zostanie ona wpisana niepoprawnie, to nie będzie ona odpowiadać sumie innych cyfr, a błąd zostanie wykryty.
{panel end}

### Jak cyfry kontrolne chronią przed zwykłymi, ludzkimi błędami?

Ludzie mogą popełniać błędy, przy wprowadzaniu liczb do komputerów i nawet skanery kodów kreskowych mogą błędnie odczytać jakąś cyfrę. Cyfry kontrolne starają się wykryć że wystąpił błąd i powiadomiają o tym komputer i / lub osobę. Załóżmy, że podajesz numer telefonu komórkowego znajomemu, aby mógł się z tobą później skontaktować. Aby upewnić się, że prawidłowo podałeś numer, możesz poprosić go o natychmiastowe wysłąnie SMSa, żeby to potwierdzić (i żebyś też zaraz miał jego numer). Jeśli nie dostaniesz tego SMSa, prawdopodobnie ponownie sprawdzisz numer i odkryjesz, że twój znajomy popełnił błąd, na przykład źle wpisał cyfrę lub odwrócił dwie cyfry leżące obok siebie. Błędy się zdarzają, a dobre systemy zapobiegają irytującym lub nawet poważnym konsekwencjom tych błędów.
Jeśli używana jest cyfra kontrolna, istnieje duża szansa, że błąd zostanie wykryty, gdy cyfra kontrolna nie jest zgodna z oczekiwaniami komputera.

Niektóre z naprawdę typowych błędów to:

- Nieprawidłowa jedna cyfra (podstawienie)
- Zamiana dwóch sąsiadujących cyfr (transpozycja)
- Brakująca cyfra
- Dodana cyfra

Dwa ostatnie zostaną zauważone przez niezgodność z oczekiwaną długością liczby; na przykład GTIN-13 ma 13 cyfr, więc jeśli wprowadzono 12 lub 14, komputer natychmiast wie, że coś jest nie w porządku. Wykrycie pierwszych  dwóch polega na cyfrze kontrolnej. Co ciekawe, wszystkie jednocyfrowe błędy zostaną wykryte przez popularne systemy sum kontrolnych, a *większość* transpozycji zostanie wykryta (czy można znaleźć przykłady transpozycji, które nie zostały wykryte, korzystając z powyższego programu interaktywnego?)

Istnieją również mniej powszechne błędy, popełniane przez ludzi

- Nieprawidłowa cyfra w dwóch lub więcej miejscach
- Podwojenie błędnej cyfry, np. umieszczenie 3481120 zamiast 3481220
- Pomieszanie 3 cyfr, np. 14829 zamiast 12489
- Błędy fonetyczne są możliwe, gdy numer został odczytany i wpisany przez kogoś słuchającego (lub czytającego sobie głośno ten numer podczas wpisywania). Na przykład "trzydzieści" (30) może być usłyszane jako "trzynaście" (13).

Eksperymentuj dalej z programem interaktywnym. Jakie błędy zostały wykryte? Jakie znajdziesz błędy, które nie zostaną? Czy często występujące błędy prawie zawsze zostają wykryte? Czy potrafisz znaleźć sytuacje, w których nie zostają? Spróbuj znaleźć przykłady tylu różnych rodzajów błędów wykrywanych i błędów, które nie są wykrywane, ile tylko możesz.

{panel type="teacher-note" summary="Częste błędy"}

Uczniowie mogą próbować odwrócić wszystkie cyfry lub całkowicie je zmienić i pokazać, że cyfra kontrolna pozostaje taka sama, a następnie twierdzić, że jest to ograniczenie algorytmu, ale nie jest to dobra ocena. Muszą myśleć o tym, jak algorytm jest normalnie używany, np. przez kasjera wprowadzającego numer kodu kreskowego do komputera, pielęgniarkę wprowadzającą numer identyfikacyjny pacjenta lub kogoś, kto kupuje coś online i podaje numer karty kredytowej oraz błędy, których realistycznie można się spodziewać. Błędy wymienione powyżej dobrze obejmują możliwe rodzaje błędów, chociaż uczniowie mogą wymyślić więcej. Oczywiście ważniejsze jest, żeby wykrywać błędy naprawdę powszechne, ale miło byłoby, gdyby wykrywane były też mniej popularne, choć nadal mogące wystąpić. Należy jednak pamiętać, że dla algorytmu byłoby większym problemem, gdyby nie mógł wykryć zmiany 1 cyfry, niż gdyby na przykład nie można było wykryć zmiany 3 cyfr.

Główne błędy, które ten system najlepiej wykryje, to jednocyfrowe literówki i zamiana dwóch sąsiednich cyfr.
Dla innych rodzajów błędów to bardziej kwestia przypadku.

Dysleksja i związane z nią problemy mogą być interesującą kwestią do rozważenia, chociaż należy zachować odpowiednie proporcje, ponieważ większość ludzi nie ma dysleksji.

{panel end}

{panel type="teacher-note" summary="Pisanie programu wykrywania błędów"}

Skłonienie studentów do napisania programu do obliczania sum kontrolnych jest dobrym ćwiczeniem programistycznym. Można to uprościć poprzez wpisywanie każdej cyfry osobno, lub można rozdzielenie cyfr uczynić częścią ćwiczenia. Utworzenie arkusza kalkulacyjnego do tych obliczeń również nie jest trudne.

{panel end}

### W jaki sposób obliczana jest cyfra kontrolna kodów kreskowych na produktach?

Pierwsze 12 cyfr kodu kreskowego przedstawia informacje takie jak kraj pochodzenia, producent i identyfikator produktu. 13. cyfra to cyfra kontrolna, wyliczana z pierwszych 12 cyfr.
Jest obliczana przy użyciu następującego algorytmu (zobacz także przykład poniżej).

- Pomnóż co drugą cyfrę (począwszy od drugiej) przez 3, a resztę przez 1 (czyli pozostają bez zmian).
- Dodaj wszystkie pomnożone liczby, otrzymując *sumę*.
- Cyfra kontrolna to ta liczba, którą należałoby dodać do sumy żeby uczynić ją wielokrotnością 10 (tj. ostatnia cyfra sumy powinna wynosić 0). Albo, bardziej formalnie, weź ostatnią cyfrę sumy i jeśli jest 0, to cyfra kontrolna wynosi 0. W przeciwnym razie odejmij ostatnią cyfrę od 10, aby uzyskać cyfrę kontrolną.

Spójrzmy na przykład ilustrujący ten algorytm. Chcemy potwierdzić, że cyfra kontrolna umieszczona na kodzie kreskowym butelki coli była poprawna. Numer kodu kreskowego to 9300675032247. Ostatnia cyfra, 7, to cyfra kontrolna. Więc bierzemy pierwsze 12 cyfr i mnożymy je przez 1 lub 3, w zależności od ich pozycji (9x1+3x3+0x1+0x3+6x1+7x3+5x1+0x3+3x1+2x3+2x1+4x3). Następnie sumujemy wszystkie pomnożone liczby, otrzymując sumę 73. Chcemy dodać taką cyfrę kontrolną, która doprowadzi sumę do najbliższej wielokrotności 10, która wynosi 80. Ta liczba to 7, która jest rzeczywiście cyfrą kontrolną na kodzie kreskowym butelki coli.

Poniższy program interaktywny może być używany do wykonywania za ciebie obliczeń.
Aby upewnić się, że rozumiesz proces, sam musisz wykonać niektóre czynności; ten program interaktywny może być używany do szerokiej gamy systemów z cyfrą kontrolną.
Aby sprawdzić numer GTIN-13, wprowadź pierwsze 12 cyfr w miejsce przy którym jest napisane "Wprowadź tutaj numer".
Mnożniki dla GTIN-13 można wprowadzić jako "131313131313" (co druga cyfra pomnożona przez 3).
To da iloczyny każdej z 12 cyfr pomnożonych przez odpowiednią liczbę.
Powinieneś samodzielnie obliczyć sumę iloczynów (liczby w okienkach) i ją wpisać.
Następnie otrzymasz resztę po podzieleniu przez 10.
Aby obliczyć sumę kontrolną, należy obliczyć cyfrę potrzebną do dopełnienia tej liczby do 10 (na przykład, jeśli reszta to 8, cyfra kontrolna to 2).
Jeśli reszta to 0, to cyfra kontrolna również wynosi 0.

{interactive name="checksum-calculator" type="in-page"}

{comment}

.. xjrm PLEASE INSERT THE GTIN-13 DIAGRAM HERE

{comment end}

Spróbuj tego z jakimiś innymi kodami kreskowymi.
Teraz popatrz, co dzieje się w obliczeniach, gdy zmienia się cyfra, lub dwie zamieni się miejscami.

Algorytm sprawdzania, czy numer kodu kreskowego został poprawnie wprowadzony, jest bardzo podobny.
Można obliczyć cyfrę kontrolną i porównać ją z 13-tą cyfrą, ale prościej jest wprowadzić wszystkie 13 cyfr.

Pomnóż co drugą cyfrę (począwszy od drugiej cyfry) przez 3, a pozostałe przez 1. Łącznie z 13. cyfrą, która jest mnożona przez 1.
Dodaj wszystkie pomnożone liczby, aby otrzymać *sumę*.
Jeśli ostatnia cyfra sumy wynosi 0, numer został wprowadzony poprawnie.
(To oznacza, że reszta z dzielenia przez 10 wynosi 0).

{panel type="curiosity" summary="Wyliczanie sumy kontrolnej w pamięci"}

W przypadku 13-cyfrowych kodów kreskowych szybkim sposobem dodania sumy kontrolnej, dającym się zrobić w pamięci (przy pewnej wprawie), jest wzięcie osobno liczb, które mają być pomnożone przez 3, dodanie ich, a następnie pomnożenie przez 3. Dla przykładu powyżej (9300675032247) dwie grupy liczb to 9+0+6+5+3+2+7=32 i 3+0+7+0+2+4=16. Więc dodajemy 32 + 16x3, co daje sumę 80 łącznie z cyfrą kontrolną.

Aby było jeszcze łatwiej, przy każdym dodawania wystarczy pamiętać ostatnią cyfrę, ponieważ pozostałe cyfry nigdy nie wpłyną na końcowy wynik.
Na przykład pierwsze dodawanie powyżej zaczyna się od 9+0+6, więc możesz powiedzieć, że daje to 5 (zamiast 15) i nadal otrzymać ten sam wynik.
Następna cyfra (5) zmienia sumę na 0 i tak dalej.
Oznacza to również, że możesz grupować cyfry, które razem dają 10 (jak 1 i 9 lub 5 i 5), i je zignorować.
Na przykład w drugiej grupie 3+0+7 na początku sumuje się do 0, a jedyną sumą, która się będzie liczyć jest 2+4, co daje w wyniku 6.

Nawet mnożenie będzie w porządku, jeśli po prostu weźmiesz ostatnią cyfrę.
W powyższym przykładzie oznacza to, że kończymy wyliczając 6x3, co daje 8 (nie 18); w oryginale było 16x3, co daje 48, ale jedyną liczącą się cyfrą będzie ostatnie 8.

Wszystkie te skróty mogą bardzo ułatwić liczenie sumy w pamięci.
{panel end}

{panel type="teacher-note" summary="Sprawdzanie a obliczanie"}

Uczniowie powinni być w stanie rozpoznać związek między tymi dwoma algorytmami (obliczaniem liczby w porównaniu z dodawaniem wszystkich 13 cyfr żeby je sprawdzić). Ponieważ 13. cyfra znajduje się na pozycji o nieparzystym numerze, zostaje pomnożona przez 1 w drugim algorytmie, zanim zostanie dodana do sumy.
Ponieważ cyfra kontrolna została wybrana tak, aby ostatnia cyfra sumowała się do wielokrotności 10 (która zawsze kończy się na 0), to jeśli liczba w drugim algorytmie została poprawnie wprowadzona, suma też będzie kończyła się na 0.

{panel end}


{panel type="extra-for-experts" summary="Dlaczego ten algorytm działa tak dobrze?"}

Aby być skutecznym, algorytm musi zapewnić, że pomnożone cyfry nie zsumują się do wielokrotności 10, jeśli tylko cyfry zostaną nieznacznie zmienione. Wybór mnożników wpływa na prawdopodobieństwo wykrycia niewielkich zmian w danych wejściowych. Możliwe jest matematyczne przeanalizowanie tego, jakie rodzaje błędów da się wykryć.

Cyfra kontrolna kodów kreskowych jest opisana w [rozdziale o korekcji błędów](chapters/code-error-control.html). Zasadniczo co druga cyfra jest mnożona przez 3, a suma tych wielokrotności jest dodawana do pozostałych cyfr.

Spójrzmy na kilka mniejszych przykładów z 5 cyframi (4 cyfry normalne i cyfra kontrolna), ponieważ te same pomysły będą miały zastosowanie do 13 cyfr.

Jeśli potrzebujemy cyfry kontrolnej dla 8954, obliczalibyśmy (8x1)+(9x3)+(5x1)+(4x3)=52, a aby zwiększyć tę wartość do 60, musimy dodać 8. Czyli pełnym numerem będzie 89548.

Pierwszą rzeczą, którą powinniśmy zauważyć jest to, że tylko cyfra jedności (ostatnia cyfra) każdej dodanej liczby ma wpływ na cyfrę kontrolną. 8+27+5+12=52 i 8+7+5+2=22 (patrzymy tylko na ostatnią cyfrę każdego dodawanego numeru). Obie liczby kończą się na 2, a zatem potrzebują 8, aby utworzyły najbliższą wielokrotność 10. Możesz dostrzec dlaczego tak jest, jeśli zauważysz, że "2" i "1" które zostały wycięte z kolumny dziesiątek, dają 10+20=30, co jest wielokrotnością 10. Odejmowanie ich wpływa tylko na kolumnę dziesiątek i wyżej. Tak jest zawsze i dlatego możemy uprościć problem, dodając do sumy tylko cyfrę jedności każdej liczby. (Może to również służyć jako skrót do obliczania sumy kontrolnej w pamięci).

*Ochrona przed pojedynczymi błędami*

Przyjrzyjmy się teraz dlaczego zmiana *jednej* cyfry w liczbie na inną cyfrę *zawsze* zostanie wykryta za pomocą tego algorytmu. Każda cyfra będzie dodawać liczbę od 0 do 9 do sumy (pamiętajmy, że teraz zależy nam tylko na kolumnie jedności). Skoro zmiana cyfry spowoduje, że doda ona inną liczbę do sumy, niemożliwe będzie żeby suma ciągle dawała wielokrotność 10. Pamiętaj, że każda cyfra jest pomnożona przez 1 lub 3, zanim jej kolumna jedności zostaje dodana do sumy.

Liczba pomnożona przez 1 zawsze będzie w całości dodana do sumy. Jeżeli na przykład cyfra miała wynosić 9, żadna inna pojedyncza cyfra nie może dodać 9 do sumy. Więc cyfry pomnożone przez 1 są w porządku.

Ale co z liczbami pomnożonymi przez 3? Aby odpowiedzieć na to pytanie, musimy spojrzeć na to, jaki wkład każda inna cyfra wnosi do sumy kiedy się ją pomnoży przez 3.

- 1 -> 3
- 2 -> 6
- 3 -> 9
- 4 -> 2 (od 1*2*)
- 5 -> 5 (od 1*5*)
- 6 -> 8 (od 1*8*)
- 7 -> 1 (od 2*1*)
- 8 -> 4 (od 2*4*)
- 9 -> 7 (od 2*7*)
- 0 -> 0

Patrząc na kolumnę po prawej stronie widać, że żadna liczba się nie powtarza. Oznacza to, że nie ma takich cyfr, które wnosiłyby do sumy tę samą wartość, gdy się je pomnoży przez 3!

Stąd właśnie wiemy, że wszystkie jednocyfrowe błędy zostaną wykryte.

*Zabezpieczenie przed zamianą sąsiednich cyfr*

Znacznie trudniej dostrzec dlaczego algorytm jest w stanie chronić przed większością błędów zamiany cyfr.

Jeśli dwie cyfry są obok siebie, jedna z nich musi być pomnożona przez 1, a druga przez 3. Jeśli są zamienione - to na odwrót. Na przykład, jeśli poprzednio wymieniony numer 89548 zostanie zmieniony na 8*59*48, wówczas do sumy dodaje się (5x3)+(9x1)=24 zamiast (9x3)+(5x1)=32. Ponieważ cyfry jedności 24 i 32 mają różne wartości, liczba dodana do sumy jest różna, a zatem błąd zostanie wykryty.

Ale czy są przypadki, w których cyfry jedności sum będą takie same? Innym sposobem spojrzenia na problem jest pobranie pary wierszy z powyższej tabeli, na przykład:

- 8 -> 4
- 2 -> 6

Pamiętaj, że pierwsza kolumna określa, ile wniosą do sumy cyfry pomnożone przez 1, a druga kolumna - cyfry pomnożone przez 3. Ponieważ sąsiednie cyfry są pomnożone przez inną wartość (jedna przez 3 a druga o 1), zostaną dodane liczby leżące po przekątnej w wybranej parze.

Jeśli na przykład pierwsze 2 cyfry w liczbie to "28", dodamy 2+4=6 do sumy. Jeśli zostaną zamienione miejscami, dodamy 8+6=14, co odpowiada 4, ponieważ wielokrotności "10" nie mają wpływu na sumę. 8+6 i 2+4 leżą na przekątnej pary!

- *8* -> **4**
- **2** -> *6*

Zatem pytanie brzmi: czy widzisz jakieś pary, w których suma przekątnych dawałaby tę samą wartość? Jest taka para!

*Ochrona przed błędami podwojenia*

Błąd podwojenia polega na tym, że cyfra, która powtarza się dwukrotnie w liczbie, zmienia się na inną cyfrę, która powtarza się dwukrotnie. Na przykład, jeśli mamy liczbę "22" w numerze, ktoś może jakoś ją zmienić na "88".

Gdy dwie liczby są obok siebie, jedna jest pomnożona przez 3, a druga przez 1. Tak więc wartość wniesiona do sumy jest sumą wiersza danej liczby w powyższej tabeli.
Na przykład 2 ma rząd "2->6". Oznacza to, że 2+6=8 zostanie dodane do sumy z powodu tych dwóch cyfr.

Jeśli dowolne wiersze sumują się do tej samej liczby, może to stanowić problem. Gdy suma przekracza 10, kolumna dziesiątek została usunięta.

- 1 -> 3 dodaje się do "4"
- 2 -> 6 dodaje się do "8"
- 3 -> 9 dodaje się do "2"
- 4 -> 2 dodaje się do "6"
- 5 -> 5 dodaje się do "0"
- 6 -> 8 dodaje się do "4"
- 7 -> 1 dodaje się do "8"
- 8 -> 4 dodaje się do "2"
- 9 -> 7 dodaje się do "6"
- 0 -> 0 dodaje się do "0"

Niektóre wiersze sumują się do tej samej liczby! Ponieważ zarówno 4, jak i 9 dodają się do 6, błąd nie zostanie wykryty, jeśli w numerze "44" zostanie zamienione na "99"!

Wiersze, które nie sumują się do tej samej liczby, zostaną wykryte. Z powyższego przykładu wynika, że jeśli 22 zmieni się na 88, zostanie to wykryte, ponieważ 22 dodaje się do 8, a 88 dodaje się do 2.

*Błąd, który nigdy nie zostanie wykryty*

Innym błędem, czasem przez ludzi popełnianym, jest błąd transpozycji ze skokiem. Polega on na tym, że zostają zamienione dwie cyfry, które mają jedną cyfrę między nimi, na przykład 812 zamienia się w 218.

Para cyfr, które są od siebie oddzielone jedną cyfrą, będzie zawsze mnożona przez te same wartości - 1 lub 3. Oznacza to, że zmiana pozycji liczb nie wpływa na to, przez co są pomnożone, a więc nie wpływa na sumę. Tak więc tego rodzaju błąd nigdy nie zostanie wykryty.

{panel end}
{comment}
End of extra-for-experts
{comment end}

{panel type="project" summary="Projekt z sumą kontrolną"}

Następujący program interaktywny wygeneruje losowe numery wybranego typu (np. numery ISBN dla książek).
Te numery są losowe i nie są oparte na numerach rzeczywistych książek (ani kont bankowych!)
Oznacza to, że możesz wykonać ten projekt bez konieczności proszenia kogokolwiek o podanie swoich danych osobowych, takich jak numery kart kredytowych (w rzeczywistości nie powinni podawać ci tych informacji!).

Chociaż numery z tego programu interaktywnego są losowe, ich cyfry kontrolne są obliczane przy użyciu odpowiedniej metody, więc możesz użyć ich jako przykładów w twoim projekcie.
W rzeczywistości nie wszystkie z nich będą poprawne, więc jednym z twoich wyzwań jest ustalenie które są w porządku!

{interactive name="number-generator" type="in-page"}

Twój projekt polega na wybraniu sumy kontrolnej innej niż 13-cyfrowe kody kreskowe i sprawdzeniu, w jaki sposób jest obliczana (wszystkie używają nieco różnych mnożników).
Powinieneś pokazać, jak działają (używając programu interaktywnego, jeśli chcesz) i odkryć, które z wygenerowanych numerów są nieprawidłowe.

ISBN-10 jest szczególnie skuteczny i możesz spróbować sprawdzić, dlaczego tak jest.

{interactive name="checksum-calculator" type="iframe"}

{panel end}

{comment}

.. Cyfry kontrolne na numerach kart kredytowych
.. ----------------------------------------------------------------------------------------------------------------

.. Numery kart kredytowych również mają cyfry kontrolne. Mogą one być używane przez systemy zakupów online w celu upewnienia się, że wprowadzony numer karty kredytowej został wprowadzony poprawnie, zanim będą musiały sprawdzić w banku, czy numer istnieje. Nie stanowi to dobrej ochrony przed oszustwami, ale sprawdza, czy prawowity użytkownik nie popełnił prostego błędu, który sprawia, że wygląda na to, że próbuje popełnić oszustwo lub czy nie została wpisana całkowicie losowa liczba. Numer karty kredytowej zawiera 16 cyfr: 15 cyfr, które tworzą numer, a ostatnia cyfra to cyfra kontrolna.

Zanim przejdziemy do dalszych rozważań nad numerami kart kredytowych, musimy wziąć pod uwagę kilka kwestii etycznych i dotyczących prywatności. O ile numery kart kredytowych nie są tajne, tak jak adres domowy, nie podałbyś tak po prostu każdemu numeru karty kredytowej. Są oszuści, którzy zbierają numery kart kredytowych i próbują korzystać z kart kredytowych innych osób. (Jednym z głównych powodów istnienia Paypala jest to, że ukrywa on numer karty kredytowej przed sprzedawcą i tylko Paypalowi trzeba ufać, a nie każdej osobie, u której dokonujesz płatności w Internecie.)

Nie jest dobrym pomysłem włączenie do ocenianego zadania domowego eksperymentów, które zawierają numer twojej karty kredytowej ani numer karty kredytowej rodziców. Trzeba też uważać na zmyślone numery kart kredytowych, ponieważ numer, który wymyślisz, może być czyimś numerem karty kredytowej. Istnieje zakres numerów kart kredytowych, które są używane tylko jako numery testowe, a zaczyna się od 5413 30. Jeśli podajesz przykłady dotyczące kart kredytowych, zalecamy, aby w zadaniach używać numerów z tego zakresu. Możesz użyć następującego generatora, aby wygenerować testowe numery kart kredytowych z tego zakresu.

.. JACK PUT THE CREDIT CARD NUMBER GENERATOR HERE

.. Poniższy program interaktywny pozwala eksperymentować z numerami z powyższego generatora i zobaczyć, jakie rodzaje błędów są wykrywane, a jakie nie (wykorzystaj informacje z poprzednich sekcji, aby poprowadzić eksperymenty). Pamiętaj, że akceptuje on tylko numery z powyższego generatora, ponieważ nie chcemy, abyś sprawdzał numery prawdziwych kart kredytowych za pomocą tego programu interaktywnego!


.. Algorytm obliczania cyfr kontrolnych numeru karty kredytowej
.. ---------------------------------------------------------------------------------------------------------------------------

{comment end}

### The whole story!

Kody omówione w tym rozdziale są szeroko stosowane, ale kody najczęściej używane do przechowywania danych są bardziej wyrafinowane, ponieważ muszą radzić sobie z bardziej złożonymi błędami niż zmiana pojedynczego bitu.
Na przykład, jeśli płyta CD jest porysowana, albo dysk twardy ma małe uszkodzenie, prawdopodobnie wpłynie to na wiele sąsiednich bitów.
Systemy te wykorzystują kody oparte na bardziej zaawansowanej matematyce.
Najczęściej używanymi kodami do przechowywania i przesyłania danych są [kody Reeda-Solomona](https://pl.wikipedia.org/wiki/Kodowanie_korekcyjne_Reeda-Solomona) i [cykliczny kod nadmiarowy (CRC)](https://pl.wikipedia.org/wiki/Cykliczny_kod_nadmiarowy).
W przypadku numerów czytelnych dla człowieka, takich jak kody kreskowe, numery bankowe, numery podatkowe, numery PESEL itd., najpowszechniejsze są [sumy kontrolne](https://pl.wikipedia.org/wiki/Suma_kontrolna), a [algorytm Luhna](https://pl.wikipedia.org/wiki/Algorytm_Luhna) jest jednym z najczęściej używanych.
Większe sumy kontrolne są również używane do sprawdzania, czy pliki zostały pobrane poprawnie.
Metoda parzystości jest rodzajem [kodu Hamminga](https://pl.wikipedia.org/wiki/Kod_Hamminga).


## Further reading

###Useful Links
- [CS Unplugged Parity Trick](http://csunplugged.org/error-detection)
- [CS4FN](http://www.cs4fn.org/) has a [free book](http://www.cs4fn.org/magic/) that contains the Parity Trick and a number of other tricks related to computer science.
- Techradar has more [information about error detection and correction](http://www.techradar.com/news/computing/how-error-detection-and-correction-works-1080736)
- [An explanation of error correcting codes](http://www.multiwingspan.co.uk/as1.php?page=error)
- [A check digit calculator for common bar codes](http://www.gs1.org/barcodes/support/check_digit_calculator)
