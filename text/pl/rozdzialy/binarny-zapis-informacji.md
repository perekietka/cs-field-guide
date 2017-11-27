# Binarny zapis informacji

{panel type="teacher-note" summary="Math in Data Representation"}
Ćwiczenia w tym rozdziale wymagają wykonywania prostych obliczeń. Można je wykonać ręcznie lub w arkuszu kalkulacyjnym.
{panel end}

## Widok z lotu ptaka

Komputery to narzędzia do przetwarzania informacji. Użytkownik komputera może tworzyć, modyfikować, czy po prostu przeglądać (oglądać, słuchać itd.) informacje, zapisane w dokumentach tekstowych, plikach graficznych czy wideo, skoroszytach arkusza kalkulacyjnego czy zbiorach baz danych. Gry komputerowe i inne programy-symulacje to przykłady tzw. wirtualnej rzeczywistości, która istnieje tylko w postaci informacji zapisanej pamięci komputera i wyświetlonej (po jej interpretacji) na ekranie monitora. Komputery pozwalają na wykonywanie obliczeń liczbowych, jak i na przesyłanie informacji przez sieć komputerową. To wszystko byłoby niemożliwe, gdyby nie wymyślono jakiegoś sposobu na zapis (reprezentację) różnego rodzaju informacji w pamięci operacyjnej komputera, na dysku twardym i ich przesyłania przez sieć komputerową.   

Kluczową koncepcją, która pozwoliła uprościć trudności związane z projektowaniem i produkcją komputerów, ale również wpłynęła na niezawodność ich działania, jest koncepcja dwuwartościowego (dwustanowego) zapisu wszelkiego rodzaju informacji. Czasami mówi się o reprezentacji zerojedynkowej (0-1), choć w praktyce (w realizacji fizycznej) możemy mieć do czynienia z czymkolwiek, co może przyjmować dwa stany. Na przykład dla pamięci elektronicznej będzie to oznaczać wysoką lub niską wartość napięcia prądu elektrycznego, a dla tradycyjnego dysku twardego – namagnesowanie małych fragmentów warstw magnetycznych (północ – południe).

Pomysł, by *wszystko* w naszym cyfrowym świecie zapisywać z użyciem tylko dwóch wartości może wydawać się nieco fantastyczny. Oto ćwiczenie, które ukaże, jak zapisywać liczby, używając zestawu kart, które z jednej strony mają białe tło, a z drugiej strony -- czarne.  
Zacznij od wskazania ostatniej karty (po prawej). Wtedy zobaczysz, że na stronie z białym tłem znajduje się pojedyncza czarna kropka.
Następnie wskaż na sąsiednią kartę, by na odwrocie zobaczyć dwie czarne kropki. Ile kropek kropek zobaczysz po odwróceniu kolejnej karty? Sprawdź! Staraj się odgadnąć liczbę kropek znajdujących się na kolejnych kartach.

{interactive name="binary-cards" type="whole-page" text="Binary Cards" parameters="digits=5&start=BBBBB"}

Kolejne wyzwanie brzmi: Które karty należy odwrócić, aby łączna liczba kropek była równa 22? Jaka będzie odpowiedź dla liczby kropek równej: 11, 29 lub 19? Czy jakiejś liczby kropek nie sa się uzyskać? Możesz zacząć zliczanie od 0, jeśli chcesz.

{panel type="teacher-note" summary="Wskazówki dla nauczyciela"}

W czasie zajęć szkolnych zamiast interaktywnego apletu, można użyć papierowych kart.

Jeśli uczniowie napotykają trudności w znalezieniu odpowiedzi na powyższe pytania, nauczyciel powinien wskazywać kolejne karty z lewej i stawiać pytania: "Czy karta z 16 kropkami jest porzebna? A karta z 8 kropkami?" itd.
Uczniowie szybko przekonają się, że skuteczna jest metoda zachłanna: albo liczba kropek na karcie jest za duża, albo karty należy użyć.

Podczas pracy z ćwiczeniem uczniowie powinni dostrzeć pewne prawidłowości.  
Na przykład: Karta z jedną kropką jest odwracana, gdy pytanie dotyczy liczby nieparzystej.

{panel end}

{panel type="spoiler" summary="Rozwiązanie"}

Można zauważyć, że liczba kropek na kolejnej karcie jest dwa razy większa niż na sąsiedniej (po prawej).
Dostrzeżenie tej prawidłowości jest istotne dla zrozumienia cyfrowego zapisu danych w komputerze.

Aby usyskać liczbę kropek równą 22 potrzebujemy układu kart: "białe, czarne, białe, białe, czarne".
Liczbę 11 przedstawimy jako: "czarny, biały, czarny, biały, biały".
Liczbę 29 jako: "biały, biały, biały, czarny, biały".
Liczbę 19 jako: "biały, czarny, czarny, czarny, biały".
{panel end}

Nietrudno odkryć, że dowolną liczbę z zakresu od 0 do 31 można przedstawić z użyciem 5 kart.
Informację o liczbie, przedstawioną na karcie, można odczytać używając tylko dwóch słów: czarne lub białe.
Na przykład informacja o liczbie 22 to ciąg słów: "biała, czarna, biała, biała, czarna"
Każdy ciąg złożony ze ciągu słów czarne lub białe można zaś jednoznacznie przypisać pewnej liczbie.
Np. "czarne, czarne, białe, białe, białe" odpowiada liczbie 7.
Idea dwustanowego (binanrego) zapisu informacji stanowi podstawę zapisu danych w jakimkolwiek użądzeniu cyfrowym.

Gdy chcemy przedstawić na papierze to, co zapisano w komputerze, to zazwyczaj uzywamy „0” dla ilustracji jednego ze stanów i „1” – dla drugiego z nich. Oznacza to np., że fragment pamięci elektronicznej komputera, dla którego wartości napięcia elektrycznego to:   

```
„niska”, „niska”, „wysoka”, „niska”, „wysoka”, „wysoka”, „wysoka”, „wysoka”, „niska”, „wysoka”, „niska”, „niska”
```

będziemy przedstawiać jako ciąg cyfr

```
0 0 1 0 1 1 1 1 0 1 0 0
```

Taka notacja jest powszechnie używana. Należy jednak pamiętać, że sformułowanie typu „komputer zapisuje informacje w postaci ciągu 0 i 1” jest skrótem myślowym. Nie ma sposobu, żeby zrobić to bezpośrednio – komputery posługują się własnościami fizycznymi takimi jak wysokie i niskie napięcie, namagnesowanie północ/południe, czy ciemne i jasne materiały.

{panel type="jargon-buster" summary="bity"}

Ponieważ używa się tylko dwóch cyfr: 0 i 1, więc mówi się też o systemie dwójkowym lub binarnym (ang. binary system) i cyfrach dwójkowych (binarnych), zwanych bitami (ang. bit to skrót od słów „binary digit”). Pojęcie bitu jest jednym z najbardziej podstawowych w języku informatyków. 

{panel end}

Każdy utworzony przez Ciebie plik, każde zdjęcie zapisane na dysku komputera, każdy dokument pobrany z Internetu to po prostu krótszy lub dłuższy ciąg bitów, czyli cyfr dwókowych. Dlatego mówi się o technologiach *cyfrowych*!

Choć informatycy na co dzień nie zajmują się bezpośrednio analizowaniem tych ciągów bitów, to wiedza na temat zasad binarnego zapisu informacji jest naprawdę istotna, gdyż pozwala np. na oszacowanie przestrzeni na dysku, potrzebnej do zapisu danych z odpowiednią jakością. Podczas lektury tekstów z różnych dziedzin informatyki możesz napotkać określenia typu „24-bitowy kolor”, „128-bitowe szyfrowanie”, „32-bitowy adres IP” czy „8-bitowy kod ASCII”. Wiedza na temat zapisu binarnego jest niezbędna informatykowi do oszacowania ilości miejsca na dysku potrzebnego do zapisania wysokiej jakości informacji o kolorze, określenia bezpieczeństwa wybranej metody szyfrowania, do wyboru odpowiedniej długości klucza podczas projektowania bazy danych, czy zastosowania kodowania odpowiedniego dla teksów języka, w których występują znaki spoza alfabetu języka angielskiego.

Ten rozdział przedstawia różne metody, jakie są używane w systemach komputerowych do zapisania różnego rodzaju informacji za pomocą ciągów bitów oraz to, jak wybór metody wpływa na koszt i jakość tego, co robimy na komputerze i czy w ogóle da się to zrobić. 

## Zaczynamy

Na początek przyjrzymy się kodowi (alfabetowi) Braille'a, który umożliwia zapisywanie i odczytywanie tekstów osobom niewidomym i niedowidzącym. Mimo, że system brajlowski nie ma nic wspólnego z komputerami, to stanowi znakomite wprowadzenie do tematu tego rozdziału przewodnika po informatyce.

{panel type="additional-information" summary="Zapis znaków Braille'a"}
Dla uproszczenia ideę tzw. sześciopunku można zilustrować używając sześciu małych kół ułożonych w dwóch kolumnach po trzy punkty w każdej.
Koła z zamalowanym wnętrzem będą ilustracją punktów wypukłych. 
{panel end}

### Czym jest kod Braille'a?

Ponad 200 lat temu 15-letni Francuz wymyślił system zapisu tekstu (liter, cyfr, znaków przestankowych itd.) z użyciem tzw. sześciopunktów jako kombinację sześciu wypukłych punktów ułożonych w dwóch kolumnach po trzy punkty w każdej. System stał się bardzo popularny wśród osób niewidomych, gdyż umożliwił względnie szybki i niezawodny sposób „czytania” tekstu. 
Alfabet Louisa Braille'a można uznać za jeden z pierwszych przykładów „binarnego” zapisu informacji – używa się w nim bowiem tylko dwóch znaków (wypukły punkt lub jego brak), a mimo to odpowiednie ich kombinacje pozwalają na wydawanie całych książek, zarówno fachowych, jak i literatury pięknej. 

{image filename="braille-alphabet-diagram.jpg" alt="Alfabet Braille'a"}

Sprawdźmy, ile różnych wzorców (znaków) w alfabecie Braille's można uzyskać, używając sześciopunktu. 
Gdyby system Braille'a używał kombinacji tylko dwóch (pary) punktów, to wzorców (znaków) byłyby cztery. 
Gdyby używał kombinacji trzech punktów, to byłoby ich osiem.

{image filename="two-and-three-dot-combinations-diagram.png" alt="Combinations of both two and three dots"}

Można było zauważyć, że w przypadku użycia trzech punktów liczba wzorców jest dwa razy większa niż dla przypadku dwóch punktów. Okazuje się, że dodanie każdego kolejnego punktu skutkuje podwojeniem liczby wzorców . To znaczy, że dla czterech punktów liczba wzorców będzie równa 16, dla pięciu – 32, a dla sześciu – 64. Dlaczego? Potrafisz to wyjaśnić?

{panel type="spoiler" summary="Wyjaśnienie"}
Po dodaniu czwartego punktu liczba wzorców podawaja się, bo nowy punkt można dołączyć do każdego wzorca 3-punktowego na dwa sposoby: jako punkt wypukły lub niewypukły.
Podobnie można objaśnić przyczynę podwojenia się liczby wzorców po dodaniu czwartego punktu.
To rozumowanie można uogólnić dla dowlnej liczby punktów.
{panel end}

{panel type="teacher-note" summary="O znaczeniu zrozumienia idei podawajania")}
Ta koncepcja (podwajanie się liczby wzorców) ma zasadnicze znaczenie dla zrozumienia istoty zapisu binarnego: każdy dodatkowy bit pozwala dwukrotnie zwiększyć liczbę wartości, które da się zapisać. Wybór odpowiedniej liczby bitów dla zapisu danych w konkretnej sytuacji jest bardzo ważny. Na przykład: 101-bitowy klucz szyfrowania jest dwa razy trudniej złamać, choć liczba użytych bitów jest większa tylko o 1%! 
{panel end}

W obrębie sześciopunktu można uzyskać 64 wzorce (znaki). To wystarcza na oznaczenie liter alfabetu i innych znaków, takich jak np. cyfry czy znaki interpunkcyjne.

### Kod Braille'a a binarny zapis informacji

Kod Braille'a jest ilustracją zapisu z użyciem bitów. Istotnie, rozróżnia się dwa stany punktu (wypukły lub niewypukły), a każdy z wzorców tzw. sześciopunktu odpowiada innemu znakowi alfabetu.
Na przykład litera m może być zapisana jako 110010, gdzie "1" oznacza punkt wypukły, a "0" niewypukły (przy założeniu, że czytamy od lewej do prawej i z góry na dół). 
W informatyce takich ciągów "1" i "0" używa się w analogiczny sposób do ukazania sposobu zapisu informacji w komputerze.

Alfabet Braille'a jest dobrą ilustracją przyczyn użyteczności zapisu binarnego. Można sobie wyobrazić system używający trzech rodzajów kropek: niewypukłych, półwypukłych i wypukłych. Z pewnością wprawny czytelnik potrafiłby je rozróżnić, a wtedy do uzyskania 64 znaków wystarczyłaby kombinacja czterech kropek. Kłopot w tym, że potrzebne byłyby bardziej dokładne (precyzyjne) urządzenia do tworzenia kropek, a ludzie musieliby więcej uwagi poświęcać rozróżnianiu kropek podczas „czytania”. Wystarczyłoby wtedy, że kartka zostałaby przygnieciona, nawet bardzo nieznacznie, a informacja stałby się nieczytelna.

Współczesne urządzenia cyfrowe prawie zawsze używają systemu dwustanowego (binarnego) do zapisu informacji. Przyczyny są podobne: dyski komputerowe i pamięć elektroniczna jest po prostu tańsza i mniejszych rozmiarów, jeśli wystarczy rozróżnić między dwoma skrajnymi wartościami (jak np. wysokie i niskie napięcie), a nie trzeba mierzyć subtelnych różnic w wartościach (np. między wartościami napięcia). 
Stosowanie systemu dziesiętnego byłoby niezwykle kosztowne.

{panel type="curiosity" summary="Komputery oparte o system dziesiętny"}
Dlaczego w technice komputerowej używa się systemu dwójkowego? Czy nie można by używać systemu dziesiętnego?
W przeszłości próbowano budować komputery oparte o system dziesiętny. Rozwiązania takie były wyjątkowo skomplikowane i kosztowne. Wymaganie, by rozróżniać 10 różnych stanów (wartości) oznacza większy stopień skomplikowania sprzętu do zapisu i odczytu (np. napięcia elektrycznego). O wiele łatwiej w praktyce realizować wymaganie, by rozróżniać dwa stany.

Bardziej pogłębione objaśnienie zalet praktycznych systemu binarnego znajduje się tutaj:

{video url="https://www.youtube.com/watch?v=thrx3SBEpL8"}
{panel end}


## Liczby

{panel type="teacher-note" summary="Rozgrzewka bez komputera"}
W ramach rozgrzewki można użyć ćwiczenia opisanego w scenariuszu zajęć projektu CS Unplugged [http://csunplugged.org/binary-numbers](http://csunplugged.org/binary-numbers). Pojęcie systemu dwójkowego (binarnego) jest tam wprowadzone krok po kroku z użyciem wyłączniem prostych operacji zliczania i dodawania. 

Dostępne jest interaktyne narzędzie online, w którym odwzorowano tradycyjne karty czarno-białe.
{interactive name="binary-cards" type="whole-page" text="Binary Cards"}

Zdecydowaliśmy, że ten rozdział rozpocznie się od przypomnienia, czym jest system liczbowy. Ktoś mógłby sądzić, że takie matematyczne podejście "odstraszy" młodego czytelnika. Tymczasem większość uczniów powinna być dobrze obeznana z używaną w tekście terminologią, gdyż była wprowadzona w początkowych klasach szkoły podstawowej. Na lekcjach matematyki w pierwszej klasie szkoły średniej młodzież uczy się o notacji wykłądniczej, więc zapis {math}541 = 5 \times 10^2 + 4 \times 10^1 + 1 \times 10^0{math end} jest im dobrze znany. Tekst poniżej jest przypomnieniem, a nie objaśnianiem pojęcia systemu liczbowego po raz pierwszy.
System dwójkowy (binarny) jest system liczbowym o podstawie 2. Zestawienie go z dobrze znanym młodziezy systemem o podstawie 10 powinno ułatawić zrozumienie istoty zagadnienia.
{panel end}

W tym rozdziale przyjrzymy się temu, jak w komputerach zapisuje się liczby. Zaczniemy od powtórzenia, czy jest system liczbowy o podstawie 10, którym posługujemy się na co dzień. Później spojrzymy na system binanry jak na sytem liczbowy o podstawie 2. W końcu będziemy chcieli wyjaśnić, jak zapisuje się w komputerze liczby ujemne i liczby niecałkowite.

### Istota dziesiętnego systemu liczbowego

Człowiek posługuje się zwykle pozycyjnym systemem liczbowym o podstawie 10 (zwanym też dziesiętnym). Warto przypomnieć sobie koncepcję zapisu **pozycyjnego**, gdyż system dwójkowy (binarny) jest również systemem pozycyjnym, choć używa się w nim mniejszej liczby cyfr! 

Przykład: W liczbie $123 cyfra 3 odpowiada liczbie $3, ale już cyfra 1 odpowiada liczbie $100. 
Wartość (mnożnik) każdej z cyfr zależy od jej pozycji w zapisie. Mnożnik cyfry na danej pozycji jest 10 razy większy niż mnożnik cyfry na pozycji po prawej. W konsekwencji możemy mówić o jednościach, dziesiątkach, setkach, tysiącach, dziesiątkach tysięcy, setkach tysięcy, milionach itd. Na każdej z pozycji może wystąpić jedna z dziesięciu cyfr (0, 1, 2, 3, 4, 5, 6, 7, 8, 9).

Np. liczba 90 328 może być zapisana w postaci sumy: 

{math}90328 = 90000 + 300 + 20 + 8{math end}

Liczbę tę można zapisać w postaci rozwinięcia (szeregu potęgowego):

{math}90328 = (9 \times 10000) + (0 \times 1000) + (3 \times 100) + (2 \times 10) + (8 \times 1){math end}

Bardziej formalnie można napisać tak:

{math}90328 = (9 \times 10^4) + (0 \times 10^3) + (3 \times 10^2) + (2 \times 10^1) + (8 \times 10^0){math end}


The key ideas to notice from this are:

- System dzięsiętny używa 10 **cyfr** (ang. digits) -- 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.
- Liczby to ciągi cyfr.
- O cyfrach tworzących zapis liczby mówimy, że znajdują się na odpowiednich **pozycjach** odpowiednio: jedności, dziesiątek, setek, tysięcy itd. Na przykład w liczbie 90 328 cyfra 3 jest na pozycji setek, a cyfra 2 na pozycji dziesiątek.
- Cyfra pierwsza po prawej (na pozycji jedności) ma najmniejszą wartość, jest najmniej znacząca.
- Cyfra pierwsza po lewej ma największą wartość, jest najbardziej znacząca.
- Gdy stosujemy 10 cyfr, to wartość cyfry na danej pozycji w liczbie jest 10 razy większa od wartości cyfry na pozycji po jej prawej stronie.

All this probably sounds really obvious, but it is worth thinking about consciously, because binary numbers have the same properties.
To, co zapisano powyżej, może brzmieć jako coś oczywistego. Warto to jednak przeanalizować dokładniej, gdyż pełną analogię dostrzeżemy w własnościach zapisu binarnego.

### Zapis liczb całkowitych w systemie binarnym

{panel type="teacher-note" summary="Jak uczyć o liczbach binarnych?"}
Ten podrozdział jest niezbędny do zrozumiwania rozdziału o cyfrowym zapisie informacji o kolorach.

Zaskakująco częstwo w podręcznikach informatyki poświęca się wiele miejsca ilorazowej metodzie konwersji między systemami liczbowymi: binanrym i dziesiętnym. W praktyce informatycy prawie nigdy się nią nie posługują. Wydaje się, że ważniejsze jest rozumienie istoty zapisu binarnego i jego własności. Dla uczącego się kluczowe jest spostrzeżenie, że dodanie do binarnego zapisu liczby kolejnej cyfry oznacza *podwojenie* zakresu liczb, które da się zapisać z użyciem tylu cyfr. Poznanie pewnych prawidłowości właściwych zapisowi binarnemu i sprawne korzystanie z tej wiedzy przydaje się w wielu dziedzinach informatyki.
{panel end}

{panel type="teacher-note" summary="Binarne pianino"}
The "binary piano" is a simple binary conversion device that can be printed on paper, and enables students to experiment with these concepts physically.
Binarne pianino to prosty środek dydaktyczny do nauki pewnej metody konwersji między systemami liczbowymi. Po wydrukowaniu uczniowie mogą wykonać samodzielne eksperymenty, które pozwolą zrozumieć istotę konwersji.
Można je [pobrać stąd](files/binary-piano-UC.pdf)
Wersja szablonu z czterema kopiami pianina [jest tutaj](files/binary-piano-UC-4up.pdf).
Stosuje się zapis 9-bitowy. W sytuacji, gdy wprowadzamy pojęcie bajta, uczniowie mogą 9. bit ustawić na 0 (zignortować).
Obecność 9. bitu na wydruku ma następujące uzasadnienie dydaktyczne: łatwo znaleźć największą liczbę 8-bitową: od wartości dziesiętnej 9. bitu wystarczy odjąć 1.
{panel end}

Jak wspomniano wcześniej, komputery zapisują informacje używając bitów, czyli rozróżniając tylko dwa możliwe stany (dwustanowo). To oznacza, że w komputerze nie jest możliwe zapisanie liczby w systemie dziesiętnym, używając cyfr od 0 do 9, jak to czyni człowiek. Używany jest system o podstawie 2, zwany dwójkowym (binarnym).

W systemie binarnym (systemie o podstawie 2), można stosować wyłącznie dwie cyfry (0 i 1). W zapisie pozycyjnym mnożnik (wartość) każdej z cyfr jest więc dwa razy większy niż mnożnik cyfry po prawej stronie (inaczej niż w systemie dziesiętnym, gdzie tym czynnikiem jest 10).

{panel type="curiosity" summary="The Denary number system"}
System liczbowy o podstawie 10 (dziesiętny) w języku angielskim określa się słowami decimal lub denary. To drugie określenie, używane najczęściej w Wielkiej Brytanii, ma formę gramatyczną analogiczną do angielskiego binary (dwójkowy, binarny). Słowo "denary" ma ścisły związek z nazwą rzymskiej monety (denarius, po polsku: denar), która miała wartość 10 asów (wybijanych z miedzi lub brązu). 
{panel end}

Interaktywne narzędzie poniżej ma pomóc w zrozumieniu zasady zapisu binarnego. Warto wykonać kilka prób (ćwiczeń). Wartość dziesiętna liczby jest wyświetlana na końcu po prawej stronie.

{interactive name="base-calculator" type="whole-page" text="Binary Number Calculator"}

**Aby upewnić się, że właściwe posługujesz się narzędziem, sprawdź, czy po wpisaniu 101101 widzisz odpowiedź 45, po wpisaniu 100000 – 32, a po wpisaniu 001010 – 10 (dziesięć).**

{panel type="teacher-note" summary="Using the binary number interactive"}
Uczniowie powinni odkryć, że zapis binarny liczby zapisanej w systemie dziesiętnym mogą uzyskać cyfra po cyfrze (od lewej do prawej) postepując zachłannie w następujący sposób: cyfrę binarną ustawia się na 0 tylko i wyłącznie wówczas, gdy wartość dziesiętna odpowiednich pozycji w zapisie binarnym jest większa niż wartość dziesiętna, którą chcemy w tym momencie poddać konwersji.
Po wykonaniu kilku prób stanie się dla uczących oczywiste, co należy robić. Z pewnością nawet młdosi uczniowie mogą istotę algorytmu odkryć samodzielnie. W konsekwencji pozwoli im to zdobyć pewność siebie i sprawność w zadaniach konwersji. 
Jeśli pomoc nauczyciela okaże się konieczna, to warto posłużyć się konkretnym przykładem. Np. dla liczby 37 nauczyciel zaczyna od ustawienia wszystkich bitów na 0 za wyjątkiem liczby na pozycji 32 (która jest pierwszą nie przekraczającą 37) i nakierowuje ucznia na szukanie odpowiedzi o wartość bitu na pozycji odpowiadającej liczbie 16: ustawienie bitu na 1 oznaczałoby, że liczba jest niemniejsza niż 48, więc bit trzeba ustawić na 0. Podobnie jest dla bitu na pozycji o wartości 8. Kolejny bit (odpowiadający składnikowi 4) należy ustawić na 1 (dostajemy sumę: 36), następny na 0, a ostatni na 1 (suma: 37). Uzyskujemy zapis binarny: 100101.
Opis metody jest w podręczniku podany uczącym się. Lepiej jednak, jeśli wcześniej samodzielnie odkryją metodę drogą eksperymentów z binanrym pianinem.

W internecie można znaleźć wiele gier, które mogą pomóć zgłębić temat liczb binarnych. Jedna z nich to [Cisco Binary game](http://forums.cisco.com/CertCom/game/binary_game_page.htm).
Motywująco dla poznających prawidłowości właściwe zapisowi binarnemu może działać fakt ograniczenia liczby prób konwersji w grze.

Istnieje inny algorytm konwersji, zwany metodą ilorazową, który często pojawia się w podręcznikach, zwłaszcza w podręcznikach programowania. Ma tę własność, że dość łatwo można go zapisać w języku programowania, ale trudniej zrozumieć jego poprawność. 
Prezentacja tego algorytmu nie jest niezbędna do zrozumienia dalszej części rozdziału.
Cyfry binartne uzyskane w czasie działania algorytmu zapisuje się od prawej do lewej. Działa w następujący sposób: najmniej znaczący (skrajny prawy bit) ustawia się na 1, jeśli liczba zapisane dziesiętnie jest nieparzysta; w przeciwnym przypadku wartośc bitu jest równa 0. Następnie dzieli się liczbę przez 2 (w razie potrzeby zaokrąglając w dół do części całkowitej). Opisaną wyżej procedurę powtarza się dla kolejnych liczb uzyskanych w wyniku połowienia. Aż do momentu uzyskania 0 jako wyniku dzielenia przez 2.
{panel end}

Znajdź zapis biarny liczb 4, 7, 12 i 57.

Jaka jest największa liczba, jaką można uzyskać, posługując się tym narzędziem? Jaka jest najmniejsza? Czy jest jakaś liczba pomiędzy nimi, której nie jesteś w stanie uzyskać? Czy są liczby, które można zapisać w systemie binarnym na dwa różne sposoby? Odpowiedzi uzasadnij.

{panel type="spoiler" summary="Największe i najmniejsze liczby"}
- 000000, czyl 0 (dziesiętnie) to najmniejsza liczba.
- 111111, czyli 63 (dziesiętnie) to największa liczba.
- Wszystkie liczby całkowite z zakresu (0, 1, 2... 63) da się zapisać binarnie (każdą wyłącznie w jeden sposób). Dokładnie tak samo, jak w systemie dziesiętnym.
{panel end}

{panel type="teacher-note" summary="Zrozumienie jednoznaczności zapisu binarnego"}
Pytanie o jednoznaczność może być ciekawym wyzwaniem dla niektórych uczniów. Chodzi o to, że każdą liczbę można zapisać binarnym wyłącznie w jeden sposób; gdyby uczniowie mieli trudność w zrozumieniu uzasadnienia, to powinni przyjąć, że jednoznaczność zapisu istotnie ma miejsce. Proces formułowania przekonującego rozumowania może wyglądać tak: Uczeń otrzymuje zadanie zapisania pewnej liczby, np. 12, w systemie binarnym z użyciem 5 bitów. Skrajny lewy bit odpowiada wartości 16 (>12), więc należy ustawić go na 0 (ustawienie bitu na 1 na pewno nie pozwoli rozwiązać zadania). Dalej mamy bit o wartości 8. Nie jest możliwe zapisanie liczby 12 bez ustawienia tego bitu na 1 (suma wartości pozostałych bitów to 7). To oznacza, że 12 *musi* być zapisane jako 01100.

Innym sposobem na wykazanie jednoznczaności zapisu binarnego jest wyznaczenie liczby wszystkich ciągów 0 lub 1. Dla przypadku 5 bitów mamy 2x2x2x2x2 (tj. 32) różnych ciągów odpowiadających 32 liczbom z zakresu od 0 do 31 (przyporządkowanie jeden-do-jednego).
{panel end}

Prawdopodobnie jest już dla Ciebie jasne, że gdy lewy skrajny („najbardziej znaczący”) bit ustawiasz na 1, to wartość dziesiętną powiększasz o 32. Podobnie ustawiając bity położone dalej na prawo dodajesz odpowiednio 16, 8, 4, 2 i 1. Gdy bit ustawiasz na 0, wartość dziesiętna nie zwiększa się. Szukanie zapisu binarnego liczby jest więc związane z przedstawieniem liczby jako sumy niektórych lub wszystkich liczb ze zbioru: 32, 16, 8, 4, 2, 1, przy czym każda z liczb może wystąpić tylko raz.

{image filename="xkcd-1-to-10.png" alt="Gdy otrzymasz 11/100 punktów ze sprawdzianu z informatyki i będziesz twierdzić, że należy ci się dostateczny, to prawdopodobnie wymagać będziesz aktualizacji. " source="https://xkcd.com/953/"}

Wybierz liczbę mniejszą niż 61 (np. numer Twojego domu przy ulicy, wiek kolegi czy koleżanki, dzień miesiąca Twojego urodzenia).  Ustaw wszystkie cyfry binarne na 0, a następnie zacznij wybierać właściwe cyfry zaczynając od skrajnej lewej cyfry (32). Za każdym razem zdecyduj, czy wybrać 0 czy 1.
Czy stosujesz metodę prób i błędów? Na czym polega Twoja metoda zamiany (konwersji) liczb?

Czy potrafisz znaleźć zapis binarny liczby 23 **bez posługiwania** się narzędziem? A liczby 4, 0 i 32? Sprawdź teraz , czy dobrze myślisz, używając narzędzia. 

{panel type="challenge" summary="Counting in binary"}
Pomyśl, jak w sposób systematyczny liczyć w systemie binarnym, począwszy od 0. Tj. 0, 1, 2, 3 itd. aż do największej liczby możliwej do zapisania z użyciem sześciu bitów. 
Zacznij od odliczenia od 0 do 16 i spróbuj dostrzec jakąś zasadę. Wskazówka: Wyobraź sobie, że dodajesz 1 do liczby zapisanej dziesiątkowo, np. 7 + 1, 38 + 1, 19 +1, 99 + 1, 230 899 999 + 1 itd. Czy możesz ten sam pomysł zastosować dla liczb dwójkowych?

Pomyśl o tym, jak zastosować wiedzę o systemie dwójkowym (binarnym) do liczenia na palcach powyżej liczby 10. Jaką największą liczbę można „zapisać” używając dziesięciu palców? Wyobraź sobie, że będziesz używać też palców u nóg. Jaka wówczas będzie odpowiedź?
{panel end}

{panel type="spoiler" summary="Zliczanie binarne"}
Aby liczbę zapisaną binarnie powiększyć o 1 wystarczy w jej zapisie biarnym odnaleźć pierwszy od prawej bit ustawiony na 0, następnie ustawić go na 1, a wszytkie bity po jego prawej stronie ustawić na 0. (W połowie przypadków tym poszukiwanym bitem 0 będzie skrajny lewy bit.)
Używając pięciu palców można policzyć do 31. W przypadku 10 palców najwięszka liczba to 1023.
Na YouTube zobaczyć wiele przykładów wideo, na których ktoś liczby na palcach. Podczas prezentacji niektórzy posługują się rękawiczkami, na których odpowiednie palce są opisane liczbami: 16, 8, 4, 2, 1.
{panel end}

Co stałoby się, gdybyśmy mieli mniej niż sześć bitów? Przykład: Dla pięciu bitów, wartości na kolejnych pozycjach byłyby równe odpowiednio: 16, 8, 4, 2 i 1. Więc największą liczbą byłaby 11111, czyli 31 (dziesiętnie). Liczba 14 zapisana na pięciu bitach to 01110.

{panel type="Challenge" summary="Binarny zapis liczb"}
Zapisz podane liczby z użyciem odpowiedniej liczby bitów (o ile to możliwe).
- **101** na **7 bitach**
- **28** na **10 bitach**
- **7** na **3 bitach**
- **18** na **4 bitach**
- **28 232** na **16 bitach**
{panel end}

{panel type="spoiler" summary="Answers for above challenge"}
Odpowiedzi (dla zwiększenia czytelności cyfry pogrupowano po cztery od prawej)
- 101: **110 0101**
- 28: **00 0001 1100**
- 7: **111**
- 18: niemożliwe na 4 bitach
- 28 232: 0110 1110 0100 1000
{panel end}

Ważnym pojęciem związanym z liczbami binarnymi jest zakres wartości, którą można zapisać przy użyciu danej liczby bitów (cyfr). Pojedynczy bit wydaje się mało użyteczny, ale wystarczy do zapisania informacji np. o stanie pola wyboru tak/nie. Grupa ośmiu bitów jest już bardziej użyteczna – pozwala na zapis wartości od 0 do 255, a więc wystarczy do przechowania informacji o czyimś wieku, dniu miesiąca itd.

{panel type="jargon-buster" summary="Co to jest bajt?"}
Grupa ośmiu bitów (oktet) jest tak użyteczna, że ma swoją nazwę: **bajt** (ang. byte). Pamięć elektroniczna i przestrzeń dyskowa jest zwykle podzielona na bajty. Większe liczby są zapisywane z użyciem większej liczby bajtów. Przykład: Dwa bajty (16 bitów) pozwalają na przechowywanie liczb z zakresu od 0 do 65 535. Cztery bajty (32 bity) umożliwiają na zapis liczb aż do 4 294 967 295. Możesz sprawdzić, czy te liczby są poprawne, badając mnożniki odpowiadające bitom. Każdy kolejny bit oznacza podwojenie zakresu liczb.
{panel end}

W praktyce, architektura dzisiejszych komputerów wymusza zapis liczb z użyciem 16, 32 lub 64 bitów. To wielokrotności bajtów (oktetów bitów).

{panel type="curiosity" summary="Binary cakes -- preventing fires"}
Świeczki na torcie urodzinowym to przykład zastosowania systemu jedynkowego (unarnego).  Kolejne liczby tworzy się przez powtarzanie  znaku 1 tyle razy, ile wynika to z wartości danej liczby (można więc powiedzieć, że mnożnik dla każdej pozycji jest równy 1). Przykład: 3 to 111, a 10 to 1111111111. 
Wraz z wiekiem pojawi się problem – stulatek powinien uważać, aby nie wywołać pożaru, gdy będzie zdmuchiwać zapalone świeczki. 

{image filename="binary-cakes.png" alt="Tort ze 100 świeczkami kula ognia!"}

Na szczęście dla świeczek na torcie urodzinowym zamiast systemu jedynkowego, można użyć dwójkowego: świeczka świeci się lub nie. Przykład: Na przyjęcie z okazji osiemnastych urodzin wystarczy pięć świeczek (i tylko dwie będą się świecić!), gdyż zapis binarny tej liczby to 10010.

Tutaj możesz zobaczyć [wideo, na którym ktoś liczby na palcach do 1023, a ktoś innym otrzymuje „binarny” tort urodzinowy. ](https://www.youtube.com/watch?v=GUqle9RE3Y8)

{image filename="binary-cake.png" alt="Im ktoś jest starszy, tym chętniej powinien używać zapisu binarnego dla świeczek na torcie urodzinowym. Liczba potrzebnych świeczek nie będzie wcale duża." caption="Im ktoś jest starszy, tym chętniej powinien używać zapisu binarnego dla świeczek na torcie urodzinowym. Liczba potrzebnych świeczek nie będzie wcale duża."}
{panel end}

### Kod szesnastkowy jako skrót dla zapisu binarnego

Komputery zapisują liczby binarne i posługują się nimi, przetwarzając dane. Na ekranie zwykle wyświetlane są już w postaci dziesiętnej, gdyż wielocyfrowy zapis dwójkowy byłby dla człowieka kompletnie nieczytelny. Czasami jednak musimy posłużyć się liczbami, które nie są zapisane dziesiętnie, np. przekazując innej osobie adres fizyczny karty sieciowej (adres MAC) lub określając precyzyjnie kolor na stronie internetowej (w kodzie HTML).

Wyobraź sobie, że masz przepisać na kartce 16-bitową liczbę:  0101001110010001. 
Można zastosować wówczas zapis skrócony: grupujemy cyfry po cztery (w tym przypadku:  0101 0011 1001 0001), i zastępujemy każdą czwórkę zapisem dziesiętnym, co daje 5391. Pojawia się jednak mały problem: co z grupą bitów postaci 1111 (czyli 15)? Przecież mamy tylko cyfry od 0 do 9.
 
Rozwiązanie jest proste: wprowadzimy specjalne symbole dla cyfr od 1010 (10) do 1111(15), tj. posłużymy się literami od A do F.
Na przykład liczbę 1011 1000 1110 0001 można w zwięzły sposób zapis tak: B8 E1. Litera "B" jest kodem dla 1011 (=11 w systemie dziesiętnym), a litera E jest kodem dla 1110 (=14).

W tym momencie mamy już 16 cyfr. Taki system liczbowy nazywamy szesnastkowym (heksadecymalnym) lub w skrócie hex. Zamiana (konwersja) reprezentacji między systemem binarnym a szesnastkowym jest bardzo prosta. To wyjaśnia, dlaczego system szesnastkowy jest bardzo powszechnie stosowany wtedy, gdy chcemy zapisać poza komputerem dużą liczbę binarną. 

Oto kompletna tablica liczb 4-bitowych i ich szesnastkowych odpowiedników:

| **zapis binarny** | **kod szesnastkowy** |
|------------|---------|
| 0000       | 0       |
| 0001       | 1       |
| 0010       | 2       |
| 0011       | 3       |
| 0100       | 4       |
| 0101       | 5       |
| 0110       | 6       |
| 0111       | 7       |
| 1000       | 8       |
| 1001       | 9       |
| 1010       | A       |
| 1011       | B       |
| 1100       | C       |
| 1101       | D       |
| 1110       | E       |
| 1111       | F       |

Przykład: Największą liczbą 8-bitową jest 11111111. Można ją zapisać jako FF. Można sprawdzić, że w systemie dziesiątkowym jest to 255.

To, jakiego zapisu (reprezentacji) liczby należy użyć, zależy od konkretnej sytuacji. Reprezentacja binarna jest reprezentacją maszynową, ale jest nieodpowiednia dla człowieka. Zapis szesnastkowy to dobry sposób na skrócenie zapisu binarnego. Zapis dziesiętny jest używany wtedy, gdy człowiek musi odczytać wartość jakiejś liczby. Wszystkie trzy notacje są używane w informatyce.

Należy pamiętać, że w praktyce w komputerach stosuje się **wyłącznie** binarny zapis liczb. Jest **niemożliwym** zapisanie liczby bezpośrednio w systemie dziesiętnym lub szesnastkowym. 

### Zapis binarny liczb w komputerze

Liczbami posługujemy się zwykle pracując z arkuszem kalkulacyjnym lub bazą danych. Dane wprowadzać może użytkownik programu bezpośrednio z klawiatury, z pliku lub za pośrednictwem różnych czujników, np. temperatury, ciśnienia powietrza, czy drgań mechanicznych.

Trzeba zaznaczyć, że nie wszystkie informacje liczbowe, są zapisywane w komputerze jako liczby, a jako ciągi znaków, np. numer telefonu zapisany jako (03) 555-1234, a więc zawierający nawiasy i łącznik. 
Z drugiej strony informacje, które na pierwszy rzut oka nie są liczbami (np. „30 stycznia 2014”), mogą być ku naszemu zaskoczeniu zapisywane przez oprogramowanie jako liczby (co pozwala np. w programie Excel na odejmowanie jednej daty od drugiej, w celu wyznaczenia liczby dni pomiędzy dwoma wydarzeniami). Rolą oprogramowania jest wyświetlenie liczby w odpowiedni sposób dla użytkownika, w zalezności od jej interpretacji w konkretnej sytuacji.

{panel type="curiosity" summary="Więcej na temat zapisu danych"}
W arkuszu kalkulacyjnym Excel próba wykonania odejmowania jednej daty od drugiej skończy się wyznaczeniem liczby dni dzielących te dwie daty. Pojedyncza data natomiast jest w istocie zapisywana w pamięci jako liczba dni, które minęły od 1 stycznia 1900 roku. 
{panel end}

Wszelkie typy danych zapisuje się dziś  komputerach cyfrowo, tzn. jako liczby zakodowane binarnie.

Z tematem zapisu liczb w komputerze wiążą się pytania: 
- Jaki zakres liczb można zapisać w praktyce?
- Jak zapisywać liczby ujemne?
- Jak zapisywać liczby niecałkowite?

### Liczba bitów używana w prkatyce

W praktyce wygląda to tak, że w pamięci komputera trzeba zarezerwować konkretną liczbę bitów jeszcze zanim będzie znana dokładna wartość liczby, którą chcemy w pamięci zapisać. Dzisiaj często rezerwuje się 32 bity lub 64 bity, choć czasem, w uzasadnionych przypadkach, może to być 16 bitów lub nawet 128 bitów. 

W każdym systemie komputerowym trzeba przyjąć pewne kompromisowe rozwiązanie pomiędzy liczbą bitów rezerwowanych w pamięci a zakresem liczb, które w taki sposób można zapisać.

Niektóre narzędzia pozwalają na wybór ilości przydzielanej pamięci spośród pewnej liczby możliwości (języki programowania czy systemy baz danych); inne w sposób arbitralny mają to ustalone z góry (np. arkusze kalkulacyjne).

Istnieją też narzędzia, które potrafią samodzielnie w razie potrzeby zwiększyć obszar rezerwowanej pamięci (np. dla liczby całkowitej czyni tak interpretator języka programowania Python). Należy podkreślić, że to zawsze będzie wielokrotność 32 bitów  (odpowiednio 32, 64, 96, 128, 160 itd.). Działa to tak, że w momencie, gdy 32 bity to zbyt mało do zapisania dokładnej wartości liczby, to następuje rezerwacja innego fragmentu pamięci o wielkości 64 bitów itp.

W niektórych językach programowania nie ma automatycznej kontroli, która pozwoliłaby stwierdzić, że nastąpiła próba zapisu zbyt dużej liczby (przepełnienie). Przykład: Dodanie 1 do liczby 127 w przypadku zapisu 8-bitowego zakończy się uzyskaniem liczby -128.
Innym przykładem jest tzw. problem roku 2038. Okazuje się, że 19 stycznia 2038 roku nastąpi błąd przepełnienia i błędnie będzie interpretowana data w oprogramowaniu, które do zapisu daty używa pewnego tradycyjnego jej zapisu jako liczby 32-bitowej. Z dość podobnym problemem mieliśmy do czynienia w roku 2000.

{image filename="xkcd-cant-sleep-comic.png" alt="A xkcd comic on number overflow" source="https://xkcd.com/571/"}

W komputerach małych rozmiarów, takich jak np. te wbudowane wewnątrz samochodu, zmywarki, czy w czujnikach o rozmiarach wielkości ziarnka piasku, może być konieczne bardziej precyzyjne określenie zakresu przewarzanych liczb. W przypadku standardowych komputerów standardem jest przetwarzanie bloków 32 bitowych jako niepodzielnej liczby bitów. Jednak czasami (np. w oprogramowaniu czujnika wstrząsów sejsmicznych) może być konieczne zastosowanie podziału: 7 bitów do zapisu szerokości geograficznej, następne 7 bitów do zapisu długości geograficznej, kolejne 10 bitów do zapisania informacji o głębokości pod powierznią ziemi, a 8 bitów dla informacji o sile wstrząsu.

Nawet podczas pracy ze standardowym komputerem jest ważne, aby starannie określić liczbę potrzebnych bitów. Na przykład, jeśli w bazie danych wartość konkretnego pola ma przyjmować jedną z czterech wartości (np. 0, 1, 2, 3 lub wartości składowych sekwencji DNA), to rezerwowanie 64 bitów do zapisania takiej wartości niepotrzebnie powiększa rozmiar bazy danych (zapisanej na dysku). Gdyby liczba rekordów bazy danych była równa 10 000 000, to w konsekwencji zmarnowanych będzie 620 000 000 bitów, czyli ok. 74 MB, gdyż do zapisu czterech różnych wartości wystarczą 2 bity. Jeśli podobnych pól w bazie danych jest więcej, to efekt marnowania pamięci komputera kumuluje się do ogromnych rozmiarów.

Narzędzia takie jak Google Maps przetwarzają astronomiczne ilości danych. Marnowanie pamięci w ich przypadkach wcale nie wchodzi w grę!

{panel type="challenge" summary="Ile bitów jest niezbędne?"}
Czymś bardzo użytecznym jest oszacowanie liczby bitów niezbędnych do zapamiętania pewnych wartości. Zastanów się, jaka byłaby odpowiedź dla sytuacji przedstawionych poniżej. Pamiętaj, że chcesz mieć możliwość zapamiętania największej z potencjalnych wartości, ale nie chcesz marnować pamięci komputera.

1. Informacja o dniu tygodnia
  - a) 1 bit
  - b) 4 bity
  - c) 8 bitów
  - d) 32 bity
2. Informacja o liczbie ludzi na świecie
  - a) 16 bitów
  - b) 32 bity
  - c) 64 bity
  - d) 128 bitów
3. Informacja o liczbie dróg w Nowej Zelandii
  - a) 16 bitów
  - b) 32 bity
  - c) 64 bity
  - d) 128 bitów
4. Informacja o liczbie gwiazd we wszechświecie
  - a) 16 bitów
  - b) 32 bity
  - c) 64 bity
  - d) 128 bitów
{panel end}

{panel type="spoiler" summary="Odpowiedzi"}
1. b (właściwie to już 3 bity pozwolą na zapis 8 różnych wartości; ale technicznie lepszym rozwiązaniem są 4 bity ze względu na to, że na 8 bitach można by łatwo zapisać informacje o dwóch dniach tygodnia)
2. c (32 bity to za mało)
3. c (ciekawe wyzwanie dla projektującego bazę danych: w Nowej Zelandii jest łącznie ok. 94 000 km dróg i założenie, że średnia długość drogi to 1 km prowadzi do wniosku, że 16 bitów to za mało)
4. d (64 bity do za mało, a 128 bitów to o wiele za dużo! Trzeba pamiętać, że 128 bitów to nie dwa razy więcej niż 64 bity.)
{panel end}

### Zapis binarny liczb ujemnych

Sposób zapisu liczb przedstawiony do tej pory pozwalał na zapis tylko liczb nieujemnych. W praktyce często potrzebujemy również zapisywać informacje o wartościach ujemnych (np. o obciążeniu rachunku bankowego, czy temperaturze powietrza zimą!). Kiedy posługujemy się zapisem dziesiętnym, to liczbę ujemną uzyskujemy poprzez dopisanie znaku minus przed liczbą. W komputerze nie ma takiej możliwości.

We will look at two possible approaches: Adding a simple sign bit, much like we do for decimal, and then a more useful system called Two's Complement.
Przyjrzymy się dwum możliwym rozwiązaniom: dodanie bitu znaku (metoda podobna do używanej przez człowieka w zapisie dziesiętnym) i tzw. uzupełnienie do 2 (metoda o wiele bardziej użyteczna w przypadku komputerów).

#### Stosowanie bitu znaku

W komputerze nie ma możliwości dopisania znaku - (minus) przed liczbą, ale możemy przydzielić jeden dodatkowy bit, zwany bitem *znaku*. To może być skrajny lewy bit bajtu – gdy ustawimy go na „0”, to uznamy liczbę za dodatnią, a w przypadku „1” liczba będzie ujemna (analogia do znaku minus). 


Przykład: W reprezentacji 8-bitowej ze znakiem liczba **41** będzie zapisana jako **00101001**, gdzie pierwszy bit (0) to bit znaku, a kolejne bity to zapis binarny liczby **41** na 7 bitach. Podobnie liczba **-59** będzie mieć reprezentację **01111011**, gdzie pierwszy bit (1) jest bitem znaku, a kolejne bity to liczba **59** zapisana binarnie.

{panel type="challenge" summary="Zapis liczb ujemnych (metoda bit-znak)"}
Znajdź 8-bitową reprezentację binarną liczb:  1, -1, -8, 34, -37, -88 i 102.
Jakie liczby będą reprezentowane jako 10000110, 01111111i  10000000 w przypadku systemu 8-bitowego?
{panel end}

{panel type="spoiler" summary="Odpowiedzi"}
-   1  to 0000 0001
-  -1  to 1000 0001
-  -8  to 1000 1000
-  34  to 0010 0010
-  -37 to 1010 0101
-  -88 to 1101 1000
-  102 to 0110 0110
{panel end}

Dekodowanie, czyli określenie wartości dziesiętnej na podstawie zapisu binarnego jest proste. Liczba zapisana jako **1001 0111** to na pewno liczba ujemna. Po bicie znaku (1) mamy 7 bitów **001 0111** reprezentujących **23**. Stąd wartość szukana to **-23**.

{panel type="challenge" summary="Converting binary with sign bit to decimal"}
Jakie liczby będą reprezentowane jako 0001 0011, 1000 0110, 10100011, 0111 1111 i 11111111 w przypadku systemu 8-bitowego?
- 00010011
- 10000110
- 10100011
- 01111111
- 11111111
{panel end}

{panel type="spoiler" summary="Odpowiedzi"}
- 0001 0011 to 19
- 1000 0110 to -6
- 1010 0011 to -35
- 0111 1111 to 127
- 1111 1111 to -127
{panel end}

Jakiej liczbie dziesiętnej odpowiada **1000 0000?** Odpowiedź to: **-0**. A **0000 0000**? To jest **+0**.
Przykład  1000 0000 jest dobrą ilustracją jednej z wad, jaką ma wyżej opisany sposób zapisu. Liczba 0 ma dwie reprezentacje: -0 i +0. To nie tylko rozrzutność, ale przede wszytkim źródło potencjalnego zamieszania. W praktyce tej metody nie używa się. Komputery używają bardziej wyrafinowanej metody opisanej poniżej.

#### Kod U2 (uzupełniania do 2)

Istnieje inny sposób zapisu liczb ujemnych zwany *kodem uzupełnienia do 2*, która nie tylko pozbawiona jest wyżej opisanej wady, ale znacznie ułatwia operacje arytmetyczne na liczbach ujemnych. Jedną z jego zalet jest ujednolicenie arytmetyki (działania wykonywane z liczbą ujemną nie muszą być traktowane jako odrębny przypadek), co daje zysk szybkości oraz upraszcza projekt cyfrowych obwodów elektronicznych. 

***Zapis liczb dodatnich w kodzie U2***

Liczby dodatnie zapisuje się dokładnie w ten sam sposób, jak to było przedstawione w poprzednich rozdziałach. W przypadku zapisu 8-bitowego lewy skrajny bit jest ustawiony na 0, a pozostałe 7 bitów przeznacza się na zapis wartości liczby; na przykład **1** zapiszmy jako **00000001**, a 65 jako **00110010**.

***Zapis liczb ujemnych w kodzie U2***

Ten przypadek jest trudniejszy. Proces konwersji (zamiany z systemu dziesiętnego na binarny) można opisać listą kroków:
1. Znajdź zapis binarny wartości bezwzględnej liczby (czyli bez znaku minus).
2. Zmień wartości wszystkich bitów na przeciwne (tj. zmień 0 na 1, a 1 na to 0).
3. Powiększ liczbę o 1 (dodanie 1 w arytmetyce binarnej jest dość proste; poniżej znajdzisz pewne wskazówki).

Na przykład dla **-118** kolejne kroki będą wyglądać tak:
1. Zapis binarny liczby **118** to **01110110**
2. **01110110** po zamianie wartości bitów to **10001001**
3. **10001001 + 1** jest równe **10001010**

Stąd zapis liczby **-118** w kodzie uzupełnieniowym (U2) to: **10001010**.

{panel type="challenge" summary="Dodanie 1 w arytmetyce binarnej"}
Reguła rządząca dodaniem 1 w arytmetyce binarnej jest bardzo prosta, więc warto ją odkryć samodzielnie.
Po pierwsze: Jeśli zapis binarny kiczby kończy się 0 (np. 1101010), to jaki będzie efekt zamiany ostatniego 0 na 1?
Rozpatrz inne przypadki: Jeśli zapis kończy się bitami 01, to o ile większa będzie liczba jeśli w tych miejscach wpiszemy 10?
Co w przypadku zapisów kończących się 011 czy 011111?

Te proste reguły oznaczają w prkatyce, że upraszcza się projektowanie sumatorów (cyfrowych układów elektronicznych). 
{panel end}

{panel type="teacher-note" summary="Dodanie 1 w arytmetyce binarnej"}
Uczniowie powinno samodzielnie, przez wykonanie kilku przykładów, odkryć regułę dodawania 1 do liczby zapisanej binarnie. 

Istnieją różne sposoby mówienia o tym procesie.
Regułę można wyrazić takimi słowami: Zacznij od skrajnej prawy cyfry. Zmień wartości kolejnych bitów na przeciwne tak długo aż pierwszy raz nie zmienisz 0 na 1.

Reguła może być sformułowana inaczej: Znajdź cyfrę 0 położoną najbardziej na prawo, zmień ją na 1, a wszystkie jedynki po prawej zmień na 0. Jak to będzie działać dla przykładu 1001**0**111? Otrzymamy 10011000.

W szczególnym przypadku (np. 1111111), można dopisać 0 na początku (01111111). Zastosowanie reguły da odpowiedź: 10000000.

Być może warto, aby uczniowie poszukali analogicznej reguły dotyczącej zapisu dziesiętnego: jak dodać 1 to 284394? To 38999? 9999799?
{panel end}

{panel type="challenge" summary="Determining the Two's Complement"}
Zapisz poniższe liczby w kodzie U2, używając 8 bitów.
1. 19
2. -19
3. 107
4. -107
5. -92
{panel end}

{panel type="spoiler" summary="Odpowiedzi"}
1. 19 ma kod **0001 0011**.
2. Dla -19, zaczynamy od zapisania kodu dla 19 = 0001 0011, po zamianie bitów mamy 1110 1100, a po dodaniu 1 otrzymujemy poszukiwany kod: **1110 1101**.
3. 107 ma kod **0110 1011**.
4. Dla -107 mamy kolejno (jako etapy pośrednie): 0110 1011 i 1001 0100, a ostatecznie: **1001 0101**.
5. Dla -92 mamy: 0101 1100, 1010 0011 i w końcu **1010 0100**. 
{panel end}

***Konwersja liczby binarnej z kodu U2 na zapis dziesiętny***

Aby dokonać konwersji w odwrotną stronę (z reprezentacji binarnej na dziesiętną) trzeba najpierw określić, czy liczba jest dodatnia (lub równa 0), czy ujemna. Jeśli liczba jest nieujemna, to jej wartości dziesiętnej szukamy w znany już sposób. W przeciwnym wypadku zaczynamy od konwersji liczby z kodu U2 do naturalnej postaci binarnej wartości bezwględnej liczby (bez znaku).

Skąd wiadomo, czy liczba jest ujemna czy nie? Wystarczy sprawdzić, czy skrajny lewy bit jest ustawiony na 1, czy 0. W pierwszym przypadku liczba jest ujemna. To wynika z opisu kodu U2 zawartego w poprzednim podrozdziale.

Jeśli zapis binarny liczby zaczyna się od 1, to proces konwersji na postać dziesiętną można przedstawić jako listę kroków:

1. Odejmij 1 (w arytmetyce binarnej).
2. Zmień wartości wszystkich bitów na przeciwne.
3. Znajdź wartość dziesiętną liczby uzyskanej w kroku 3.
4. Dopisz znak - (minus) przed wartością wyznaczoną w kroku 4.

Na przykład dla liczby 11100010 kolejne kroki dają takie efekty:

1. **11100001**
2. **00011110**.
3. **30**.
4. **-30**.

{panel type="challenge" summary="Ćwiczenie"}
Wyznacz wartości dziesiętne liczb zapisanych w kodzie U2:
1. 00001100
2. 10001100
3. 10111111
{panel end}

{panel type="spoiler" summary="Odpowiedzi"}
1. **12**
2. 10001100 -> 10001011 -> 01110100 -> 116 -> **-116**
3. 10111111 -> 10111110 -> 01000001 -> 65 -> **-65**
{panel end}


***Ile liczb można zapisać w kodzie U2?***

Wiadomo już, że na 8 bitach można zapisać 256 różnych liczb. W przypadku kodu U2 największą możliwą liczbą nie będzie 255.
Trzeba pamiętać, że skrajny lewy bit to bit znaku!

W praktyce można zapisać liczby z zakresów podanych w tabeli. 

Wynika to wprost z faktu, że dla 8 bitów w kodzie naturalnym najmniejsza liczba ma kod 00000000, a największa -- 11111111.
W kodzie uzupełnienowym (U2) wygląda to inaczej: 10000000 (kod najmniejszej liczby) i 01111111 (kod największej liczby).

|      liczba bitów     |        zakres liczb w kodzie naturalnym           |               zakres liczb w kodzie U2                    |
|-----------------|---------------------------------|----------------------------------------------------------|
| 8 bit		  | 0 to 255                        | od -128 do 127                                              |
| 16 bit	  | 0 to 65 535                     | od -32 768 do 32 767                                        |
| 32 bit	  | 0 to 4 294 967 295              | od −2 147 483 648 do 2 147 483 647                          |
| 64 bit	  | 0 to 18 446 744 073 709 551 615 | od −9 223 372 036 854 775 808 do 9,223,372,036,854,775,807  |


#### Dodawanie liczb ujemnych

Spójrzmy najpierw na dodawanie liczb dodatnich.
Reguły są analogiczne do tych znanych z pisemnego sposobu dodowania liczb w systemie dziesiętnym. Jest przy tym prościej: są tylko dwa rodziaje cyfr, więc upraszcza się tabliczna dodawania!

Sposób pisemnego dodawania przypomniemy na przykładzie **128 + 255**.

```
  1   (przeniesienie)
 128
+255
----
 383
```
Zauważmy, że wynik dodawania 5 + 8 jest liczbą większą od 9. Dlatego na pozycji jedności w wyniku zapisujemy 3, a 10 (=13-3) stanowi jedną dziesiątkę, więc mówimy o przeniesieniu (dodatkowy składnik w kolumnie dziesiątek). 
Dodawanie w systemie binarnym realizuje się w analogiczny sposób.

***Dodawanie liczb dodatnich***

Chcąc wykonać dodawanie dwóch liczb, np. **00001111** i **11001110**, należy się posłużyć sposobem pisemnym dodawania (w kolumnach).
W przypadku systemu binarnego wszystkie reguły, jaki trzeba znać dotyczą działań: 0+0, 0+1, 1+0, 1+1 oraz 1+1+1.
Wyniki pierwszych trzech dodawań są oczywiste. Dodawanie 1+1 kończy się przeniesieniem, gdyż 1+1=10 (binarnie). W zapisie sposobem pisemnym oznacza to zapisanie 0 jako wyniku częściowego i przeniesienie 1 do kolumny z lewej (o ile istnieje). 
Ostatnie dodawanie, 1+1+1 daje sumę 11 (binarnie), co oznacza zapisanie 1 jako wyniku częściowego i przeniesienie 1 do kolumny z lewej (o ile istnieje).
Oto przykład:

```
    111   (przeniesienie)
 11001110
+00001111
---------
 11011101
```

Trzeba pamiętać, że w zapisie binarnym używa się wyłącznie cyfr 1 i 0. To oznacza konieczność przeniesienia 1 do kolumny na wyższej pozycji (z lewej), gdy suma częściowa jest równa 2 lub 3 (dziesiętnie).

***Dodawanie liczb ujemnych w kodzie bit-znak***

W przypadku liczb ujemnych zapisanych w kodzie bit-znak (czyli z lewym skrajnym bitem jako bitem znaku), metoda opisana wyżej nie zadziała. Dla przykładu dodanie **+11 (01011)** do **-7 (10111)** powinno zakończyć się wynikiem **+4 (00100)**.

```
11111 (przeniesienie)
 01011
+10111
100010
```

Wynikiem jest jednak liczba **-2**.

Jak można ten problem rozwiązać? Okazuje się, że zamiast dodawnia kolumn można by użyć odejmowania kolumn. To w konkretnej realizacji sprzętowej wymagałoby użycia specjalnego układu elektronicznego.
Na szczęście jest inne rozwiązanie: z pomocą przychodzi kod uzupełnieniowy (U2)!

***Dodawanie liczb ujemnych w kodzie U2***

Dla przykładu (+11 + -7) należy rozpocząć od zapisania składników w kodzie U2 na 5 bitach. Otrzymujemy: **01011 (+11)** i **11001 (-7)**.

Dodawanie w kolumnach zapiszemy tak:

```
 01011
 11001
100100
```

Dodatkowy szósty bit (po lewej) powstały z przeniesienia należy zignorować. Pozostałe 5 bitów to **00100**, czyli **4**. Takiego wyniku oczekiwaliśmy.

Opisaną wyżej metodę można zaadaptować do odejmowania: zaimast działania 5 - 2, należy wykonać wykonać działanie 5 + (-2) = 3.

Własności kodowania U2 są bardzo użyteczne. Dlatego, że zarówno liczby ujemne, jak i nieujemne można działają z tymi samymi elektornicznymi układami arytmetycznymi, a dodawanie i odejmowanie można potraktować jako ten sam typ operacji arytmetycznej.

{panel type="curiosity" summary="What's going on with Two's complement?"}

Pomysł wykonywania dodawania na tzw. dopełnieniu liczby zamast odejmowania liczby można zastosować w obliczeniach na liczbach dziesiętnych. Dopełnieniem dziesiętnym x jest 10-x, np. dla 4 to 6, a dla 8 to 2. 
(Słowo "dopełnić" ma ten sam rdzeń, co słowo pełnia. Liczba 10 jest w tym przypadku taką pełną, ,,okrągłą'' liczbą.)

Odejmowanie 2 od 6 jest tożsame z dodawaniem 8 do 6 (6 + 8 = 14) i ignorowaniem 1 z przeniesienia (po lewej).

Check that adding 872 to 255 produces (almost) the same result as subtracting 128.
Dla większych liczb (np. trzycyfrowych) dopełnieniem liczby jest liczba, która stanowi różnicę brakującą do kolejnej potęgi 10, tj. 1000-128 = 872.

W przypadku zapisu binarnego sytuacja jest prostsza, bo używa się tylko dwóch różnych cyfr. Porównanie z systemem dziesiętnym może być jednak pomocne dla zrozumienia tematu.

{panel end}



#### Using sign bits vs using Two's Complement

We have now looked at two different ways of representing negative numbers on a computer. In practice, a simple sign bit is rarely used, because of having two different representations of zero, and requiring a different computer circuit to handle negative and positive numbers, and to do addition and subtraction.

Two's Complement is widely used, because it only has one representation for zero, and it allows positive numbers and negative numbers to be treated in the same way, and addition and subtraction to be treated as one operation.

There are other systems such as "One's Complement" and "Excess-k", but Two's Complement is by far the most widely used in practice.


{comment}

TODO: Write this section

### Representing decimal points and fractions in practice

Another type of number used in computer systems is the "floating point" value. While we won't look at it in detail, to get a taste of what's involved, consider the bit values in a 4-bit number, which are 8, 4, 2 and 1. What would the value of a bit *to the right* of the one bit be? And to the right of that one?

The following version of the base conversion interactive has bits that are smaller than the 1-bit. Try representing the decimal number 3.5 using this system. How about 2.8125? What about 2.8?

This system is a fixed-point number system; floating point numbers are based on this idea, but allow for the number of digits to be fixed, but the position of the point to change (by giving an exponent value).
{panel end}

{panel type="teacher-note" summary="Solution for extra for experts"}

The values to the right of the 1-bit continue to be a half of the value to their left, so they are 0.5, 0.25, 0.125 and so on. The decimal number 3.5 can be represented as 11.1, and 2.8125 is 10.1101. The number 2.8 can't be represented accurately in binary! The closest value with the 10 bits in the interactive is 10.11001100. In fact, the number never finishes in binary; it contains "1100" repeating forever! This rounding error can be seen in some spreadsheets: try adding 110 + 2.8 - 2.8 - 100. With enough places of accuracy, you can see that the sum doesn't (quite) come to zero.

**Note:** The interactive here has not been updated to the new system. Please [view the interactives on the Data Representation page](http://www.csfieldguide.org.nz/releases/1.9.9/DataRepresentation.html) on the older version of the CSFG. We are currently in the process of updating these interactives for release.

{panel end}

{comment end}

## Text

There are several different ways in which computers use bits to store text. In this section, we will look at some common ones and then look at the pros and cons of each representation.

### ASCII

W poprzednim podrozdziale stwierdziliśmy, że sześć punktów systemu Braille'a pozwala uzyskać 64 różne wzorce (znaki). 

Spróbuj policzyć, ile różnych dużych liter, małych liter, liczb i innych znaków możesz wprowadzić do edytora tekstu, używając klawiatury komputerowej. (Nie zapomnij o znakach, które współdzielą klawisze z liczbami i o znakach interpunkcyjnych!) 

{panel type="jargon-buster" summary="Characters"}
The collective name for upper-case letters, lower-case letters, numbers, and symbols is *characters* e.g. a, D, 1, h, 6, \*, ], and ~ are all characters.
Importantly, a space is also a character.
{panel end}

If you counted correctly, you should find that there were more than 64 characters, and you might have found up to around 95.
Because 6 bits can only represent 64 characters, we will need more than 6 bits;
it turns out that we need at least 7 bits to represent all of these characters as this gives 128 possible patterns.
This is exactly what the **ASCII** representation for text does.

{panel type="challenge" summary="Why 7 bits?"}
In the previous section, we explained what happens when the number of dots was increased by 1 (remember that a dot in Braille is effectively a bit). Can you explain how we knew that if 6 bits is enough to represent 64 characters, then 7 bits must be enough to represent 128 characters?
{panel end}

Koncepcją zastosowaną w ASCII było przypisanie różnych wzorców bitowych każdemu ze znaków stosowanych w tekstach angielskich (oraz pewnej liczbie tzw. znaków sterujących, używanych dawniej w aparatach dalekopisowych – dziś tylko niektóre z nich mają zastosowanie w technice komputerowej, ale ten wątek pominiemy). W dzisiejszej postaci kodu ASCII dla języka angielskiego stosuje się wzorce 8-bitowe (oktety bitów, czy bajty), w których pierwszy bit ma zawsze wartość 0, co znaczy, że kod pozwala na zapis 128 znaków. 

W tabeli przedstawiono zestawienie znaków i odpowiadajacych im wzorców 7-bitowych:

| Postać binarna  | Znak  | Postać binarna  | Znak | Postać binarna  | Znak  |
|---------|-------|---------|------|---------|-------|
| 0100000 | spacja (odstęp) | 1000000 | @    | 1100000 | `     |
| 0100001 | !     | 1000001 | A    | 1100001 | a     |
| 0100010 | "     | 1000010 | B    | 1100010 | b     |
| 0100011 | #     | 1000011 | C    | 1100011 | c     |
| 0100100 | $     | 1000100 | D    | 1100100 | d     |
| 0100101 | %     | 1000101 | E    | 1100101 | e     |
| 0100110 | &     | 1000110 | F    | 1100110 | f     |
| 0100111 | '     | 1000111 | G    | 1100111 | g     |
| 0101000 | (     | 1001000 | H    | 1101000 | h     |
| 0101001 | )     | 1001001 | I    | 1101001 | i     |
| 0101010 | \*    | 1001010 | J    | 1101010 | j     |
| 0101011 | \+    | 1001011 | K    | 1101011 | k     |
| 0101100 | ,     | 1001100 | L    | 1101100 | l     |
| 0101101 | \-    | 1001101 | M    | 1101101 | m     |
| 0101110 | .     | 1001110 | N    | 1101110 | n     |
| 0101111 | /     | 1001111 | O    | 1101111 | o     |
| 0110000 | 0     | 1010000 | P    | 1110000 | p     |
| 0110001 | 1     | 1010001 | Q    | 1110001 | q     |
| 0110010 | 2     | 1010010 | R    | 1110010 | r     |
| 0110011 | 3     | 1010011 | S    | 1110011 | s     |
| 0110100 | 4     | 1010100 | T    | 1110100 | t     |
| 0110101 | 5     | 1010101 | U    | 1110101 | u     |
| 0110110 | 6     | 1010110 | V    | 1110110 | v     |
| 0110111 | 7     | 1010111 | W    | 1110111 | w     |
| 0111000 | 8     | 1011000 | X    | 1111000 | x     |
| 0111001 | 9     | 1011001 | Y    | 1111001 | y     |
| 0111010 | :     | 1011010 | Z    | 1111010 | z     |
| 0111011 | ;     | 1011011 | [    | 1111011 | {     |
| 0111100 | <     | 1011100 | \\   | 1111100 | \|    |
| 0111101 | =     | 1011101 | ]    | 1111101 | }     |
| 0111110 | >     | 1011110 | ^    | 1111110 | ~     |
| 0111111 | ?     | 1011111 | _    | 1111111 | Delete   |

Przykład: Litera c (mała litera) ma w tabeli przypisany wzorzec: „01100011” (0 na początku jest dopełnieniem kodu do 8 bitów). Litera o ma wzorzec „01101111”.
Warto w ramach ćwiczenia zapisać jakieś angielskie słowo, używając kodu ASCII i dać komuś innemu, kto również zapoznaje się z tym tematem, do odkodowania. 

{panel type="teacher-note" summary="Using the table"}
Exchanging short messages in code will force students to use the table, and they should start to pick up some of the patterns (e.g. capital letters have a different code to lower case letters, but they only have one bit different.)
{panel end}

Computers can represent pieces of text with sequences of these patterns, much like Braille does. For example, the word “computers” (all lower-case) would be 01100011 01101111 01101101 01110000 01110101 01110100 01100101 01110010 01110011. This is because "c" is "01100011", "o" is "01101111", and so on.
Have a look at the ASCII table above to check that we are right!

{panel type="curiosity" summary="What does ASCII stand for?"}
The name "ASCII" stands for "American Standard Code for Information Interchange", which was a particular way of assigning bit patterns to the characters on a keyboard.
The ASCII system even includes "characters" for ringing a bell (useful for getting attention on old telegraph systems),
deleting the previous character (kind of an early "undo"),
and "end of transmission" (to let the receiver know that the message was finished).
These days those characters are rarely used, but the codes for them still exist (they are the missing patterns in the table above).
Nowadays ASCII has been supplanted by a code called "UTF-8",
which happens to be the same as ASCII if the extra left-hand bit is a 0,
but opens up a huge range of characters if the left-hand bit is a 1.
{panel end}


{panel type="challenge" summary="More practice at ASCII"}
Have a go at the following ASCII exercises

- How would you represent “science” in ASCII?
- How would you represent "Wellington" in ASCII? (note that it starts with an upper-case “W”)
- How would you represent “358” in ASCII (it is three characters, even though it looks like a number)
- How would you represent "Hello, how are you?" (look for the comma, question mark, and space characters in ASCII table)

Be sure to have a go at all of them before checking the answer!
{panel end}

{panel type="spoiler" summary="Answers to questions above"}

These are the answers.

- "science" = 01110011 01100011 01101001 01100101 01101110 01100011 01100101
- "Wellington" = 01010111 01100101 01101100 01101100 01101001 01101110 01100111 01110100 01101111 01101110
- "358" = 00110011 00110101 00111000

Note that the text "358" is treated as 3 characters in ASCII, which may be confusing, as the text "358" is different to the number 358! You may have encountered this distinction in a spreadsheet e.g. if a cell starts with an inverted comma in Excel, it is treated as text rather than a number. One place this comes up is with phone numbers; if you type 027555555 into a spreadsheet as a number, it will come up as 27555555, but as text the 0 can be displayed.
In fact, phone numbers aren't really just numbers because a leading zero can be important, as they can contain other characters -- for example, +64 3 555 1234 extn. 1234.
{panel end}

#### ASCII usage in practice

ASCII was first used commercially in 1963, and despite the big changes in computers since then, it is still the basis of how English text is stored on computers. ASCII assigned a different pattern of bits to each of the characters, along with a few other “control” characters, such as delete or backspace.

English text can easily be represented using ASCII, but what about languages such as Chinese where there are thousands of different characters? Unsurprisingly, the 128 patterns aren’t nearly enough to represent such languages. Because of this, ASCII is not so useful in practice, and is no longer used widely. In the next sections, we will look at Unicode and its representations. These solve the problem of being unable to represent non-English characters.

{panel type="curiosity" summary="What came before ASCII?"}
There are several other codes that were popular before ASCII, including the [Baudot code](https://en.wikipedia.org/wiki/Baudot_code) and [EBCDIC](https://en.wikipedia.org/wiki/EBCDIC). A widely used variant of the Baudot code was the "Murray code", named after New Zealand born inventor [Donald Murray](https://en.wikipedia.org/wiki/Donald_Murray_(inventor\)). One of Murray's significant improvements was to introduce the idea of "control characters", such as the carriage return (new line). The "control" key still exists on modern keyboards.
{panel end}

### Introduction to Unicode

In practice, we need to be able to represent more than just English characters. To solve this problem, we use a standard called **Unicode**. Unicode is a **character set** with around 120,000 different characters, in many different languages, current and historic. Each character has a unique number assigned to it, making it easy to identify.

Unicode itself is not a representation -- it is a character set. In order to represent Unicode characters as bits, a Unicode **encoding scheme** is used. The Unicode encoding scheme tells us how each number (which corresponds to a Unicode character) should be represented with a pattern of bits.

The following interactive will allow you to explore the Unicode character set. Enter a number in the box on the left to see what Unicode character corresponds to it, or enter a character on the right to see what its Unicode number is (you could paste one in from a foreign language web page to see what happens with non-English characters).

{interactive name="unicode-chars" type="in-page"}

The most widely used Unicode encoding schemes are called UTF-8, UTF-16, and UTF-32;
you may have seen these names in email headers or describing a text file.
Some of the Unicode encoding schemes are **fixed length**, and some are **variable length**.
**Fixed length** means that each character is represented using the same number of bits.
**Variable length** means that some characters are represented with fewer bits than others.
It's better to be **variable length**, as this will ensure that the most commonly used characters are represented with fewer bits than the uncommonly used characters.
Of course, what might be the most commonly used character in English is not necessarily the most commonly used character in Japanese.
You may be wondering why we need so many encoding schemes for Unicode.
It turns out that some are better for English language text, and some are better for Asian language text.

The remainder of the text representation section will look at some of these Unicode encoding schemes so that you understand how to use them, and why some of them are better than others in certain situations.

### UTF-32

UTF-32 is a **fixed length** Unicode encoding scheme. The representation for each character is simply its number converted to a 32 bit binary number. Leading zeroes are used if there are not enough bits (just like how you can represent 254 as a 4 digit decimal number -- 0254).
32 bits is a nice round number on a computer, often referred to as a word (which is a bit confusing, since we can use UTF-32 characters to represent English words!)

For example, the character **H** in UTF-32 would be:
```
00000000 00000000 00000000 01001000
```

The character **$** in UTF-32 would be:
```
00000000 00000000 00000000 00100100
```

And the character **犬** in UTF-32 would be:
```
00000000 00000000 01110010 10101100
```

The following interactive will allow you to convert a Unicode character to its UTF-32 representation. The Unicode character's number is also displayed. The bits are simply the binary number form of the character number.

{interactive name="unicode-binary" type="iframe" parameters="mode=utf32"}

{panel type="project" summary="Represent your name with UTF-32"}
1. Represent each character in your name using UTF-32.
2. Check how many bits your representation required, and explain why it had this many (remember that each character should have required 32 bits)
3. Explain how you knew how to represent each character. Even if you used the interactive, you should still be able to explain it in terms of binary numbers.
{panel end}

ASCII actually took the same approach. Each ASCII character has a number between 0 and 255, and the representation for the character the number converted to an 8 bit binary number. ASCII is also a fixed length encoding scheme -- every character in ASCII is represented using 8 bits.

In practice, UTF-32 is rarely used -- you can see that it's pretty wasteful of space.
UTF-8 and UTF-16 are both variable length encoding schemes, and very widely used. We will look at them next.

{panel type="challenge" summary="How big is 32 bits?"}
1. What is the largest number that can be represented with 32 bits? (In both decimal and binary).

2. The largest number in Unicode that has a character assigned to it is not actually the largest possible 32 bit number -- it is 00000000 00010000 11111111 11111111. What is this number in decimal?

3. Most numbers that can be made using 32 bits do not have a Unicode character attached to them -- there is a lot of wasted space. There are good reasons for this, but if you had a shorter number that could represent any character, what is the minimum number of bits you would need, given that there are currently around 120,000 Unicode characters?
{panel end}

{panel type="spoiler" summary="Answers to above challenge"}
1. The largest number that can be represented using 32 bits is 4,294,967,295 (around 4.3 billion). You might have seen this number before -- it is the largest unsigned integer that a 32 bit computer can easily represent in programming languages such as C.

2. The decimal number for the largest character is 1,114,111.

3. You can represent all current characters with 17 bits. The largest number you can represent with 16 bits is 65,536, which is not enough.
If we go up to 17 bits, that gives 131,072, which is larger than 120,000. Therefore, we need 17 bits.
{panel end}

### UTF-8

UTF-8 is a **variable length** encoding scheme for Unicode. Characters with a lower Unicode number require fewer bits for their representation than those with a higher Unicode number. UTF-8 representations contain either 8, 16, 24, or 32 bits. Remembering that a **byte** is 8 bits, these are 1, 2, 3, and 4 bytes.

For example, the character **H** in UTF-8 would be:
```
01001000
```
The character **ǿ** in UTF-8 would be:
```
11000111 10111111
```

And the character **犬** in UTF-8 would be:
```
11100111 10001010 10101100
```

The following interactive will allow you to convert a Unicode character to its UTF-8 representation. The Unicode character's number is also displayed.

{interactive name="unicode-binary" type="iframe" parameters="mode=utf8"}

#### How does UTF-8 work?

So how does UTF-8 actually work? Use the following process to do what the interactive is doing and convert characters to UTF-8 yourself.

1. Lookup the Unicode number of your character.

2. Convert the Unicode number to a binary number, using as **few** bits as necessary.
Look back to the section on binary numbers if you cannot remember how to convert a number to binary.

3. Count how many bits are in the binary number, and choose the correct pattern to use, based on how many bits there were. Step 4 will explain how to use the pattern.

  ```
  7  or fewer bits: 0xxxxxxx
  11 or fewer bits: 110xxxxx 10xxxxxx
  16 or fewer bits: 1110xxxx 10xxxxxx 10xxxxxx
  21 or fewer bits: 11110xxx 10xxxxxx 10xxxxxx 10xxxxxx
  ```

4. Replace the x's in the pattern with the bits of the binary number you converted in 2. If there are more x's than bits, replace extra left-most x's with 0's.

For example, if you wanted to find out the representation for **貓** (cat in Chinese), the steps you would take would be as follows.

1. Determine that the Unicode number for **貓** is **35987**.
2. Convert **35987** to binary -- giving **10001100 10010011**.
3. Count that there are **16** bits, and therefore the third pattern **1110xxxx 10xxxxxx 10xxxxx** should be used.
4. Substitute the bits into the pattern to replace the x's -- **11101000 10110010 10010011**.

Therefore, the representation for **貓** is **11101000 10110010 10010011** using UTF-8.

### UTF-16

Just like UTF-8, UTF-16 is a **variable length** encoding scheme for Unicode. Because it is far more complex than UTF-8, we won't explain how it works here.

However, the following interactive will allow you to represent text with UTF-16. Try putting some text that is in English and some text that is in Japanese into it. Compare the representations to what you get with UTF-8.

{interactive name="unicode-binary" type="iframe" parameters="mode=utf16"}

### Comparison of text representations

We have looked at ASCII, UTF-32, UTF-8, and UTF-16.

The following table summarises what we have said so far about each representation.

Representation | Variable or Fixed | Bits per Character | Real world Usage
--- | --- | --- | ---
*ASCII* | Fixed Length | 8 bits | No longer widely used
*UTF-8* | Variable Length | 8, 16, 24, or 32 bits | Very widely used
*UTF-16* | Variable Length | 16 or 32 bits | Widely used
*UTF-32* | Fixed Length | 32 bits | Rarely used

In order to compare and evaluate them, we need to decide what it means for a representation to be "good". Two useful criteria are:

1. Can represent all characters, regardless of language.
2. Represents a piece of text using as few bits as possible.

We know that UTF-8, UTF-16, and UTF-32 can represent all characters, but ASCII can only represent English. Therefore, ASCII fails the first criterion.
But for the second criteria, it isn't so simple.

The following interactive will allow you to find out the length of pieces of text using UTF-8, UTF-16, or UTF-32. Find some samples of English text and Asian text (forums or a translation site are a good place to look), and see how long your various samples are when encoded with each of the three representations. Copy paste or type text into the box.

{interactive name="unicode-length" type="in-page"}

As a general rule, UTF-8 is better for English text, and UTF-16 is better for Asian text. UTF-32 always requires 32 bits for each character, so is unpopular in practice.

{panel type="curiosity" summary="Emoji and Unicode"}
Those cute little characters that you might use in your Facebook statuses, tweets, texts, and so on, are called "emojis", and each one of them has their own Unicode value.
Japanese mobile operators were the first to use emojis, but their recent popularity has resulted in many becoming part of the Unicode Standard and today there are well over 1000 different emojis included.
A current list of these can be seen [here](http://unicode.org/emoji/charts/full-emoji-list.html).
What is interesting to notice is that a single emoji will look very different across different platforms, i.e. &#128518 ("smiling face with open mouth and tightly-closed eyes") in my tweet will look very different to what it does on your iPhone.
This is because the Unicode Consortium only provides the character codes for each emoji and the end vendors determine what that emoji will look like, e.g. for Apple devices the "Apple Color Emoji" typeface is used (there are rules around this to make sure there is consistency across each system).
{panel end}

### Project: Messages hidden in music

There are messages hidden in this video using a 5-bit representation. See if you can find them! Start by reading the explanation below to ensure you understand what we mean by a 5-bit representation.

{video url="https://www.youtube.com/watch?v=L-v4Awj_p7g"}

If you *only* wanted to represent the 26 letters of the alphabet, and weren’t worried about upper-case or lower-case, you could get away with using just 5 bits, which allows for up to 32 different patterns.

You might have exchanged notes which used 1 for "a", 2 for "b", 3 for "c", all the way up to 26 for "z". We can convert those numbers into 5 digit binary numbers.
In fact, you will also get the same 5 bits for each letter by looking at the last 5 bits for it in the ASCII table (and it doesn't matter whether you look at the upper case or the lower case letter).

Represent the word "water" with bits using this system. Check the below panel once you think you have it.

{panel type="spoiler" summary="Representation for water}
```
w: 10111
a: 00001
t: 10111
e: 10100
r: 10010
```
{panel end}

**Now, have a go at decoding the music video!**

{panel type="teacher-note" summary="More information about the video"}
The video actually contains over 20 hidden messages, all using the 5-bit system.
An easy one to start with is the drum solo at the beginning.
The first 5 sounds are "kick kick snare kick kick".
Students need to decide which is 0 and which is 1; this number could either be 00100
(letter number 4, which is "d") or 11011 (letter number 27, which doesn't exist!)
Carrying on with the first option, the first few letters will spell "drum".

The challenges get harder (there are messages in most instrument parts and singing, as well as the dancing and background colours).
The song itself talks about how it is a form of "steganography", a term that students might like to research.

{panel end}


## Images and Colours

### How do computers display colours?

In school or art class you may have mixed different colours of paint or dye together in order to make new colours.
In painting it's common to use red, yellow and blue as three "primary" colours that can be mixed to produce lots more colours.
Mixing red and blue give purple, red and yellow give orange, and so on. By mixing red, yellow, and blue, you can make many new colours.

For printing, printers commonly use three slightly different primary colours: cyan, magenta, and yellow (CMY). All the colours on a printed document were made by mixing these primary colours.

Both these kinds of mixing are called "subtractive mixing", because they start with a white canvas or paper, and "subtract" colour from it. The interactive below allows you to experiment with CMY incase you are not familiar with it, or if you just like mixing colours.

{interactive name="cmy-mixer" type="in-page"}

Computer screens and related devices also rely on mixing three colours, except they need a different set of primary colours because they are *additive*, starting with a black screen and adding colour to it.
For additive colour on computers, the colours red, green and blue (RGB) are used.
Each pixel on a screen is typically made up of three tiny "lights"; one red, one green, and one blue. By increasing and decreasing the amount of light coming out of each of these three, all the different colours can be made. The following interactive allows you to play around with RGB.

{interactive name="rgb-mixer" type="in-page"}

See what colours you can make with the **RGB** interactive. Can you make black, white, shades of grey, yellow, orange, and purple?

{panel type="spoiler" summary="Hints for above"}
Having all the sliders at the extremes will produce black and white, and if they are all the same value but in between, it will be grey (i.e. between black and white).

Yellow is not what you might expect - it's made from red and green, with no blue.
{panel end}

{panel type="curiosity" summary="Primary colours and the human eye"}
There's a very good reason that we mix three primary colours to specify the colour of a pixel.
The human eye has millions of light sensors in it, and the ones that detect colour are called "cones". There are three different kinds of cones, which detect red, blue, and green light respectively. Colours are perceived by the amount of red, blue, and green light in them. Computer screen pixels take advantage of this by releasing the amounts of red, blue, and green light that will be perceived as the desired colour by your eyes. So when you see "purple", it's really the red and blue cones in your eyes being stimulated, and your brain converts that to a perceived colour.
Scientists are still working out exactly how we perceive colour, but the representations used on computers seem to be good enough give the impression of looking at real images.

{image filename="pixels-on-screens.jpg" alt="This image shows the small red, green, and blue pixels that are used on screens to display colour."}

For more information about RGB displays, see [RGB on Wikipedia](https://en.wikipedia.org/wiki/Rgb); for more information about the eye sensing the three colours, see [Cone cell](https://en.wikipedia.org/wiki/Cone_cell) and [trichromacy ](https://en.wikipedia.org/wiki/Trichromacy) on Wikipedia.
{panel end}

### Describing a colour with numbers

Because a colour is simply made up of amounts of the primary colours -- red, green and blue -- three numbers can be used to specify how much of each of these primary colours is needed to make the overall colour.

{panel type="jargon-buster" summary="Pixel"}
The word **pixel** is short for "picture element". On computer screens and printers an image is almost always displayed using a grid of pixels, each one set to the required colour. A pixel is typically a fraction of a millimeter across, and images can be made up of millions of pixels (one megapixel is a million pixels), so you can't usually see the individual pixels. Photographs commonly have several megapixels in them.

It's not unusual for computer screens to have millions of *pixels* on them, and the computer needs to represent a colour for each one of those pixels.
{panel end}

A commonly used scheme is to use numbers in the range 0 to 255. Those numbers tell the computer how fully to turn on each of the primary colour "lights" in an individual pixel. If red was set to 0, that means the red "light" is completely off. If the red "light" was set to 255, that
would mean the "light" was fully on.

With 256 possible values for each of the three primary colours (don't forget to count 0!), that gives 256 x 256 x 256 = 16,777,216 possible colours -- more than the human eye can detect!

{panel type="challenge" summary="What is special about 255?"}
Think back to the binary numbers section. What is special about the number 255,
which is the maximum colour value?

We'll cover the answer later in this section if you are still not sure!
{panel end}

The following interactive allows you to zoom in on an image to see the pixels that are used to represent it. Each pixel is a solid colour square, and the computer needs to store the colour for each pixel.
If you zoom in far enough, the interactive will show you the red-green-blue values for each pixel. You can pick a pixel and put the values on the slider above - it should come out as the same colour as the pixel.

{interactive name="pixel-viewer" type="whole-page" text="Pixel Viewer interactive"}

{panel type="curiosity" summary="Alternative material on bits and colour"}
Another exercise to see the relationship between bit patterns and colour images is [provided here](https://sites.google.com/a/bxs.org.uk/mrkershaw/ict/bitmapgraphics).
{panel end}

### Representing a colour with bits

The next thing we need to look at is how bits are used to represent each colour in a high quality image. Firstly, how many bits do we need? Secondly, how should we decide the values of each of those bits? This section will work through those problems.

#### How many bits will we need for each colour in the image?

With 256 different possible values for the amount of each primary colour, this means 8 bits would be needed to represent the number.

{math}2^8 = 2 \times 2 \times 2 \times 2 \times 2 \times 2 \times 2 \times 2 = 256{math end}

The smallest number that can be represented using 8 bits is 00000000 -- which is 0. And the largest number that can be represented using 8 bits is 11111111 -- which is 255.

Because there are three primary colours, each of which will need 8 bits to represent each of its 256 different possible values, we need **24 bits in total** to represent a colour.

{math}3 \times 8 = 24{math end}

So, how many colours are there in total with 24 bits? We know that there is 256 possible values each colour can take, so the easiest way of calculating it is:

{math}256 \times 256 \times 256 = 16,777,216 {math end}

This is the same as {math}2^{24}{math end}.

Because 24 bits are required, this representation is called **24 bit colour**. 24 bit colour is sometimes referred to in settings as "True Color" (because it is more accurate than the human eye can see). On Apple systems, it is called "Millions of colours".

#### How do we use bits to represent the colour?

A logical way is to use 3 binary numbers that represent the amount of each of red, green, and blue in the pixel. In order to do this, convert the amount of each primary colour needed to an 8 bit binary number, and then put the 3 binary numbers side by side to give 24 bits.

Because consistency is important in order for a computer to make sense of the bit pattern, we normally adopt the convention that the binary number for red should be put first, followed by green, and then finally blue. The only reason we put red first is because that is the convention that most systems assume is being used.
If everybody had agreed that green should be first, then it would have been green first.

For example, suppose you have the colour that has red = 145, green = 50, and blue = 123 that you would like to represent with bits. If you put these values into the interactive, you will get the colour below.

{image filename="colour-purple.png" alt="The colour purple."}

Start by converting each of the three numbers into binary, using 8 bits for each.

You should get:
- red = 10010001,
- green = 00110010,
- blue = 01111011.

Putting these values together gives 100100010011001001111011, which is the bit representation for the colour above.

There are **no spaces** between the three numbers, as this is a pattern of bits rather than actually being three binary numbers, and computers don’t have any such concept of a space between bit patterns anyway --- everything must be a 0 or a 1. You could write it with spaces to make it easier to read, and to represent the idea that they are likely to be stored in 3 8-bit bytes, but inside the computer memory there is just a sequence of high and low voltages, so even writing 0 and 1 is an arbitrary notation.

Also, all leading and trailing 0’s on each part are kept --- without them, it would be representing a shorter number. If there were 256 different possible values for each primary colour, then the final representation **must** be 24 bits long.

{panel type="curiosity" summary="Monochromatic images"}
"Black and white" images usually have more than two colours in them; typically 256 shades of grey, represented with 8 bits.

Remember that shades of grey can be made by having an equal amount of each of the 3 primary colours, for example red = 105, green = 105, and blue = 105.

So for a monochromatic image, we can simply use a representation which is a single binary number between 0 and 255, which tells us the value that all 3 primary colours should be set to.
{panel end}

The computer won’t ever convert the number into decimal, as it works with the binary directly --- most of the process that takes the bits and makes the right pixels appear is typically done by a graphics card or a printer. We just started with decimal, because it is easier for humans to understand.
The main point about knowing this representation is to understand the trade-off that is being made between the accuracy of colour (which should ideally be beyond human perception) and the amount of storage (bits) needed (which should be as little as possible).

{panel type="curiosity" summary="Hexadecimal colour codes"}
If you haven't already, read the section on [Hexadecimal](chapters/data-representation.html#shorthand-for-binary-numbers---hexadecimal), otherwise this section might not make sense!

When writing HTML code, you often need to specify colours for text, backgrounds, and so on. One way of doing this is to specify the colour name, for example “red”, “blue”, “purple”, or “gold”. For some purposes, this is okay.

However, the use of names limits the number of colours you can represent and the shade might not be exactly the one you wanted. A better way is to specify the 24 bit colour directly. Because 24 binary digits are hard to read, colours in HTML use **hexadecimal codes** as a quick way to write the 24 bits, for example #00FF9E. The hash sign means that it should be interpreted as a hexadecimal representation, and since each hexadecimal digit corresponds to 4 bits, the 6 digits represent 24 bits of colour information.

This "hex triplet" format is used in HTML pages to specify colours for things like the background of the page, the text, and the colour of links. It is also used in CSS, SVG, and other applications.

In the 24 bit colour example earlier, the 24 bit pattern was 100100010011001001111011.

This can be broken up into groups of 4 bits:  1001   0001   0011   0010   0111   1011.

And now, each of these groups of 4 bits will need to be represented with a **hexadecimal** digit.

- 1001 -> 5
- 0001 -> 1
- 0011 -> 3
- 0010 -> 2
- 0111 -> 7
- 1011 -> B

Which gives #51327B.

Understanding how these hexadecimal colour codes are derived also allows you to change them slightly without having to refer back the colour table, when the colour isn’t exactly the one you want. Remember that in the 24 bit color code, the first 8 bits specify the amount of red (so this is the first 2 digits of the hexadecimal code), the next 8 bits specify the amount of green (the next 2 digits of the hexadecimal code), and the last 8 bits specify the amount of blue (the last 2 digits of the hexadecimal code). To increase the amount of any one of these colours, you can change the appropriate hexadecimal letters.

For example, #000000 has zero for red, green and blue, so setting a higher value to the middle two digits (such as  #004300) will add some green to the colour.

You can use this HTML page to experiment with hexadecimal colours. Just enter a colour in the space below:

{interactive name="hex-background-colour" type="in-page"}

{panel end}


### Representing colours with fewer bits

What if we were to use fewer than 24 bits to represent each colour? How much space will be saved, compared to the impact on the image?

#### The range of colours with fewer bits

The following interactive gets you to try and match a specific colour using 24 bits, and then 8 bits.

It should be possible to get a perfect match using 24 bit colour. But what about 8 bits?

{interactive name="colour-matcher" type="whole-page" text="Colour Matcher interactive"}

The above system used 3 bits to specify the amount of red (8 possible values), 3 bits to specify the amount of green (again 8 possible values), and 2 bits to specify the amount of blue (4 possible values). This gives a total of 8 bits (hence the name), which can be used to make 256 different bit patterns, and thus can represent 256 different colours.

You may be wondering why blue is represented with fewer bits than red and green. This is because the human eye is the least sensitive to blue, and therefore it is the least important colour in the representation. The representation uses 8 bits rather than 9 bits because it's easiest for computers to work with full bytes.

Using this scheme to represent all the pixels of an image takes one third of the number of bits required for 24-bit colour, but it is not as good at showing smooth changes of colours or subtle shades, because there are only 256 possible colors for each pixel. This is one of the big tradeoffs in data representation: do you allocate less space (fewer bits), or do you want higher quality?

{panel type="jargon-buster" summary="Colour depth"}
The number of bits used to represent the colours of pixels in a particular image is sometimes referred to as its "colour depth" or "bit depth". For example, an image or display with a colour depth of 8-bits has a choice of 256 colours for each pixel. There is [more information about this in Wikipedia](https://en.wikipedia.org/wiki/Color_depth). Drastically reducing the bit depth of an image can make it look very strange; sometimes this is used as a special effect called "posterisation" (ie. making it look like a poster that has been printed with just a few colours).
{panel end}

{panel type="curiosity" summary="Colour depth and compression"}
There's a subtle boundary between low quality data representations (such as 8-bit colour) and compression methods. In principle, reducing an image to 8-bit colour is a way to compress it, but it's a very poor approach, and a proper compression method like JPEG will do a much better job.
{panel end}

#### What impact does fewer bits have on the overall image?

The following interactive shows what happens to images when you use a smaller range of colours (including right down to zero bits!) You can choose an image using the menu or upload your own one. In which cases is the change in quality most noticeable? In which is it not? In which would you actually care about the colours in the image? In which situations is colour actually not necessary (i.e. when are we fine with two colours)?

{interactive name="image-bit-comparer" type="whole-page" text="Image Bit Comparer"}

{panel type="additional-information" summary="Software for exploring colour depth"}
Although we provide a simple interactive for reducing the number of bits in an image, you could also use software like Gimp or Photoshop to save files with different colour depths.
{panel end}

You probably noticed that 8-bit colour looks particularly bad for faces, where we are used to seeing subtle skin tones. Even the 16-bit colour is noticably worse for faces.

In other cases, the 16-bit images are almost as good as 24-bit images unless you look really carefully. They also use two-thirds (16/24) of the space that they would with 24-bit colour. For images that will need to be downloaded on 3G devices where internet is expensive, this is worth thinking about carefully.

Have an experiement with the following interactive, to see what impact different numbers of bits for each colour has. Do you think 8 bit colour was right in having 2 bits for blue, or should it have been green or red that got only 2 bits?

{interactive name="image-bit-comparer" type="whole-page" text="Image Bit Comparer - Change Bits mode" parameters="change-bits=true"}

{panel type="curiosity" summary="Do we ever need more than 24 bit colour?"}
One other interesting thing to think about is whether or not we’d want more than 24 bit colour. It turns out that the human eye can only differentiate around 10 million colours, so the ~ 16 million provided by 24 bit colour is already beyond what our eyes can distinguish. However, if the image were to be processed by some software that enhances the contrast, it may turn out that 24-bit colour isn't sufficient. Choosing the representation isn't simple!
{panel end}

#### How much space will low quality images save?

An image represented using 24 bit colour would have 24 bits per pixel. In 600 x 800 pixel image (which is a reasonable size for a photo), this would contain {math}600 \times 800 = 480,000 {math end} pixels, and thus would use {math}480,000 \times 24 bits = 11,520,000 {math end} bits. This works out to around 1.44 megabytes. If we use 8-bit colour instead, it will use a third of the memory, so it would save nearly a megabyte of storage. Or if the image is downloaded then a megabyte of bandwidth will be saved.

8 bit colour is not used much anymore, although it can still be helpful in situations such as accessing a computer desktop remotely on a slow internet connection, as the image of the desktop can instead be sent using 8 bit colour instead of 24 bit colour. Even though this may cause the desktop to appear a bit strange, it doesn’t stop you from getting whatever it was you needed to get done, done. Seeing your desktop in 24 bit colour would not be very helpful if you couldn't get your work done!

In some countries, mobile internet data is very expensive. Every megabyte that is saved will be a cost saving. There are also some situations where colour doesn’t matter at all, for example diagrams, and black and white printed images.

#### What about in practice?

If space really is an issue, then this crude method of reducing the range of colours isn't usually used; instead, compression methods such as JPEG, GIF and PNG are used.

These make much more clever compromises to reduce the space that an image takes, without making it look so bad, including choosing a better palette of colours to use rather than just using the simple representation discussed above.
However, compression methods require a lot more processing, and images need to be decoded to the representations discussed in this chapter before they can be displayed.

The ideas in this present chapter more commonly come up when designing systems (such as graphics interfaces) and working with high-quality images (such as RAW photographs), and typically the goal is to choose the best representation possible without wasting too much space.

Have a look at the Compression Chapter to find out more!

## Program Instructions

{panel type="caution" expanded="True"}
Before reading this section, you should have an understanding of low level languages (see the section on [Machine Code in the Programming Languages](chapters/programming-languages.html#machine-code-low-level-languages) chapter).
{panel end}

In a similar fashion to representing text or numbers using binary, we can represent an entire actual program using binary.
Since a program is just a sequence of instructions, we need to decide how many bits will be used to represent a single instruction and then how we are going to interpret those bits.
Machine code instructions typically have a combination of two pieces: operation and operand.

```
li $t0, 10 #Load the value 10 into register $t0
li $t1, 20 #Load the value 20 into register $t1
#Add the values in $t0 and $t1, put the result in register $a0
add $a0, $t0, $t1
```

In the above machine code program li and add are considered to be operations to "load an integer" and "add two integers" respectively.
$t0, $t1, and $a0 are register operands and represent a place to store values inside of the machine.
10 and 20 are literal operands and allow instructions to represent the exact integer values 10 and 20.
If we were using a 32-bit operating system we might encode the above instructions with each instruction broken into 4 8-bit pieces as follows:

| Operation |    Op1   |    Op2   |   Op3    |
|-----------|----------|----------|----------|
| 00001000  | 00000000 | 00000000 | 00001010 |
| 00001000  | 00000001 | 00000000 | 00010100 |
| 00001010  | 10000000 | 00000000 | 00000001 |

Our operation will always be determined by the bits in the first 8-bits of the 32-bit instruction.
In this example machine code, 00001000 means li and 00001010 means add.
For the li operation, the bits in Op1 are interpreted to be a storage place, allowing 00000000 to represent $t0.
Similarly the bits in Op1 for the add instruction represent $a0.
Can you figure out what the bits in Op3 for each instruction represent?

Using bits to represent both the program instructions and data forms such as text, numbers, and images allows entire computer programs to be represented in the same binary format.
This allows programs to be stored on disks, in memory, and transferred over the internet as easily as data.

## The whole story!

The kind of image representations covered here are the basic ones used in most digital systems, and the main point of this chapter is to understand how digital representations work, and the compromises needed between the number of bits, storage used, and quality.

The colour representation discussed is what is often referred to as "raw" or "bitmap" (bmp) representation.
For large images, real systems use compression methods such as JPEG, GIF or PNG to reduce the space needed to store an image, but at the point where an image is being captured or displayed it is inevitably represented using the raw bits as described in this chapter, and the basic choices for capturing and displaying images will affect the quality and cost of a device.
Compression is regarded as a form of encoding, and is covered in a later chapter.

The representation of numbers is a whole area of study in itself.
The choice of representation affects how quickly arithmetic can be done on the numbers, how accurate the results are, and how much memory or disk space is used up storing the data.
Even integers have issues like the order in which a large number is broken up across multiple bytes.
Floating point numbers generally follow common standards (the IEEE 754 standard is the most common one) to make it easy to design compatible hardware to process them.
Spreadsheets usually store numbers using a floating point format, which limits the precision of calculations (typically about 64 bits are used for each number).
There are many experiments that can be done (such as calculating 1/3, or adding a very large number to a very small one) that demonstrate the limitations of floating point representations.


## Further reading

This puzzle can be solved using the pattern in binary numbers: [http://www.cs4fn.org/binary/lock/](http://www.cs4fn.org/binary/lock/)

[This site](http://courses.cs.vt.edu/~csonline/NumberSystems/Lessons/index.html) has more complex activities with binary numbers, including fractions, multiplication and division.


### Useful Links

- [Basics of binary numbers](http://csunplugged.org/binary-numbers)
- [Representing bits using sound](http://csunplugged.org/modem)
- [Hex game](http://www.purposegames.com/game/049fc90a)
- [Thriving in our digital world](http://www.cs.utexas.edu/~engage/) has good illustrations of data representation
- [How a hard disk works](http://ed.ted.com/lessons/how-do-hard-drives-work-kanawat-senanan)
u **pozycyjnego**, gdyż system dwójkowy (binarny) jest również systemem pozycyjnym, choć używa się w nim mniejszej liczby cyfr! r dates on Tuesday, 19 January 2038.

