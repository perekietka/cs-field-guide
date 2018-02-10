# Języki formalne

## Z lotu ptaka

{comment}
.. index:: błąd składni
{comment end}

Jeśli kiedykolwiek zdarzyło ci się korzystać z arkusza kalkulacyjnego i wpisywać w nim formułę lub pisać programy, to jest bardzo prawdopodobne, że na pewnym etapie pisania system wyświetlił komunikat o błędzie i nie może zastosować się do twojego polecenia.

{image filename="python-syntax-error.png" alt="Błąd składni w x = (a+b) \*c+d) w związku z brakiem nawiasu ( w wyrażeniu"}

Są to „błędy składni” (po angielsku „syntax errors”). Te uciążliwe komunikaty są znane każdemu programiście. Oznacza to, że w czasie pracy popełnili błąd w składni jakiegoś polecenia. Błąd mógłbyś bardzo mały. Dla przykładu przypuścmy, że miałeś wpisać poniższą instrukcję:
```
x = (a+b)*(c+d)
```

ale przypadkowo zapomniałeś o jednym nawiasie:

```
x = (a+b)*c+d)
```

Kiedy spróbujesz skompilować lub skompilować i uruchomić program, wtedy komputer wyświetli informację, że wystąpił błąd. Jest to bardzo pomocne, w szczególności gdy dostaniesz wskazówkę gdzie ten błąd się znajduje. Do momentu jego naprawienia nie będziesz w stanie uruchomić programu. 

Może się to wydawać irytujące, ale w rzeczywistości poprzez wymuszenie precyzji i dbałości o szczegóły, kompilator pomaga wskazać tobie błędy zanim staną się one błędami w gotowym programie. Wtedy będą musiały być usunięte dopiero, gdy ktoś przetestuje program i zauważy, że nie działa poprawnie.

Zawsze przy wystąpieniu takiego błędu, masz do czynienia z *językiem formalnym*. Określają one ścisłe zasady, takie jak „wszystkie nawiasy, które zostały otwarte, muszą zostać zamknięte”, „wszystkie polecenia w programie muszą być słowami kluczowymi wybranymi ze ściśle okreśłonego, małego zestawu” lub „data musi zawierać trzy liczby odseparowane myślnikami”. 

Języki formalne nie są tylko używane w językach programowania — są one używane wszędzie tam, gdzie format jakiegoś wejścia jest ściśle określony, na przykład wpisywanie adresu emailowego w formularz internetowy. 

W tych wszystkich przypadkach, polecenia, które wpisałeś (czy to w Python, Scratch, Snap!, C, Pascal, Basic, C#, HTML, lub XML) zostały zinterpetowane przez program komputerowy. (Zgadza się… Python jest programem, który interpetuje programy napisane w języku Phyton). W rzeczywistości, kompilator języka programowanie jest często napisany w swoim własnym języku. Większość kompilatorów języka C jest napisana w C — co stawarza pytanie, kto napisał pierwszy kompilator C (i co jeśli miał on błędy)?! Informatycy odkryli dobre sposoby na pisanie programów, które przetwarzają inne programy, a kluczowym składnikiem jest to, że musisz dokładnie określić to, co jest dozwolone w programie. Nad tym własnie czuwają języki formalne.

Wiele z koncepcji, którym będziemy przyglądać się w tym rozdziale, jest używane w wielu innych sytuacjach: sprawdzenie poprawności wpisanych danych na stronie internetowej; analizowanie interfejsów użytkowników; przeszukiwanie tekstu, w szczególności z wieloznacznikami, które mogą pasować do dowolnego ciągu znaków; tworzenia układów logicznych; określenia protokołów komunikacyjnych; projektowaniu systemów wbudowanych. Niektóre zaawansowane koncepcje w językach formalnych wykorzystano do zbadania granic tego co może zostać obliczone.

Gdy zapoznasz się z ideą języków formalnych, zobaczysz jakie jest to potężne narzędzie, aby bardzo skomplikowane systemy rozłożyć na mniejsze za pomocą prostych reguł.

{image filename="xkcd-tags.png" hover-text="<A>: Like </a>this." alt="Bajkowy komentarz xkcd o tagach HTML" source="https://xkcd.com/1144/"}

## Zaczynamy

Aby dać ci smak tego, do czego można wykorzystać języki formalne, zacznijmy od poszukiwania słów, które pasują do konkretnych wzorców.
Przypuśćmy, że szukasz słów, które zawierają imię „tim”. wpisz słowo „tim” (lub kilka liter ze swojego imienia), następnie naciśnij przycisk „Filtruj wyrazy”, aby znaleźć wszystkie słowa zawierające frazę „tim”.

{interactive name="regular-expression-filter" type="in-page"}

Teraz wprowadzimy *dziką kartę*, znak który zastąpi nam dowolny symbol, który w tym przypadku to „.” — jest to powszechnie stosowana konwencja w językach formalnych.
Ten znak oznacza, że przypasować możemy do niego dowolną literę.
Teraz możesz zrobić wyszukiwanie takie jak:

```
tim.b
```

i otrzymasz dowolne słowa, które mają zarówno „tim” oraz „b” z dowolnym pojedynczym znakiem w środku. Czy są jakieś słowa pasujące do „tim..b”? „tim ...b”? Możesz określić dowolną liczbę wystąpień symbolu, wstawiając za nim znak '\*' (ponownie powszechnie używana konwencja), a więc:

```
tim.*b
```

dopasuje dowolne słowa, w których po „tim” następuje litera „b”, oddzielona dowolną liczbą znaków - włącznie z żadnym.

Spróbuj wykonać następujące wyszukiwanie. Jakie ciągi znaków zostaną znalezione?

```
x.*y.*z
```

{panel type="teacher-note" summary="Wyjaśnienie powyższego wyszukiwania"}

Ten kod znajduje wyrażenia zawierające x, y oraz z (w tej kolejności) oddzielone przez zero lub więcej symboli. Jest 16 słów, to zestaw danych, który pasuje do tego.
{panel end}

- Czy możesz znaleźć słowa, które zawierają twoje imię lub inicjały?
- Co z słowami zawierającymi litery od imienia w prawidłowej kolejności, niebędące twoim imieniem?
- Czy są jakieś słowa, które zawierają wszystkie angielskie samogłoski w kolejności (a, e, i, o, u)?

{panel type="teacher-note" summary="Rozwiązanie problemu samogłosek"}

Aby znaleźć słowa ze wszystkimi samogłoskami w kolejności, należy użyć kodu „a.\*e.\*i.\*o.\*u”, jest 47 dopasowań.

Uczniowie mogą zapytać, jak wykonać bardziej skomplikowane wyszukiwania, takie jak litery w dowolnej kolejności. Jeśli są zainteresowani, mogą to zbadać samodzielnie, ale to tylko ćwiczenie rozgrzewkowe. Omówimy to dokładniej w sekcji na temat [wyrażeń regularnych](rozdzialy/jezyki-formalne.html#wyrażenia-regularne).

{panel end}

Kod, którego użyłeś powyżej, jest częścią języka formalnego zwanego „wyrażeniem regularnym”. Programy komputerowe, które mają za zadanie interpretowanie wpisanych danych wejściowych i ich akceptację, używają wyrażeń regularnych do sprawdzania elementów takich jak daty, numery kart kredytowych i kody produktów. Są szeroko używane przez kompilatory i interpretatory języków programowania, aby zrozumieć tekst, który programista wpisuje.

Przyjrzymy się im bardziej szczegółowo w sekcji na temat [wyrażeń regularnych](rozdzialy/jezyki-formalne.html#wyrażenia-regularne).

Następnie zbadamy prosty system do odczytu wejścia o nazwie
{glossary-link term="automat skończenie stanowy" reference-text="Jęzki formalne"}automat skończenie stanowy{glossary-link end},
który — jak przekonamy się później — jest blisko związany z 
{glossary-link term="wyrażenie regularne"}wyrażeniami regularnymi{glossary-link end}.
Później przyjrzymy się idei
{glossary-link term="gramatyka"}gramatyki{glossary-link end},
która jest innym rodzajem języka formalnego, który radzi sobie z bardziej skomplikowanymi formami danych wejściowych.

{panel type="teacher-note" summary="Ćwiczenie - językoznawstwo klingońskie"}

Dla zabawnej dyskusji, moglibyśmy poprosić uczniów na spojrzenie na [ćwiczenie pod nazwą językoznawstwo klingońskie na stronie CS4FN](http://www.cs4fn.org/linguistics/klingon.html). Ta strona przedstawia podstawy języków - słowa (alfabet) i {glossary-link term="gramatyka"}gramatykę{glossary-link end} (zasady składni). Omówiono tam, dlaczego języki są tłumaczone i jak można zmienić znaczenie poprzez tłumaczenie. Wyjaśnia również, dlaczego należy tłumaczyć języki komputerowe.

{panel end}

## Automaty skończonie stanowe

{panel type="teacher-note" summary="Poszukiwanie skarbów (alternatywne wprowadzenie)"}

Na początku tego podrozdziału jest zabawny wariant wyzwania, który obejmuje bieganie po placu zabaw. Jest on opisany jako ćwiczenie [poszukiwanie skarbów](http://csunplugged.org/wp-content/uploads/2014/12/unplugged-11-finite_state_automata.pdf) na stronie CS unplugged.
Może to być zbyt dziecinne dla niektórych uczniów, ale jeśli możesz im to sprzedać, jest to świetny sposób, aby wykonać trochę ćwiczeń fizycznych z dala od komputerów i zobaczyć większość koncepcji w tej sekcji jako aktywność fizyczną. Możliwych jest wiele wariantów; na przykład to może być wykonane jako gra karciana, w której karta A/B dla każdej stacji jest na żądanie odwracana. Zobacz stronę Unplugged w poszukiwaniu innych pomysłów.

{panel end}

Oto mapa systemu kolei podmiejskich dla miasta Trainsylvania. Kłopot w tym, że nie pokazuje ona, dokąd jeżdżą pociągi — wiesz jedynie, że z każdej stacji odjeżdżają dwa pociagu, pociąg A i pociąg B. Mieszkańcom Trainsylvanii wydaje się to nie przeszkadzać — fajnie jest wybierać pociąg na każdej stacji, a po pewnym czasie zwykle przyjeżdżasz tam, gdzie chciałeś.

{image filename="trainsylvania-blank.png" alt="Niekompletna mapa pociągów" caption="Kliknij, aby powiększyć"}

Możesz podróżować po Transylwani samodzielnie, korzystając z następujących narzęrzędzi interaktywnych. Zaczynasz od stacji City Mall i musisz znaleźć drogę do Suburbopolis.
Na każdej stacji możesz wybrać pociąg A lub pociąg B — naciśnij przycisk, aby dowiedzieć się, dokąd cię zabierze.
Prawdopodobnie, tak jak mieszkańcy Trainsylvanii, prawdopodobnie zaczniesz rysować mapę linii kolejowych, ponieważ później możesz zostać poproszony o znalezienie drogi w inne miejsce.
Jeśli chcesz narysować szablon, możesz [wydrukować go stąd](files/trainsylvania-blank.pdf).

{interactive name="trainsylvania" type="in-page"}

{panel type="teacher-note" summary="Użycie narzędzia interaktywnego i rozwiązanie"}

Powinieneś pozwolić uczniom wymyślić ich własną notację do tego zadania. Wkrótce dowiedzą się (być może na swój sposób), że powinni zapisywać wszystkie trasy ze strzałką (ponieważ pociągi niekoniecznie wracają tą samą trasą) i oznaczać je strzałki z literami A lub B. Pełna mapa dla tego ćwiczenia znajduje się poniżej, ale nie psuj zabawy uczniom, pokazując mapę — przynajmniej, jeszcze nie teraz.

{image filename="trainsylvania-complete.png" alt="Rozwiązanie dla mapy pociągów" caption="Kliknij obrazek, aby powiększyć"}

{panel end}

Czy znalazłeś taką sekwencję pociągów, aby dostać się z City Mall do Suburbopolis? Aby się upewnić, że masz dobrą sekwencję, możesz ją wpisać do poniższego ćwiczenia, w celu sprawdzenia. Na przykład, jeśli skorzystałeś z pociągu A, następnie pociągu B, a następnie pociągu A, wpisz ABA.

{interactive name="trainsylvania-planner" type="in-page"}

Czy potrafisz teraz znaleźć sekwencję, która zabierze Cię z City Mall do Suburbopolis? Czy możesz znaleźć kolejną sekwencję, być może dłuższą? Przypuśćmy, że chcesz jechać naprawdę długą trasą. Czy znajdziesz sekwencję 12 przesiadek, która doprowadzi cię do celu? A 20 przesiadek?

Oto kolejna mapa. Przedstawia inne miasto, a stacje mają tylko numery, a nie nazwy (oczywiście jeśli chcesz, możesz je nazwać).

{image filename="finite-state-automata-train-example.png" alt="Prostsza mapa pociagów"}

Załóżmy, że zaczynasz od stacji 1 i musisz dostać się do stacji nr 3 (ma podwójne kółko, aby pokazać, dokąd zmierzasz).

- Jaka jest najkrótsza droga ze stacji 1 do stacji 3?
- Gdzie skończysz, jeśli zaczniesz od stacji 1 i jedziesz pociągami ABAA?
- Gdzie skończysz, jeśli zaczynasz na stacji 1 i wykonujesz 20 przesiadek, zawsze naprzemiennie A, B, A, B, A, B?
- Czy możesz podać łatwą do opisania sekwencję 100 lub więcej przesiadek, które doprowadzą cię do stacji nr 3?

{panel type="teacher-note" summary="Rozwiązania"}

Rozwiązania:

- AA
- stacja 3
- stacja 4 (każde AB to po prostu jazda w dwie strony pomiędzy 2 i 4)
- istnieje wiele rozwiązań, ale w oparciu o poprzednie pytanie, AB powtórzone 49 razy doprowadzi do stacji 4 (to 98 przesiadek), a następnie AA doprowadzi do stacji 3. Istnieje wiele innych rozwiązań, opartych na wielokrotnym chodzeniu w kółko, na przykład, powtarzanie A 101 razy zakończy podróż na stacji 3, ponieważ dowolna wielokrotność trzech „A” w środku nie robi różnicy.

{panel end}

Używana przez nas mapa z okręgami i strzałkami, jest tak naprawdę czymś, co w informatyce nazywa się automatem skończenie stanowym, lub w skrócie {glossary-link term="automat skończenie stanowy" reference-text="skrót FSA"}FSA{glossary-link end} (ang. „Finite State Atomaton”).
Umiejętność korzystania z takich automatów jest bardzo przydatna dla informatyków.

{panel type="jargon-buster" summary="Automat skończenie stanowy"}

{glossary-definition term="Automat skończenie stanowy" definition="W językach formalnych, prosta "maszyna", która posiada stany i przejścia z jednego stanu do drugiego w oparciu o ciąg wejściowych symboli. Po angielsku „Finite State Automaton”"}
Nazwa
{glossary-link term="Automat skończenie stanowy" reference-text="Języki formalne"}automat skończenie stanowy{glossary-link end} (w skrócie FSA) może wydawać się dziwna, ale każde słowo jest w zasadzie proste.
„Skończony” oznacza po prostu, że na jest ograniczona liczba stanów (takich jak stacje kolejowe na mapie). „Stan” jest po prostu inną nazwą dla stacji kolejowych, z których korzystaliśmy. „Automat” to stare słowo oznaczające maszynę działającą samodzielnie, zgodnie z prostymi zasadami (takimi jak kukułka w zegarze z kukułką).

{glossary-definition term="Automat skończenie stanowy" definition="Alternatywna nazwa dla automatu skończenie stanowego."}
Czasami FSA jest nazywany
{glossary-link term="Maszyna skończenie stanowa" reference-text="Języki formalne"}Maszyną skończenie stanową{glossary-link end} (w skrócie FSM) (ang. Finite State Machine),
lub w skrócie „maszyną stanową”.
Nawiasem mówiąc, w języku angielskim liczbą mnogą słowa „Automaton” może być „Automata” lub „Automatons”.
Osoby pracujace z językami formalnymi zwykle używają określenia automat skończenie stanowy lub automat stanowy, lub w skrócie „FSA” (w liczbie mnogiej po angielsku „Finite State *Automata*”, ale w skrócie „FSAs”).
{panel end}

FSA nie jest przydatny w przypadku map pociągów, ale notacja jest wykorzystywana do wielu innych celów, od sprawdzania danych wejściowych do programów komputerowych po kontrolowanie zachowania interfejsu.
Być może natknąłeś się na to po wybraniu numeru telefonu i otrzymałeś komunikat „Naciśnij 1, aby... Naciśnij 2, aby... Naciśnij 3, aby porozmawiać z operatorem”. Gdy naciskasz klawisze telefonu, to wchodzisz doautomatu skończenie stanowego na drugim końcu linii telefonicznej. Dialog może być dość prosty lub bardzo złożony. Czasami poruszasz się w kółko, ponieważ w automacie skończenie stanowym istnieje swoista pętla. Jeśli tak się dzieje, jest to błąd w konstrukcji systemu, co może być bardzo frustrujące dla dzwoniącego!

Innym przykładem jest pilot do klimatyzatora. Może mieć sześć głównych przycisków, a naciśnięcie przycisku zmienia tryb pracy (na przykład ogrzewanie, chłodzenie, automatyczny).
Aby przejść do pożądanego trybu, musisz nacisnąć odpowiednią sekwencję. Jeśli naciśniesz o jeden przycisk za dużo, to tak, jakbyś już był na docelowej stacji kolejowej, ale przez przypadek wskoczył do jeszcze jednego pociągu. Za to twoja podróż powrotna na stację docelową może być bardzo długa i zakończona odkryciem wielu nowych sposobów, aby się tam dostać!
Jeśli istnieje instrukcja dla kontrolera, może on zawierać diagram, który wygląda jak automat skończony.
Jeśli nie ma instrukcji, możesz narysować mapę, tak jak w przypadku pociągów powyżej, abyś mógł lepiej zrozumieć jak działa urządzenie.

{comment}

.. TCB nie potrzebujemy naprawdę tego przykładu
.. Innym przykładem jest gotówka z bankomatu. Program w komputerze urządzenia przeprowadzi cię przez sekwencję zdarzeń. Wewnątrz programu wszystkie możliwe sekwencje są utrzymywane jako automat skończenie stanowy. Każdy wciśnięty klawisz przenosi automat do innej „stacji” na mapie. Niektóre „stacje” mają instrukcje dla komputera na nich, takie jak „wydać 100$ gotówki” lub „wydrukować wyciąg” lub „wyjmij kartę”

{comment end}

Mapa, której użyliśmy powyżej, korzysta ze standardowej notacji. Oto mniejsza:

{image filename="finite-state-automata-simple-1.png" alt="Prosty automat skończenie stanowy"}

Zwróć uwagę, że ta mapa ma trasy, które prowadzą bezpośrednio do miejsca, z którego się zaczęły!
Na przykład, jeśli zaczynasz od 1 i wybierasz trasę „b”, natychmiast kończysz z powrotem w tym samym miejscu.
To może wydawać się bez sensu, ale może być całkiem przydatne.
Każda ze „stacji kolejowych” jest nazywana stanem, który jest ogólnym terminem po prostu reprezentującym miejsce, w którym znajdujesz się po sekwencji danych wejściowych lub decyzji.
Jego rzeczywiste znaczenie, zależy od tego, do czego służy dany FSA. Stany mogą reprezentować tryb działania (taki jak szybki, średni lub wolny przy wyborze cyklu wirowania pralki) lub stan blokady lub alarmu (włączanie, wyłączanie, tryb wyjścia) lub wiele innych rzeczy. Wkrótce poznamy więcej przykładów.

Jeden ze stanów ma podwójne kółko.
Zgodnie z konwencją oznacza to stan „ostateczny” lub „akceptujący”. Jeśli tam dotrzemy, to osiągnęliśmy pewien cel.
Jest też stan „startowy” - do którego dochodzi znikąd strzałka.
W FSA na ogół chodzi o to, aby znaleźć ciąg danych wejściowych, które doprowadzą cię od stanu początkowego do stanu końcowego.
W powyższym przykładzie najkrótszym wejściem, aby przejść do stanu 2, jest „a”, ale możesz też tam dotrzeć poprzez „aa”, „aba” lub „baaaaa”. Mówimy wtedy, że te dane wejściowe są „akceptowane”, ponieważ potrafią nasz przeprowadzić od stanu początkowego do stanu końcowego — nie musi to być najkrótsza droga.

W jakim stanie znalazłbyś się, gdyby dane wejściowe były literą „a” powtórzoną 100 razy?

Oczywiście, nie wszystkie dane wejściowe umożliwiają dojście do stanu 2. Na przykład „aab” lub nawet „b” nie są akceptowane przez ten prosty system. Czy potrafisz scharakteryzować, które dane wejściowe są akceptowane?

{panel type="teacher-note" summary="Rozwiązanie dla FSA"}

Powyższy FSA przyjmuje dowolny ciąg danych wejściowych, które kończą się na „a”, więc interaktywne narzędzie poniżej zachowuje się dość trywialnie: naciśnij „a”, aby zostać zaakceptowanym, a „b”, aby nie zostać zaakceptowanym. To działa jak dwuprzyciskowy przełącznik zasilania z przyciskiem włączania i wyłączania. Chociaż tego typu FSA wydają się bardzo trywialne, ważne jest, aby uczniowie dobrze je zrozumieli. Niektóre z FSA stosowane w praktyce mają tylko kilka takich stanów, ale nawet małe systemy mogą wykonywać dość złożone zadania.

{panel end}

Oto interaktywne narzędzie, który jest zgodne z zasadami powyższego FSA. Możesz go użyć do testowania różnych danych wejściowych.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/fsa-2state-v3.html?map=one" text="Zobacz interaktywne ćwiczenie stanów (1)"}

Oto kolejny FSA, który wygląda podobnie do poprzedniego, ale zachowuje się zupełnie inaczej. Możesz przetestować go w interaktywnym narzędziu poniżej.

{image filename="finite-state-automata-simple-2.png" alt="Prosty automat skończenie stanowy"}

Sprawdź, które z poniższych wejść są akceptowane. Pamiętaj, aby za każdym razem zacząć od stanu 1!
- „aaa”
- „abb”
- „aaaa”
- „bababab”
- „babababa”
- litera „a” powtórzona 100 rzy
- litera „a” powtórzona 1001 razy
- litera „b” miliona razy, potem „a”, potem kolejny milion liter „b”

Czy możesz podać ogólną zasadę akceptacji danych wejściowych?

{panel type="teacher-note" summary="Rozwiązania"}

Ogólną zasadą tego automatu jest to, że dane wejściowe muszą zawierać nieparzystą liczbę liter „a”, liczba liter „b” jest nieistotna. Z tego wynika, że w powyższych przykładach akceptowane ciągi to „aaa”, „abb”, „bababab”, litera „a” powtórzona 1001 razy, i ostatni ciąg (litera „b” milion razy, a następnie „a”, następnie kolejny milion liter „b”).

{panel end}

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/fsa-2state-v3.html?map=two" text="Zobacz kolejne interaktywne narzędzie stanów"}

{glossary-definition term="Alfabet" definition="W językach formalnych, lista znaków, które mogą wystąpić w języku, lub bardziej ogólnie lista wszystkich możliwych wejść, które mogą wystąpić."}
Aby zachować precyzję, zdefiniujemy dwa kolejne terminy.
Jednym z nich jest 
{glossary-link term="alfabet" reference-text="Języki formalne"}alfabet{glossary-link end},
który jest po prostu listą wszystkich możliwych wejść, które mogą wystąpić.
W kilku ostatnich przykładach alfabet składa się z dwóch liter — „a” i „b”,
ale w przypadku FSA, który przetwarza tekst wpisany na komputerze, alfabet będzie musiał zawierać każdą literę występującą na klawiaturze.

{glossary-definition term="Przejście" definition="W automacie skończenie stanowym, połączenie pomiędzy dwoma stanami."}
{glossary-definition term="Łańcuch" definition="Ciąg znaków."}
{glossary-definition term="Język" definition="W językach formalnych, to zbiór wszystkich łańcuchów, które język akceptuje. To znaczy, które są poprawne."}
Połaczenia pomiędzy stanami nazywane są
{glossary-link term="przejścia" reference-text="Języki formalne"}przejściami{glossary-link end},
ponieważ następuje zmiana stanu.
Ciąg znaków, które wprowadzamy do FSA, jest często nazywany 
{glossary-link term="łańcuch" reference-text="Języki formalne"}łańcuchem{glossary-link end},
(to po porostu łańcuch liter),
to zbiór wszystkich łańcuchów, które mogą być zaakceptowane przez konkretny FSA, nazywany jest jego
{glossary-link term="język" reference-text="Języki formalne"}językiem{glossary-link end}.
W przypadku FSA w ostatnim przykładzie jego *język* zawiera *ciągi* „a”, „aaa”, „bab”, „ababab” i wiele więcej, ponieważ są one przez niego akceptowane.
Jednak nie zawiera ciągów „bb” ani „aa”.

Większość FSA posiada spory język. W rzeczywistości te, których właśnie oglądaliśmy, są nieskończene. Mógłbyś spędzyć cały dzień, wypisując łańcuchy, które akceptują. Nie ma ograniczeń długości łańcuchów, które mogą zaakceptować.

Jest to bardzo pożądane, ponieważ wiele prawdziwych FSA ma do czynienia z „nieskończonymi” danymi wejściowymi.
Na przykład poniższy diagram pokazuje FSA dla prędkości wirowania na pralce, gdzie każde naciśnięcie przycisku wirowania zmienia ustawienie.

{image filename="finite-state-automata-spin-speeds.png" alt="FSA dla ustawień wirowania pralki"}

Byłoby frustrujące, gdybyś mógł zmienić ustawienie wirowania tylko 50 razy, a potem dane wejściowe przestałyby być akceptowane.
Jeśli chcesz, możesz przełączyć się z szybkiego na wolne wirowanie naciskając przycisk wirowania 3002 razy.
Zadziała również dwa razy. Lub 2 miliony razy (spróbuj, jeśli nie jesteś przekonany).

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/fsa-spin-graphic.html" text="Zobacz interaktywne narzędzie prędkości wirowania"}

Poniższy diagram podsumowuje wprowadzoną przez nas terminologię. Zauważ, że ten FSA ma dwa stany akceptujące. Może być ich tyle. ile potrzebujesz, ale zawsze tylko jeden stan początkowy.

{image filename="finite-state-automata-train-example-terminology.png" alt="Objaśniona terminologia FSA"}

W przypadku tego FSA, łańcuchy „aa” i „aabba” byłyby akceptowane, w przeciwieństwie do „aaa” oraz „ar”.
Przy okazji zauważmy, że często umieszczamy łańcuchy w cudzysłowach, aby było jasne, gdzie zaczynają się oraz kończą.
Oczywiście cudzysłowy nie są częścią łańcuchów.
Zauważ, że „r” zawsze wraca do stanu 1 — jeśli kiedykolwiek wystąpi na wejściu, to zadziała jak reset.

Czasami zobaczysz FSA nazywane Skończoną Maszyną Stanową lub FSM (z angielskiego „Finite State Machine”). Istnieją także inne ściśle powiązane systemy o podobnych nazwach. Póżniej, wspomnimy niektóre z nich w tym rozdziale.

{panel type="teacher-note" summary="Terminologia języków formalnych"}
Poniższa strona zawiera obszerną listę terminów odnoszących się do języków formalnych, chociaż jest dużo głębsza i bardziej formalna niż nasza: [http://www.csee.umbc.edu/portal/help/theory/lang_def.shtml](http://www.csee.umbc.edu/portal/help/theory/lang_def.shtml)
{panel end}

Teraz jest coś, co musimy wyjaśnić, zanim pójdziemy dalej. Jeśli mówimy o tym, które łańcuchy danych wejściowych wprowadzą cię w konkretny stan, a system zaczyna się w tym stanie, to *pusty łańcuch* — czyli ciąg bez żadnych liter — jest jednym z rozwiązań!
Dla przykładu, oto prosty automat skończenie stanowy z jednym tylko wejściem (przycisk a), który reprezentuje specyficzny rodzaj przełącznika światła.
Przycisk resetowania nie jest częścią FSA; to tylko sposób na powrót do stanu początkowego.
Sprawdź, czy potrafisz określić, które wzorce wejścia zapalą światło:

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/fsa-strangelight-v3.html" text="Zobacz interaktywne  dotyczące światła"}

{panel type="teacher-note" summary="Rozwiązanie"}
Światło włącza się co trzecim naciśnięciem przycisku (co jest celowo mylące - uczniowie będą prawdopodobnie oczekiwać, że co drugie naciśnięcie włacza, ale to ma na celu skłonienie ich do myślenia o tym, co się tutaj dzieje!) Sekwencjami, które właczają światło są „aaa”, „aaaaaa” itd. - dowolna liczba wciśnięc, która jest wielokrotnością trzech, włącznie z sytuacją gdy mamy zero wciśnięć.
{panel end}

Czy odkryłeś, które sekwencje naciśnięć guzików włączają światło? Teraz pomyśl o *najkrótszej* sekwencji od momentu zresetowania, która może je włączyć.

Ponieważ światło jest już włączone po zresetowaniu, najkrótsza sekwencja to *zero*.
Ponieważ cieżko zapisać łańcuch o długości zero (chociaż można użyć „”), dlatego będziemy używać specjalnego symbolu, który jest grecką literą epsilon: {math}\epsilon{math end}.
Często spotkasz się z {math}\epsilon{math end} podczas nauki o językach formalnych.

Może to być nieco mylące. Na przykład język (to znaczy lista wszystkich zaakceptowanych danych wejściowych) powyższego FSA zawiera „aaa”, „aaaaaa” i {math}\epsilon{math end}.
Jeśli chciałbyś komuś powiedzieć, że „nic” zapali światło, tak osoba mogłaby opacznie zrozumieć, że światła nigdy nie da się zaświecić. Dlatego przydaje się tutaj stwierdzenie, że *pusty ciąg* (lub {math}\epsilon{math end}) zapali światło.
Jak widać „nic” może mieć różne znaczenie i musimy być precyzyjni co do tego, co mamy na myśli!

Oto FSA dla dziwnego przełącznika światła. Możesz powiedzieć, że {math}\epsilon{math end} jest częścią języka, ponieważ stan początkowy jest również stanem końcowym (w rzeczywistości jest to jedyny stan końcowy). W rzeczywistości przełącznik nie jest wcale taki dziwny — rzutniki często wymagają dwóch naciśnięć przycisku zasilania, aby uniknąć ich przypadkowego wyłączenia.

{image filename="finite-state-automata-light-switch-example.png" alt="Automat skończenie stanowy dla dziwnego przełącznika światła"}

I informatycje bardoz ważne jest rozważanie skrajnych przypadków. Jednym z ekstremalnych przypadków jest brak danych wejściowych: co zrobić, jeśli program otrzymuje pusty plik lub baza danych zawiera zero wpisów? Zawsze ważne jest, aby upewnić się, że te sytuacje zostały przemyślane przez twórców systemu.
Nic więc dziwnego, że mamy symbol pustego łańcucha. 
Zauważmy, że niektórzy informatycy używają greckiej litery lambda ({math}\lambda{math end}) zamiast {math}\epsilon{math end}, aby przedstawić pusty łańcuch znaków.

{panel type="teacher-note" summary="Epsilon czy lambda?"}

Dwa główne elementy zalecanego oprogramowania w tym rozdziale (Exorciser i JFLAP) wykorzystują dwie notacje.
JFLAP można zmienić tak, aby używał epsilon ({math}\epsilon{math end}) z menu Preferencje, więc będzemy używali epsilon w całym rozdziale.
Możesz wcześnie zmienić preferencje JFLAP lub po prostu pokazać uczniom, że epsilon i lambda ({math}\lambda{math end}) mogą być używane zamiennie.

{panel end}

Nawiasem mówiąc, język powyższego trzy-stanowego FSA jest nieskończenie duży, ponieważ jest zbiorem wszystkich łańcuchów, które zawierają literę potrójne wielokrotnosci litery „a” tzn. {{math}\epsilon{math end}, aaa, aaaaa, aaaaaaaa, ...}. To całkiem imponujące jak na taką małą maszynę.

Podczas gdy patrzymy na skrajności, spójrzmy na kolejny FSA. Używa on „a” i „b” jako swojego alfabetu.

{image filename="finite-state-automata-two-or-less-letters.png" alt="FSA dla krótkich łańcuchów"}

Czy zaakceptuje on ciąg „aaa”? lub „aba”? Czy może cokolwiek z 3 lub więcej znakami?

Gdy przejdzie on do trzeciego znaku ciągu, znajdziesz się w stanie nr 4 który nazywa się stanem *pułapki* (po angielsku „trap state”), ponieważ nie możesz się z niego wydostać.
Gdyby to była mapa dla systemu kolei podmiejskiej, który mieliśmy na początku tej sekcji, spowodowałoby to problemy, ponieważ w końcu wszyscy znaleźliby się w stanie pułapki i mielibyśmy potężne przeludnienie na dworcu.
Stan pułapki może być jednak bardzo przydatny w innych sytuacjach — szczególnie, gdy wystąpi błąd w danych wejściowych. Nie ważne co wystąpi po błędzie, nie chcesz iść dalej.

W powyższym przykładzie językiem FSA jest dowolna kombinacja co najwyżej dwóch liter „a” i „b”.
Nie zapominaj, że pusty ciąg jest również akceptowany. To bardzo mały język; jedynymi ciągami w nim są:
{{math}\epsilon{math end}, a, b, aa, ab, ba, bb}.

Oto kolejny FSA do rozważenia:

{image filename="finite-state-automata-no-trap-example.png" alt="FSA z brakującymi przejściami"}

Dość oczywiste jest to, co będzie akceptowane: łańcuchy takie jak „ab”, „abab”, „abababababab” i oczywiście {math}\epsilon{math end}.
Ale są pewne brakujące przejścia: jeśli jesteś w stanie 1 i kolejnym znakiem jest „b”, nie masz dokąd iść.
Jeśli dane wejściowe nie mogą zostać zaakceptowane, to zostaną odrzucone, tak jak w tym przypadku. Moglibyśmy wprowadzić stan pułapki, aby to wyjaśnić:

{image filename="finite-state-automata-trap-added-example.png" alt="FSA z brakującymi przejściami i stanem pułapki"}

Rzeczy mogą się łatwo wymknąć spod kontroli. Co stałoby się, jeśli w alfabecie byłoby więcej liter? Potrzebowalibyśmy czegoś takiego:

{image filename="finite-state-automata-trap-added-extreme-example.png" alt-"FSA z brakującymi przejściami"}

Zamiast tego po prostu mówimy, że każde nieokreślone przejście powoduje odrzucenie danych wejściowych (tzn. Zachowuje się tak, jakby przechodziło w stan pułapki). Innymi słowy, wystarczy użyć prostej wersji powyżej, z zaledwie dwoma przejściami.

Teraz, gdy mamy już uporządkowaną terminologię, przyjrzyjmy się kilku zastosowaniom tej prostej, ale potężnej „maszyny” zwanej automatem skończenie stanowym.

### Kto używa automatów skończenie stanowych?

Automaty skończenie stanowe są używane w projektowaniu obwodów cyfrowych (takich jak elektronika w dysku twardym) i systemach wbudowanych (takich jak alarmy antywłamaniowe lub kuchenki mikrofalowe).
Wszystko, co ma kilka przycisków i przechodzi w różne stany po naciśnięciu tych przycisków (takich jak włączenie/wyłączenie alarmu, wysoka/średnia/niska moc) jest tak naprawdę pewnym rodzajem FSA.

Przez to FSA mogą być używane przez projektantów, aby zaplanować, co stanie się dla każdego wejścia w każdej sytuacji. Mogą być również wykorzystane do analizy interfejsu urządzenia.
Jeśli FSA opisujący urządzenie jest naprawdę skomplikowany, jest to ostrzeżenie, że interfejs prawdopodobnie nie będzie zrozumiały dla człowieka.
Dla przykładu spórz na poniższy FSA dla kuchenki mikrofalowej. Zwróć uwagę, że na przykład nie można przejść z power2 do power1 bez przechodzenia przez timer1. Tego typu ograniczenia będą bardzo frustrujące dla użytkownika.
Na przykład, jeśli ktoś chciałby ustawić power1, to nie zadziała to dopóki nie ustawi przedtem timer1.
Po zapoznaniu się z tą sekwencją jest to łatwe, ale projektant powinien zastanowić się, czy konieczne jest zmuszenie użytkownika do tego rodzaju czynności.
Tego rodzaju problemy stają się proste, gdy spojrzysz na FSA.
Właśnie wkroczyliśmy w obszar interakcji człowiek — komputer! Nie jest to zaskakujące, ponieważ większość dziedzin informatyki ostatecznie przenika się nawzajem — ale nie jest to aż tak ważne zastosowanie FSA, więc wróćmy do bardziej powszechnych zastosowań.

{image filename="finite-state-automata-microwave-example.png" alt="FSA dla kuchenki mikrofalowej"}

Jak zobaczymy w następnym podrozdziale, jednym z najcenniejszych zastosowań FSA w informatyce jest sprawdzenie danych wejściowych na komputerach, niezależnie czy jest to wartość wpisana w okienko dialogowe, program analizowany przez kompilator, czy też coś do wyszukania w dużym dokumencie.
Istnieją również metody kompresji danych, które wykorzystują FSA do przechwytywania wzorców w danych, które są kompresowane. Inne warianty FSA symulują duże systemy komputerowe, aby sprawdzić jak najlepiej je skonfigurować, zanim będzie potrzeba wydania pieniędzy na ich budowę.

{panel type="ciekawostrka" summary="Największy FSA na świecie"}
Jaki jest największy FSA na świecie, który jest używany przez wiele osób każdego dnia? To jest World-Wide Web, czyli Internet. Każda strona internetowa przypomina stan, a odnośniki na jej stronie są przejściami między nimi. W 2000 roku sieć miała miliard stron. W 2008 r. Google oświadczyło, że znalazło bilion różnych adresów stron internetowych. To dużo. Książka o miliardach stron miałaby grubość 50 km. Z bilionem stron jej grubość przekroczyłaby obwód Ziemi.

Ale Internet to tylko automat skończenie stanowy. Abyś mógł korzystać z wyników wyszukiwarki internetowej, firmy takie jak Google muszą sprawdzić wszystkie strony, aby zobaczyć, jakie zawierają słowa. Badając sieć, podążają za wszystkimi odnośnikami, tak jak w przypadku podróży pociągiem. Tylko dlatego, że Internet nazywa się siecią, badanie nazywa się „crawling” - tak jak robią to pająki.

{panel end}

{comment}

.. Zastanów się nad dodaniem aktywności: FSA opisujacy pinball

.. „gra” HTML5, w której otrzymujesz FSA i musisz wpisać znaki, aby przejść do stanu końcowego, ale nie możesz ponownie użyć ciągów Dodaj dźwięki/efekty pinballowe, piłka odbija się naookoło stanów. Oparte na tym:

{comment end}

### Ćwiczenie: Stwórz swój FSA

{panel type="teacher-note" summary="Wybór pomiędzy Exorciser i JFLAP"}

Ten podrozdział wykorzystuje bezpłatne oprogramowanie edukacyjne, które ułatwia uczniom tworzenie i eksperymentowanie z FSA. To oprogramowanie będzie również przydatne w następnej sekcji dotyczącej wyrażeń regularnych, więc warto się z tym zapoznać. Możesz wybrać pomiędzy „Exorciser” lub „JFLAP” (patrz dalej). System Exorciser od [SwissEduc] (http://www.swisseduc.ch/compscience/) jest bardziej przejrzysty i prostszy, ale JFLAP zawiera kilka funkcji przydatnych w sekcjach dotyczących wyrażeń regularnych i gramatyk. (Materiał Exorciser dla gramatyk jest zbyt zaawansowany, a jego funkcje z wyrażeń regularnych są nieco bardziej nużące do użycia dla naszych celów). Oba systemy mają rozbudowane funkcje, które nie mają związku z tym rozdziałem, więc uczniowie będą musieli ignorować wiele z tego, co zobaczą!

Zalecamy rozpoczęcie nauki od Exorcisera, jeśli uczniowie chcą wykonać bardziej zaawansowane maszyny, wtedy mogą zapoznać się z JFLAP.

Szybka wskazówka: aby uniknąć nieporozumień, w Exorciser usuń zaznaczenie opcji przejścia z pustymi łańcuchami, klikając prawym przyciskiem myszy w tle, wybierając „A = {a, b}” i odznaczając {math}\epsilon{math end}. Używające tego menu uczniowie mogą dodawać inne znaki do alfabetu, chociaż wystarczy „a” i „b”, aby rozpocząć swoją przygodę z tworzeniu FSA.

{panel end}

To ćwiczenie polega na skonstruowaniu i testowaniu własnego FSA, za pomocą bezpłatnego oprogramowania, które można pobrać samemu. Zanim to zrobimy, przyjrzymy się ogólnym sposobom tworzenia FSA z danego opisu. Jeśli chcesz wypróbować użyte przykłady na „żywym” FSA, przeczytaj kolejne dwa podrozdziały dotyczące używania Exorciser i JFLAP, które pozwalają ci na napisanie poniższych FSA w jednym z programów i przetestowanie ich.

Dobrym punktem wyjścia jest pomyślenie o najkrótszym łańcuchu, który jest potrzebny do danego opisu. Załóżmy na przykład, że potrzebujesz FSA, który akceptuje wszystkie łańcuchy zawierające parzystą liczbę liter „b”. Najkrótszym takim ciągem jest
{math}\epsilon{math end},
co oznacza, że stan początkowy musi również być stanem końcowym, więc możesz rozpocząć od narysowania tego:

{image filename="finite-state-automata-create-example-1.png" alt="tworzenie FSA"}

Jeśli zamiast tego musiałbyś zaprojektować FSA, gdzie najkrótszym zaakceptowanym łańcuchem jest „aba”, potrzebowałbyś sekwencji 4 stanów takich jak poniższe:

{image filename="finite-state-automata-create-example-2.png" alt="tworzenie FSA"}

Następnie musisz pomyśleć, co dalej. Na przykład, jeśli akceptujemy łańcuchy o parzystej liczbie „b”, to wtedy pojedynczy „b” musiałby przenieść cię od stanu początkowego do nieakceptującego:

{image filename="finite-state-automata-create-example-3.png" alt="tworzenie FSA"}

Ale kolejne „b” spowoduje parzystość ciągu liter b, więc nasz FSA musi taki łańcuch zaakcpetować. Każde kolejne „b” spowoduje przeniesienie się pomiędzy tymi dwoma stanami:

{image filename="finite-state-automata-create-example-4.png" alt="tworzenie FSA"}

Zwykle każdemu stanowi można nadać „znaczenie”. W tym przykładzie bycie w stanie 1 oznacza, że do tej pory wprowadziłeś parzystą liczbę „b”, a stan 2 oznacza, że dotychczasowa liczba była nieparzysta.

{comment}

.. xJRM poniższe dwa diagramy pojawiają się znacznie później w wersji PDF; prawdopodobnie trudny do rozwiązania problem LaTeX, ale to będzie dobra robota na deszczowy dzień!

{comment end}

Teraz musimy pomyśleć czy nie brakuje nam jakiś przejść. Jak dotąd nie powiedzieliśmy maszynie co ma robić w przypadku gdy kolejnym znakiem łańcucha będzie litera „a”. Nasz FSA ma akceptować parzystą liczbę liter „b” w łańcuchu, dlatego liczba liter „a” nie może wpływać na zmianę stanu:

{image filename="finite-state-automata-create-example-5.png" alt="tworzenie FSA"}

To samo gdy automat znajduje się w stanie 2 i kolejnym znakiem jest litera „a”. Automat pozostaje w niezmienionym stanie:

{image filename="finite-state-automata-create-example-6.png" alt="tworzenie FSA"}

Teraz każdy stan ma przejście dla każdego znaku wejściowego, więc FSA jest gotowy. Przetestuj teraz FSA na różnych przykładach aby upewnić się, że zawsze parzysta liczba liter „b” w łańcuchu spowoduje przejście do stanu 1.

Wykonaj to ćwiczenie samemu, korzystając z poniższych instrukcji dla dwóch różnych programów w celu zbudowania i przetestowania własnego FSA. 

#### Exorciser

W tym podrozdziale pokażemy, jak korzystać z oprogramowania edukacyjnego o nazwie „Exorciser”. (W następnym podrozdziale przedstawiono alternatywę o nazwie JFLAP, która jest nieco trudniejsza w użyciu). Exorciser posiada udogodnienia do wykonywania zaawansowanych ćwiczeń związanych z językami formalnymi. Tutaj skupimy się tylko na tych najprostszych.

Exorciser może zostać ściągnięty [stąd](http://www.swisseduc.ch/compscience/exorciser/index.html).

Po uruchomieniu wybierz „Konstruowanie automatów skończonych” (pierwszy element menu); kliknij odnośnik „Początkujący”, aby wykonać nowe ćwiczenie.
Najtrudniejszą częścią każdego ćwiczenia związanego z budową FSA jest oczywiście część po znaku „|” znajdującego się w nawiasach klamrowych. Na przykład na poniższym diagramie jesteś poproszony o narysowanie FSA, który akceptuje łańcuch wejściowy „w”, jeśli „w ma długość co najmniej 3”. Powinieneś narysować i przetestować swoją odpowiedź. Na początku pomocne może okazać się kliknięcie „Rozwiąż ćwiczenie”, aby uzyskać rozwiązanie. Następnie obserwowanie łańcuchów, które spełniają rozwiązanie tego zadania. Tak właśnie zrobiliśmy wykonując poniższy schemat. 

{image filename="finite-state-automata-exorciser-screenshot.png" alt="Oprogramowanie Exorciser od SwissEduc"}

Aby narysować FSA w systemie Exorciser, kliknij prawym przyciskiem myszy w dowolne puste miejsce, a pojawi się menu dotyczące dodawania i usuwania stanów, wybierania alfabetu i tak dalej.
Aby dokonać przejścia pomiędzy stanami, przeciągnij myszką od zewnętrznego kręgu jednego stanu do drugiego (lub wyjdź i wróć z powrotem, aby stworzyć pętlę).
Możesz kliknąć prawym przyciskiem myszy na stany i przejścia, aby je zmieniać.
Zapis „a|b” oznacza, że przejście zostanie wykonane dla znaku „a” lub „b” (odpowiada to dwóm równoległym przejściom).

Jeśli twój FSA nie rozwiąże zadanego problemu, otrzymasz podpowiedź w postaci łańcucha, który FSA traktuje niepoprawnie. Dzięki temu możesz go testować i poprawiać. Jeśli utkniesz, kliknij „Rozwiąż ćwiczenie”.
Możesz również śledzić dane wejściowe podczas pisania — kliknij prawym przyciskiem myszy, aby wybrać tę opcję.
Na [stronie SwissEduc](http://www.swisseduc.ch/compscience/) możesz znaleźć więcej instrukcji.

{image filename="finite-state-automata-exorciser-error-screenshot.png" alt="Oprogramowanie Exorciser od SwissEduc"}

Podrozdział po następującym podrozdziale podaje kilka przykładów do wypróbowania.
Jeśli robisz to jako część projektu, zachowaj kopie automatów i testy, które wykonujesz. Kliknij wtedy prawym przyciskiem myszy, aby wybrać opcję „Zapisz jako” lub zrób zrzut ekranu z obrazkami.

#### JFLAP

{panel type="teacher-note" summary="JFLAP"}

Program o nazwie JFLAP jest alternatywą dla Exorcisera dla uczniów w celu zaprojektowania i przetestowania własnego FSA. Można go pobrać za darmo i jest powszechnie używany do nauczania języków formalnych. Jest to potężne narzędzie, które można wykorzystać w większości koncepcji w tym rozdziale, co sprawia, że warto nauczyć się z niego korzystać. Niestety JFLAP ma o wiele więcej funkcji, niż potrzebujemy w tym rozdziale, a niektórzy nauczyciele uznali, że jest to trudny w klasie w szkole średniej, więc zalecamy użycie Exorciser, jeśli jest dostępny.

Jeśli chcesz korzystać z JFLAP, najpierw zapoznaj się z nim, abyś mógł objaśnić go uczniom: interfejs ma wiele rozpraszających funkcji i może być trochę dziwaczny, a błądzenie bez poświęcania czasu na naukę korzystania z niego będzie frustrującym doświadczeniem. Na szczęście [tutaj](http://www.jflap.org/tutorial/) istnieje dobry samouczek dotyczący używania JFLAP, a [tutaj](http://www.cs.duke.edu/csed/pltl/exercises/lessons/29/finiteautomata.zip) (plik ZIP) trochę materiałów z Duke University o FSA zbudowanych w JFLAP.

Jeśli masz problemy z używaniem Exorciser lub JFLAP, istnieje również przykład FSA w „Java Applets Center” na [http://www.cosc.canterbury.ac.nz/mukundan/thco/DFA.html](http://www.cosc.canterbury.ac.nz/mukundan/thco/DFA.html).

{panel end}

Innym szeroko stosowanym programem do eksperymentowania z FSA jest JFLAP (pobierz z http://jflap.org). Możesz użyć go jako alternatywy dla Exorcisera, jeśli to konieczne. Będziesz musiał postępować ostrożnie z instrukcjami, ponieważ ma o wiele więcej funkcji, niż potrzebujesz. Przez to może być trudno wrócić do miejsca, w którym zacząłeś.

Poniżej przedstawiamy instrukcję do stworzenia FSA w JFLAP. Użyjemy następującego przykładu:

{image filename="jflap-create-state.png" alt="Tworzenie FSA — przykład"}

{comment}

.. xTCB umieść kilka zrzutów ekranu i najlepiej wideo tutaj, aby pokazać, jak używać JFLAP.

{comment end}

Aby stworzyć ten FSA, uruchom JFLAP oraz:
- Kliknij przycisk „Finite Automaton” na panelu sterowania.
- W oknie edytora kliknij obrazek stanu (z niewielkim q na nim), a następnie kliknij w oknie, aby utworzyć stany.
- Aby przenieść stany, kliknij narzędzie ze strzałką na pasku narzędzi (ikonka najbardziej po lewej). Nie ma znaczenia, gdzie są stany, ale chcesz, aby były łatwe do oglądania.
- Aby stworzyć przejście między dwoma stanami, kliknij narzędzie przejścia (trzecia ikonka), przeciągnij linię między dwoma stanami, wpisz etykietę przejścia („a” lub „b” dla tego ćwiczenia) i naciśnij klawisz „Return”. (System zaoferuje pusty ciąg ({math}\lambda{math end}) jako etykietę, ale prosimy nie rób tego!)
- Aby zrobić pętlę powracającą do stanu, wystarczy kliknąć na stan za pomocą narzędzia przejścia.
- Możesz wybrać stan początkowy, wybierając narzędzie strzałki (ikonka najbardziej na lewo), klikając prawym przyciskiem myszy na stan i wybierając „Initial”. Tylko jeden stan może być stanem początkowym, ale możesz ustawić więcej niż jeden stan „Final” (akceptujący) w ten sam sposób, klikając je prawym przyciskiem myszy.

Jeśli chcesz coś zmienić, możesz usunąć rzeczy za pomocą narzędzia do usuwania (ikonka czaszki). Ewentualnie wybierz narzędzie strzałki i kliknij dwukrotnie etykietę przejścia, aby ją edytować lub kliknij prawym przyciskiem myszki stan.
Możesz przesuwać stany za pomocą narzędzia strzałki.

Aby zobaczyć, jak FSA przetwarza dane wejściowe, użyj menu „Wejście” (u góry), wybierz „Krok z zamknięciem”, wpisz krótki ciąg znaków, np. „abaa” i kliknij „OK”. Następnie w dolnej części okna możesz śledzić łańcuch znak po znaku, naciskając „Krok”, który podświetla bieżący stan podczas przechodzenia przez łańcuch.
Jeśli przejdziesz przez łańcuch i skończysz w stanie ostatecznym (akceptującym), panel zmieni się na zielony. Aby powrócić do okna edytora, przejdź do menu „Plik” i wybierz „Odrzuć kartę”.

{image filename="jflap-create-accept.png" alt="Tworzenie FSA — testowanie z wejściem"}

Możesz uruchomić wiele testów za jednym razem. Z menu „Wejście” wybierz „Wielokrotne uruchomienie” i wpisz swoje łańcuchy testowe do tabeli lub załaduj je z pliku tekstowego.

{image filename="jflap-create-accept-multi.png" alt="Tworzenie FSA — wielokrotne uruchomienie"}

Możesz nawet wykonać testy z pustym łańcuchem, pozostawiając pustą linię w tabeli, którą możesz zrobić, naciskając przycisk „Enter Lambda”.

W kolejnym podrozdziale podajemy kilka pomysłów na skonsturowanie FSA.
Jeśli robisz to jako część projektu, zachowaj kopie automatów i testów, które robisz (menu „Plik” i „Zapisz obraz jako...” lub możesz zapisać FSA które utworzyłeś w pliku, aby otworzyć później).

#### Przykłady do wypróbowania

Korzystając z Exorciser lub JFLAP, skonstruuj FSA, który pobiera dane wejściowe stworzone z liter „a” oraz „b”, i akceptuje dane wejściowe, jeśli spełnia jeden z poniższych wymagań. Dla każdego z tych problemów powinieneś zbudować osobny FSA.

- łańcuchy rozpoczynające się od litery „a” (np. „aa”, „abaaa” i „abbbb”).
- łańcuchy kończące się literą „a” (np. „aa”, „abaaa” i „bbbba”).
- łańcuchy, które mają parzystą liczbę liter „a” (np. „aa”, „abaaa”, „bbbb” i nie zapominaj o pustym ciągu {math}\epsilon{math end}).
- łańcuchy, które mają nieparzystą liczbę liter „a” (np. „a”, „baaa”, „bbbab”, ale nie {math}\epsilon{math end}).
- łańcuchy, w których liczba „a” w danych wejściowych jest wielokrotnością trzech (np. „abaaaa”, „bababab”).
- łańcuchy, w których za każdym razem, gdy „a” pojawia się na wejściu, następuje „b” (np. „abb”, „bbababbbabab”, „bbb”).
- łańcuchy, które kończą się na „ab”.
- łańcuchy rozpoczynające się od „ab” i kończące na „ba”, i tylko „b” w środku (np. „abba”, „abbbbba”)
{comment}

.. xTCB napisz odpowiedzi/wskazówki dla nauczycieli

{comment end}

{panel type="teacher-note" summary="Rozwiązania"}

Poniższe rozwiązania podane są dla najmniejszego/najprostszego sposobu przedstawienia powyższych języków, ale uczniowie mogą wymyślić inne, które są prawidłowe. Aby je sprawdzić, wypróbuj przykłady łańcuchów, które są akceptowane i nie są akceptowane. [Rozwiązania do powyższego, które należy jeszcze podać — skontaktuj się z Timem Bellem, jeśli ich potrzebujesz, a my ustalimy je priorytetowo]

{panel end}

{comment}

.. xtcb na pewnym etapie możemy zaoferować rygorystyczny sprawdzacz do tego? lub zminimalizować ich rozwiązanie i sprawdzić, czy jest takie samo co minimum rozwiązania

{comment end}

W przypadku FSA, które konstruujesz, sprawdź, czy akceptują prawidłowe dane wejściowe, ale również upewnij się, że odrzucają nieprawidłowe dane wejściowe.

{panel type="teacher-note" summary="Wskazówka"}

Sprawdzenie, czy nieprawidłowe dane wejściowe nie są skuteczne, jest ważne — w przeciwnym razie uczeń mógłby wykonać FSA, który akceptuje dowolne dane wejściowe, i przejdzie wszystkie testy. Uczniowie będą musieli wymyślić przykłady, które testują różne części FSA, aby pokazać, że nie dają wyników fałszywie pozytywnych lub fałszywie ujemnych.

{panel end}

Oto kilka sekwencji znaków dla których możesz zbudować FSA. Alfabet wejściowy to więcej niż „a” i „b”, ale nie musisz wprowadzać przejścia dla każdego możliwego znaku w każdym stanie, ponieważ FSA może automatycznie odrzucić dane wejściowe, jeśli używa znaku, dla którego nie ustanowiłeś przejścia. Spróbuj wykonać dwa lub trzy z poniższych przykładów:

- nazwy międzynarodowych standardowych rozmiarów papieru (od A1 do A10, od B1 do B10 itd.)
- poprawna trzyliterowa nazwa miesiąca w języku angielskim (Jan, Feb, Mar itd.)
- poprawny numer miesiąca (1, 2, ... 12)
- prawidłowa nazwa dnia tygodnia (poniedziałek, wtorek, ...)

{panel type="teacher-note" summary="Rozwiązania"}

Rozwiązania dla zadań zostaną dostarczone w późniejszej wersji tego przewodnika.

{panel end}

{comment}

.. xTCB udziel odpowiedzi/wskazówek dla nauczycieli — np. miej „dzień” wspólnie na końcu

{comment end}

Klasycznym przykładem FSA jest oldskulowy automat sprzedający batoniki, który przyjmuje tylko kilka rodzajów monet.
Załóżmy, że masz maszynę, która przyjmuje tylko monety 50 groszy i 1 zł. Ty musisz włożyć 3 zł, aby kupić napój.
Alfabet maszyny to moneta o nominale 50 gr i 1 zł, którą w skrócie nazwiemy odpowiednio F i T.
Na przykład, TTT wprowadzałby monety o sumie 3 zł, które byłyby akceptowane. TFFT również zostałoby zaakceptowane, ale TFFF nie.
Czy możesz zaprojektować FSA, który akceptuje dane wejściowe, gdy 3 zł lub więcej zostanie wprowadzone do urządzenia?
Możesz stworzyć własną wersję dla różnych nominałów monet i wymaganej sumy.

{panel type="teacher-note" summary="Rozwiązania"}

Rozwiązania dla zadań zostaną dostarczone w późniejszej wersji tego przewodnika.

{panel end}

{comment}

.. xTCB napisz odpowiedzi

{comment end}

Jeśli miałeś do czynienia z liczbami binarnymi, zastanów się co robi poniższy FSA. Wypróbuj każdą z podanych liczb binarnych jako dane wejściowe: 0, 1, 10, 11, 100, 101, 110, etc.

{image filename="finite-state-automata-binary-multiples.png" alt="FSA do testowania z liczbami binarnymi jako wejściem"}

Czy możesz ustalić, co to znaczy, gdy dla danej liczby FSA kończy się w stanie q1? Stanie q2?

{panel type="teacher-note" summary="Rozwiązanie"}

Ten FSA wykrywa liczby binarne, które są wielokrotnościami 3 (tj. 0, 11, 110, 1001 ..., czyli 0, 3, 6, 9 ... w systemie dziesiętnym). Stan, w którym się znajduje, reprezentuje pozostałą część, gdy dotychczasowe wejście jest podzielone przez 3, więc stan 0 (akceptacja) znaczy, tyle że liczba dzieli się bez reszty przez 3. Jako wyzwanie dla najlepszych uczniów sprawdź, czy potrafią zaprojektować maszynę, która znajdzie wielokrotności 5 (można to zrobić korzystając z 5 stanów). Byłoby to typowe pytanie na rozmowę kwalifikacyjną dla firm, które chcą dowiedzieć się, czy absolwent informatyki naprawdę zna się na rzeczy! Odpowiedzi są dostępne w Internecie, ponieważ jest to dość znany problem, ale mam nadzieję, że niektórzy z twoich uczniów będą chcieli rozwiązać je samodzielnie.

{panel end}

{panel type="activity" summary="Automaty skończenie stanowe w życiu codziennym"}
Istnieje wiele systemów wykorzystujących FSA. Mógłbyś wybrać jakiś system iwyjaśnić, jak można go reprezentować za pomocą FSA oraz pokazać przykłady sekwencji danych wejściowych, które musi obsłużyć. Przykłady takich systemów to:

- Gry planszowe. Proste gry planszowe są często po prostu FSA, gdzie następny ruch jest określony przez pewne dane wejściowe (np. liczbę z rzutu kostką), a stan końcowy oznacza, że ​​ukończyłeś grę — czyli pierwsza osoba, która dotrze do stanu końcowego wygrywa. Większość gier jest zbyt skomplikowana, aby narysować pełną wersję FSA, ale jako przykład można posłużyć się prostą grą, taką jak węże i drabiny. Podaj przykłady sekwencji rzutów kostką, które doprowadzą cię do końca gry? A które nie?!
- Proste urządzenia z kilkoma przyciskami często mają stany, które można łatwo zidentyfikować. Na przykład zdalne sterowanie alarmem samochodowym może mieć dwa przyciski. To, co dzieje się z samochodem, zależy od kolejności, w jakiej je naciskasz i aktualnego stanu samochodu (czy alarm w nim jest włączony, czy nie). W przypadku urządzeń, które automatycznie włączają się lub wyłączają po pewnym czasie, konieczne może być wprowadzenie danych wejściowych, takich jak „oczekiwanie przez 30 sekund”. Inne urządzenia do rozważenia to zegarki cyfrowe (z takimi stanami jak „pokazywanie czasu”, „pokazywanie daty”, „pokazywanie stopera”, „stoper działa”), przyciski zasilania i wysuwania na odtwarzaczu CD, wybór kanału na pilocie telewizora (tylko liczby), ustawienie zegara, przechowywanie ustawień wstępnych w radiu samochodowym i panele kontrolne alarmów przeciwwłamaniowych.

{panel end}

{panel type="activity" summary="Biedronka Kara"}

[SwissEduc](http://www.swisseduc.ch/compscience/) ma środowisko programistyczne zwane [Kara](http://www.swisseduc.ch/compscience/karatojava/kara/) (do instalacji wymaga Javy), która jest programowalną biedronką. Krąży ona (w swojej najprostszej wersji) wokół wyimaginowanego świata kontrolowanego przez działania wydawane przez automat skończonie stanowy. Biedronka ma (symulowane) detektory, które wyczuwają jej bezpośrednie otoczenie; służą one jako dane wejściowe do FSA.
{comment}
.. xtcb Obecnie wygląda na to, że błąd w prostym programie Kara i ładuje się ona tylko w 88% (najwyraźniej ma to związek z wersją Java). Istnieje wersja o nazwie „MultiKara” (w tym samym pakiecie), która ma wiele biedronek, więc możesz po prostu użyć jednej biedronki i uzyskać podobny efekt.
 http://swisseduc.ch/informatik/karatojava/download.html
{comment end}
{panel end}

{panel type="teacher-note" summary="Inne źródła"}

Istnieje wiele zasobów internetowych do eksperymentowania z FSA; opisaliśmy te, które naszym zdaniem są najbardziej dostępne. Jednak mogą istnieć wariacje, które mogą okazać się pomocne, zarówno na różnych platformach komputerowych, jak i tematach odpowiednich dla uczniów. Oto kilka innych, które możesz zbadać.

Gra Manufactoria zasadniczo dotyczy konstruowania automatu skończenie stanowego, który reprezentuje podane reguły. Niektóre z zagadek są dość trudne, a jeśli uczniowie mogą je rozwiązać, to dobrze zrozumieli FSA. (Podpowiedzi: Pasy przenośnikowe są przejściami, gałęzie B/R są stanami z przejściem na niebieski lub czerwony. Możesz mieć przenośniki taśmowe, które działają jak mosty). Gra jest dostępna [tutaj](http://pleasingfungus.com/#Manufactoria) i [tutaj](http://jayisgames.com/games/manufactoria/).

Jeśli używasz graficznego systemu edukacyjnego [Greenfoot](http://www.greenfoot.org/door) operatego na Javie jako środowisko programistyczne, [ćwiczenie poszukiwanie skarbów jako automat skończenie stanowy](http://greenroom.greenfoot.org/resources/5) jest oparte na ćwiczeniu Poszukiwaniu Skarbów FSA ze strony CS Unplugged. Nauczyciele mogą zarejestrować się w obszarze zasobów [Greenroom](http://greenroom.greenfoot.org/door) i pobrać oprogramowanie. Uczniowie mogą wchodzić w interakcję z ćwiczeniem bez uzyskiwania dostępu do kodu źródłowego poprzez: http://www.greenfoot.org/scenarios/1678 .

Jeśli używasz [Scratcha](http://scratch.mit.edu/), to poniższy program jest obiecujący, ale nie ma żadnego ćwiczenia ani przewodnika, a dla uczniów z liceum Scratch może być zbyt infantylny. Implementuje on działanie automatu skończenie stanowego CS Unplugged w Scratch i może być pobrane jako część pliku pełnego zestawu aktywności Unplugged [plik zip](http://code.google.com/p/scratch-unplugged/downloads/detail?name=scratch-unplugged-1-0.zip&can=2&q=). Plik [ReadMe.txt](http://code.google.com/p/scratch-unplugged/downloads/detail?name=readme.txt&can=2&q=) posiada dokumentację. Został opracowany przez [Mordechaja (Moti) Ben-Ariego](http://stwww.weizmann.ac.il/g-cs/benari/) z [Instytutu Naukowego Weizmanna w Izraelu](http://www.weizmann.ac.il/).

Jeśli chcesz utworzyć schematy FSA, możesz użyć programu JFLAP lub programu graphviz, który ma wiele opcji do rysowania tego rodzaju diagramów: [http://www.graphviz.org/](http://www.graphviz.org/)

{panel end}

{comment}

.. Niewykorzystany materiał:

.. TCB xJRM [niepilne] czy którekolwiek z poniższych filmów są bardzo pomocne??
.. Making Things Interact (MTI)ma kilka filmów pokazujących przykłady implementacji automatów skończenie stanowych na różne sposoby
.. Uytkownik YouTuba tarbidian ma autmaty skończenie stanowe 01 - Introduction zilustrowane dobrym przykładem przy wcześniejszym użyciu przeglądu diagramu stanu (ang. State Transition Diagram Review)

.. TCB oto kolejny internetowy symulator FSA (autorstwa Mukunda), który może zostać użyty jako model, jeśli zdecydujemy się na zrobienie tego w hmtl5
.. TCB można określić i uruchomić FSA na: http://www.cosc.canterbury.ac.nz/mukundan/thco/DFA.html
.. TCB to działa poprawnie na Windowsie, ale jest wyłączone i nie działa na Macu.

.. ciekawa prezentacja, ale nie daje wiele szczegółów: http://mtifall09.wordpress.com/category/8-finite-state-machines/
.. ma maszyny zbudowane przez uczniów jako projekt, np. cukierek albo psikus. Głównie tylko 3 proste stany, większość pracy związana jest ze sprzętem.

.. TCB Poniższe informacje były przydatne, ale wydaje się, że teraz jest ograniczony dostęp: Merchant Taylors 'School UK w swoim bezpłatnym kursie na Moodle, którego celem jest AS Computing, ma ćwiczenie o maszynach skończenie stanowych opartych na Kara. Ich przewodnik „Getting started with Kara” jest przydatny, ponieważ podręcznik dla Kary jest dość krótki. Wygląda na to, że już go nie ma.

.. ćwiczenie/przykład, który nie został użyty: dla języka FSA, transformacja dla uzupełnienia (zmiana stanów akceptacji), odwrócenie?

.. JRM  wideo wprowadzające o fsm: https://www.youtube.com/watch?v=Obt3L1YBwlM Wyjaśnia to dość wyraźnie, ale nie wiem, jak dobrze zostanie to odebrane przez młodszych odbiorców. Jest to dość długa (15 minut), ale dość standardowa prezentacja (powerpoint z ręcznym rysowaniem na górze z narracją). To było dla mnie dobre, ale nie wiem, jak to dobrz dla dzieci. Jeśli obejrzysz pierwsze dwie minuty, dobrze zrozumiesz styl. Zaczyna od podstaw i buduje w miłym, stabilnym tempie, często używa „bitów”, co jest dobre, ale na początku wymienia „puls zegara” i zajęło mi trochę czasu, aby zrozumieć to. Występuje mały błąd w filmie, ma jednak adnotację wyjaśniającą. To całkiem niezły film.

.. Dla przypomnienia, wczesny i wciąż bardzo czytelny artykuł o FSA pojawia się poniższej
.. stronie, ale byłoby to rozpraszające linkowanie tego tutaj:
.. http://www.ccs3.lanl.gov/mega-math/workbk/machine/mabkgd.html

.. Maszyny Mealy'ego/ Moore'a — poza zakresem?
.. Jeśli pracowałeś z liczbami binarnymi, sprawdź, czy możesz dowiedzieć się, co ten
.. FSA robi (wypróbuj każdą liczbę binarną jako dane wejściowe: 0, 1, 10, 11, 100, 101, 110 etc.)
.. zrób to w jflap
.. stan wejście przejście wyjście
.. s0  0 s0 0
.. s0 1 s1 0
.. s1 0 s0 1
.. s1 1 s1 0
.. podawaj najpierw liczbę binarną msb -> odejmuj

.. TCB oto kolejny symulator FSM, ale nie jest to ładny interfejs, ale może być bardziej dostępny: http://courses.cs.vt.edu/~cs1104/FSM/FSM.Design.html

{comment end}

{comment}

.. fl-regex:

{comment end}

## Wyrażenia regularne

{panel type="teacher-note" summary="Wyrażenia regularne"}

Wyrażenia regularne (ang. „regular expressions”, w skrócie regex) są blisko związane z FSA, jak zaraz się przekonamy. Duża część terminologii, która jest potrzebna, została już omówiona w poprzednich podrozdziałach: będziemy używać:
{glossary-link term="alfabet"}aflabetów{glossary-link end} do
złożenia razem
{glossary-link term="łańcuch"}łańcuchów{glossary-link end}
liter.
Zbiór wszystkich łańcuchów, które mogą być zaakceptowane przez konkretną FSA, nazywany jest jej
{glossary-link term="język"}językiem{glossary-link end}.
Będziemy potrzebować pustego łańcucha({math}{\epsilon}{math end} lub {math}{\lambda}{math end}),
i ostatecznie
{glossary-link term="automat skończenie stanowy"}automaty skończenie stanowe{glossary-link end}.
Dlatego poprzedni podrozdział dotyczący FSA musi zostać omówiona przed rozpoczęciem wyrażeń regularnych.

Możliwe, że uczniowie używali już wyrażeń regularnych, ponieważ są one wbudowane w wiele języków programowania i są często używane podczas pisania programów skryptowych. Będziemy krótko przyglądać się takim zastosowaniom — a są one bardzo istotne — ale w językach formalnych interesuje nas również granica tego, co może zostać zaprezentowane za ich pomocą i jak przekonwertować wyrażenie regularne na FSA. Dlatego to powinno być coś, co skłoni uczniów do myślenia, nawet jeśli są ekspertami w programowaniu z wykorzystaniem „regex”.

{panel end}

{panel type="teacher-note" summary="Ćwiczenie — odwrócone kalambury"}

Jeśli masz czas, następujące ćwiczenie („odwrócone kalambury”) można wykonać przed lub po nauczeniu wyrażeń regularnych. Zalecamy korzystanie z niego wcześniej, ponieważ staje się ono konstruktywistycznym podejściem, które zachęca uczniów do projektowania własnych notacji dla języków regularnych i jest motywatorem do nauki precyzyjnej notacji.

Przydatnym ćwiczeniem w celu opanowania przez uczniów znajomości FSA i wyrażeń regularnych jest gra „odwrócone kalambury” dla automatów skończonych, opracowana przez Lindę Pettigrew. Korzysta z [tej ulotki] (files/reverse-pictionary-worksheet.pdf) (lub możesz stworzyć własne proste FSA).

Podziel klasę na dwie grupy: A i B. Rozdaj jedną kopię FSM-A każdej parze uczniów w grupie A i FSM-B, aby utworzyć pary w grupie B. Każda para wymaga również arkusza językowego. Będą pisać tylko w górnej połowie arkusza. Uczniowie muszą teraz opisać wszystkie akceptowalne dane wejściowe dla danego FSA (używając dowolnej notacji, którą mogą wymyślić, lub wyrażeń regularnych, jeśli już je napotkali). Kiedy są zadowoleni z ich opisu (lub minęło pięć minut), zapisują to w arkuszu językowym. Niektóre odpowiednie opisy są następujące. Użyliśmy standardowej notacji regex, ale uczniowie mogą wymyślić coś innego.

```
FSM-A: bee*p(-bee*p)*  or  be*ep(-be*ep)*  or  be+p(-be+p)*
FSM-B: cl(i|a)ck(-cl(i|a)ck)*
FSM-A: mee*o*w  or  me*eo*w  or  me+ow
FSM-B: squ((el)|(ir))ch(-squ((el)|(ir))ch)*
```

Arkusze językowe z obu grup są następnie gromadzone. Arkusze z grupy A są rozdawane grupie B i odwrotnie. Pary teraz czytają opis „języka” i wypełniają dolną połowę arkusza językowego czterema łańcuchami, które FSM zaakceptuje, a czterema, których nie zaakceptuje. Tutaj uczniowie działają jako „programiści”, próbując zmusić komputer po drugiej stronie do wykonania określonego zadania.

Następnie arkusze językowe są zbierane ponownie, a te z grupy A rozprowadzane wśród B i grupy B do grupy A. Nie ma potrzeby, aby pary otrzymywały swój oryginalny arkusz. Pary są teraz „komputerami” i muszą sprawdzić, czy dane wejściowe podane w dolnej części arkusza językowego są zgodne z FSA. Jeśli jeden z łańcuchów zostanie zaakceptowany lub odrzucony niepoprawnie, grupy będą musiały ustalić, skąd pochodzi błąd.

alsza dyskusja może sprawdzić, czy niektóre opisy były dłuższe, niż były potrzebne lub mylące dla zrozumienia oraz czy język maszyn został poprawnie przechwycony.

{panel end}

Już pomakowaliśmy
{glossary-link term="Wyrażenie regularne" reference-text="wprowadzenie"}wyrażeń regularnych{glossary-link end}
w podrozdziale [wprowadzającym](rozdzialy/jezyki-formalne.html#zaczynamy). Są one po prostu prostym sposobem wyszukiwania rzeczy w danych wejściowych lub określenia, jaki rodzaj danych wejściowych zostanie zaakceptowany jako poprawny.
Na przykład wiele programów do obsługi skryptów internetowych używa ich do sprawdzania danych wejściowych dla wzorców, takich jak daty, adresy e-mail i adresy URL. Stały się tak popularne, że są teraz wbudowane w większoścu języków programowania.

Być może podejrzewasz, że wyrażeniania regularne związane są z 
{glossary-link term="automaty skończenie stanowe" reference-text="związane z wyrażeniami regularnymi"}automatami skończenie stanowymi{glossary-link end}.
I masz rację, ponieważ okazuje się, że każde wyrażenie regularne ma automat skończony, który może sprawdzić dopasowania, a każdy automat skończony może zostać przekonwertowany na wyrażenie regularne, które pokazuje dokładnie to, co robi (i nie robi) dopasowanie. Wyrażenia regularne są zwykle łatwiejsze do odczytania przez ludzi. W przypadku komputerów program komputerowy może przekonwertować dowolne wyrażenie regularne na FSA, a następnie komputer może bez problemu speawdzić dane wejściowe.

Najprostszym rodzajem dopasowywania jest właśnie wpisywanie tekstu w celu dopasowania. Otwórz interaktywne nrzędzie poniżej i wpisz tekst „cat” w polu oznaczonym „Wyrażenie regularne”:

{interactive name="regular-expression-search" type="whole-page" text="Wyszukiwanie wyrażeniami regularnymi - ćwiczenie 1" parameters="text=The fat cat sat on the mat.%0AThe vindication was catastrophic.%0AThe bilocation of the cataract required certification.%0AThe 42 buffalo baffled them with a pfffffffft sound.%0APennsylvania 6-5000.%0AAssorted exhalations: pfft pffft pft.%0AWas that a match or was it not?"}

{comment}
.. polska wersja nie ma zbytnio sensu, gdyźż słowo kot występuje raz (Tomek)
{interactive name="regular-expression-search" type="whole-page" text="Wyszukiwanie wyrażenia regularnego - ćwiczenie 1" parameters="text=Tłusty kot siedział na macie.%0AWindykacja była katastrofalna.%0ABilokacja zaćmy wymagała certyfikacji.%0A42 bawołó zaskoczyło ich dźwiękiem spoffffft.%0APennsylwania 6-5000.%0ARóżne wydechy: pfft pffft pft.%0ACzy to było dopasowanie, czy nie było?"}
{comment end}

{panel type="teacher-note" summary="Alternatywne strony internetowe do ćwiczenia wyrażeń regularnych"}

Uczniowie mogą również przejrzeć przykłady w tym podrozdziale, używając narzędzi [Rubular](http://rubular.com/) lub [Regex101](https://regex101.com/).

Ewentualnie możesz ich również skłonić do skorzystania z doskonałego samouczka [RegexOne](http://regexone.com/). RegexOne zapewnia odpowiedzi na wyzwania i testy w tym samym oknie. Uczniom mogą ujść płazem nieskuteczne odpowiedzi, ale jest to dobre środowisko do zabawy z konceptem.
{image filename="regexone-example-screenshot.png" alt="Zrzut ekranu Regexone"}

{comment}

Rozważ użycie http://www.debuggex.com/?re=(foo|bar)baz* jednak na dzień 31.03.2016 r. witryna nie jest aktywnie utrzymywana

{comment end}

{panel end}

Jeśli wpisałeś tylko 3 znaki „cat”, to powinno wyszukać 6 dopasowań.

Teraz spróbuj wpisać kropkę jako czwartą literę: „cat.”. W wyrażeniu regularnym „.” może dopasować dowolny pojedynczy znak. Spróbuj dodać więcej kropek przed i po „cat”. Co dzieje się dla „cat.s” lub „cat..n”?

Co otrzymasz, jeśli wyszukujesz „ ... ” (trzy kropki ze spacją przed i po)?

Teraz spróbuj wyszukać „ic.”. Znak „.” pasuje do dowolnej litery, więc jeśli chcesz wyszukać kropkę, musisz napisać tak: „ic\.” — użyj tego wyszukiwania, aby znaleźć „ic” na końcu zdania.

Kolejny specjalny symbol to „\\d”, który pasuje do dowolnej cyfry. Spróbuj dopasować 2, 3 lub 4 cyfry z rzędu (na przykład dwie cyfry z rzędu to „\\d\\d”).

Aby wybrać z małego zestawu znaków, spróbuj „[ua]ff”. Każdy ze znaków w nawiasach kwadratowych będzie dopasowany. Spróbuj napisać wyrażenie regularne, które będzie dopasowywało „fat”, „sat” i „mat”, ale nie „cat”.

{panel type="teacher-note" summary="Rozwiązanie"}

Odpowiednim wyrażeniem jest [fsm]at

{panel end}

Skrótem dla dopasoania „[mnopqrs]” jest „[m-s]”; spróbuj również „[m-s]at” i „[4-6]”.

Kolejnym użytecznym skrótem jest możliwość dopasowania powtarzających się liter. Istnieją cztery wspólne zasady:

- a* dopasowuje 0 lub więcej powtórzeń a
- a+ dopasowuje 1 lub więcej powtórzeń  a
- a? dopasowuje 0 lub 1 wystąpień a (to znaczy a jest opcjonalne)
- a{5} dopasowuje „aaaaa” (to znaczy, że a jest powtórzone 5 razy)

Spróbuj z nimi eksperymentować. Oto kilka przykładów, które warto wypróbować:
```
f+
pf*t
af*
f*t
f{5}
.{5}n
```

Jeśli chcesz wybrać między opcjami, przydatna jest pionowa kreska. Wypróbuj poniższe przykłady i sprawdź, do czego pasują. Możesz wpisać dodatkowy tekst w obszarze łańcucha testowego, jeśli chcesz eksperymentować:

```
was|that|hat
was|t?hat
th(at|e) cat
[Tt]h(at|e) [fc]at
(ff)+
f(ff)+
```

Zwróć uwagę na użycie nawiasów w celu grupowania części wyrażenia regularnego. Przydaje się to, jeśli chcesz zastosować „+” lub „\*” do więcej niż jednego znaku.

{panel type="jargon-buster" summary="Wyrażenie regularne"}
{glossary-definition term="wyrażenie regularne" definition="Formuła używana do opisu wzorca w tekście, który ma być dopasowany lub wyszukiwany. Są one zwykle używane do znajdowania elementów programu (takich jak nazwy zmiennych) i sprawdzania danych wejściowych w formularzach (np. Sprawdzanie, czy adres e-mail ma odpowiedni format).)"}
Termin
{glossary-link term="wyrażenie regularne reference-text="skróty"}wyrażenie regularne{glossary-link end}
jest czasami zapisywany skrótowo jako „regex”, „regexp”, lub „RE”. Jest ono „regularne”, ponieważ można go używać do definiowania zestawów łańcuchów znaków z bardzo prostej klasy języków zwanych „językami regularnymi”. Jest „wyrażeniem”, ponieważ jest kombinacją symboli, zgodnie z pewnymi zasadami.

{panel end}

Kliknij tutaj, aby wykonać kolejne ćwiczenie: powinieneś spróbować napisać krótkie wyrażenie regularne pasujące do dwóch pierwszych słów, ale nie trzech ostatnich:

{interactive name="regular-expression-search" type="whole-page" text="Wyszukiwanie wyrażeniami regularnymi - ćwiczenie 2" parameters="text=meeeeeeeow%0Ameoooooooooooow%0A%0Awoof%0Amew%0Acluck"}

{panel type="teacher-note" summary="Rozwiązanie"}

„me+o+w” jest dobrym rozwiązaniem.

{panel end}

Głównie wyrażenia regularne są używane w poważniejszych celach. Kliknij poniższe narzędzie interaktywne, aby uzyskać nowy tekst do wyszukania:

{interactive name="regular-expression-search" type="whole-page" text="Wyszukiwanie wyrażeniami regularnymi - ćwiczenie 3" parameters="text=Contact me at spam@mymail.com or on 555-1234%0AFFE962%0ADetails: fred@cheapmail.org.nz (03) 987-6543%0ALooking forward to 21 Oct 2015%0AGood old 5 Nov 1955%0ABack in 2 Sep 1885 is the earliest date%0AABC123%0ALet's buy another 2 Mac 9012 systems @ $2000 each."}

Poniższe wyrażenie regularne znajdzie typowe tablice rejestracyjne Nowej Zelandii w przykładowym tekście, ale czy możesz znaleźć krótszą wersję używając notacji {n}?

```
[A-Z][A-Z][A-Z]\d\d\d
```

{panel type="teacher-note" summary="Rozwiązanie"}

„[A-Z]{3}\\d{3}”

{panel end}

A jak znaleźć daty w tekście? Oto jedna z opcji, choć nie idealna:

```
\d [A-Z][a-z][a-z] \d\d\d\d
```

Czy możesz to poprawić?

{panel type="teacher-note" summary="Rozwiązanie"}

Wyrażenie „\\d\\d? (Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec) \\d\\d\\d\\d” jest bardziej precyzyjne, ale bardziej wyrafinowana wersja byłaby w praktyce stosowana w celu uwzględnienia różnych formatów.

{panel end}

A co z numerami telefonów? Musisz zastanowić się, jakie odmiany numerów telefonów są częste!
Jak znaleźć adresy e-mail?

{panel type="teacher-note" summary="Rozwiązania"}

Oto dwa dość proste rozwiązania dla adresów e-mail, ale możliwe są bardziej wyrafinowane:

- \\w+@\w+\\.\\w+   znajduje tylko adres e-mail z dwiema częściami w domenie
- \\w+@\\w+(\\.\\w+)* dopasowuje więcej części domeny

{panel end}

{image filename="xkcd-regular-expressions.png" hover-text="Wait, forgot to escape a space.  Wheeeeee[taptaptap]eeeeee." alt="Komentarz xkcd do kreskówek o wyrażeniach regularnych" source="https://xkcd.com/208/"}

Wyrażenia regularne są przydatne!

Szczególna forma wyrażen regularnych, których używalismy została zaczerpnięta z języka programowania Ruby (popularnego języka do tworzenia stron internetowych), chociaż jest bardzo podobna do wyrażeń regularnych używanych w innych językach, w tym Java, JavaScript, PHP, Python i Microsoft .NET Framework. Nawet niektóre arkusze kalkulacyjne mają funkcje dopasowywania wyrażenia regularnego.

{comment}

.. TCB dla jasności, robi to Google Docs. Excel ma to, ale to naprawdę VB.

{comment end}

Wyrażenia regularne mają swoje ograniczenia — na przykład, nie będziesz w stanie stworzyć takiego, który będzie w stanie dopasować palindromom (słowa i frazy, które są takie same czytane zarówno od przodu jak i od tyłu, takie jak „kajak”, „oko” i „atak kata”). Nie można użyć jednego do wykrycia łańcuchów składających się z *n* powtórzeń litery „a”, po której następuje *n* powtórzeń litery „b”.
Do tego typu wzorców potrzebny jest mocniejszy system zwany gramatyką (zobacz [rozdział o gramatyce] ((rozdzialy/jezyki-formalne.html#gramatyki-i-paroswanie)).
Niemniej jednak wyrażenia regularne są bardzo przydatne w w typowym dostosowaniu wzorców.

{comment}

.. xTCB ciekawostka: pomysł pochodzi od Kleene (dodaj dane osobowe, daty)

{comment end}

### Wyrażenia regularne i automaty skończenie stanowe

Istnieje bezpośredni związek między wyrażeniami regularnych i FSA. Dla przykładu rozważ następujące wyrażenie regularne, które dopasowuje łańcuchy zaczynające się parzystą liczbą liter „a” i kończą się parzystą liczbą liter „b”:
```
(aa)+(bb)+
```

Teraz spójrz, jak następujący FSA działa na tych łańcuchach — możesz spróbować „aabb”, „aaaabb”, „aaaaabbbb”, a także zobacz, co dzieje się z łańcuchami takimi jak „aaabb”, „aa”, „aabbb” i tak dalej.

{image filename="finite-state-automata-aabb-trap.png" alt="FSA dla (aa)+(bb)+"}

Być może zauważyłeś, że q2 jest „stanem pułapki”. Ten sam efekt możemy osiągnąć za pomocą następującego FSA, w którym usunięto wszystkie przejścia do stanu pułapki - FSA może odrzucić dane wejściowe, od razu gdy nie ma pasującego do nich przejścia.

{image filename="finite-state-automata-aabb.png" alt="FSA dla (aa)+(bb)+"}

Tak jak FSA, każde wyrażenie regularne reprezentuje 
{glossary-link term="język" reference-text="wyrażenie regularne"}język{glossary-link end},
które jest po prostu zbiorrem wszystkich 
{glossary-link term="łańcuch" reference-text="regular expression"}łańcuchów{glossary-link end},
które pasują do tego wyrażenia regularnego.
W powyższym przykładzie najkrótszym łańcuchem w języku jest „aabb”, potem są „aaaabb”, „aabbbb” i tak dalej w nieskończoność.
Istnieje również nieskończona liczba łańcuchów, które *nie są* w tym języku, jak „a”, „aaa”, „aaaaaa” i tak dalej.

W powyższym przykładzie FSA jest naprawdę łatwym sposobem sprawdzenia wyrażenia regularnego — możesz napisać bardzo szybki i mały program, żeby zaimplementować to (w rzeczywistości jest to dobre ćwiczenie: zazwyczaj masz tablicę lub listę z wpisem dla każdego stanu, a każdy wpis informuje cię, do którego stanu idziesz po każdym znaku, a także czy jest to stan ostateczny. Na każdym kroku program po prostu sprawdza, do którego stanu iść.)

Na szczęście *każde* wyrażenie regularne można przekonwertować na FSA. Nie przyjrzymy się w jaki sposób jest to robione, ale zarówno Exorciser, jak i JFLAP mogą to zrobić za ciebie (zobacz ćwiczenia poniżej).

Większość języków programowania potrafi konwertować wyrażenia regularne na FSA.
Programiści zwykle używają wyrażeń regularnych, wywołując funkcje lub metody, którym przekazuje się wyrażenie regularne i szukany łańcuch.
Kompilator konwertuje wyrażenie regularne na automat skończenie stanowy. Następnie zadanie sprawdzena twojego wyrażenia regularnego jest bardzo łatwe.

{panel type="project" summary="Tworzenie wyrażeń regularnych"}

Oto kilka pomysłów na wyrażenia regularne, które możesz spróbować utworzyć. Możesz je sprawdzić za pomocą [wyszukuwania wyrażeń regularnych] interactives/regular-expression-search/index.html?reference=true), tak jak to zrobiliśmy wcześniej, ale musisz stworzyć własny tekst, by sprawdzić swoje wyrażenie regularne.
Testując wyrażenia, upewnij się, że nie tylko akceptują one poprawne łańcuchy, ale odrzucają te niepasujące, nawet jeśli brakuje tylko jednego znaku.

Może będzie dla ciebie prostsze, aby mieć jeden testowy łańcuch dopasowania na linię w „twoim testowym łańcuchu”.
Możesz zmusić swoje wyrażenie regularne do dopasowania do całej linii, wstawiając „^” (początek linii) przed wyrażeniem regularnym i „$” (koniec linii) za nim. Na przykład „^a+$” dopasowuje tylko linie, które składają się tylko i wyłącznie z liter „a”.

Możesz stworzyć wyrażenia regularne dla następujacych problemów:

- lokalne formy niezindywidualizowanych tablic rejestracyjnych (np. PO 12345 dla miastach na prawach powiatu i np POZ 1234 dla zwykłych powiatów)
- dowolna rozszerzona forma słowa „halo”, np. „haloooooooooooo”
- warianty „aaaarrrrrgggggghhhh”
- zegar 24 godzinny (np. 23:00) lub 12 godzinny (np. 11:55 pm)
- numer konta bankowego lub karty kredytowej
- data ważności karty kredytowej (musi mieć 4 cyfry, np. 01/15)
- hasło, które musi zawierać co najmniej 2 cyfry
- data
- numer telefonu (wybierz swój format, np. tylko telefon komórkowy, numery krajowe lub międzynarodowe)
- kwota w złorych wpisana na stronie banku, która powinna akceptować różne formaty, np. „21{,}43 zł”, „21”, „21{,}43”, i „5.000PLN”, ale nie „zł21”, „21.5”, „5,0000.00” i „PLN300”.
- akceptowalne identyfikatory w twoim języku programowania (zwykle coś w rodzaju litery, po której następuje kombinacja liter, cyfr i niektórych symboli interpunkcyjnych)
- liczba całkowita w twoim języku programowania (pozwól na + i - z przodu, a niektóre języki pozwalają na przyrostki takie jak L lub przedrostki takie jak 0x)
- adres IP (np. 172.16.5.2  lub 172.168.10.10:8080)
- ades MAC urządzenia (np. e1:ce:8f:2a:0a:ba)
- kody pocztowe dla kilku krajów np. NZ: 8041, Kanada: T2N 1N4, USA: 90210
- (niektóre) adresy URL http, takie jak „http://abc.xyz”, „http://abc.xyz#conclusion”, „http://abc.xyz?search=fgh„”.

{panel end}

{panel type="project" summary="Konwertowanie wyrażeń regularnych na FSA"}

{comment}

.. xTCB Na dłuższą metę dobrze byłoby mieć wbudowany konwerter na stronie książki. Poniżej znajduje się kod Pythona dla konwersji RE do FS http://osteele.com/software/python/fsa/, ale coś na podstawie JFLAP lub Exorciser byłoby łatwiejsze.

.. xTCB lepszą oceną byłaby szybkość implementacji FSA? http://swtch.com/~rsc/regexp/ podaje przykłady naprawdę dobrych i złych implementacji oraz trudne RegExy do przetestowania ich.

.. xTCB więcej pomysłów tutaj: http://www.drdobbs.com/architecture-and-design/regular-expressions/184410904

{comment end}

W tym projekcie utworzymy wyrażenie regularne, skonwertujemy je na FSA i pokażemy, jak przetwarzane są niektóre łańcuchy.

Jest jedna sztuczka, którą musisz znać: oprogramowanie, z którego korzystamy, nie ma wszystkich notacji, których używaliśmy powyżej, które są powszechne w językach programowania, ale nie są używane w teorii języków formalnych. W rzeczywistości jedynymi dostępnymi są:

- `a*` dopasowuje 0 lub więcej powtórzeń a
- `a|b` dopasowuje a lub b
- `(aa|bb)*` Nawiasy grupują polecenia; w tym przypadku daje mieszaninę par liter „a” i par liter „b”.

Ograniczenie do tych rzech notacji nie jest problemem, gdyż wszystkie inne można uzyskać korzystając z nich.
Na przykład „a+” jest tym samym co „aa*”, a „\\d” to „0|1|2|3|4|5|67|8|9”. Będzie to trochę powolne, ale użyjemy głównie ćwiczeń, które wykorzystują tylko kilka znaków.

**Kowersja z Exorciser**

Skorzystaj z tej części, jeśli używasz Exorciser, który jest zalecany dla tego projektu, ale jeśli używasz JFLAP, przejdź do **Konwersja z JFLAP** poniżej.

Exorciser jest bardzo prosty. W rzeczywistości, jeśli nie zmienisz ustawień domyślnych, może on konwertować tylko wyrażenia regularne, używając dwóch znaków: „a” i „b”. Ale nawet to wystarczy (teoretycznie każde wejście może być reprezentowane dwoma znakami — to tak jak w liczbach binarnych!)

Na dodatek Exorciser ma dostępny pusty symbol łańcucha — jeśli wpiszesz „e”, zostanie przekonwertowany na {math}\epsilon{math end}.
Na przykład „(a| {math}\epsilon{math end})” oznacza opcjonalne „a” w danych wejściowych.

Aby wykonać ten projekt za pomocą Exorciser, przejdź do okna startowego („home”) i wybierz drugie łącze „Konwersja wyrażenia regularnego do automatów skończonych”.
Teraz wpisz swoje wyrażenie regularne w polu wprowadzania tekstu zaczynającym się od „R=”.

Na rozgrzewkę spróbuj:

```
aabb
```

potem kliknij „rozwiąż ćwiczenie” (to jest skrót — oprogramowanie jest przeznaczone dla uczniów do tworzenia własnych FSA, ale to wykracza poza to, co robimy w tym rozdziale).

Powinieneś otrzymać bardzo prosty FSA!

Aby przetestować FSA, kliknij prawym przyciskiem myszy tło i wybierz „Śledź wejście”.

Teraz spróbuj niektórych bardziej złożonych wyrażeń regularnych, takich jak poniższe. Dla każdego z nich wpisz je, kliknij „rozwiąż ćwiczenie”, a następnie prześledź kilka przykładowych danych wejściowych, aby zobaczyć, jak akceptuje i odrzuca różne łańcuchy.

```
aa*b
a(bb)*
(bba*)*
(b*a)*a
```

Twój raport z projektu powinien pokazywać wyrażenia regularne, wyjaśniać, jakie rodzaje łańcuchów pasują do nich, pokazywać odpowiednie FSA, pokazywać sekwencję stanów, przez które przechodzą niektóre łańcuchy próbne, i powinieneś wyjaśnić, w jaki sposób komponenty FSA odpowiadają częściom wyrażenia regularnego za pomocą przykładów.

**Konwertowanie z JFLAP**

W [JFLAP] (http://www.jflap.org) możesz używać prawie dowolnego znaku jako danych wejściowych.
Głównymi wyjątkami są „\*”, „+” (mylące: „+” jest używany zamiast „|” dla alternatywy) i „!” (który jest pustym łańcuchem — w preferencjach, które możesz wybrać, ustaw czy jest pokazywany jako {math}\lambda{math end} lub {math}\epsilon{math end}).

Zatem głównymi operatorami dostępnymi w JFLAP są:

- `a*` dopasowuje 0 lub więcej powtórzeń a
- `a+b` dopasowuje a lub b
- `(aa+bb)*` Nawiasy grupują polecenia; w tym przypadku daje mieszaninę par liter „a” i par liter „b”.

Oprogramowanie JFLAP może współpracować z różnymi językami formalnymi, więc musisz zignorować wiele opcji, które oferuje! W tej części dowiesz się, co dokładnie należy robić.

W poniższym samouczku są pewne szczegóły dotyczące formatu, który JFLAP wykorzystuje do wyrażeń regularnych — wystarczy przeczytać sekcję „Definicja” i „Tworzenie wyrażeń regularnych”.

[http://www.jflap.org/tutorial/regular/index.html](http://www.jflap.org/tutorial/regular/index.html)

W ramach rozgrzewki przekształcimy poniższe wyrażenie regularne w FSA:

```
ab*b
```

W głównym oknie kontrolnym JFLAP kliknij „Wyrażenie regularne” i wpisz swoje wyrażenie regularne do JFLAP:

{image filename="jflap-ab-star-a-regex-screenshot.png" alt="Wpisywanie ab\*a do JFLAP"}

{comment}

.. TCB szczegółowe informacje na temat konwersji znajdują się na: http://www.jflap.org/tutorial/fa/createfa/fa.html

{comment}

Z menu „Konwertuj” wybierz „Konwertuj na NFA”.
Spowoduje to tylko rozpoczęcie konwersji. Naciśnij przycisk „Zrób wszystko”, aby ją ukończyć (system jest zaprojektowany, aby pokazać wszystkie etapy konwersji, ale chcemy po prostu dostać końcowy wynik).
Otrzymujemy następujący niedeterministyczny automat skończenie stanowy (NFA), który nie jest dokładnie tym, czego chcemy i prawdopodobnie wygląda raczej niechlujnie:

{image filename="jflap-ab-star-a-nfa-screenshot.png" alt=" NFA wygenerowane (niechlujna wersja pośrednia FSA)"}

Potrzebujemy DFA (deterministycznego FA), a nie NFA.
Aby przekonwertować NFA na DFA, naciśnij przycisk „Eksportuj”, a następnie z menu „Konwertuj” wybierz „Konwertuj na DFA”, naciśnij przycisk „Zakończ”, aby zakończyć konwersję, a następnie przycisk „Gotowe?”, który umieści go w nowym oknie:

{image filename="jflap-ab-star-a-dfa-screenshot.png" alt="Po konwersji do DFA"}

To już prawie koniec. Jeśli trudno jest odczytać FSA, możesz przesuwać stany po ekranie, wybierając narzędzie strzałki (po lewej stronie paska narzędzi — jeśli stany nie będą się przesuwać, gdy je chwycisz, to upewnij się, że klikniesz ikonę strzałki zanim spróbujesz je przenieść). Stany mogą mieć pod nimi jakieś nieistorne etykiety; możesz je ukryć, wybierając narzędzie strzałki, klikając prawym przyciskiem myszy białą część okna i odznacz pole „Wyświetlaj etykiety stanów”.

{image filename="jflap-ab-star-a-dfa-tidy-screenshot.png" alt="Po uporządkowaniu DFA"}

Jeśli FSA jest wystarczająco prosty, może być równie proste skopiowanie schematu ręcznie i spróbowanie ustawienia go samodzielnie. W przeciwnym razie możesz zapisać go jako obraz do umieszczenia w projekcie.
{comment}

.. xTCB muszę to powiedzieć tutaj? Musisz kliknąć przycisk „Gotowe”, aby zakończyć konwersję.

{comment end}

Teraz wypróbuj kilka przykładowych danych wejściowych. Stan początkowy jest oznaczony jako q0 i ma dużą strzałkę wskazującą na niego. Możesz zmusić JFLAP, aby przeszedł przez niektóre dane wejściowe za pomocą menu „Wejście”. „Krok po stanie” będzie podążał za twoim wejściem stan po stanie, „Szybkie uruchamianie” pokaże sekwencję odwiedzonych stanów dla twojego wejścia, a „Wielokrotne uruchamianie” pozwala załadować listę łańcuchów do przetestowania.

Wielokrotne uruchomienie dobrze nadaje się do wykonania wielu testów na twoim wyrażeniu regularnym:

{image filename="jflap-ab-star-a-dfa-tidy-output-screenshot.png" alt="Po uporządkowaniu DFA"}

Na przykład „ab” zostaje odrzucone, ponieważ dojdzie tylko do stanu 2.

Teraz powinieneś wymyślić własne wyrażenia regularne, które przetestują interesujące wzorce i wygenerują dla nich FSA.
W JFLAP możesz utworzyć FSA dla niektórych wyrażeń regularnych, których użyliśmy wcześniej, takich jak (proste) daty, adresy e-mail lub adresy URL.

Jeśli konwersja wyrażeń regularnych na FSA jest częścią projektu, to powinieneś pokazać wyrażenia regularne, wyjaśniać, jaki rodzaj łancuchów pasuje do nich, pokazać odpowiadający FSA, pokazać sekwencję stanów, przez które przechodzą niektóre łańcuchy próbne, i powinieneś wyjaśnić, w jaki sposób komponenty FSA odpowiadają częściom wyrażenia regularnego za pomocą przykładów.

{panel end}

{panel type="projekt" summary="Inne pomysły na projekty i ćwiczenia"}

Oto kilka pomysłów, które można wykorzystać do zbadania wyrażeń regularnych:

- Na [stronie regexdict](http://www.visca.com/regexdict/), przeczytaj instrukcję na temat rodzajów
{glossary-definition term="Dopasowywanie wzorców" definition="W językach formalnych znajdowanie tekstu pasującego do konkretnej reguły, zwykle przy użyciu wyrażenia regularnego podając regułę."}
{glossary-link term="dopasowywanie wzorców" reference-text="Języki formalne"}dopasowywania wzorców{glossary-link end}
które to narzędzie może wykonać i napisz wyrażenia regularne do wyszukiwania słów takich jak:
 - słowa zawierające „aa”
 - wszystkie słowa z 3 literami
 - wszystkie słowa z 8 literami
 - wszystkie wyrazy zawierające więcej niż 8 liter
 - słowa zawierające litery twojego imienia
 - słowa, które składają się z liter które występują w twoim imieniu
 - słowa zawierające wszystkie samogłoski w odwrotnej kolejności
 - słowa, które można stworzyć za pomocą używając tylko nut na pianinie (tj. litery od A do G i od a do g)
 - słowa, które są wyjątkami od reguły w języku angielskim „i przed e za wyjątkiem po c” (ang. „i before e except after c”) — upewnij się, że znajdziesz słowa takie jak „forfeit” oraz „science”.

- Komenda *Znajdź* w Microsoft Word używa wyrażeń regularnych po wybraniu opcji „Użyj symboli wieloznacznych”. Aby uzyskać więcej informacji, zobacz artykuł [Grahama Mayora](http://word.mvps.org/AboutMVPs/graham_mayor.htm) - [„Znajdowanie i zastępowanie znaków za pomocą symboli wieloznacznych”](http://word.mvps.org/FAQs/General/UsingWildcards.htm).

- Odkryj wyrażenia regularne w arkuszach kalkulacyjnych. Arkusz kalkulacyjny Google docs ma funkcję RegExMatch, RegExExtract i RegExReplace. W Excelu są one dostępne przez Visual Basic.

- Dziewiarskie wzory są formą wyrażeń regularnych. Jeśli interesuje cię dziewiarstwo, możesz sprawdzić, jak są one ze soba powiązane w [artykule o dzianinie i wyrażeniach regularnych na stronie CS4FN](http://www.cs4fn.org/regularexpressions/knitters.php).

- Polecenie „grep” jest dostępne w wielu wierszach poleceń systemów operacyjnych i dopasowuje wyrażenie regularne w poleceniu do linii w pliku wejściowym. (nazwa pochodzi od „Global Regular Expression Parser” (pl. „Globalny parser wyrażenia regularnego”)). Zademonstruj polecenie grep dla różnych wyrażeń regularnych.
- Funkcje dopasowania względem wyrażeń regularnych pojawiają się w większości języków programowania. Jeśli twój ulubiony język ma tę funkcję, możesz pokazać, jak to działa, używając przykładowych wyrażeń regularnych i łańcuchów.

- zaawansowane: Darmowe narzędzia *lex* i *flex* mogą przyjmować specyfikacje dla wyrażeń regularnych i tworzyć programy analizujące dane wejściowe zgodnie z regułami. Są one powszechnie używane jako część interfejsowa kompilatora, a dane wejściowe to program, który jest kompilowany. Możesz zbadać te narzędzia i zademonstrować prostą implementację.

{comment}
.. TCB xJRM [nie jest pilne i prawdopodobnie nie odniesie sukcesu] Czy istnieją podobne wzory dla tkania lnu, które mozna dodać do wzorów dziewiarskich? Nie mogę otworzyć stron, które powinny je mieć; na przykład, czy są tu wzory? www.alibrown.co.nz/instructions.html Te mogą być bardziej istotne/interesujące
{comment end}
{panel end}

{panel type="teacher-note" summary="Więcej informacji na temat wyrażeń regularnych"}

Istnieje wiele informacji na temat wyrażeń regularnych na: [http://www.regular-expressions.info/](http://www.regular-expressions.info/)

[Regex Coach](http://weitz.de/regex-coach/) to aplikacja graficzna dla systemu Windows, której można używać do interaktywnego eksperymentowania z wyrażeniami regularnymi.

Inne strony do eksperymentów z wyrażeniami regularnymi obejmują:

- [http://regexpal.com/](http://regexpal.com/) (dopasowuje podczas pisania)
- [http://www.regexplanet.com/advanced/javascript/index.html](http://www.regexplanet.com/advanced/javascript/index.html) (zawiera odmiany wyrażeń regularnych dla wielu języków programowania)
- [http://www.txt2re.com/](http://www.txt2re.com/) — wpisujesz przykładowy tekst i próbuje zasugerować wyrażenie regularne!
- [http://www.regextester.com/](http://www.regextester.com/)
- [http://www.pyweek.org/e/RegExExpress/](http://www.pyweek.org/e/RegExExpress/)
- [https://regexhero.net/  (może być płatne)](https://regexhero.net/)
- [http://www.brics.dk/automaton/](http://www.brics.dk/automaton/)
- [http://www.regular-expressions.info/javascriptexample.html](http://www.regular-expressions.info/javascriptexample.html)


{panel end}

## Gramatyki i parsowanie

{comment}
.. ostrzeżenie:: ten podrozdział nie został jeszcze ukończony; poniższy materiał to tylko wstęp
{comment end}

{panel type="teacher-note" summary="Sekcja jest niekompletna"}
Obecnie sekcja jest tylko wprowadzeniem

Jest wprowadzenie do tego tematu (który bardziej dotyczy gramatyki angielskiej) na stronie:[http://ozark.hendrix.edu/~burch/cs/150/reading/grammar/index.html](http://ozark.hendrix.edu/~burch/cs/150/reading/grammar/index.html). Można to wykorzystać do dyskusji w klasie.

Przygotowując się do lektury tego rozdziału, możesz wykonać ćwiczenie „planeta ABBA” z uczniami jako klasą, ponieważ zapoznają się oni z notacją.
{panel end}

{comment}

.. xtcb albo gra karciana, w której możesz podstawić reguły gramatyki (podając ciąg znaków, spróbuj zastosować gramatykę od dołu do góry — zamień sekwencję na terminal, dozwolone jest cofanie, to znaczy zamień terminal ponownie - używaj obrazów zamiast  a/b? zobrazkami powinny być jabłka/banany, może nawiasy?) lub HTML5, w którym musisz rozwiązać zagadkę (zasady, aby dostać się do danego ciągu znaków)

.. xtcb http://cs.jhu.edu/~jason/papers/#eisner-smith-2008-tnlp może być użyteczne (konkursowe pisanie gramatyki)

.. Blisko start: nauczycielu: Planet ABBA, gramatyka pieniędzy i głupie zdania, z http://www.mathmaniacs.org/lessons/06-grammars/index.htmlz dodanymi arkuszami:
.. http://www.cosc.canterbury.ac.nz/tim.bell/dt/fg-images/FL-grammars-mathmaniacs.pdf
.. Niech uczniowie zaczną myśleć o podstawach gramatyk

{comment end}

Pamietasz Yodę z Gwiednych Wojen? Ma on bardzo osobliwą gramatykę. Jednak wciąż potrafisz go zrozumieć.
Elastyczność reguł gramatyki angielskiej (jak i polskiej) oznacza, że zazwyczaj możesz zostać zrozumiany, nawet jeśli nie jesteś całkiem poprawny, ale oznacza to również, że reguły są bardzo skomplikowane i trudne do zastosowania.

Gramatyki w językach formalnych są znacznie bardziej przewidywalne niż gramatyki w językach naturalnych. Dlatego nazywa się je językami *formalnymi*!
Kiedy mówisz po angielsku, gramatyka moze sprawiać tobie wiele trudności. Istnieje wiele reguł i wiele wyjatków od tych reguł — na przykład potrzebujesz apostrofu, jeśli piszesz „the computer's USB port”, ale musisz to pominąć, jeśli powiesz „its USB port”.

{glossary-definition term="gramatyka" definition="W językach formalnych: zestaw reguł dla określania języka, na przykład w celu określenia składni języków programowania."}
{glossary-link term="gramatyka" reference-text="Języki formalne"}Gramatyki{glossary-link end}
w informatyce są używane głównie do określania języków programowania i formatów plików. Przez nie kompilatory robią problemy, nawet jeśli pominiesz tylko jeden nawias lub przecinek!
Równocześnie są one bardzo przewidywalne. 

{comment}

.. Przykład początkowy - tylko jeden lub dwa ciągi w języku? Planeta ABBA? użycie prostej gramatyki języka angielskiego?

{comment end}

W tym podrozdziale [gdy będzie skończony!] przyjrzymy się gramatykom powszechnie stosowanym w informatyce.
Są one bardzo wydajne, ponieważ pozwalają, że bardzo skomplikowany system (jak kompilator języka lub format HTML) jest określony w bardzo zwięzły sposób, a także są programy, które automatycznie korzystając z gramatyki zbudują system dla ciebie.
Gramatyki dla konwencjonalnych języków programowania nie są dobrym pomysłem, aby użyć ich jako początkowych przykładów, więc będziemy pracować z kilkoma małymi przykładami, w tym z częściami gramatyk dla języków programowania.

Notatka: pozostała część tej sekcji nie została jeszcze opracowana.

{comment}

.. TCB aby utrzymać porządek, surowy materiał został przeniesiony https://docs.google.com/document/d/1GvMxAGAso8cD5n-tuzJsGgPSQDWmKLuAAWrSFZw4Xbo/edit

{comment end}


{panel type="projekt" summary="Inne pomysły na projekty i ćwiczenia"}

(Zauważ, że będą one miały większy sens po zakończeniu poprzedniego wprowadzenia do gramatyki!)

- Zademonstruj, w jaki sposób kompilatory, interpretery, analizatory składni lub walidatory znajdują błędy w językach formalnych, np. wprowadź błąd do skompilowanego programu, pliku dokumentu XML lub strony internetowej i pokaż efekt błędu.

- Znajdź gramatykę dla języka programowania i pokaż, jak analizować przykładowy program za pomocą gramatyki.

- Użyj przykładów, aby pokazać drzewo parsowania (lub drzewo) dla poprawnego i niepoprawnego fragmentu programu lub pokazania sekwencji produktów gramatyki, aby zbudować poprawny fragment programu.

- Zbadaj gramatykę dla zrównoważonych nawiasów S -> SS, S -> (S), S -> ( )

- Znajdź gramatykę dla prostego wyrażenia arytmetycznego w języku programowania i pokaż drzewo parsowania dla przykładowych wyrażeń (takich jak (a+b)\*(c-d) ).

{panel end}

{panel type="projekt" summary="Gramatyki w sztuce i muzyce"}


{image filename="context-free-tree-screenshot.png" alt="Drzewo narysowane za pomocą oprogramowania z contextfreeart.org" source="http://contextfreeart.org/"}

Program *context free art* (http://www.contextfreeart.org/](http://www.contextfreeart.org/)) umożliwia identyfikowanie obrazów za pomocą gramatyki bezkontekstowej. Na przykład następujące zdjęcia drzew są zdefiniowane przez kilka zasad, które opierają się na tym, że las składa się z drzew, drzewo składa się z gałęzi, a gałęzie z kolei składają się z samych gałęzi! Te proste definicje mogą tworzyć obrazy z dużą ilością szczegółów, ponieważ proces rysowania może rozkładać gramatykę na tyle poziomów, ile jest wymagane. Możesz definiować swoje własne gramatyki, aby generować obrazy, a nawet tworzyć film  jak są one tworzone, jak ten poniżej. Oczywiście, jeśli robisz to jako projekt, upewnij się, że rozumiesz, jak działa system i jesteś w stanie wyjaśnić język formalny, za którym stoi twoje dzieło.


{video url="http://player.vimeo.com/video/52320658"}

{comment}

..TCB powyższy film context-free-tree został wygenerowany z programu bezkontekstowego — możesz kontrolować szybkość klatek itp., Jeśli potrzebna jest inna wersja. To jest po prostu „demo1” w programie. Muzyka pochodzi z utworu Andrew Bella

{comment end}

Program JFLAP ma również funkcję renderowania „systemów Lindenmayera”([https://pl.wikipedia.org/wiki/L-system](https://pl.wikipedia.org/wiki/L-system)), które są innym sposobem korzystania z gramatyk w celu tworzenia uporządkowanych obrazów.
Przeczytaj o ich działaniu w samouczku JFLAP
([http://www.jflap.org/tutorial/index.html](http://www.jflap.org/tutorial/index.html)),
a tutaj [http://www.cs.duke.edu/csed/pltl/exercises/lessons/20/L-system.zip] jest bardziej szczegółowy samouczek (http://www.cs.duke.edu/csed/pltl/exercises/lessons/20/L-system.zip).
Oto kilka przykładowych plików, które mogą cię zainspirować: (te zaczynające się „ex10...” [http://www.cs.duke.edu/csed/jflap/jflapbook/files/](http://www.cs.duke.edu/csed/jflap/jflapbook/files/) )
a oto przykład obrazu, który można w ten sposób uzyskać:

{image filename="jflap-tree-leaves-l-systems-screenshot.png" alt="Narysowane drzewo przy użyciu L-systems w JFLAP"}

Istnieje również system online do generowania obrazów z systemami L: [http://www.kevs3d.co.uk/dev/lsystems/](http://www.kevs3d.co.uk/dev/lsystems/)

{comment}

.. Tego rodzaju obrazy są przykładami fraktali, które są strukturami, w których xxxx ma naturę: http://paulbourke.net/fractals/googleearth/

..  TCB podaje link do gramatyki muzycznej (informacje od David Bainbridge poniżej)
.. Gramatyki zostały zdefiniowane dla *notacji muzycznej* [podaj link].

{comment end}

Gramatyki zostały użyte w notacji muzycznej:

{comment}

.. todo: xTCB trzeba to zbadać.

.. trochę informacji na http://www.springerlink.com/content/c235877773143671/

{comment end}

- Poniżej znajduje się [Gramatyka BNF dla formatu muzycznego ABC](http://web.archive.org/web/20080309023424/http://www.norbeck.nu/abc/abcbnf.htm)
- [http://abc.sourceforge.net/](http://abc.sourceforge.net/)
- [https://meta.wikimedia.org/wiki/Music_markup](https://meta.wikimedia.org/wiki/Music_markup)
- [http://www.emergentmusics.org/theory/15-implementation](http://www.emergentmusics.org/theory/15-implementation)
- przeanalizuj prosty utwór muzyczny pod kątem gramatyki formalnej.

{comment}

.. Jednak nawet to może być trochę onieśmielające. Na plus, jest tam oprogramowanie i powiązane.. zasoby, które można pobrać i pobawić się z nim. Poniższe ma prostszy zbiór reguł, które moim zdaniem są łatwiejsze do strawienia:
.. https://meta.wikimedia.org/wiki/Music_markup
.. i (jak sądzę) jest dobrym motywującym przykładem - coś, co pozwoli ludziom piszącym Wikipedię zwięźle włączyć muzykę do treści, które tworzą
.. Natknąłem się również na następujące rzeczy, które mogą być interesujące:
.. http://www.emergentmusics.org/theory/15-implementation

{comment end}

{panel end}

## Podsumowanie

{panel type="teacher-note" summary="Zaawansowany materiał"}
W tej części przedstawiamy kilka wskazówek dotyczących zaawansowanego materiału o językach formalnych, które wykraczają poza zakres tego rozdziału.
Nie spodziewalibyśmy się, aby zwykli uczniowie będą zajmować się poniższymi tematami, ale może znajdzie się jeden lub dwóch, którzy uważają to pole za interesujące i chcą uzyskać wskazówki, gdzie szukać dalej. Chcemy jasno powiedzieć, że rozdział jest tylko początkiem tego co jest bardzo bogatą częścią informatyki.

{panel end}

Ten rozdział jest tylko zarysem tego co można robić wykorzystując języki formalne. Jeśli uznałeś materiał w tym rozdziale za interesujący, oto kilka tematów, które możesz chcieć zgłębić.

Języki formalne pojawiają się w różnych dziedzinach informatyki i są bardzo przydatnymi narzędziami dla naukowców zajmujących się komputerami. Redukują one niewiarygodnie złożone systemy do małego opisu, i odwrotnie pozwalają stworzyć bardzo złożone systemy z kilku prostych zasad.
Są one niezbędne do pisania kompilatorów, a więc są aktywowane za każdym razem, gdy ktoś pisze program! Są one również związane z teorią automatów i kwestiami związanymi z obliczalnością i są w pewnym stopniu wykorzystywane w przetwarzaniu języka naturalnego, gdzie komputery próbują zrozumieć ludzki język.

W podrozdziale [Wyrażenia regularne i automaty skończenie stanowe](rozdzialy/jezyki-formalne.html#wyrażenia-regularne-i-automaty-skońćzenie-stanowe) korzystaliśmy z FSA, które tak naprawdę są *Deterministycznymi automatami skończonymi* (DFA), ponieważ decyzja o tym, którego przejścia należy dokonać, jest jednoznaczna na każdym etapie.

Zdarza się także, że okresla się takie FSA jako *Skończony akceptor stanowy*, ponieważ akceptuje i odrzuca dane wejściowe w zależności od tego, czy osiąga stan końcowy.
Istnieją różne warianty automatów, o których nie wspominaliśmy, w tym maszyny Mealy'ego i Moore'a (które generują dane wyjściowe dla każdego dokonanego przejścia lub osiągniętego stanu), zagnieżdżona maszyna stanów (gdzie każdy stan może być FSA samym w sobie), niedeterministyczne automaty skończone (które mogą mieć tę samą etykietę na więcej niż jednym przejściu poza stan) i lambda-NFA (które mogą zawierać przejścia na pustym ciągu, {math}\lambda{math end}).
Wierzcie lub nie, wszystkie te odmiany są w zasadzie równoważne i można je przekształcać z jednych na drugie. Są one wykorzystywane w wielu praktycznych sytuacjach do projektowania systemów dla przetwarzania danych wejściowych.

Jednak istnieją również bardziej złożone modele obliczeń, takie jak automat PDA (Push-Down Automaton), który jest w stanie przestrzegać reguł gramatyk bezkontekstowych i najbardziej ogólny model obliczeń zwany maszyną Turinga.
Modele te są coraz bardziej skomplikowane i abstrakcyjne, a struktury takie jak maszyna Turinga nie są wykorzystywane jako urządzenia fizyczne (z wyjątkiem zabawy), ale zamiast tego jako narzędzie do wnioskowania o ograniczeniach, co można obliczyć.
W zasadzie każdy komputer jest rodzajem ograniczonej maszyny, więc te wszystkie ograniczenia, które znajdziemy w maszynie Turinga, stanowią ograniczenia w codziennych obliczeniach.

{comment}
.. TCB, jeśli zdecydujemy się opisać niedeterministyczne automaty - może zastosować humorystyczne podejście - np. trasa pociągu jest częściowo losowa lub kilku pasażerów wypróbowuje wszystkie trasy?
{comment end}

Maszyna Turinga nosi swoją nazwę po Alanie Turingu, który pracował nad tymi koncepcjami na początku XX wieku (to ten sam Turing od testu Turinga w AI. Są to dwie rózne rzeczy - prace Turinga pojawiają się w wielu dziedzinach informatyki!) Jeśli chcesz zbadać ideę maszyny Turinga i lubisz czekoladę, istnieje [ćwiczenie na stronie cs4fn] (http://www.cs4fn.org/turing/turingmachines.php), która podaje przykłady jak ona działa.

Środowisko programowania Kara również posiada [demonstrację maszyn Turinga](http://www.swisseduc.ch/compscience/karatojava/turingkara/)

{comment}

.. inne języki

{comment end}

W tym rozdziale omówiliśmy dwa główne rodzaje języka formalnego: wyrażenie regularne (RE) i gramatykę bezkontekstową (CFG). Są one typami języków, które są szeroko stosowane w kompilatorach i systemach przetwarzania plików. Wyrażenia regularne wykorzystuje się do znajdowania prostych wzorców w pliku, takich jak identyfikatory, słowa kluczowe i liczby w programie lub znaczniki w pliku HTML, lub daty i adresy URL w formularzu internetowym. Gramatyki bezkontekstowe są dobre, gdy musisz się zmierzyć z zagnieżdżonymi strukturami, na przykład, gdy wyrażenie składa się z innych wyrażeń lub gdy instrukcja „jeżeli” zawiera blok zdań, które z kolei mogą być wyrażeniami „jeżeli”, ad infinitum.

Istnieją bardziej zaawansowane formy gramatyki, z których najczęstsze to gramatyki kontekstowe i nieograniczone gramatyki, które pozwalają na posiadanie więcej niż jednego symbolu nieterminalnego po lewej stronie produkcji; na przykład mógłbyś mieć

xAy {math}\to{math end} aBb,

co jest bardziej elastyczne, ale o wiele trudniejsze w obsłudze.
Relacje między głównymi rodzajami gramatyki opisał językoznawca Noam Chomsky. Na jego cześć klasyfikację języków formalnych nazwano
{glossary-definition term="Hierarchia Chomsky’ego" definition="Hierarchia czterech klasyfikacji języków formalnych, od prostych wyrażeń regularnych do bardzo elastycznych (ale trudnych obliczeniowo) gramatyk."}
{glossary-link term="Hierarchia Chomsky’ego" reference-text="Formal languages"}hierarchią Chomsky’ego{glossary-link end}.

Istnieje bezpośrednia zgodność między „maszynami” (takimi jak FSA) i językami (takimi jak wyrażenie regularne), ponieważ każdy coraz bardziej złożony język potrzebuje odpowiednio złożonej maszyny do jej przetworzenia.
Na przykład, FSA może być użyty do określenia, czy dane wejściowe pasują do danego wyrażenia regularnego, ale PDA jest potrzebne, aby dopasować ciąg do CFG.
Badanie języków formalnych analizuje te relacje i wymyśla sposoby tworzenia odpowiednich maszyn dla danego języka i odwrotnie.

Dostępnych jest wiele narzędzi, które będą czytać w specyfikacji dla danego języka i tworzyć inny program do analizowania języka; niektóre z nich nazywane są „Lex” i „Flex” (oba wykonują leksykalną analizę wyrażeń regularnych), „Yacc” („yet another compiler compiler”) i „Bison” (ulepszona wersja Yacc).
Te programy sprawiają, że stosunkowo łatwo jest stworzyć własny język programowania i skonstruować dla niego kompilator, chociaż wymagają one sporej gamy umiejętności, aby wszystko działało!

{comment}
.. xTCB należy sprawdzić fakty powyżej o lex/flex/yacc/bison
{comment end}

Dopiero zaczęliśmy mówić o tym, co można zrobić w językach formalnych, ale intencją tego rozdziału jest zasygnalizowanie rodzajów struktur, z którymi pracują informatycy, oraz potężnych narzędzi, które zostały stworzone, aby mieć możliwość pracy z nieskończenie złożonymi systemami przy użyciu niewielkich opisów.

## Dalsza lektura
Inspiracją dla niektórych materiałów z tego rodziału była strona [http://www.ccs3.lanl.gov/mega-math/workbk/machine/malearn.html](https://web.archive.org/web/20130102053644/http://www.ccs3.lanl.gov/mega-math/workbk/machine/malearn.html)

Na poniższej stronie znajduje się bardzo dobry artykuł o FSA
[http://www.i-programmer.info/babbages-bag/223-finite-state-machines.html](http://www.i-programmer.info/babbages-bag/223-finite-state-machines.html)

### Książki

Podręczniki o językach formalnych będą miały znacznie bardziej zaawansowany materiał i bardziej matematyczny rygor, niż można się było spodziewać na poziomie szkoły średniej, ale dla uczniów, którzy naprawdę chcą czytać więcej, popularna jest książka
„Wprowadzenie do teorii obliczeń” Michaela Sipsera.

Wyrażenia regularne i ich relacje z FSA są dobrze wyjaśnione w książce „Algorytmy” Roberta Sedgewicka.

### Ciekawe odnośniki

- [https://en.wikipedia.org/wiki/Formal_language](https://en.wikipedia.org/wiki/Formal_language)
- [https://en.wikipedia.org/wiki/Context-free_grammar#Examples](https://en.wikipedia.org/wiki/Context-free_grammar#Examples)
- [https://en.wikipedia.org/wiki/Abstract_syntax_tree](https://en.wikipedia.org/wiki/Abstract_syntax_tree)
- [https://en.wikipedia.org/wiki/Regular_expression](https://en.wikipedia.org/wiki/Regular_expression)
- [http://csunplugged.org/finite-state-automata](http://csunplugged.org/finite-state-automata)
- [http://www.i-programmer.info/babbages-bag/223-finite-state-machines.html](http://www.i-programmer.info/babbages-bag/223-finite-state-machines.html)
- [http://www.jflap.org/](http://www.jflap.org/)
- [https://en.wikipedia.org/wiki/Deterministic_finite_automaton](https://en.wikipedia.org/wiki/Deterministic_finite_automaton)
- [https://en.wikipedia.org/wiki/Finite-state_machine](https://en.wikipedia.org/wiki/Finite-state_machine)

{comment}

.. TCB poniżej jest zwięzłe podsumowanie wielu koncepcji wspomnianych w tym rozdziale; nie jest bezpośrednio użyteczne dla studentów, ale traktowauj to jako komentarz, ponieważ może być przydatne dla autorów rozdziałów: http://www.csee.umbc.edu/portal/help/theory/automata_def.shtml and http://www.csee.umbc.edu/portal/help/theory/lang_def.shtml


.. xTCB dodaj poniższe jeśli/gdy używane w sekcji gramatyka:
.. Języki formalne,
.. Diagramy syntaktyczne,
.. Gramatyki bezkontekstowe,
.. Automaty skończenie stanowe,
.. Notacja BNF,
.. Wyrażenia regularne,
.. Odwrotna Notacja Polska (RPN) lub
.. Notacja postfiksowa, Notacja infiksowa,
.. Algorytm Stacji Rozrządowej
.. Diagram stanów
.. Automat Mealy’ego, Automat Moore’a

.. Zobacz również: Drzewo wyprowadzenia/Drzewo składniowe,
.. Wyrażenie Poprawnie zbudowane (WFF),
.. Semantyka formalna języków programowania

{comment end}
