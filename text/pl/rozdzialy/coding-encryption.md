# Kodowanie. Szyfrowanie

## Z lotu ptaka

Szyfrowanie służy do zachowania poufności danych. Najprościej rzecz ujmując, plik lub przesyłane dane są zniekształcane tak, że tylko właściwe osoby posiadające tajny ,,klucz'' mogą odtworzyć oryginalny tekst.
Gdy korzystasz z urządzeń cyfrowych, cały czas używasz systemów opartych na szyfrowaniu: kiedy korzystasz z bankowości internetowej, łączysz się z siecią Wi-Fi, płacisz kartą płatniczą (wkładając ją do czytnika, przesuwając pasek magnetyczny, albo dotykając czytnika); naprawdę wokół prawie każdej czynności pojawi się szyfrowanie.
Bez szyfrowania twoje informacje byłyby dostępne dla całego świata - każdy mógłby podjechać pod Twój dom i odczytać wszystkie dane przechodzące przez Twoją sieć Wi-Fi, a skradzione laptopy, dyski twarde i karty SIM byłyby źródłem wielu informacji o Tobie - więc szyfrowanie ma kluczowe znaczenie dla użyteczności systemów komputerowych.

System szyfrowania często składa się z dwóch programów komputerowych: pierwszy służy do *zaszyfrowania* danych (nazywanych *tekstem jawnym*), przekształcając je w coś przypominającego bzdury (*szyfrogram*), a drugi program służy do *odszyfrowania* szyfrogramu, zmieniając go z powrotem w tekst jawny. Szyfrowanie i deszyfrowanie polegają na użyciu bardzo sprytnych operacji matematycznych na tekście za pomocą wybranego *klucza*. Wkrótce dowiesz się więcej o tych pojęciach.

Oczywiście nie potrzebowalibyśmy szyfrowania, gdybyśmy żyli w świecie, w którym wszyscy byliby uczciwi i moglibyśmy im ufać -- wtedy każdy mógłby mieć dostęp do wszystkich Twoich danych osobowych, na przykład dokumentacji medycznej, wszystkiego co pisałeś w sieci, kont bankowych itd. i wiedzielibyśmy, że nikt by nie ingerował w takie rzeczy jak systemy kontroli samolotów i broń sterowana komputerowo. Jednak informacje są cenne, ludzie cenią sobie prywatność, a bezpieczeństwo jest ważne, dlatego szyfrowanie jest podstawą przy projektowaniu systemów komputerowych. Nawet złamanie zabezpieczeń systemu sygnalizacji świetlnej może być wykorzystane dla osiągnięcia osobistej korzyści.

{panel type="curiosity" title="Ciekawostka" summary="Hakowanie sygnalizacji świetlnej"}
Interesującym przykładem pokazującym, że należy używać szyfrowania nie tylko do tajnych wiadomości jest przypadek dwóch inżynierów, którzy zostali skazani za [zmianę rytmu sygnalizacji świetlnej w celu spowodowania chaosu podczas strajku](http://latimesblogs.latimes.com/lanow/2009/12/engineers-who-hacked-in-la-traffic-signal-computers-jamming-traffic-sentenced.html). Podobnym problemem w Stanach Zjednoczonych były sygnały drogowe, które reagowały na kody wysyłane przez pojazdy ratunkowe, zmieniając kolor na zielony; kiedyś nie korzystały one z szyfrowania i można było dojść do tego jak nimi sterować dla własnej korzyści.
{panel end}

Dużym problemem związanym z systemami szyfrowania są ludzie, którzy chcą się do nich włamać i odszyfrować wiadomości bez klucza (który jest jakąś tajną wartością, która może być użyta do odblokowania zaszyfrowanego pliku). Niektóre systemy, używane wiele lat temu, okazały się być niewystarczająco zabezpieczone przed takimi atakami, więc nie można ich już używać. Możliwe, że ktoś kiedyś znajdzie skuteczny sposób włamywania się do systemów powszechnie używanych obecnie, co spowodowałoby wiele problemów.

Jak każdą technologię, szyfrowanie można wykorzystać do dobrych i złych celów. Organizacja broniąca praw człowieka może użyć szyfrowania, aby potajemnie wysłać zdjęcia nadużyć w zakresie praw człowieka do mediów, a handlarze narkotyków mogą go użyć, aby zabezpieczyć swoje plany przed śledczymi. Zrozumienie w jaki sposób szyfrowanie działa i co jest możliwe przy jego użyciu, może pomóc w podejmowaniu świadomych decyzji dotyczących takich rzeczy jak wolność słowa, prawa człowieka, śledzenie działalności przestępczej, prywatność, kradzież tożsamości, bankowość i płatności internetowe oraz bezpieczeństwo systemów, które mogą zostać przejęte, jeśli zostały ,,zhakowane''.

{panel type="jargon-buster" title="Co to znaczy?" summary="Rozszyfrowywanie, deszyfrowanie, atakowanie, łamanie, hakowanie, kryptoanaliza, hakerzy i crackerzy"}
Istnieje wiele słów, którymi można określić próbę uzyskania tekstu jawnego z zaszyfrowanego tekstu, w tym: rozszyfrowanie, zdeszyfrowanie, złamanie i kryptoanaliza. Często próbę złamania mechanizmów kryptograficznych nazywamy ,,atakiem''. Terminu ,,hakowanie'' też się czasem używa, ale ma on też inne konotacje i jest używany tylko nieformalnie.

Ci, którzy próbują odszyfrować wiadomości, to kryptoanalitycy; czasem używa się mniej formalnych terminów, takich jak hakerzy i crackerzy, co zwykle sugeruje, że mają oni złe intencje.
Bycie kryptoanalitykiem jest jednak na ogół dobrą rzeczą -- używający systemów szyfrowania chcą wiedzieć, czy mają one słabe strony i nie chcą żeby pierwsi odkryli je ludzie o złych zamiarach.
To coś w rodzaju strażnika sprawdzającego drzwi w budynku; strażnik ma nadzieję, że nie da rady dostać się do środka, ale jeśli znajdzie otwarte drzwi, będzie mógł temu zaradzić, żeby żaden złoczyńca nie mógł dostać się do środka. Oczywiście jeśli strażnik znajdzie otwarte drzwi i wykorzysta to, żeby coś ukraść, to nie wykonuje on swojej pracy w sposób właściwy!
{panel end}


## Szyfry podstawieniowe

{panel type="teacher-note" title="Dla nauczyciela" summary="Zaczynamy od niezbyt bezpiecznego szyfru!"}
Ten podrozdział stanowi wprowadzenie do idei szyfrowania, wykorzystując bardzo prosty szyfr podstawieniowy zwany szyfrem Cezara. Choć szyfr Cezara nie jest już używany w praktyce, wciąż jest bardzo przydatny jako narzędzie do nauczania, ilustrujące podstawowe pojęcia i terminologię szyfrowania. Szyfr Cezara bardzo łatwo złamać, nawet bez pomocy komputera, ale to właśnie z tego powodu jest dobrym wprowadzeniem do procesów dotyczących szyfrów. Jedynym powodem, dla którego działał w czasach Juliusza Cezara, był niskim poziom umiejętności czytania i pisania wśród tych, którzy mogliby się na niego natknąć, dzięki czemu zakładaliby raczej, że był to obcy język, zamiast próbować go zaatakować. Uczeń liceum z XXI wieku powinien posiadać wszystkie umiejętności (czytania i pisania oraz matematyczne) potrzebne do złamania tego kodu.

Gdy uczniowie zrozumieją podstawowe pojęcia w szyfrze Cezara, mogą przejść do wyrafinowanych szyfrów używanych w praktyce.
{panel end}

### Rozgrzewka -- szyfr Cezara

Przyjrzymy się teraz prostemu szyfrowi podstawieniowemu nazywanemu szyfrem Cezara. Szyfr Cezara ma ponad 2000 lat i został wynaleziony przez Juliusza Cezara. Zanim przejdziemy dalej, spróbuj złamać ten prosty kod. Jeśli utkniesz, spróbuj popracować w małej grupie z przyjaciółmi i kolegami z klasy, aby móc wspólnie omawiać pomysły. Do wykonania tego ćwiczenia przyda się tablica lub długopis i papier.

```
TEDBY YN ZYVENXSK NY ZYVXYMI 
MJOUKT XK WSCTO BKDEXUYGK. 
EJITOWI ROVSUYZDOBK, MSOJKBYGOU S MJYVQYG.
LKNJ QYDYGI NY EMSOMJUS QNI DIVUY 
BYJVOQXK CSO DBJI QVYCXO CIQXKVI QGSJNUK. 
LONO WSKV MJOBGYXK YZKCUO XK BOMO. 
```
Gdy już zorientujesz się, co mówi tekst, ułóż tabelę z literami alfabetu w kolejności, a następnie wpisz literę, którą każda z nich reprezentuje w szyfrogramie. Powinieneś zauważyć ciekawy wzór.

Biorąc pod uwagę, jak łatwo można złamać ten szyfr, prawdopodobnie nie chciałbyś, aby Twoje dane bankowe były nim zaszyfrowane. W praktyce używa się znacznie silniejszych szyfrów, choć na razie będziemy dalej analizować szyfrowanie szyfrem Cezara, ponieważ jest to znakomite wprowadzenie do wielu pojęć związanych z szyfrowaniem.

{panel type="teacher-note" title="Dla nauczyciela" summary="Odpowiedź"}
Odpowiedź to:

```
JUTRO OD POLUDNIA DO POLNOCY
CZEKAJ NA MISJE RATUNKOWA.
UZYJEMY HELIKOPTERA, CIEZAROWEK I CZOLGOW.
BADZ GOTOWY DO UCIECZKI GDY TYLKO 
ROZLEGNA SIE TRZY GLOSNE SYGNALY GWIZDKA.
BEDE MIAL CZERWONA OPASKE NA RECE.
```

Niektóre techniki, których uczniowie mogli użyć do jego odszyfrowania, to:

- Szukanie ciekawych kombinacji liter. Na przykład niewiele jest w języku polskim słów dwuliterowych takich jak YN i NY w zaszyfrowanym tekście, które składają się z tych samych liter w różnej kolejności. 
- Szukanie słów jednoliterowych -- tu jedyne takie słowo występuje w ,,wyliczance'', co można zauważyć dostrzegając przecinek, a co wskazuje na to, że jest to ,,i''.
- Po domyśleniu się, które litery w zaszyfrowanym tekście odpowiadają literom w tekście jawnym, powinno się sporządzić ich listę i spojrzeć na inne słowa w zaszyfrowanym tekście używające tych samych liter.
- Szukanie liter w zaszyfrowanym tekście, które często występują; najprawdopodobniej odpowiadają one często występującym literom w języku polskim.
- Szukanie liter, które się NIE pojawiły (być może odpowiadają literom takim jak Q i X).

Jeśli uczniowie utknęli, być może trzeba im dać kilka wskazówek.

Tabela, którą powinni otrzymać, powinna wyglądać tak.

{image filename="caesar-cipher-table-2.png"}

Celem tego ćwiczenia było, aby uczniowie myśleli jak kryptoanalitycy i aby zobaczyli, dlaczego szyfr Cezara nie jest przydatny w praktyce.
{panel end}

### Jak działa szyfr Cezara?

Kiedy poznałeś szyfr Cezara w poprzednim podrozdziale i (miejmy nadzieję) złamałeś go, i odkryłeś, co mówi wiadomość, prawdopodobnie zauważyłeś jakie było powiązanie liter pierwotnej wiadomości z literami w odszyfrowanej wiadomości. Każda litera w pierwotnej wiadomości została zdekodowana do litery, która znajdowała się 10 miejsc przed nią w alfabecie. Sporządzona tabela powinna to pokazać. Oto tabela powiązań liter, w której litera ,,K'' oznacza ,,A''. Jeśli Twoja tabela jest odwrotna, czyli pokazuje zmianę ,,A'' na ,,K'' zamiast ,,K'' na ,,A'', to też wszystko w porządku. Jeśli nie byłeś w stanie złamać szyfru Cezara w poprzednim podrozdziale, wróć do niego teraz i zdekoduj przy użyciu tabeli.

{image filename="caesar-cipher-table-2.png"}

W tym przykładzie mówimy, że kluczem jest *10*, ponieważ klucze w szyfrze Cezara są liczbami od 1 do 25 (zastanów się, dlaczego nie chcemy klucza 26!), które określają, jak daleko należy obrócić alfabet. Gdybyśmy zamiast tego użyli klucza *8*, tabela konwersji będzie następująca.

{image filename="caesar-cipher-table-3.png"}

{panel type="jargon-buster" title="Co to znaczy?" summary="Co to jest klucz?"}
W szyfrze Cezara klucz reprezentuje liczbę miejsc o które należy obrócić alfabet. W powyższych przykładach użyliśmy kluczy ,,8'' i ,,10''. Bardziej ogólnie rzecz ujmując, klucz jest po prostu wartością wymaganą do wykonania operacji matematycznych do szyfrowania i deszyfrowania. Podczas gdy szyfr Cezara ma tylko 25 możliwych kluczy, prawdziwe systemy szyfrowania mają niewyobrażalnie dużą liczbę możliwych kluczy -- czasem klucze te zawierają setki lub nawet tysiące cyfr binarnych. Posiadanie ogromnej liczby różnych możliwych kluczy jest ważne, ponieważ sprawdzenie wszystkich 25 kluczy szyfru Cezara zajęłoby komputerowi mniej niż sekundę.

W świecie fizycznym zamek szyfrowy jest dokładną analogią szyfru (można wręcz wysłać tajną wiadomość w skrzynce zablokowanej za pomocą zamka szyfrowego).
Zakładamy, że jedyny sposób na otworzenie pudełka to odgadnięcie kombinacji zamka.
Kombinacja zamka jest *kluczem* dla pudełka.
Jeśli jest to trzycyfrowy zamek, jest tylko 1000 wartości do wypróbowania, co może nie zająć wiele czasu.
Czterocyfrowy zamek ma 10 razy więcej wartości do wypróbowania, więc jest o wiele bezpieczniejszy.
Oczywiście mogą istnieć sposoby zmniejszenia wymaganej ilości pracy -- na przykład, jeśli wiesz, że osoba, która je zablokowała, nigdy nie zostawia na widoku poprawnej cyfry, to masz tylko 9 cyfr do odgadnięcia dla każdego miejsca, a nie 10, co zajęłoby mniej niż trzy czwarte czasu!
{panel end}

Spróbuj eksperymentować z następującym programem interaktywnym dla szyfru Cezara. Prawdopodobnie będziesz chciał odwołać się do niego też później, podczas ćwiczeń w dalszych podrozdziałach dotyczących szyfru Cezara.

{interactive name="caesar-cipher" type="iframe"}

#### Odszyfrowanie szyfru Cezara

Wcześniej przyjrzeliśmy się *łamaniu* szyfru Cezara -- otrzymywaniu tekstu jawnego z zaszyfrowanego tekstu bez posiadania klucza. Jest jeszcze łatwiej *odszyfrować* szyfr Cezara, gdy **mamy** klucz. W praktyce dobry system szyfrowania zapewnia, że ​​tekst jawny nie może być uzyskany z zaszyfrowanego tekstu bez klucza, tj. może być *odszyfrowany*, ale nie *złamany*.

Jako przykład *deszyfrowania* za pomocą szyfru Cezara, załóżmy, że mamy następujący zaszyfrowany tekst i że klucz to 6.

```
GRG SG QUZG O JAFKMU VYG
```

Ponieważ wiemy, że klucz to 6, możemy odjąć 6 miejsc od każdej litery w zaszyfrowanym tekście. Na przykład litera 6 umieszczona przed ,,G'' to ,,A'', 6 miejsc przed ,,R'' to ,,L'', a 6 miejsc przed ,,S'' to ,,M''. Z tego wiemy, że pierwsze słowa to ,,ALA MA''. Przechodząc przez cały tekst zaszyfrowany, uzyskamy w ten sposób tekst jawny:

```
ALA MA KOTA I DUZEGO PSA
```

Powyższy program interaktywny może wykonać ten proces za Ciebie. Wystarczy umieścić tekst zaszyfrowany w polu po prawej stronie, wpisać klucz i nakazać odszyfrowanie. Powinieneś jednak wiedzieć jak samemu szyfrować wiadomości!

{panel type="challenge" title="Wyzwanie" summary="Odszyfrowanie szyfru Cezara"}
**Wyzwanie 1**

Odszyfruj następującą wiadomość za pomocą szyfru Cezara. Klucz to 4.

```
VSDWDCJVSAERMI WDCJVY GIDEVE NIWX TVSWXI 
```

**Wyzwanie 2**

Jaki jest klucz do następującego *szyfrogramu*?

```
TO JEST PODCHWYTLIWE PYTANIE
```
{panel end}


{panel type="teacher-note" title="Dla nauczyciela" summary="Odpowiedzi do odszyfrowywania szyfru Cezara"}
W przypadku pierwszego wyzwania odpowiedź brzmi:

```
ROZSZYFROWANIE SZYFRU CEZARA JEST PROSTE
```


W przypadku drugiego wyzwania odpowiedź wynosi 26 (lub 0 lub dowolna wielokrotność 26). Ponieważ jest to pełny obrót, tekst zaszyfrowany i tekst jawny są takie same.
{panel end}


#### Szyfrowanie szyfrem Cezara

Szyfrowanie jest równie proste. Zamiast obracać się do tyłu (odejmowanie), tak jak zrobiliśmy przy odszyfrowywaniu, obracamy do przodu (dodajemy) każdą literę w tekście o tyle miejsc, ile wynosi klucz. Załóżmy na przykład, że chcemy zaszyfrować poniższy tekst kluczem 7.

```
JAK SIE MASZ
```

Zaczęlibyśmy od ustalenia, że literą o 7 miejsc za ,,J'' jest ,,Q'', 7 miejsc za ,,A'' znajduje się ,,H'', a 7 miejsc za ,,K'' mamy ,,R''. Oznacza to, że pierwsze słowo tekstu jawnego zaszyfrujemy do ,,QHR'' w zaszyfrowanym tekście. Przechodząc przez cały tekst jawny, uzyskamy w ten sposób tekst zaszyfrowany:

```
QHR ZPL THZG
```

{panel type="challenge" title="Wyzwanie" summary="Szyfrowanie za pomocą szyfru Cezara"}
**Wyzwanie 1**

Zaszyfruj poniższą wiadomość za pomocą szyfru Cezara i klucza 20.

```
KOLEJNA LOSOWA WIADOMOSC DO ZASZYFROWANIA
```

**Wyzwanie 2**

Dlaczego użycie klucza 26 w poniższym komunikacie nie jest dobrym pomysłem?

```
KORZYSTANIE Z KLUCZA DWADZIESCIA SZESC W SZYFRZE CEZARA NIE JEST DOBRYM POMYSLEM
```
{panel end}


{panel type="teacher-note" title="Dla nauczyciela"  summary="Odpowiedzi do szyfrowania za pomocą szyfru Cezara"}
W przypadku pierwszego wyzwania odpowiedź brzmi:

```
EIFYDHU FIMIQU QCUXIGIMW XI TUMTSZLIQUHCU 
```

Zwróć uwagę, że jeśli uczniowie odejmują zamiast dodawać lub nieprawidłowo używają interaktywnego programu, otrzymają błędną odpowiedź.

W przypadku drugiego wyzwania odpowiedź jest dla uczniów oczywista. Użycie klucza 26 powoduje, że tekst jawny i tekst zaszyfrowany są takie same -- tak samo jak nieużywanie szyfrowania!
{panel end}


{panel type="curiosity" title="Ciekawostka" summary="Szyfr Cezara ROT13"}
Szyfr Cezara z kluczem 13 jest taki sam, jak operacja zwana [ROT13 (obróć o 13 znaków)](https://pl.wikipedia.org/wiki/ROT13), które jest czasem używane do zakrywania rzeczy takich jak puenta żartu, szczegóły fabuły opowiadania, odpowiedź na pytanie lub tekst, który może być obraźliwy. Łatwo jest ją odkodować (a do tego jest mnóstwo automatycznych systemów), ale użytkownik musi świadomie poprosić o odczytanie wersji odkodowanej. Klucz 13 dla szyfru Cezara ma interesującą właściwość polegającą na tym, że metoda szyfrowania jest identyczna z metodą odszyfrowywania, tj. ten sam program może być użyty w obu przypadkach. Wiele silnych metod szyfrowania próbuje uczynić procesy szyfrowania i odszyfrowywania jak najbardziej zbliżonymi, tak aby to samo oprogramowanie lub sprzęt mogły być użyte do obu tych zadań, zazwyczaj z niewielkimi tylko adaptacjami.
{panel end}

### Problemy z szyframi podstawieniowymi

{panel type="jargon-buster" title="Co to znaczy?" summary="Co to jest szyfr podstawieniowy?"}
Szyfr podstawieniowy oznacza po prostu, że każda litera w tekście jawnym zastępowana jest inną literą w celu utworzenia zaszyfrowanego tekstu. Jeśli ta sama litera pojawia się więcej niż jeden raz w tekście jawnym, to ma tę samą postać przy każdym wystąpieniu w zaszyfrowanym tekście. Na przykład wyrażenie ,,ALA MA KOTA'' ma wiele liter A. Wszystkie A w tekście jawnym mogą na przykład zmienić się na ,,C'' w zaszyfrowanym tekście. Szyfr Cezara jest przykładem szyfru podstawieniowego. Inne szyfry podstawieniowe są lepsze od szyfru Cezara, ponieważ litery nie są w nich uporządkowane, a niektóre starsze szyfry używają różnych symboli dla każdego symbolu. Jednak szyfry podstawieniowe łatwo się atakuje, ponieważ atak statystyczny jest prosty: wystarczy wyszukać kilka wspólnych liter i ciągów liter, a następnie dopasować je do typowych dla danego języka wzorców.
{panel end}

Do tej pory rozważaliśmy jeden sposób złamania szyfru Cezara: używanie wzorców w tekście. Poszukując charakterystycznych wzorców, takich jak jednoliterowe słowa, inne krótkie słowa, podwójne litery i znając reguły, takie jak to, że wszystkie słowa muszą zawierać co najmniej jedną samogłoskę (z wyjątkiem niektórych skrótów czy słów pisanych ,,po SMSowemu''), łatwo złamać  szyfr Cezara. Żadnego dobrego kryptosystemu nie powinno dać się analizować w ten sposób, tzn. system powinien być *semantycznie bezpieczny*.

{panel type="jargon-buster" title="Co to znaczy?" summary="Co rozumiemy pod pojęciem semantycznie bezpieczny?"}
Semantycznie bezpieczeństwo oznacza, że nie jest znany skuteczny algorytm, który mógłby użyć zaszyfrowanego tekstu, aby uzyskać jakiekolwiek informacje na temat tekstu jawnego, inne niż długość wiadomości. Jest bardzo ważne, aby stosowane w praktyce kryptosystemy były semantycznie bezpieczne.

Jak widzieliśmy powyżej, szyfr Cezara nie jest semantycznie bezpieczny.
{panel end}

Istnieje wiele innych sposobów na złamanie szyfru Cezara, którym przyjrzymy się w tej sekcji. Zrozumienie różnych prostych ataków na szyfry będzie ważne, gdy będziemy patrzeć na wyszukane, używane w praktyce kryptosystemy.

#### Analiza częstotliwościowa

Analiza częstotliwościowa polega na sprawdzaniu, ile razy każda litera pojawia się w zaszyfrowanej wiadomości, i wykorzystaniu tej informacji do złamania kodu. Jeśli litera pojawia się wiele razy w wiadomości, to jest o wiele bardziej prawdopodobne, że jest to ,,A'' niż na przykład ,,F''.

Poniższy program interaktywny ułatwia analizę fragmentu tekstu poprzez zliczanie częstotliwości liter.
Możesz wkleić tekst, aby zobaczyć, które litery występują najczęściej i najrzadziej. 

{interactive name="frequency-analysis" type="in-page"}

Następujący tekst został zakodowany przy użyciu szyfru Cezara.
Aby spróbować go zrozumieć, wklej go do analizatora statystycznego powyżej.

```

IQZLF BNFITRTXH EFBNJWF BNJQJ 
XYFYDXYDHESDHM BXPFETBJP PYTWDHM 
RTESF ZEDH IT FSFQNED PYTWJ QNYJWD 
BDXYJUZOF SFOHEJXHNJO, F B 
QFRFSNZ XEDKWZ RTLF SFBJY UTRTH 
SFOHEJXYXEJ UFWD QZG YWTOPN QNYJW
```

{panel type="teacher-note" title="Dla nauczyciela" summary="Alternatywny system analizy"}
Dostępne są również analizatory tekstu online, takie jak na [tej stronie](http://www.richkni.co.uk/php/crypta/freq.php).
Dla podanego tekstu podaje on wynik jak w poniższej tabeli:

```
Liczba wystąpień każdej litery w zaszyfrowanym tekście

F : 18       N : 9        S : 7        I : 3
J : 13       X : 9        Z : 6        M : 2
Y : 11       H : 9        R : 5        L : 2
T : 11       W : 8        O : 5        G : 1
E : 10       B : 8        P : 5        K : 1
D : 10       Q : 7        U : 3
```
{panel end}


,,A'' jest najczęstszą literą alfabetu polskiego. Rozsądnym byłoby więc przypuszczenie, że ,,F'' w zaszyfrowanym tekście odpowiada ,,A'' w tekście jawnym. Ponieważ ,,F'' jest o 5 liter po literze ,,A'' w alfabecie, możemy się domyślić, że kluczem jest 5. Jeśli umieścisz tekst zaszyfrowany w powyższym programie interaktywnym i ustawisz klucz o wartości 5, przekonasz się, że jest to rzeczywiście poprawny klucz.

{interactive name="caesar-cipher" type="iframe"}

{panel type="spoiler" title="Spojler" summary="Odszyfrowana wiadomość"}

Wiadomość, którą powinieneś odszyfrować, to:

```
DLUGA WIADOMOSC ZAWIERA WIELE 
STATYSTYCZNYCH WSKAZOWEK KTORYCH 
MOZNA UZYC DO ANALIZY KTORE LITERY
WYSTEPUJA NAJCZESCIEJ, A W 
LAMANIU SZYFRU MOGA NAWET POMOC 
NAJCZESTSZE PARY LUB TROJKI LITER
```
{panel end}


Jak głosi komunikat, długie wiadomości zawierają wiele wskazówek statystycznych. Bardzo krótkie wiadomości (np. tylko kilka słów) prawdopodobnie nie będą miały oczywistych trendów statystycznych. W bardzo długich wiadomościach (np. w całych książkach) *prawie* zawsze litera ,,A'' występuje najczęściej. Wikipedia ma [listę częstotliwości liter](https://pl.wikipedia.org/wiki/Alfabet_polski#Cz%C4%99sto%C5%9B%C4%87_wyst%C4%99powania_liter), które mogą ci się przydać.

{panel type="challenge" title="Wyzwanie" summary="Analiza częstotliwości"}

Umieść zaszyfrowany tekst w powyższym analizatorze częstotliwości, zgadnij jaki jest klucz (używając metody wyjaśnionej powyżej), a następnie spróbuj użyć tego klucza z tekstem zaszyfrowanym w powyższym programie interaktywnym. Spróbuj odgadnąć klucz w jak najmniejszej liczbie zgadywanek!

**Wyzwanie 1**

```
ID ZDATYCP LXPSDBDHR ZIDGP BDOCP QTO EGDQATBJ OAPBPR JONLPYPR PCPAXON ROTHIDIAXLDHRX
```
**Wyzwanie 2**

```
R OZE RDVYJHJNXD RDYVX YPUJ GDOZM D FOJMV UVEHPEZ YMPBDZ HDZENXZ XUZNOJNXD R EZUTFP KJGNFDH
```

**Wyzwanie 3**

```
RGYPGIQ RKGMPGIQ RQRQNWFPKC RGYPC RCPK RQOCBCNC RGYPGOW RCPW RQNKEBMK RQOCFMC 
```
{panel end}

{panel type="teacher-note" title="Dla nauczyciela" summary="Odpowiedzi do analizy częstotliwości"}
W pierwszym wyzwaniu najczęstszą literą jest ,,A'', a klucz to 15.

'''
TO KOLEJNA WIADOMOSC KTORA MOZNA BEZ PROBLEMU ZLAMAC UZYWAJAC ANALIZY CZESTOTLIWOSCI
'''

W pierwszym wyzwaniu najczęstszą literą jest ,,I'', a klucz to 21.

'''
W TEJ WIADOMOSCI WIDAC DUZO LITER I KTORA ZAJMUJE DRUGIE MIEJSCE CZESTOSCI W JEZYKU POLSKIM
'''

W trzecim wyzwaniu najczęstszą literą jest ,,P'', a klucz to 2. Oczywiście było to dużo trudniejsze niż dwa poprzednie!

'''
PEWNEGO PIEKNEGO POPOLUDNIA PEWNA PANI POMAZALA PEWNEMU PANU POLICZKI POMADKA
'''

{panel end}

{panel type="curiosity" title="Ciekawostka" summary="Litera A nie zawsze jest najczęstszą literą..."}
Chociaż w prawie wszystkich tekstach polskich litera A jest najczęstszą literą, to jednak nie jest tak zawsze. Niektóre utwory literackie (nazywane [lipogramami](https://pl.wikipedia.org/wiki/Lipogram)) są celowo pisane tak, żeby nie zawierać niektórych liter. Na przykład najbardziej znany polski lipogram, pochodzący z książki Juliana Tuwima [Pegaz dęba](https://pl.wikipedia.org/wiki/Pegaz_d%C4%99ba,_czyli_panopticum_poetyckie), nie zawiera w ogóle litery ,,R''. Ponadto tekst, który atakujesz, może nie być polski. Podczas pierwszej i drugiej wojny światowej w armii amerykańskiej służyło wielu Indian [Code talkers](https://pl.wikipedia.org/wiki/Code_talker), którzy tłumaczyli wiadomości na ich własny język, co w tamtych czasach zapewniało silną warstwę bezpieczeństwa.
{panel end}


{panel type="curiosity" title="Ciekawostka" summary="Szyfr Vigenere'a"}
Nieco silniejszym szyfrem niż szyfr Cezara jest [Szyfr Vigenere'a](https://pl.wikipedia.org/wiki/Szyfr_Vigen%C3%A8re%E2%80%99a), który jest tworzony przy użyciu wielu szyfrów Cezara, w którym występuje klucz w postaci frazy (np. ,,acb''), a każda litera w kluczu daje przesunięcie (w tym przykładzie będzie to 1, 3, 2). Przesunięcia te są powtarzane w celu uzyskania przesunięcia którym koduje się każdy znak w tekście jawnym.

Gdy mamy wiele szyfrów Cezara, często występujące litery, takie jak E, nie będą już się tak bardzo wyróżniać, czyniąc analizę częstotliwości o wiele trudniejszą. Poniższa strona internetowa (po angielsku) pokazuje wpływ tego rozwiązania na dystrybucję liter.
[http://www.simonsingh.net/The_Black_Chamber/vigenere_strength.html](http://www.simonsingh.net/The_Black_Chamber/vigenere_strength.html)

Jednakże, chociaż czyni to szyfr Vigenere'a trudniejszym do złamania niż szyfr Cezara, odkryto sposoby jego szybkiego złamania. W rzeczywistości, kiedy już znasz długość klucza, sprowadza się to po prostu do złamania kilku szyfrów Cezara (co, jak widzisz, jest proste i możesz nawet użyć analizy częstotliwości na poszczególnych szyfrach Cezara!). Opracowano kilka metod statystycznych do odkrycia długość klucza.

Atakowanie szyfru Vigenere'a przez wypróbowanie każdego możliwego klucza jest trudne, ponieważ jest o wiele więcej możliwych kluczy niż dla szyfru Cezara, ale atak statystyczny może działać dość szybko.
Szyfr Vigenere'a znany jest jako *polialfabetyczny szyfr podstawieniowy*, ponieważ używa wielu reguł podstawiania.
{panel end}


#### Ataki ze znanym tekstem jawnym

Innym rodzajem ataku jest *atak ze znanym tekstem jawnym*, w którym znasz część lub całe rozwiązanie. Na przykład, jeśli wiesz, że wszystkie moje wiadomości zaczynam od ,,DZIEN DOBRY'', możesz łatwo znaleźć klucz dla następującej wiadomości.

```
WSBXG WHUKR MTCGX LIHMDTGBX HWUXWSBX LBX P LHUHMX H ZHWSBGBX WKNZBXC
```

Nawet jeśli nie wiesz, że kluczem jest prosty obrót (nie wszystkie szyfry podstawieniowe takie są), to wiesz że D->W, Z->S, I->B, E->X, N->G, O->H, B->U, R->K, Y->R. To znacznie ułatwia rozszyfrowanie wiadomości. Wypisując znane litery, otrzymasz:

```
WSBXG WHUKR MTCGX LIHMDTGBX HWUXWSBX LBX P LHUHMX H ZHWSBGBX WKNZBXC
DZIEN DOBRY ___NE __O___NIE ODBEDZIE _IE _ _OBO_E O _ODZINIE DR__IE_
```
Znając wyżej podane sztuczki, wiemy że istnieje bardzo ograniczona liczba możliwości dla pozostałych liter. Spróbuj odszyfrować powyższy tekst.

{panel type="spoiler" title="Spojler"  summary="Powyższa wiadomość to..."}
Odszyfrowana wiadomość to:

```
DZIEN DOBRY TAJNE SPOTKANIE ODBEDZIE SIE W SOBOTE O GODZINIE DRUGIEJ
```
{panel end}

Atak ze znanym tekstem jawnym od razu łamie szyfr Cezara, ale dobry kryptosystem nie powinien mieć takiej luki, ponieważ ktoś może zaskakująco łatwo domyślić się, że dana wiadomość została wysłana. Na przykład typową wiadomością może być ,,nic do zgłoszenia''. W bankowości internetowej najprawdopodobniej pojawią się typowe komunikaty, takie jak nagłówki na rachunku bankowym lub części strony internetowej, które zawsze są wyświetlane. Jeszcze gorszy jest *atak z wybranym tekstem jawnym*, w którym ktoś skłania użytkownika, żeby wysłał wybraną wiadomość za pośrednictwem swojego systemu, żeby atakujący mógł zobaczyć, jaki jest odpowiadający jej szyfrogram.

Z tego powodu istotne jest, aby dobry kryptosystem nie był możliwy do złamania, nawet jeśli atakujący posiada fragmenty tekstu jawnego wraz z odpowiadającym im szyfrogramem. W tym celu kryptosystem powinien dawać inny zaszyfrowany tekst za każdym razem, gdy zaszyfrowana jest ta sama wiadomość. Początkowo może wydawać się to niemożliwe, chociaż istnieje kilka sprytnych technik stosowanych w prawdziwych systemach kryptograficznych.

{panel type="curiosity" title="Ciekawostka" summary="Bardziej ogólne szyfry podstawieniowe"}
Podczas gdy szyfr Cezara ma klucz określający obrót, bardziej ogólny szyfr podstawieniowy może losowo wymieszać cały alfabet. Wymaga to klucza składającego się z sekwencji 26 liter lub cyfr, określających które litery będą sobie odpowiadały. Na przykład pierwszą częścią klucza mogłoby być ,,D, Z, E'', co oznaczałoby D:A, Z:B, E:C. Klucz musiałby mieć kolejne 23 litery, aby określić resztę przyporządkowania.

Zwiększa to liczbę możliwych kluczy, a tym samym zmniejsza ryzyko ataku brutalnego. Literę A można zastąpić dowolną z 26 liter w alfabecie, następnie B może być zastąpione dowolną z pozostałych 25 liter (26 oprócz litery już zastępującej A), C może zostać zastąpiona dowolną z pozostałych 24 liter...

Daje nam to 26 możliwości dla A, razy 25 możliwości dla B, razy 24 dla C... aż do 2 możliwości dla Y i 1 dla Z.

{math}
26 \times 25 \times 24 \times 23 \times 22 \times 21 \times 20 \times 19 \times 18 \times 17 \times\\
16 \times 15 \times 14 \times 13 \times 12 \times 11 \times 10 \times 9 \times 8 \times 7 \times 6 \times\\
5 \times 4 \times 3 \times 2 \times 1 = 26!
{math end}

Reprezentowanie każdej z tych możliwości wymaga około 88 bitów, co sprawia, że rozmiar klucza szyfru wynosi około 88 bitów i choć to mniej niż we współczesnych standardach, to wcale nie jest tak źle!

Jednak to rozwiązuje tylko jeden z problemów. Inne techniki łamania szyfru Cezara, które poznaliśmy, są nadal wysoce skuteczne we wszystkich szyfrach podstawieniowych, w szczególności w analizie częstotliwości. Z tego powodu w praktyce potrzebujemy lepszych szyfrów, którym przyjrzymy się wkrótce.
{panel end}

#### Ataki brutalne

Innym podejściem do łamania szyfrogramu jest *atak brutalny*, który polega na wypróbowaniu wszystkich możliwych kluczy i sprawdzeniu, czy któryś z nich nie tworzy zrozumiałego tekstu. Jest to łatwe dla szyfru Cezara, ponieważ istnieje tylko 25 możliwych kluczy. Na przykład poniższy szyfrogram to pojedyncze słowo, ale jest zbyt krótkie, by przeprowadzić statystyczny atak. Umieść go w powyższym dekoderze i próbuj różne klucze, aż odszyfrujesz.

```
EIJUDJQSOZDYU
```

{panel type="teacher-note" title="Dla nauczyciela" summary="Odpowiedz na powyższe pytanie"}
Słowem tym jest ,,ostentacyjnie'' i zostało ono zakodowane poprzez przesunięcie 16 liter w prawo (lub 10 w lewo).
{panel end}

Obecnie klucze szyfrowania są zwykle liczbami o długości 128 bitów lub więcej. Można obliczyć, ile czasu zajęłoby wypróbowanie wszystkich możliwych 128-bitowych liczb, jeśli komputer mógłby przetestować milion na sekundę (w tym testując, czy każdy zdekodowany tekst zawiera polskie słowa). W końcu to odkryje wiadomość, ale po upływie czasu, którego to będzie wymagało, będzie mało prawdopodobne, aby jeszcze się to do czegokolwiek przydało -- a użytkownik klucza prawdopodobnie go zmienił!

Jeśli to policzymy, testowanie 128-bitowy klucza w tempie 1 000 000 na sekundę zajmie 10 790 283 070 000 000 000 000 000 lat. Oczywiście można znaleźć coś już w pierwszym roku, ale szanse na to są absurdalnie niskie i bardziej realistyczne byłoby mieć nadzieję na zdobycie najwyższej nagrody w Lotto trzy razy z rzędu (a prawdopodobnie zapewniłoby to więcej pieniędzy). Średnio będzie to zajmować około połowę tego czasu, czyli nieco ponad 5 000 000 000 000 000 000 000 000 lat. Nawet jeśli masz naprawdę szybki komputer, który może sprawdzić jeden bilion kluczy na sekundę (w praktyce jest to mało realne), zajmie to około 5 000 000 000 000 000 lat. Nawet gdybyś mógł zdobyć milion takich komputerów (jeszcze mniej realne w praktyce), to wymagałoby to 5 000 000 lat.

A nawet gdybyś miał sprzęt, który rozważaliśmy powyżej, ludzie zaczęliby używać większych kluczy. Każdy bit dodany do klucza podwoi liczbę lat potrzebnych do jego odgadnięcia. Wystarczy dodać 15 lub 20 bitów więcej do klucza w powyższym przykładzie, aby zwiększyć wymagany czas do wartości znacznie dłużej niż oczekiwany czas życia Ziemi i Słońca! W ten sposób prawdziwe kryptosystemy chronią się przed atakami brutalnej siły. Kryptografia w wielu przypadkach opiera się na niskich prawdopodobieństwach sukcesu.

Poniższy kalkulator obsługuje naprawdę wielkie liczby. Jeśli chcesz, możesz sprawdzić nasze powyższe obliczenia! Sprawdź również, co by się stało, gdyby rozmiar klucza był podwójny (tj. 256 bitów) lub gdyby został użyty klucz 1024 lub 2048 bitowy (co jest w dzisiejszych czasach powszechne).

{comment}
Tu trzeba wstawić kalkulator działający na wielkich liczbach
{comment end}

{panel type="curiosity" title="Ciekawostka" summary="Obliczalność -- problemy, których rozwiązanie zajmuje zbyt wiele czasu"}
Ataki brutalne wypróbowują każdy możliwy klucz, a liczba możliwych kluczy rośnie *wykładniczo* ze wzrostem długości klucza.
Jak widzieliśmy powyżej, żaden nowoczesny system komputerowy nie mógłby przetestować wszystkich możliwych wartości klucza 128-bitowego w rozsądnym czasie, a nawet gdyby było to możliwe, dodanie tylko jednego bitu podwajałoby czas jego działania.

W informatyce problemy wymagające wykładniczego czasu na rozwiązanie nie są generalnie uważane za
{glossary-link term="obliczalny" reference-text="Kodowanie -- szyfrowanie"} obliczalne {glossary-link end}.

Ustalenie, które problemy są obliczalne a które nie, jest dużym obszarem badań w dziedzinie informatyki -- wiele innych problemów, na których rozwiązaniu nam zależy, wydaje się nie być obliczalnymi, co jest bardzo frustrujące.
Dziedzina szyfrowania to jedna z niewielu sytuacji, w których cieszymy się, że algorytm nie jest obliczalny!

Niniejszy przewodnik zawiera [cały rozdział dotyczący obliczalności](chapters/complexity-tractability.html), w którym możesz dowiedzieć się więcej o tej problematyce.
{panel end}

{panel type="jargon-buster" title="Co to znaczy?" summary="Terminologia, którą powinieneś już znać"}
Oto najważniejsze rzeczy, które powinieneś zapamiętać: *tekst jawny* jest *zaszyfrowany* przez *szyfr* w celu utworzenia *szyfrogramu* przy użyciu *klucza szyfrowania*. Ktoś bez klucza szyfrującego, kto chce *zaatakować* szyfr, może próbować różnych podejść, w tym *ataku brutalnego* (wypróbowanie wszystkich możliwych kluczy), *analizy częstotliwości* (szukanie wzorców statystycznych) i *ataku ze znanym tekstem jawnym* (porównywanie znanego tekstu z odpowiadającym mu szyfrogramem w celu znalezienia klucza).

Jeśli otrzymasz do analizy przykład użycia prostego szyfru, powinieneś być w stanie mówić o nim używając właściwej terminologii.
{panel end}


## Kryptosystemy stosowane w praktyce

Opisane powyżej systemy podstawieniowe nie zapewniają żadnego zabezpieczenia w nowoczesnych systemach komputerowych.
W dalszej części tego rozdziału przyjrzymy się systemom szyfrowania, które są używane w praktyce.
Pierwszym wyzwaniem jest znalezienie sposobu na wymianę kluczy -- jeśli komunikujesz się z kimś przez Internet, jak zamierzasz wysłać mu klucz do swojej tajnej wiadomości?

Kryptosystemy są również wykorzystywane do celów takich jak *uwierzytelnianie* (sprawdzanie hasła).
Wydaje się to łatwe, ale jak sprawdzić, czy ktoś się loguje, *bez* konieczności przechowywania hasła (w końcu, jeśli ktoś uzyskał listę haseł, może to zrujnować twoją reputację i firmę, więc bezpieczniej jest ich w ogóle nie przechowywać.)

Istnieją dobre rozwiązania tych problemów, które są powszechnie używane -- w rzeczywistości prawdopodobnie używasz ich już online, być może nawet o tym nie wiedząc!
Zaczniemy od spojrzenia na systemy, które umożliwiają odkodowywanie tajnych wiadomości bez konieczności wysyłania klucza.

## Problem dystrybucji kluczy

{panel type="curiosity" title="Ciekawostka" summary="Kim są Alicja, Bob i Ewa?"}
Podczas opisywania scenariusza szyfrowania kryptolodzy często używają wymyślonych postaci -- ,,Alicji'' i ,,Boba'', przy czym wiadomość jest wysyłana od Alicji do Boba (od A do B).
Zawsze zakładamy, że ktoś podsłuchuje rozmowę (w rzeczywistości, jeśli korzystasz z połączenia bezprzewodowego, podsłuchanie transmisji między Alicją i Bobem jest trywialne, dopóki jesteś w zasięgu sieci bezprzewodowej, której jedno z nich używa).
Wymyślone imię podsłuchującego to zwykle Ewa.

{image filename="xkcd-protocol.png" alt="Komiks xkcd o protokołach" hover-text="Zmiana imion byłaby łatwiejsza, ale jeśli kłamanie nie idzie ci dobrze, spróbuj przyjaźnić się tylko z ludźmi o imionach Alicja, Bob, Carol, itp." source="https://xkcd.com/1323/"}

Istnieje kilka innych postaci używanych do opisywania czynności związanych z protokołami szyfrowania: na przykład Mallory (złośliwy atakujący) i Trudy (intruz). Wikipedia ma [listę przyjaciół Alicji i Boba](https://pl.wikipedia.org/wiki/Alicja_i_Bob)
{panel end}

Jeśli Alicja wysyła zaszyfrowaną wiadomość do Boba, powoduje to interesujący problem w szyfrowaniu.
Sam szyfrogram może być bezpiecznie wysłany przez ,,niebezpieczną'' sieć (podsłuchiwaną przez Ewę), ale klucz -- nie. Jak Alicja może dostarczyć klucz Bobowi? Pamiętaj, że klucz to jest to, co mówi Bobowi, jak przekształcić szyfrogram z powrotem w tekst jawny. Zatem Alicja nie może umieścić go w zaszyfrowanej wiadomości, ponieważ wtedy Bob nie mógłby uzyskać do niego dostępu. Alicja nie może po prostu włączyć go do wiadomości jako zwykły tekst, ponieważ wtedy Ewa będzie mogła go pobrać i użyć go do odszyfrowania wiadomości, które będą nim zaszyfrowane. Możesz zapytać, dlaczego Alicja nie zaszyfruje klucza za pomocą innego schematu szyfrowania, ale skąd Bob miałby znać ten nowy klucz? Alicja musiałaby przekazać Bobowi klucz, który został użyty do jego zaszyfrowania... i tak dalej... Ten pomysł nie zadziała!

Pamiętaj, że Alicja i Bob mogą być w różnych krajach i mogą komunikować się tylko przez Internet. To również wyklucza przekazanie klucza Bobowi osobiście przez Alicję.

{panel type="curiosity" title="Ciekawostka" summary="Czy jesteśmy paranoikami?"}
W kwestii bezpieczeństwa komputerowego zakładamy, że Ewa, podsłuchujący, może odczytać każdą wiadomość między Alicją i Bobem.
Brzmi to jak niewiarygodny poziom podsłuchu, ale co z systemami bezprzewodowymi?
Jeśli korzystasz z sieci bezprzewodowej (lub telefonu komórkowego), wszystkie dane są nadawane i mogą zostać odebrane przez dowolny odbiornik bezprzewodowy w pobliżu.
W rzeczywistości, jeśli inna osoba w pokoju również korzysta z łączności bezprzewodowej, ich komputer już i tak odbiera wszystko, co jest przesyłane przez twój komputer, i musi zadać sobie trud ignorowania tego. 

Nawet w połączeniu przewodowym dane są przekazywane z węzła sieciowego do węzła sieciowego, przechowywane na komputerach pomiędzy nimi.
Możliwe, że wszyscy, którzy obsługują te komputery, są godni zaufania, ale trudno nawet stwierdzić, które firmy przetwarzały twoje dane w ciągu ostatnich 24 godzin, nie mówiąc już o tym, czy można zaufać każdemu ich pracownikowi.

Założenie, że ktoś może obserwować każdy bit wysyłany i odbierany przez twój komputer, jest więc całkiem rozsądne.
{panel end}

Fizyczna dystrybucja kluczy jest bardzo kosztowna, a do lat 70. XX wieku wydawano duże sumy na fizyczne wysyłanie kluczy za granicę. Takie systemy są nazywane szyfrowaniem *symetrycznym*, ponieważ Alicja i Bob potrzebują identycznej kopii klucza. Przełomem było odkrycie, że można stworzyć system wykorzystujący różne klucze do kodowania i dekodowania. Przyjrzymy się temu bliżej w następnym podrozdziale.

{panel type="curiosity" title="Ciekawostka" summary="Garść dodatkowych informacji"}
[Wideo Simona Singha](http://simonsingh.net/media/online-videos/cryptography/the-science-of-secrecy-going-public/) dobrze wyjaśnia (po angielsku) dystrybucję kluczy.

Poniższy film (również po angielsku) ilustruje działanie systemów kluczy publicznych przy użyciu analogii kłódki.

{video url="https://www.youtube.com/watch?v=a72fHRr6MRU"}
{panel end}

{panel type="teacher-note" title="Dla nauczyciela" summary="Jeszcze więcej o Alicji i Bobie"}
Jest [angielska piosenka o Alicji i Bobie](http://www.catonmat.net/blog/musical-geek-friday-alice-and-bob/) w wykonaniu rapera MC Plus+ (tak, specjalizuje się w informatyce). Niektóre użyte wyrażenia mogą być zbyt niestosowne żeby puścić piosenkę w klasie, więc zanim to zrobisz -- zastanów się.

{image filename="xkcd-alice-and-bob.png" hover-text="Jeszcze jeden powód, dla którego nie pozwalają mi jeździć na konferencje kryptologiczne." alt="Komiks xkcd o Alicji i Bobie" źródło="https://xkcd.com/177/"}
{panel end}


### Szyfrowanie z kluczem publicznym

Jednym z niezwykłych odkryć w dziedzinie informatyki w latach 70. była metoda zwana *szyfrowaniem z kluczem publicznym*, w której można powiedzieć wszystkim, co jest kluczem do szyfrowania wiadomości, ale do odszyfrowania potrzebny jest specjalny klucz prywatny. Ponieważ Alicja i Bob używają różnych kluczy, nazywa się to *asymetrycznym* systemem szyfrowania.

To tak, jakby rozdawać kłódki wszystkim swoim znajomym, aby każdy mógł zamknąć pudełko i wysłać je do ciebie, ale jeśli masz jedyny (prywatny) klucz, to jesteś jedyną osobą, która może otworzyć pudełka. Gdy znajomy zamknie pudełko, nawet on nie będzie mógł go otworzyć. Dystrybucja kłódek jest bardzo łatwa. Klucze publiczne są takie same -- możesz je upublicznić -- często ludzie umieszczają je na swojej stronie internetowej lub dołączają do wszystkich emaili, które wysyłają. To zupełnie inna jakość niż konieczność wynajęcia firmy ochroniarskiej, która dostarczy je twoim kolegom.

Szyfrowanie z kluczem publicznym jest bardzo często wykorzystywane w handlu elektronicznym (takim jak bankowość internetowa i płatność kartą kredytową), ponieważ komputer może nawiązać połączenie z firmą lub bankiem automatycznie, korzystając z publicznego klucza, bez konieczności wcześniejszego spotkania w celu uzgodnienia klucza. Systemy klucza publicznego są zwykle wolniejsze od systemów symetrycznych, dlatego system kluczy publicznych jest często używany do wysyłania nowego klucza dla systemu symetrycznego tylko raz na sesję, a od tego momentu klucz symetryczny może już być używany do szybszego, symetrycznego systemu szyfrowania.

Bardzo popularnym systemem klucza publicznego jest RSA. W tym podrozdziale dotyczącym systemów z kluczem publicznym użyjemy RSA jako przykładu.

#### Generowanie kluczy szyfrowania i deszyfrowania

{panel type="teacher-note" title="Dla nauczyciela" summary="Pomysły na zabawę z RSA w klasie"}
Jedna z rzeczy, które możesz zrobić, to poprosić każdego ucznia o wygenerowanie pary kluczy, a następnie umieścić ich klucze publiczne z  nazwiskami w udostępnionym arkuszu kalkulacyjnym (na przykład dokumencie google). Następnie, gdy uczniowie będą chcieli wysłać zaszyfrowaną wiadomość do jednego z kolegów z klasy, mogą wyszukać klucz publiczny danej osoby w arkuszu kalkulacyjnym.
{panel end}

Po pierwsze, musisz wygenerować parę kluczy za pomocą interaktywnego generatora kluczy. Powinieneś *zachować klucz prywatny w tajemnicy* i *publicznie ogłaszać klucz publiczny*, aby twoi znajomi mogli wysyłać ci wiadomości (np. umieść je na tablicy lub wyślij je pocztą elektroniczną do znajomych). Upewnij się, że masz gdzieś zapisane klucze, żeby ich nie zapomnieć -- najlepiej w pliku tekstowym.

{interactive name="rsa-key-generator" type="in-page"}

#### Szyfrowanie wiadomości za pomocą klucza publicznego

Poniższy interaktywny program jest szyfratorem i służy do szyfrowania wiadomości za pomocą **klucza publicznego**. Twoi przyjaciele powinni użyć go do zaszyfrowania wiadomości.

{interactive name="rsa-no-padding" type="iframe"}

Aby się upewnić, że rozumiesz, spróbuj zaszyfrować krótką wiadomość za pomocą **klucza publicznego**. W następnej sekcji znajduje się interaktywny program, którego możesz użyć do odszyfrowania wiadomości za pomocą swojego klucza prywatnego.

#### Deszyfrowanie wiadomości za pomocą klucza prywatnego

Poniższy program interaktywny jest deszyfratorem. Służy do odszyfrowywania wiadomości zaszyfrowanych za pomocą klucza publicznego. Aby odszyfrować wiadomości, potrzebujesz **klucza prywatnego**.

{interactive name="rsa-no-padding" type="iframe" parameters="mode = decrypt"}

Nawet gdy twoi wrogowie znają twój klucz publiczny (skoro go publicznie ogłosiłeś), nie mogą go użyć do odszyfrowania wiadomości, które zostały zaszyfrowane przy jego użyciu. Jesteś jedyną osobą, która może odszyfrować wiadomości, ponieważ wymaga to klucza prywatnego, do którego, miejmy nadzieję, tylko ty masz dostęp.

Zauważ, że implementacja RSA w tym programie interaktywnym jest po prostu demonstracją koncepcji i nie jest zupełnie taka sama jak implementacje używane w systemach szyfrowania wykorzystywanych w rzeczywistości.

{panel type="curiosity" title="Ciekawostka" summary="Czy możemy odwrócić obliczenia RSA?"}

Jeśli zostałbyś poproszony o pomnożenie dwóch dużych liczb pierwszych, okaże się że ręczne wykonanie tego jest trochę męczące (chociaż jest to zdecydowanie możliwe), a w ciągu ułamka sekundy można uzyskać odpowiedź za pomocą komputera.

```
97394932817749829874327374574392098938789384897239489848732984239898983986969870902045828438234520989483483889389687489677903899
```

```
34983724732345498523673948934032028984850938689489896586772739002430884920489508348988329829389860884285043580020020020348508591
```

Ale z drugiej strony, jeśli zostałeś zapytany, jakie dwie liczby pierwsze zostały pomnożone, aby uzyskać poniższą wielką liczbę, miałbyś o wiele większy problem! (Jeśli znajdziesz odpowiedź, daj nam znać! Będziemy bardzo zainteresowani!)

```
3944604857329435839271430640488525351249090163937027434471421629606310815805347209533599007494460218504338388671352356418243687636083829002413783556850951365164889819793107893590524915235738706932817035504589460835204107542076784924507795112716034134062407
```

Utworzenie kodu RSA wymaga wykonania powyższego mnożenia, co jest łatwe dla komputerów.
Gdybyśmy mogli rozwiązać drugi problem i znaleźć czynniki dużej liczby, moglibyśmy złamać kod RSA.
Jednak nikt nie zna szybkiego sposobu, aby to zrobić.
Nazywa się to jednokierunkową funkcja z zapadką -- łatwo jest ją zrobić w jednym kierunku (pomnożyć dwie liczby), ale jest prawie niemożliwe jej odwrócenie (znalezienie czynników), chyba że się zna jakąś tajną informację pozwalającą przejść ,,zapadkę'' (np. jeden z czynników).

Dlaczego więc, pomimo że te dwa problemy są podobne, jeden z nich jest ,,łatwy'', a drugi ,,trudny''? Cóż, sprowadza się to do znanych nam algorytmów rozwiązania każdego z problemów.

Prawdopodobnie robiłeś mnożenia w słupku w szkole, pisząc jeden wiersz dla każdej cyfry drugiej liczby, a następnie dodając wszystkie wiersze. Możemy analizować szybkość tego algorytmu, podobnie jak to robiliśmy w rozdziale dotyczącym algorytmów sortowania i wyszukiwania.
Zakładając, że każdy z tych dwóch numerów ma taką samą liczbę cyfr, którą nazwiemy *n*, musimy napisać *n* wierszy.
W każdym z tych *n* wierszy będziemy musieli wykonać około *n* mnożeń.
To daje nam {math}n \times n{math end} małych mnożeń.
Musimy także dodać *n* wierszy na końcu, ale to nie trwa długo, więc tę część zignorujmy.
Ustaliliśmy, że liczba małych mnożeń potrzebnych do pomnożenia dwóch dużych liczb jest w przybliżeniu kwadratem liczby cyfr.
Więc dla dwóch liczb o 1000 cyfr, to 1 000 000 małych operacji mnożenia.
Komputer może to zrobić szybciej niż w sekundę! Jeśli znasz notację Landaua, jest to algorytm o złożoności {math}O(n^2){math end}, gdzie *n* to liczba cyfr.
Warto wspomnieć, że są znane nieco lepsze algorytmy, ale powyższe oszacowanie jest wystarczająco dobre dla naszych celów.

Do rozwiązania drugiego problemu potrzebowalibyśmy algorytmu, który mógłby znaleźć dwie liczby, które zostały pomnożone.
Najpierw możesz spytać, dlaczego nie możemy po prostu odwrócić tego mnożenia? Odwrotność mnożenia to dzielenie, więc czy nie możemy po prostu podzielić, aby uzyskać te dwie liczby?
To dobry pomysł, ale nie zadziała.
Żeby podzielić, musimy znać dużą liczbę i jedną z małych liczb, przez którą chcemy podzielić, i to da nam tę drugą małą liczbę.
Ale w tym przypadku my znamy *tylko* dużą liczbę. Wcale nie jest to prosty problem dzielenia pisemnego!
Okazuje się, że nie jest znany szybki algorytm, który rozwiązałby ten problem. Jednym ze sposobów jest po prostu próba dzielenia przez każdą liczbę, która jest mniejsza niż dana liczba (cóż, właściwie musimy dojść tylko do pierwiastka kwadratowego, ale to niewiele pomoże!). Istnieją miliardy miliardów miliardów liczb, które musielibyśmy sprawdzić. Nie pomoże nam w tym nawet komputer, który mógłby sprawdzić 1 miliard możliwości na sekundę! Jeśli znasz notację Landaua, to jest to {math}algorytm o złożoności O(10^n){koniec matematyki}, gdzie n to liczba cyfr -- nawet mała liczba cyfr to zbyt wiele, by sobie z tym poradzić!
Są nieco lepsze rozwiązania, ale żadne z nich nie pozwala oszczędzić wystarczająco dużo czasu, aby było użyteczne dla problemów o wielkości takiej jak powyżej!

Rozdział poświęcony [złożoności i obliczalności](chapters/ complexity-tractability.html) przedstawia więcej problemów informatycznych, które są zaskakująco trudne do rozwiązania. Jeśli uważasz, że jest to interesujące, przeczytaj o złożoności i obliczalności, gdy skończysz ten rozdział.
{panel end}

{panel type="curiosity" title="Ciekawostka" summary="Szyfrowanie za pomocą klucza prywatnego zamiast klucza publicznego -- podpisy cyfrowe!"}
Aby zaszyfrować wiadomość, używany jest klucz publiczny. Aby ją odszyfrować, należy użyć odpowiedniego klucza prywatnego. Ale co by się stało, gdyby wiadomość została zaszyfrowana przy użyciu klucza *prywatnego*? Czy można odszyfrować ją za pomocą klucza publicznego?

Początkowo może to brzmieć bezsensownie -- dlaczego miałbyś zaszyfrować wiadomość, którą można odszyfrować za pomocą klucza dostępnego dla wszystkich na świecie!?! Okazuje się, że szyfrowanie wiadomości kluczem prywatnym, a następnie odszyfrowanie jej za pomocą klucza publicznego, działa i ma bardzo przydatne zastosowanie.

Jedyną osobą, która może *zaszyfrować* wiadomość przy użyciu klucza *prywatnego*, jest osoba, która jest właścicielem klucza prywatnego. Klucz publiczny odszyfruje wiadomość tylko wtedy, gdy klucz prywatny użyty do jej zaszyfrowania jest kluczem prywatnym pasującym do klucza publicznego. Jeśli wiadomości nie można odszyfrować, to nie mogła być zaszyfrowana za pomocą tego klucza prywatnego.
Dzięki temu nadawca może dowieść, że wiadomość faktycznie pochodzi od niego i jest to znane jako
{glossary-definition term="Podpis cyfrowy" definition="System szyfrowania, który umożliwia odbiorcy sprawdzenie, czy dokument został wysłany przez osobę, która twierdzi, że go wysłała."}
{glossary-link term="Digital signature"}podpis cyfrowy{glossary-link end}.

Możesz sprawdzić, czy ktoś jest autentycznym posiadaczem prywatnego klucza, podając mu frazę do zaszyfrowania kluczem prywatnym. Następnie odszyfrujesz ją za pomocą klucza publicznego, aby sprawdzić, czy rzeczywiście zaszyfrował frazę, którą mu dałeś.

Pełni to taką samą funkcję jak fizyczny podpis, ale jest bardziej niezawodne, ponieważ jest w zasadzie niemożliwe do podrobienia.
Niektóre systemy pocztowe tego używają, aby mieć pewność, że email pochodzi od osoby, która twierdzi, że ją wysłała.

{panel end}

{comment}
Ten podrozdział o RSA zostanie dopiero napisany.
### RSA w praktyce

Odnośniki do programów interaktywnych RSA, korzystających z biblioteki jsencrypt, rzeczywiście używanej w poważnych zastosowaniach.
{interactive name="rsa-jsencrypt" type="whole-page" text="Szyfrator RSA (z wypełnieniem)"}
{interactive name="rsa-jsencrypt" type="whole-page" text="Deszyfrator RSA (z wypełnieniem)" parameters="mode=decrypt"}

#### Jak działa RSA?

#### Zapobieganie atakom ze znanym tekstem jawnym

#### Powszechne użycie
{comment end}

## Bezpieczne przechowywanie haseł

Naprawdę interesującym zagadnieniem w szyfrowaniu jest przechowywanie haseł w taki sposób, że nawet jeśli baza danych z hasłami zostanie ujawniona, hasła nie będą miały użytecznej postaci. Taki system ma wiele pozornie sprzecznych wymagań.

- Kiedy użytkownik się loguje, musi być możliwe sprawdzenie, czy wprowadzono poprawne hasło.
- Nawet jeśli baza danych wycieknie, a atakujący ma ogromną moc obliczeniową...
- Baza danych nie powinna zdradzać oczywistych informacji, takich jak długości haseł, użytkowników, którzy wybierali te same hasła, częstotliwości liter w hasłach lub wzorców w hasłach.
- Użytkownicy powinni mieć co najmniej kilka dni / tygodni, aby móc zmienić hasło, zanim napastnik je złamie. Najlepiej byłoby, gdyby nigdy nie uzyskał hasła.
- Nie powinno być możliwości odzyskania zapomnianego hasła. Jeśli użytkownik zapomni hasła, musi ono zostać zmienione. Nawet administratorzy systemu nie powinni mieć dostępu do hasła użytkownika.

Większość systemów logowania ma limit, ile razy można zgadywać hasło. Chroni to wszystkie hasła, oprócz najgorzej wybranych, przed odgadnięciem przez dobrze zaprojektowany formularz logowania. Wykrywanie podejrzanego logowania przez sprawdzanie adresu IP i kraju pochodzenia również staje się coraz częstsze. Jednak żadne z tych wymuszonych zabezpieczeń nie działa, gdy atakujący ma kopię bazy danych i może użyć tyle mocy obliczeniowej, ile chce, bez ograniczeń nakładanych przez aplikację. Jest to często nazywane atakiem *offline*, ponieważ atakujący może zaatakować bazę danych u siebie.

W tym podrozdziale przyjrzymy się kilku szeroko stosowanym algorytmom bezpiecznego przechowywania haseł. Następnie przyjrzymy się kilku przypadkom, w których wyciekły duże bazy danych. Bezpieczne przechowywanie haseł sprowadza się do używania sprytnych algorytmów i technik szyfrowania oraz sprawienia, by użytkownicy wybierali skuteczne hasła. Wiedza na temat przechowywania haseł może również pomóc w zrozumieniu znaczenia wyboru dobrych haseł i nieużywania tego samego hasła w wielu różnych, ważnych stronach WWW.

### Haszowanie haseł

*Algorytm haszowania* to algorytm, który przyjmuje hasło i wykonuje na nim złożone obliczenia, a następnie zwraca pozornie losowy ciąg znaków zwany *skrótem* lub *haszem*. Ten proces nazywa się *haszowaniem*. Dobre algorytmy haszowania mają następujące właściwości:

- Za każdym razem, gdy dane hasło jest haszowane, powinno ono dawać ten sam skrót.
- Mając dany konkretny **hasz**, nie powinno być możliwe szybkie wyliczenie oryginalnego hasła.

Matematycznie algorytm skrótu nazywany jest ,,funkcją jednokierunkową''. Oznacza to po prostu, że bardzo łatwo jest obliczyć hasz danego hasła, ale próba odzyskania hasła z danego hasza może być wykonana tylko przez brutalną siłę. Innymi słowy, łatwo jest robić w jedną stronę, ale prawie niemożliwe jest odwrócenie. Popularny algorytm haszowania nazywa się SHA-256. Pozostała część tego rozdziału skupi się na SHA-256.

{panel type="jargon-buster" title="Co to znaczy?" summary="Co oznacza brutalna siła?"}
W podrozdziale o szyfrowaniu szyfrem Cezara krótko mówiliśmy o atakach brutalnych. Atak brutalną siłą w tym kontekście oznaczał próbowanie każdego możliwego klucza, aż do znalezienia właściwego.

Bardziej ogólnie, atak brutalną siłą próbuje wszystkich możliwości, aż znajdzie rozwiązanie. W przypadku skrótu oznacza to czytanie długiej listy możliwych haseł, przepuszczania każdego z nich przez algorytm haszowania, a następnie sprawdzanie, czy wyjściowy skrót jest identyczny z tym, który próbujemy odwrócić.
{panel end}

Jest to świetne rozwiązanie problemu haseł. Zamiast przechowywać hasła w naszej bazie danych, możemy przechowywać skróty. Gdy użytkownik zarejestruje się lub zmieni swoje hasło, musimy po prostu przetworzyć hasło za pomocą algorytmu SHA-256, a następnie zapisać wynikowy skrót zamiast hasła. Gdy użytkownik chce się zalogować, musimy ponownie wprowadzić hasło do algorytmu SHA-256. Jeśli wyjściowy skrót jest zgodny z przechowywanym w bazie danych, to użytkownik musiał wprowadzić poprawne hasło. Jeśli atakujący zdoła uzyskać dostęp do bazy danych z hasłami, nie będzie w stanie ustalić rzeczywistych haseł. Same skróty nie są atakującemu przydatne.

Poniższy program interaktywny umożliwia haszowanie słów, takich jak hasła (ale nie należy umieszczać w nich prawdziwego hasła, ponieważ nigdy nie należy wpisywać hasła w losowych witrynach). Jeśli wprowadzisz dobrze dobrane hasło (np. losowy ciąg cyfr i liter) i będzie ono miało wystarczającą długość, będziesz mógł bez obaw umieścić skrót na publicznej stronie internetowej, a nikt nie będzie w stanie określić, jakie było twoje hasło.

{interactive name="sha2" type="in-page"}

Na przykład poniższa tabela bazy danych pokazuje czterech użytkowników fikcyjnego systemu i skróty ich haseł. Możesz wyznaczyć ich hasła, wprowadzając różne możliwości do algorytmu SHA-256 i sprawdzając, czy dane wyjściowe są takie same jak któreś hasło w bazie danych.

{image filename="hash-passwords-table.png"}

To może początkowo brzmieć tak, jakbyśmy mieli doskonały system. Ale niestety nadal istnieje duży problem.
Możesz znaleźć w sieci *tęczowe tablice*, które są zawczasu przeliczonymi listami popularnych haseł z wartościami, do których się haszują. Nie jest trudno wygenerować tęczowe tabele zawierające wszystkie hasła do określonej wielkości (jest to jeden z powodów, dla których zdecydowanie zaleca się używanie długich haseł!).
Tego problemu można uniknąć, wybierając hasło, które nie jest często spotykanym słowem lub kombinacją słów.

Haszowanie to dobry początek, ale musimy jeszcze ulepszyć nasz system, żeby dwaj użytkownicy wybierający to samo hasło mieli różne hasze, zapewniając jednocześnie możliwość sprawdzenia, czy użytkownik wprowadził poprawne hasło. Następny pomysł, ,,solenie'', rozwiązuje ten problem.

{panel type="curiosity" title="Ciekawostka" summary="Hasła, które mają taki sam skrót"}
Mówiąc, że jeśli haszowane hasło pasuje do tego w bazie danych, to użytkownik musiał wprowadzić poprawne hasło, nie mówiliśmy całej prawdy. Analizując problem matematycznie, wiemy że muszą istnieć hasła, które dawałyby taki sam skrót. Wynika to z tego, że długość hasza wyjściowego ma ustaloną maksymalną długość, podczas gdy długość hasła (lub innych danych których skrót obliczamy) może być znacznie większa. Dlatego istnieje więcej możliwych wejść niż wyjść, a zatem niektóre wejścia muszą dawać to samo wyjście. Gdy dwa różne wejścia dają ten sam skrót na wyjściu, nazywamy to *kolizją*.

Obecnie nikt nie zna dwóch różnych haseł, które miałyby taki sam skrót obliczany funkcją SHA-256. Nie ma znanego matematycznego sposobu znajdowania kolizji, poza haszowaniem wielu wartości, a następnie szukaniem pary, która ma ten sam skrót. Prawdopodobieństwo znalezienia kolizji w ten sposób jest rzędu 1 do biliona biliona biliona biliona bilionów. Przy obecnie dostępnej mocy obliczeniowej nikt nie ma na to szans w czasie krótszym niż czas życia Słońca, a być może i wszechświata.

Niektóre stare algorytmy, takie jak MD5 i SHA-1, okazały się nie być tak odporne na znalezienie kolizji, jak początkowo sądzono. Możliwe, że istnieją sposoby na skuteczniejsze znajdowanie kolizji niż poleganie na szczęściu. Dlatego ich stosowanie nie jest obecnie zalecana do zastosowań, w których kolizje mogą powodować problemy.

W przypadku przechowywania haseł kolizje nie stanowią problemu. Prawdopodobnie i tak hasło wybrane przez użytkownika jest w pewnym stopniu przewidywalne (na przykład słowo ze słownika, z niewielkimi modyfikacjami) i jest znacznie bardziej prawdopodobne, że atakujący odgadnie prawdziwe hasło, a nie takie, które ma taki sam skrót jak ono.

Ale haszowanie służy nie tylko do przechowywania haseł. Jest również używane do podpisów cyfrowych, w których skróty muszą być unikatowe. W przypadku tych zastosowań ważne jest, aby nie można było znaleźć kolizji.
{panel end}

### Haszowanie haseł z ,,soleniem''

Naprawdę sprytną techniką, która rozwiązuje niektóre problemy z używaniem zwykłego skrótu, jest solenie. Solenie oznacza po prostu dołączenie dodatkowych danych, zwanych *solą*, na końcu hasła, a następnie haszowanie hasła i soli. Zwykle sól jest dość duża (na przykład 128 bitów). Kiedy użytkownik próbuje się zalogować, musimy znać sól jego hasła, aby można było ją dodać do hasła przed haszowaniem i sprawdzeniem. Początkowo może się to wydawać trudne, ale sól nie powinna być trzymana w sekrecie. Znajomość soli nie pomaga atakującemu w matematycznym odwróceniu hasza i odzyskaniu hasła. Dlatego powszechnie praktykuje się przechowywanie jej w postaci tekstu jawnego w bazie danych.

Gdy użytkownik się rejestruje, generowana jest duża losowa wartość soli, dodawana na koniec hasła, a połączone hasło i sól są haszowane. Tekst jawny soli jest przechowywany obok skrótu.

{comment}
TODO (ale ponad to, co naprawdę musimy omówić -- może być dodatkiem dla ekspertów)
### Haszowanie haseł z solą i rozciąganiem
{comment end}

### Znaczenie dobrego doboru haseł przez użytkowników

Jeśli hasła są solone i mieszane, wtedy tęczowa tablica jest bezużyteczna dla atakującego. Przy obecnej mocy obliczeniowej i pamięci nie można generować tabel tęczowych dla wszystkich popularnych haseł ze wszystkimi możliwymi solami. Powoduje to znaczne spowolnienie atakującego, jednak wciąż może on próbować odgadnąć każde hasło, jedno po drugim. Po prostu musi odgadnąć hasła, dodać sól do nich, a następnie sprawdzić, czy hasz jest gdzieś w bazie danych.

Typowym atakiem brutalnym jest *atak słownikowy*. Atakujący pisze prosty program, który przechodzi długą listę słów ze słownika, innych popularnych haseł i wszystkich kombinacji znaków poniżej pewnej długości. Do każdego wpisu na liście program dodaje sól, a następnie haszuje, aby sprawdzić, czy pasuje to do skrótu, dla którego próbuje ustalić hasło. Dobry sprzęt może sprawdzać miliony, a nawet miliardy wpisów na sekundę. Wiele haseł wybieranych przez użytkowników można odzyskać w czasie krótszym niż sekunda przy użyciu ataku słownikowego.

Niestety, ze szkodą dla użytkowników, wiele firm stara się wyciszyć wycieki baz danych, ponieważ jest to ogromna afera, która może negatywnie wpłynąć na firmę. Czasami firma nie wie, że jej baza danych wyciekła, lub ma podejrzenia, że tak było, ale z powodów wizerunkowych temu zaprzecza. W najlepszym wypadku może cię poprosić o wybranie nowego hasła, jako powód podając niejasne ogólniki. Z tego powodu ważne jest, aby w każdym miejscu używać różnych haseł, aby napastnik nie włamał się na twoje konta w innych witrynach. Prawdopodobnie krążą gdzieś po świecie twoje hasła, o których myślisz, że nikt ich nie zna, ale gdzieś jakiś atakujący uzyskał je z bazy danych do której której się włamał.

{comment}
Wypróbuj następujący program interaktywny. Wymaga od ciebie odgadnięcia haseł użytkowników.
- Alicja i Bob używali haseł, które należą do najczęściej używanych 20 haseł.
- Casey wybrała hasło ze słownika. Jej hasło może być trudniejsze do odkrycia, chociaż komputer mógłby je zdobyć w ciągu sekundy. Chętni mogą samemu dokonać ataku słownikowego.
- Hasło Dave'a jest krótkie, ale jego 5 znaków może być symbolami, cyframi, dużymi literami lub małymi literami. Może się okazać, że jest to trochę trudniejsze do wymyślenia, ale dla komputera jest to łatwe i chętni mogą napisać program, który pomoże je znaleźć.
- Hasło Evelyn to także losowa mieszanina różnych znaków, ale jest ich aż 16. Sądzimy, że nie uda ci się odgadnąć jej hasła, nawet jeśli napiszesz program, który ci pomoże! Ale daj nam znać, jeśli Ci się uda!
Program wyświetla bazę danych z prostą funkcją sprawdzania. Dla każdego użytkownika musisz skopiować jego sól do pola formularza, wprowadzić możliwe hasło i kliknąć przycisk obliczania skrótu. Program interaktywny automatycznie powiadomi cię, czy wynikowy skrót pasuje do jednej z powyższych pozycji w bazie danych (żebyś nie musiał sam uważnie porównywać czy zgadzają się ciągi znaków).

{comment end}

Choć w teorii szyfrowanie soli wygląda na dobry sposób na zwiększenie bezpieczeństwa, w praktyce wcale nie jest tak dobrze. Nie możemy użyć jednokierunkowej funkcji skrótu (ponieważ potrzebujemy soli do sprawdzenia hasła), więc zamiast tego musielibyśmy użyć jednej z metod szyfrowania, które poznaliśmy wcześniej, które do deszyfrowania używają tajnego klucza. Ten tajny klucz musiałby być znany programowi który sprawdza hasło (w przeciwnym razie nie mógłby on poznać soli potrzebnych do sprawdzenia haseł!), i musimy założyć, że atakujący również by go zdobył. Najlepszym zabezpieczeniem przed brutalnymi atakami offline są dobrze wybrane przez użytkowników hasła.

To dlatego strony internetowe wymuszają minimalną długość hasła i często wymagają kombinacji małych i wielkich liter, symboli i cyfr. Istnieje 96 standardowych znaków, których możesz użyć w haśle: 26 wielkich liter, 26 małych liter, 10 cyfr i 34 symboli. Jeśli wybrane hasło jest całkowicie losowe (np. nie są to słowa ani żadne wzorce), każdy dodany znak powoduje, że twoje hasło jest 96 razy trudniejsze do odgadnięcia. 8 do 16 znaków może zapewnić bardzo wysoki poziom bezpieczeństwa, o ile hasło jest naprawdę losowe. Takich właśnie haseł powinieneś używać (i upewnij się, że używasz innego hasła dla każdej witryny!).

Niestety te wymagania nie powodują, że użytkownicy wybierają dobre hasła. Atakujący znają sztuczki, których używają użytkownicy do tworzenia haseł, żeby spełniały wszystkie wymagania, ale żeby było je łatwo zapamiętać. Na przykład P@$$w0rd zawiera 8 znaków (powszechnie używane minimum) i zawiera mieszankę różnych typów znaków. Jednak atakujący wiedzą, że użytkownicy lubią zastępować S za pomocą $, zamieniać o i 0, i na !, itd. Właściwie mogą po prostu dodać te sztuczki do listy, której używają do ataków słownikowych. W przypadku stron internetowych, które wymagają od haseł posiadania co najmniej jednej cyfry, wynik jest jeszcze gorszy. Wielu użytkowników wybiera standardowe polskie słowo, a następnie dodaje jedną cyfrę na końcu. To znowu łatwizna dla ataku słownikowego!

Jak wskazuje ten komiks xkcd, większość porad dotyczących haseł nie ma większego sensu.

{image filename="xkcd-password-strength.png" hover-text="Każdego, kto rozumie teorię informacji oraz bezpieczeństwo i jest w trakcie irytującego sporu z kimś, kto ich nie rozumie (być może dotyczącego małych i wielkich liter), szczerze przepraszam." alt="Komiks xkcd o sile haseł" source="https://xkcd.com/936/"}

Być może nie wiesz, co oznaczają niektóre ze słów. W uproszczeniu, komiks mówi, że jest znacznie mniej modyfikacji popularnych słów słownikowych niż losowych wyborów czterech spośród 2000 najpopularniejszych słów słownikowych. Zauważ, że szacunki szybkości opierają się na próbach odgadnięcia przez system logowania. W przypadku wycieku bazy danych atakujący może przetestować miliardy haseł na sekundę, a nie tylko kilka tysięcy.



{comment}
TODO:
### Studia rzeczywistych przypadków

#### Adobe -- wyzwania

- Dobre techniki przechowywania
- Niestety najbardziej wrażliwymi danymi były adresy email

{comment end}





### Podsumowanie

Pierwsze przykłady w tym rozdziale wykorzystują bardzo słabe metody szyfrowania, które zostały wybrane w celu zilustrowania pojęć, ale nigdy nie zostałyby użyte w systemach komercyjnych czy wojskowych.

Istnieje wiele aspektów bezpieczeństwa komputera poza szyfrowaniem. Na przykład kontrola dostępu (m.in. systemy haseł i bezpieczeństwo kart inteligentnych) ma kluczowe znaczenie dla zabezpieczenia systemu.
Innym poważnym problemem jest pisanie bezpiecznego oprogramowania, które nie daje użytkownikowi możliwości uzyskania dostępu do informacji, których nie powinien poznać (np. przez wpisanie polecenia bazy danych do kwerendy w witrynie, które system przypadkiem uruchomi lub przepełnienie bufora dużą ilością danych wejściowych, które mogą przypadkowo zastąpić części programu).
Ponadto, systemy muszą być chronione przed atakami typu ,,zablokowanie usługi'' ("Denial Of Service" -- DOS), gdzie są tak przeładowane żądaniami (np. prośbami o wysłanie strony internetowej, jak przy przeglądaniu), że serwer nie może sobie z nimi poradzić, a uprawnieni użytkownicy otrzymują odpowiedzi bardzo powoli, albo system może nawet całkowicie zawieść.

Jeśli chodzi o inne rodzaje ataków związanych z bezpieczeństwem komputerowym, patrz [wpis w angielskiej Wikipedii na temat hakerów](https://en.wikipedia.org/wiki/Security_hacker#Attacks).

Nad bezpieczeństwem wszystkich obecnych metod szyfrowania wiszą ciemne chmury: [komputery kwantowe](https://pl.wikipedia.org/wiki/Komputer_kwantowy).
Komputery kwantowe są w powijakach, ale jeśli to podejście do obliczeń okaże się udane, może umożliwić działanie bardzo szybkich algorytmy atakowania naszych najbezpieczniejszych systemów szyfrujących (na przykład mogłoby być użyte do bardzo szybkiego wyznaczania dzielników liczb). W rzeczywistości algorytmy kwantowe zostały już wynalezione, ale nie wiemy, czy można zbudować komputery kwantowe, na których mogłyby one działać. 
Takie komputery najprawdopodobniej nie pojawią się z dnia na dzień, a jeśli ich budowa stanie się możliwa, otworzą również możliwość stosowania nowych algorytmów szyfrowania. Jest to kolejna zagadka w informatyce -- nie wiemy, co przyniesie przyszłość i gdzie mogą nastąpić poważne zmiany. Ale będziemy potrzebować bardzo zdolnych informatyków do radzenia sobie z takimi zmianami!

Ale jest też dobra strona -- [kwantowe protokoły dystrybucji kluczy](https://pl.wikipedia.org/wiki/Kwantowa_dystrybucja_klucza) i są one stosowane w praktyce (przy użyciu specjalistycznego sprzętu do generowania bitów kwantowych); zapewniają one teoretycznie doskonały system szyfrowania i nie polegają na tym, że atakujący nie jest w stanie rozwiązać określonego problemu obliczeniowego. Ze względu na konieczność użycia specjalistycznego sprzętu są one wykorzystywane tylko w środowiskach o wysokim poziomie bezpieczeństwa, takich jak bankowość.

Oczywiście szyfrowanie nie rozwiązuje wszystkich naszych problemów związanych z bezpieczeństwem, a ponieważ są dostępne dobre systemy szyfrowania, złodzieje informacji muszą zastosować inne podejścia, w szczególności inżynierię społeczną. Najłatwiejszym sposobem uzyskania hasła użytkownika jest spytanie go o nie! [Atak phishingowy](https://pl.wikipedia.org/wiki/Phishing) robi właśnie coś takiego, a istnieją szacunki, że aż 1 na 20 użytkowników komputera zdradził kiedyś w ten sposób tajne informacje.

Inne stosowane metody inżynierii społecznej, to przekupywanie lub szantażowanie osób mających dostęp do systemu lub po prostu szukanie hasła zapisanego na karteczce przyklejonej do czyjegoś monitora! Uzyskanie dostępu do czyjegoś konta email jest szczególnie łatwym sposobem na uzyskanie wielu haseł, ponieważ wiele systemów przywracania ,,zgubionego hasła'' wysyła nowe hasło na konto email.

{comment}
.. xtcb prawdopodobnie odnośnik do http://nsf.gov/cise/csbytes/newsletter/vol3/pdf/csbb-vol3-i2.pdf i https://www.youtube.com/watch?v=T2DXrs0OpHU

{comment end}


{comment}
.. np. (bb84)

.. historia enigmy http://www.mtholyoke.edu/~adurfee/cryptology/enigma_j.html
{comment end}

{panel type="curiosity" title="Ciekawostka" summary="Steganografia"}

Kryptografia polega na ukryciu treści wiadomości, ale czasami ważne jest ukrycie *istnienia* wiadomości. W przeciwnym razie wróg może zorientować się, że coś jest w trakcie planowania właśnie dlatego, że wysyłanych jest znacznie więcej wiadomości, nawet jeśli nie jest w stanie ich odczytać.
Jednym ze sposobów osiągnięcia tego jest *steganografia*, gdzie tajna wiadomość jest ukryta w innej wiadomości, która wydaje się niewinna. Klasycznym scenariuszem byłoby opublikowanie wiadomości w drobnych ogłoszeniach w gazecie lub wysłanie listu z więzienia, gdzie liczba liter w każdym słowie stanowi kod. Dla zwykłego czytelnika komunikat może wydawać się nieistotny (a nawet mówić coś przeciwnego do ukrytego), ale ktoś, kto zna kod, może go odkryć. Wiadomości mogą być ukryte w obrazach cyfrowych przez wprowadzanie niezauważalnych zmian w pikselach tak, żeby przechowywały pewne informacje. Możesz dowiedzieć się [więcej o steganografii na Wikipedii](https://pl.wikipedia.org/wiki/Steganografia) lub w tym [wykładzie (po angielsku) na temat steganografii](https://www.youtube.com/watch?v=Py-qu9KWXhk#t=29).

Dwa zabawne zastosowania steganografii, które możesz sam spróbować zdekodować, to [film ,,The Thomas Beale Cipher'', o szyfrach zawierających steganografię](http://www.thomasbealecipher.com/), a także przykład ćwiczenia (po angielsku) z [pięciobitowymi kodami tekstowymi ukrytymi w muzyce](http://csunplugged.org/modem).

{panel end}


## Dalsza lektura

[Artykuł o kryptologii na Wikipedii](https://pl.wikipedia.org/wiki/Kryptologia) dość przystępnie wyjaśnia terminologię użytą w tym rozdziale.

Obecnie stosowane metody szyfrowania opierają się na dość zaawansowanej matematyce; z tego powodu książki o szyfrowaniu zwykle albo wymagają większej wiedzy niż na poziomie liceum, albo opisują kody, które nie są używane w praktyce.

{comment}

.. przykład dobrej książki każdego typu?

{comment end}

Istnieje wiele intrygujących historii dotyczących szyfrowania, w tym jego wykorzystania w czasie wojny i do szpiegowania. Oto kilka książek na ten temat:

- David Kahn ,,How I Discovered World War II's Greatest Spy and Other Stories of Intelligence and Code''

- Friedrich L. Bauer ,,Sekrety kryptografii''

- Craig Bauer ,,Secret History: The Story of Cryptology''

- David Kahn ,,Łamacze kodów. Historia kryptologii''

- Marek Grajek ,,Enigma. Bliżej prawdy''

Poniższe ćwiczenia na stronie CS Unplugged pozwalają pobawić się protokołami kryptograficznymi. Są po angielsku, ale pierwsze dwa posiadają polską instrukcję. Metody szyfrowania w nich użyte nie są wystarczająco mocne, aby można je było wykorzystać w praktyce, ale zapewniają pewien wgląd w to, co jest możliwe:

- [Ukrywanie informacji](http://csunplugged.org/information-hiding)

- [Protokoły kryptograficzne](http://csunplugged.org/cryptographic-protocols)

- [Szyfrowanie z kluczem publicznym](http://csunplugged.org/public-key-encryption)

Artykuł [War in the fifth domain](http://www.economist.com/node/16478792) o wojnie w cyberprzestrzeni opowiada o tym, jak szyfrowanie i bezpieczeństwo są kluczowe dla naszej obrony.

Istnieje wiele [artykułów w CS4FN na temat kryptografii](http://www.cs4fn.org/security/crypto/), w tym o [ataku statystycznym który doprowadził do... ścięcia głowy](http://www.cs4fn.org/security/beheading/secrets1.html).

Książka ,,Hacking Secret Ciphers with Python: A beginner's guide to cryptography and computer programming with Python'' (autor: Al Sweigart) omawia niektóre proste szyfry, w tym te omówione w tym rozdziale, a także jak można je programować (i atakować) za pomocą programów w języku Python.


### Przydatne odnośniki

- [How Stuff Works -- o szyfrowaniu (po angielsku)](http://www.howstuffworks.com/encryption.htm)
- [Cryptool](http://www.cryptool.org/) to darmowy system pozwalający wypróbowywać klasyczne i nowoczesne metody szyfrowania. Niektóre z nich wykraczają poza zakres tego rozdziału, ale wiele z nich może się przydać do eksperymentowania z kryptografią i prowadzenia demonstracji.
- [Wikipedia -- klucze kryptograficzne](https://pl.wikipedia.org/wiki/Klucz_%28kryptografia%29)
- [Wikipedia -- szyfr Cezara](https://pl.wikipedia.org/wiki/Szyfr_Cezara)
- [Filmy o nowoczesnych metodach szyfrowania (po angielsku)](http://simonsingh.net/media/online-videos/cryptography/the-science-of-secrecy-going-public/)
- [Programy interaktywne z prostymi szyframi (po angielsku)](http://www.braingle.com/brainteasers/codes/index.php)
