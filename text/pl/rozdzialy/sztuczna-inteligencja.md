# SSztuczna inteligencja

{video url="https://www.youtube.com/watch?v=ia-oYtacJHE"}

## What's the big picture?

Sztuczna inteligencja przywołuje na myśl wiele obrazów – prawdopodobnie myślisz o przyjaznych systemach, które mogą z tobą rozmawiać i rozwiązywać trudne problemy; albo o maniakalnych robotach, które są skłonne do dominacji nad światem? Jest obietnica samochodów bez kierowcy, które są bezpieczniejsze niż człowiek prowadzący auto, oraz obawy o systemy doradztwa medycznego które utrzymują życie ludzi w ich wirtualnych rękach. Sztuczna inteligencja jest częścią informatyki, która jest bardzo obiecująca ale też stwarza wiele obaw. Może być ona używana do podejmowania decyzji w systemach tak dużych jak samolot czy  [automatyczna wywrotka](http://www.komatsu.com/CompanyInfo/profile/product_supports/), jak i małych takich jak telefony komórkowe, które dokładnie przewidują tekst, który jest do nich wpisywanych. Ich wspólną cechą jest to, że próbują naśladować ludzką inteligencję. I co ważne, takie systemy mogą być znaczącym ułatwieniem w codziennym ludzkim życiu.

SI (znane także jako inteligentne systemy) jest przede wszystkim gałęzią informatyki, ale czerpie wiele z koncepcji i pomysłów innych dziedzin, w szczególności [matematyki](https://pl.wikipedia.org/wiki/Matematyka) (głównie logika, kombinatoryka, statystyka, prawdopodobieństwo i teoria optymalizacji), [biologii](https://pl.wikipedia.org/wiki/Biologia), [psychologii](https://pl.wikipedia.org/wiki/Psychologia), [językoznawstwa](https://pl.wikipedia.org/wiki/Lingwistyka), [naurobiologii](https://pl.wikipedia.org/wiki/Neurobiologia) and [filozofii](https://pl.wikipedia.org/wiki/Filozofia).

W tym rozdziale omówimy szereg tych inteligentnych systemów. Oznacza to, nieuchronnie, zajęcie się również aspektami etycznymi i filozoficznymi – Czy naprawdę chcemy, aby maszyny przejmowany niektóre nasze zawody? Czy możemy im ufać? Czy pewnego dnia może to wszystko pójść za daleko? Co tak naprawdę rozumiemy przez powiedzenie, że komputer jest inteligentny? Chociaż nie odpowiemy na te pytania bezpośrednio w tym rozdziale, zdobycie wiedzy technicznej na temat SI pozwoli ci podejmować bardziej świadome decyzje dotyczące głębszych problemów.

## Chatboty i test Turinga

{image filename="computer-studying-turing-test.png" alt="Komputer czyta książkę pod tytułem 'Rozmawiać jak człowiek'"}

Wielu ludzi przyjmuje za pewnik fakt, że mogą łatwo rozmawiać z inną osobą i na podstawie tej rozmowy wybrać odpowiednie rzeczy, które chcą powiedzieć. Zdolność do tego jest formą inteligencji, a dla komputerów nie jest to takie proste! Podjęto wiele prób zaprojektowania programów komputerowych, które mogą prowadzić rozmowę z człowiekiem i brzmieć inteligetnie. Te programy komputerowe nazywane są *chatterbotami* lub po prostu *chatbotami* (lub spolszczona wersja *czatbot*) albo *linguabotami*

Możesz spotkać się z czatbotami online w poważnych sytuacjach (np. udzielanie pomocy na stronie rezerwacji). 
Czasami trudno powiedzieć, czy otrzymujesz automatyczną odpowiedź. 
Zaczniemy od spojrzenia na kilka bardzo prostych czatbotów, które są zaprojektowane raczej jako eksperyment niż oferowanie poważnej porady.

### Sesja terapeutyczna z czatbotem Eliza

{panel type="teacher-note" summary="Czatboty na lekcji"}
Jeśli ten materiał jest używany w klasie i czas jest ograniczony, upewnij się, że uczniowie nie spędzają za dużo czasu rozmawiając z każdym z czatbotów. 15 minut to maksymalny czas na rozmowę z każdym czatbotem - Elizą, Alice i Cleverbotem (w sumie 45 minut) oraz dodatkowe 15 - 45 minut (w zależności od ograniczeń czasowych) dla uczniów na poszukanie innych czatbotów, które będą adekwatne dla uczniów, aby uczyć się o różnicach między czatbotami.
{panel end}

Jednym z takich czatbotów jest **Eliza**, która stara się brzmieć jak psychoterapeutka rogeriańska i brzmi najbardziej inteligentnie w tego rodzaju rozmowach, które miałaby miejsce podczas takiej sesji terapeutycznej. ([Psychoterapia rogeriańska](https://pl.wikipedia.org/wiki/Psychoterapia_zorientowana_na_klienta) – jest to technika, która polega na próbie zrozumienia klienta poprzez zadawanie pytań i odzwierciedlania ich wypowiedzi w celu wyjaśnienia, że zostały one zrozumiane). 

{panel type="UWaga" summary="Czatboty i informacje osobiste!"}
Eliza jest systemem, który był przeznaczony do wprowadzenia ludzi w świat SI i nie powinna być używana do prawdziwych sesji terapeutycznych. Nigdy nie powinieneś wprowadzać informacji osobistych, których nie chciałbyś aby inni czytali, do komputera, ponieważ nigdy nie możesz być pewnym, że strona internetowa nie zbiera informacji lub przekazuje je do innych. Tak więc nie chcesz powiedzieć Elizie takich rzeczy, które prawdziwy pacjent powiedziałby na sesji terapeutycznej --- dlatego zmyślaj rzeczy, gdy będziesz rozmawiać z Elizą. Z tego samego powodu nie przekazuj żadnemu czatbotowi żadnych innych informacji osobistych takich jak pełne imię i nazwisko, data urodzenia lub adres.
{panel end}

Idź do linku poniżej i rozpocznij rozmowę z Elizą w języku angielskim, (pamiętając, że została zaprojektowana jako psychoterapeutka rogeriańska więc będzie odpowiadała jak jedna z nich)
[Naciśnij tutaj aby użyć Elizy na stronie nlp-addiction.com](http://nlp-addiction.com/eliza/)

{image filename="eliza-chatbot-screenshot.png" alt="Czatbot Eliza na stronie nlp-addiction.com"}

Myślisz, że Eliza jest tak samo mądra jak człowiek? Czy uwierzyłbyś, że ona była człowiekiem jeśli ktoś by tobie powiedział, że była? 

Prawdopodobnie zgodzisz się, że chociaż Eliza brzmi czasami trochę inteligentnie, to daje ona bardzo niejasne i ogólne odpowiedzi, zapomina o wcześniejszej części rozmowy i czasami mówi rzeczy, które brzmią bardzo dziwnie!. Jako przykład, poniżej zamieszczona jest rozmowa z Elizą:

**Eliza**: Cześć, Jestem Eliza.
**Człowiek**: Cześć, jestem człowiekiem
**Eliza**: Czy wierzysz to, że to normalne być człowiekiem?
**Człowiek**: Tak
**Eliza**: Jesteś pewny?
**Człowiek**: Tak
**Eliza**: Dlaczego powtarzasz się?


Eliza często daje bardzo ogólnikowe odpowiedzi, patrząc na odpowiednie zasady, opierając się tylko na linii tekstu, którą właśnie wpisałeś. To często prowadzi do bardzo dziwnych konwersacji, takich jak ta powyżej! W tym przypadku Eliza użyła dopasowania wzorców do określenia, że może będzie właściwie zapytać „czy wierzysz w to, że to normalne być człowiekiem?”, gdy powiedziałem, że jestem człowiekiem; jeśli bym powiedział „Jestem bananem”, wtedy ta sama reguła wygenerowałaby odpowiedź „Czy wierzysz w to, że to normalne być bananem?”. Gdy odpowiedziałem „Tak”, to właściwie Eliza nie zrozumiała znaczenia mojej wypowiedzi, więc po prostu zapytała mnie czy byłem tego pewny jako, że ma generalną odpowiedź, że gdy ktoś mówi „Tak”, to dobrze jest go zapytać czy na pewno. Eliza ma także reguły, które są wywoływane, gdy ktoś powtarza się i wtedy powinna zapytać się dlaczego. Ponieważ Eliza właściwie nie rozumie znaczeń, ale zamiast tego trzyma się zasad, które mówią co może być właściwymi odpowiedziami. Ona nie może w żaden sposób wiedzieć czy dwukrotna odpowiedź „Tak” była dla mnie naprawdę ważna! To właściwie duża wskazówka, że Eliza nie jest tak naprawdę inteligentna i właściwie nie rozumie kontekstu rozmowy, a także nawet tego czy odpowiedź na jej pytanie jest lub nie jest faktycznie sensowna.

{panel type="teacher-note" summary="Odpowiedzi Elizy"}
Te odpowiedzi, które daje Eliza są nazywane *odpowiedziami predefiniowanymi ang. canned responses*.
{panel end}


Teraz wróć i przeprowadź kolejną konwersację z Elizą. Jest wiele innych przykładów podobnych do konwersacji powyżej, gdy Eliza mówi rzeczy, które nie mają sensu/ Ile możesz takich znaleźć? Dodatkowo, jak Eliza odpowiada, gdy robisz poniższe rzeczy?

- Spróbuj być “papugą”, która tylko powtarza wszystko, co powiedziała Eliza.
- Co się dzieje, gdy nie dajesz znaczących odpowiedzi na jej pytania? 
- Jeśli mówisz te same rzeczy, które powiedziałeś wcześniej, czy Eliza zawsze odpowiada w ten sam sposób? (Gdy powiesz je od razu jeszcze raz po wypowiedzeniu, wtedy prawdopodobnie nie, jako że będzie ona komentowała to, że powtórzyłeś się dwukrotnie!)
- Co się stanie gdy zaczniesz mówić o rzeczach, które są nie związane z tym co mogło być powiedziane na sesji terapeutycznej takich jak - będziesz starał się mieć ogólną konwersację z Elizą (pamiętaj, że Eliza operuje w specjalistycznej dziedzinie to znaczy ona zakłada, że jest terapeutką). 

### Czatbot Alice

Widzieliśmy wyżej, że Eliza jest czatbotem, który pracuje w specjalistycznej dziedzinie (próbuje być terapeutką), I stara się brzmieć inteligentnie poprzez wypisywanie ogólnych odpowiedzi. Jako, że prawdopodobnie to odkryłeś, to szybko ujawnia, że Eliza nie jest w ogóle inteligentna i będzie powtarzała te same rzeczy w kółko. Dodatkowo, prawdopodobnie zauważyłeś, że wypowiedzi Elizy często nie zawierają dużo sensu i ostatecznie kończy się zdaniem które jest bez sensu dla człowieka.

Spróbuj przeprowadzić rozmowę z kolejnym czatbotem --- Alice. Zauważ, że ona nazywa cię "sędzią". Możesz odkryć dlaczego tak jest, gdy przeczytasz część rozdziału o teście Turinga poniżej. 

[Naciśnij tutaj,aby przejść do Alice na stronie pandorabots.com](http://www.pandorabots.com/pandora/talk?botid=f5d922d97e345aa1)

{image filename="alice-chatbot-screenshot.png" alt="Czatbot Alice na stronie pandorabots.com"}

Czy Alice brzmi bardziej inteligentnie od Elizy? Czy brzmi równie inteligentnie jak człowiek lub czy możesz sprawić, że będzie mówiła ona rzeczy bez sensu? Spróbuj użyć tych samych wskazówek, aby oszukać Elizę i zobacz czy działają one na Alice. (spójrz na listę punktów powyżej w paragrafie poświęconym Elizie). 

Zarówno Alice jak i Eliza, używa reguł do tego, aby wiedzieć co napisać, jednakże ma ona ich więcej, a algorytm odpowiedzialny za wybranie tego co powiedzieć jest bardziej wyrafinowany. Jeśli chcesz wiedzieć więcej, po prostu zapytaj Alice jak pracuje a ona tobie powie!

Wybrane możliwe reguły, które może posiadać Alice:
- Jeśli jest wspomniany “ulubiony kolor”, powiedz, że twoim ulubionym kolorem jest „zielony”
- Jeśli wspomniany jest członek rodziny (np. „mama”, „tata” lub „brat”), powiedz coś związanego z rodziną.


Aby użyć reguł, czatbot analizuje twoje ostatnie zdanie (i możliwe, ze również wcześniejsze zdania) poprzez dopasowanie zdania do wzorców, które ma zapisane. Jeśli zdanie pasuje do wzorca w regułach, wtedy dana reguła jest „aktywowana”. Zasada określa odpowiedź. Czasami jest ona po prostu szablonem zdania i czatbot analizuje tekst, który ty wpisałeś i wybiera słowa, które mogą być wpisane szablon. To dlatego czasami odpowiedzi są konstruowane w ten sposób, że używane są części tekstu, które zostały wpisane przez człowieka.

Jakość tych reguł determinuje to, jak inteligentnie czatbot będzie brzmiał.

Podczas gdy Alice jest bez wątpienia bardziej inteligentna od Elizy, nadal ma ograniczenia. Czasami ona sama się do nich przyznaje!

**Sędzia**: Co wydarzy się w roku 2000?
**Alice**: Nie mogę przewidzieć przyszłości.
**Sędzia**: To jest przeszłość
**Alice**: Tak, to jest coś z przeszłości.
**Sędzia**: Więc dlaczego powiedziałaś, że nie możesz przewidzieć przyszłości?
**Alice**: To była wstępnie zaprogramowana odpowiedź, całkowicie zdeterminowana przez twoje stwierdzenie.


Przypuszczam, że byłem trochę złośliwy oszukując ją i mówiąc „co będzie”. Jej zasady nie przewidują, że człowiek może ją w taki sposób oszukać. 

### Czatboty, które uczą się od ludzi

W poprzednich paragrafach widzieliśmy przykłady dwóch czatbotów, które mają reguły pomagające określić im odpowiednią rzecz do powiedzenia. Jeden z nich działa w specjalistycznej dziedzinie, symulując terapeutę i nie jest w stanie prowadzić bardzo ogólnej konwersacji, drugi jest w stanie prowadzić bardziej ogólną rozmowę. Obydwa czatboty mają swoje zasady co powiedzieć, które zostały określone przez programistów w czasie ich programowania. Te zasady nie zmienią się nigdy jeśli programista nie zdecyduje o ich zmianie.

Istnieją innego rodzaju czatboty, które są w stanie uczyć się zasad od ludzi w czasie konwersacji z człowiekiem. Poprzez patrzenie jak człowiek odpowiada na różne rozmowy, czatbot próbuje nauczyć się jak powinien odpowiadać w różnych sytuacjach. Założeniem jest, że jeśli odpowiada w sposób podobny do człowieka, wtedy może będzie brzmiał jak człowiek. Celem większości tych czatbotów jest prowadzenie ogólnej konwersacji, tzn. nie są one ograniczone do jednej dziedziny tak jak terapeutka Eliza.


Jeśli próbujesz symulować ludzką inteligencję, wtedy prawdopodobnie uczenie się od ludzi jest drogą do celu?

{panel type="Ostrzeżenie" summary="Interakcja z czarbotami, które się uczą"}
Proszę zauważyć, że poniższe ćwiczenie wymaga interakcji z jednym z czatbotów, które się uczą. Ponieważ czatbot uczy się od ludzi, wtedy z dość dużym prawdopodobieństwem nauczył się mówić rzeczy, które dla ciebie mogą być bardzo obraźliwe. Podczas gdy staraliśmy się wybrać czatboty, które nie wypowiadają się obraźliwie, nie jest możliwe zagwarantowanie tego, więc bądź dyskretny rozmawiając z nimi; możesz także pominąć ten paragraf i nadal zrozumieć główne założenia tego rozdziału. Ponieważ Eliza i Alice nie uczą się od ludzi, one nigdy nie powiedzą obraźliwych rzeczy, dopóki ty nie zrobisz tego pierwszy!

Przypominamy znowu, nie używaj w konwersacji z czatbotami twoich danych personalnych (takich jak imię i nazwisko, datę urodzenia, adres i żadnej innej informacji, której nie chciał byś nikomu udostępnić). Gdy potrzeba, zmyślaj. Bardzo prawdopodobne, że czatbot, który uczy się od ludzi, przekaże, to co powiedziałeś innym ludziom, żeby brzmieć inteligentnie w stosunku do *nich*.

Te ostrzeżenia będą bardziej sensowne, wtedy gdy nauczysz się jak czatboty działają.
{panel end}

Przykładem czatbota, który uczy się od ludzi jest Cleverbot.

[Kliknij w ten link, aby porozmawiać z Cleverbotem](http://www.cleverbot.com/)

{image filename="cleverbot-chatbot-screenshot.png" alt="Czatbot Cleverbot"}

W przeciwieństwie do Elizy i Alice, których reguły były określone przez programistów, Cleverbot uczy się zasad opierając się na tym co powiedzą ludzie. Na przykład, gdy Cleverbot mówi „cześć” do człowieka, to śledzi wszystkie różne reakcje, które ludzie robią na to stwierdzenie, takie jak "hej", "hello!", "siema", "co tam?" (angielskie "hi", "hello!", "hey ya", "sup!"). Zasada mówi, że jeśli ktoś powie cześć do ciebie, to wtedy rzeczy które na ogół mówią w odpowiedzi do Cleverbota na „hej” są właściwymi rzeczami na odpowiedzenie na "hej". Z kolei gdy Cleberbot mówi coś w rodzaju "co tam?" lub "hello!", to wtedy będzie przyglądał się temu jak ludzie odpowiadają na to, aby nauczyć się właściwej odpowiedzi na te wypowiedzi. I wtedy będzie się uczyć odpowiedzi na te odpowiedzi. To pozwala zbudować Celverbotowi coraz większą bazę danych odpowiedzi.

{comment}
Być może musimy dołączyć wykres, który pokazuje proces uczenia się, tak aby uczniowie, którzy preferują wykresy, a nie tekst, mieli szansę zrozumienia tego. To jest poniekąd rekurencyjne i jest to trochę mylące!
{comment end}

Wynikiem uczenia się od ludzi jest to, że Cleverbot przyjmuje założenie, że ludzie są rzeczywiście inteligentni i będą nauczali go mówienia inteligentnych rzeczy.Jeśli na przykład człowiek powie Cleverbotowi coś jak „szkoła jest nudna” w odpowiedzi na „hej”, Cleverbot może nauczyć się, że gdy osoba powie „hej”, to właściwą odpowiedzią Clverbota jest "Szkoła jest nudna"!

{panel type="Ciekawostka" summary="Krótki film napisany przez Cleverbota"}

Sprawdź krótki film ["Do You Love Me"](https://www.youtube.com/watch?v=QkNA7sy5M5s) (około 3 mins), tktóry jest rezultatem współpracy Chrisa R Wilsona z Cleverbotem, aby napisać scenariusz filmowy

{panel end}

### Jeszcze więcej czatbotów!

Istnieje o wiele więcej czatbotów, z którymi możesz rozmawiać. Możesz zajrzeć na [listę na Wikipedii](https://en.wikipedia.org/wiki/List_of_chatterbots), lub wyszukać je w Internecie za pomocą wyszukiwarki. Każdy czatbot na liście ma swoją stronę na Wikipedii. Powinieneś być w stanie znaleźć czatboty poprzez wyszukiwarkę lub spoglądając na odnośniki na stronach Wikipedii. Część z tych czatbotów będzie miała reguły zdefiniowane przez programistów, część będzie miała reguły, kótre powstały poprzez uczenie się od ludzi.

Jeśli masz urządzenie z systemem Apple iOS (np. iPhone), spójrz na czatbota  [Siri](https://pl.wikipedia.org/wiki/Siri), który znajduje się w systemie pomocy urządzenia. Siri jest przykładem czatbota, którego zadaniem jest *pomoc* człowiekowi, w przeciwieństwie do większości czatbotów, których celem jest po prostu rozrywka internetowa. Siri ma również rozpoznawanie głosu, dlatego możesz do niej mówić, a nie tylko pisać.

### Test Turinga

W paragrafach powyżej zaznajomiłeś się z niektórymi czatbotami i (mam nadzieję!), że wyciągnąłeś wniosek, że nie są one całkowicie przekonujące, że brzmią jak człowiek (choć niektóre są lepsze od innych!). Ale może wkrótce, pojawią się nowe czatboty, które nie będą miały tych samych ograniczeń. Czy powinniśmy uważać je za inteligentne? W jaki sposób moglibyśmy to stwierdzić? Czy istnieje formalny sposób, w jaki możemy ustalić, czy czatbot jest na poziomie ludzkiej inteligencji?

Bardzo znany informatyk, Alan Turing, odpowiedział na to pytanie w 1950 roku, zanim istniał pierwszy czatbot! Alan Turing miał niezwykłą wizję przyszłości i wiedział, że wymyślenie inteligentnych komputerów stałoby się wielką rzeczą i że potrzebowalibyśmy sposobu, aby dowiedzieć się, kiedy udało nam się stworzyć naprawdę inteligentny komputer.

Myślał o tym, jak można byłoby zdefiniować inteligencję (określenie inteligencji jest zaskakująco trudne!) i stwierdził, że jednym ze sposobów byłoby powiedzenie, że człowiek jest inteligentny i że jeśli komputer jest w stanie przekonująco komunikować się jak człowiek, to musi być także inteligentny. Definicja ta nie obejmuje całej inteligencji, ponieważ uwzględnia jedynie to, co osoba lub komputer mówi i ignoruje inne elementy inteligencji, takie jak określenie najlepszego sposobu na przejście przez budynek (lub labirynt) lub zdecydowanie, jak działać w konkretnej sytuacji (na przykład na imprezie towarzyskiej, przy podejmowaniu decyzji o tym, jaką kolejną rzecz zrobić w pracy lub gdy ktoś się zgubi). Jednakże, komunikacja jest jednak nadal bardzo istotnym elementem ludzkiej inteligencji.

Aby sprawdzić, czy program komputerowy może lub nie może komunikować się jak człowiek, Turing zaproponował test. Oprócz programu komputerowego do przeprowadzenia testu wymagane są dwie osoby. Jedna z osób działa jako "przesłuchujący", a druga jako "człowiek", do porównania z programem komputerowym. Przesłuchującego umieszcza się w oddzielnym pomieszczeniu niż komputer z programem komputerowym i "człowiek". Przesłuchujący rozmawia zarówno z człowiekiem, jak i z programem komputerowym, ale nie wie z kim rozmawia w danej chwili. Rozmowy przeprowadzane są na zasadzie podobnej do komunikatora tekstowego, dzięki czemu program komputerowy nie potrzebuje komunikować się głosowo. Podczas rozmów człowiek musi przekonać śledczego, że rzeczywiście jest człowiekiem, a program komputerowy musi przekonać śledczego, że on jest rzeczywiście człowiekiem. Po zakończeniu rozmów przesłuchujący musi powiedzieć, który z rozmówców był komputerem, a który człowiekiem. Jeśli nie jest w stanie tego wiarygodnie stwierdzić, oznacza to, że komputer przeszedł pomyślnie test.

Test zaproponowany przez Turinga stał się w końcu sławny i otrzymał nazwę "Testu Turinga". Jedną z motywacji do tworzenia czatbotów jest próba stworzenia takiego, który zda test Turinga. Niestety nie został jeszcze stworzony czatbot, który zdałby test Turinga, a kwestią otwartą w informatyce jest to czy jest to w ogóle możliwe, podobnie jak inne pytania o sztuczną inteligencję, które napotkasz dalej w tym rozdziale. 

Istnieją również inne formy testu Turinga. Gry akcji mają czasami postać sterowaną komputerowo, która walczy z twoją postacią, zamiast drugiej, kontrolowanej przez człowieka postaci. Odmianę testu Turinga można wykorzystać do określenia tego, czy komputerowo kontrolowany gracz wydaje się posiadać (lub nie) ludzką inteligencję, pobierając przesłuchującego, aby grał zarówno przeciwko postaci komputerowej, jak i ludzkiej, i aby sprawdzić, czy potrafi odróżnić je od siebie.

W rzeczywistości wiele części ludzkiej inteligencji mogłoby zostać przetestowanych przed odmianę testu Turinga. Jeśli chciałbyś mieć komputerowego szachistę, który wyglądałby jak człowiek, a nie komputer (niektórzy ludzie woleliby grać przeciwko człowiekowi, a nie komputerowi), możesz również użyć do tego testu Turinga! Jakie inne możliwe testy Turinga możesz wymyślić?

{panel type="Ciekawostka" summary="Prawdziwy test Turinga"}
Alan Turing zaczął od zaproponowania prostej gry towarzyskiej wymagającej trzech graczy, w której pierwszym graczem była kobieta, drugim graczem był mężczyzną, a trzecim graczem mógł być zarówno mężczyzna jak i kobieta i przejmował on rolę „przesłuchującego”. Przesłuchujący znajdował się w innym pokoju niż pozostała dwójka graczy i mógł komunikować się z nimi tylko przekazując notatki (np. przez przekazywanie notatek  pod drzwiami. Mężczyzna musiał spróbować przekonać  przesłuchującego, że jest tak naprawdę kobietą, a kobieta że jest kobietą.  Na koniec śledczy musiał powiedzieć, kto był mężczyzną, a kto kobietą i jeśli śledczy odgadł niepoprawnie, to mężczyzna "wygrywał".
{panel end}

{panel type="projekt" summary="RUruchom swój własny test Turinga na czatbocie"}

Ten paragraf wymaga przeprowadzenia testu Turinga. Przeczytaj całą tę część uważnie (i poprzedni paragraf, jeśli jeszcze tego nie zrobiłeś) przed rozpoczęciem, i upewnij się, że rozumiesz wszystko przed rozpoczęciem.

Na przedmiotach przyrodniczych, takich jak biologia, fizyka i chemia, często wykonuje się eksperymenty. Jeśli masz takie zajęcia, prawdopodobnie będziesz wiedział, że jeśli eksperyment nie zostanie przeprowadzony prawidłowo (np. w chemii niektórzy uczniowie są kuszeni tym, aby umieścić więcej substancji chemicznej niż mówi polecenie, lub gdy koordynacja jest ważna to łatwo można się pomylić), wtedy wyniki niekoniecznie będą tymi, których szukacie, a wasz eksperyment jest w zasadzie bezsensowny i bezcelowy. Musisz również uważać, aby inne czynniki nie wpływały na wyniki np. kontrolowanie temperatury i wilgotności w eksperymentach biologicznych, które obejmują rosnące mikroorganizmy.

Przeprowadzenie testu Turinga jest przeprowadzeniem eksperymentu, tak jak przeprowadzanie eksperymentów na lekcjach chemii. Podobnie jak w przypadku eksperymentów chemicznych, przeprowadzanie testu Turinga wymaga zachowania ostrożności przy prawidłowym wykonywaniu poleceń i kontrolowania czynników, które mogą potencjalnie wpływać na wyniki, ale nie są częścią tego, co jest sprawdzane. Powinieneś o tym pamiętać podczas realizacji tego projektu.

Np. większość czatbotów komunikuje się w formie tekstowej, a nie słownej. Komunikacja w formie ustnej polega nie tylko na wybieraniu brzmiąco inteligentnych rzeczy do powiedzenia, ale także wymaga przekonującego głosu i prawidłowego wymawiania słów. Ton głosu lub akcent mógłby potencjalnie sprawić, że dla przesłuchującego będzie bardzo oczywiste, która rozmowa byłą z człowiekiem, a która z komputerem, bez konieczności nawet rozważania, co zostało powiedziane w rozmowie. To nie jest to, co test Turinga ma sprawdzać! Dlatego w teście Turinga komputer i człowiek będą komunikować się w formie pisemnej z przesłuchującym. 

Innym przykładem, który mógłby mieć wpływ na wynik testu, może być szybkość reakcji. Komputer prawdopodobnie będzie w stanie odpowiedzieć natychmiast, podczas gdy człowiek będzie potrzebował czasu na przemyślenie, a następnie napisanie odpowiedzi. Aby uniemożliwić przesłuchującemu podejmowanie decyzji w oparciu o szybkość, a nie treść, szybkość reakcji również musi być kontrolowana. Sposób przeprowadzania testu Turinga opisany poniżej próbuje kontrolować te dodatkowe czynniki.

Wybierz czatbota z listy na Wikipedii (zobacz powyższy paragraf of czatbotach) lub ewentualnie użyj Alice lub Cleverbota (Eliza nie jest do tego zalecana). Przyjmiesz rolę śledczego, ale będziesz potrzebował innej osoby, aby działała jako "człowiek". W tym celu zaleca się wybrać osobę w klasie, której nie znasz zbyt dobrze. Nie wybieraj swojego najlepszego przyjaciela z klasy, ponieważ zbyt dobrze poznasz odpowiedzi na pytania, więc będziesz w stanie odróżnić go od czatbota w oparciu o jego osobowość, a nie o jakość czatbota.

Oprócz chatterbota i twojego kolegi z klasy, który będzie działał jako człowiek, będziesz potrzebować dostępu do klasy z komputerem z Internetem (może to być po prostu sala komputerowa), innego pokoju na zewnątrz (korytarz będzie dobry), kawałków papier, 2 długopisów oraz monetę lub kostkę.

Czatbot powinien zostać uruchomiony na komputerze, a twój kolega z klasy powinien znajdować się w tym samym pokoju z komputerem. Ty powinieneś być poza tym pokojem. Jako śledczy będziesz najpierw rozmawiał albo z kolegą z klasy albo z komputerem, a następnie z drugim. Nie powinieneś wiedzieć, w jakiej kolejności będziesz z nimi rozmawiał; aby ustalić, z kim rozmawiasz jako pierwszym, twój kolega z klasy powinien użyć kostki lub monety, aby losowo o tym zdecydować (i nie powinien o tym tobie mówić).

Aby przeprowadzić rozmowy, zacznij od napisania czegoś na górze kartki, na przykład "cześć", "hej" lub "jak się masz?". Umieść znak obok linijki, aby było jasne, że linijka została napisana przez CIEBIE. Podaj kartkę papieru do pokoju, w którym znajduje się twój kolega z klasy i komputer (jeśli możesz, wsuń ją pod drzwi), gdzie twój kolega napisze na niej odpowiedź i przekaże ci ją. Powinieneś wtedy napisać odpowiedź i powtórzyć proces. Każda rozmowa powinna znajdować się na oddzielnym arkuszu papieru i mieć długość od 20 do 40 linijek (co oznacza, że każda osoba / komputer powinna napisać około 10 - 20 linijek w każdej rozmowie). Umieść znak obok każdej linii, którą piszesz, aby było jasne kto napisał które linie.

Jeśli teraz to twój kolega rozmawia z tobą (a nie czatbot), to napisze odpowiedź na podstawie tego, co by powiedział.

Jeśli teraz to czatbot rozmawia z tobą, twój kolega powinien napisać czatbotowi to co powiedziałeś i następnie napisać odpowiedź czatbota na kartce papieru. Przed wysłaniem wypowiedzi do czatbota, powinien sprawdzić czy na pewno wpisał ją poprawnie.

Problem polega na tym, że rozmowa pomiędzy tobą a czatbotem potrwa dłużej niż między tobą a kolegą, ponieważ twój kolega musi wpisywać to, co mówisz do czatbota. Nie chciałbyś, żeby stało się oczywiste, która rozmowa była z  komputrem a która z człowiekiem z tego powodu! Aby poradzić sobie z tym, możesz celowo opóźniać każdą odpowiedź, tak aby każda z nich trwała dokładnie jedną minutę 

Możesz zapytać o co chcesz, chociaż pamiętaj o tym, aby przyjąć założenie, że nie znasz swojego kolegi, więc nie odwołuj się do tego co obydwoje wiedzie, co się stało w przeszłości w klasie lub w weekend, gdy pytasz kolegę lub czatbota. Byłoby to niesprawiedliwe dla czatbota, ponieważ nie może wiedzieć o tych rzeczach. Pamiętaj, że oceniasz czatbota pod kątem jego zdolności do pokazania ludzkiej inteligencji, a nie tego, czego nie wie.

Dobrymi tematami rozmowy będą ulubione kolory, gry, jedzenie, pogoda i takie tematów rozmów, które mógłbyś mieć z osobą, której nie znasz, ale rozmawiasz z nią w pracy, w supermarkecie lub na imprezie. Wymyślenie dobrych rzeczy do zapytania jest trudne, ale zadaj sobie pytanie, czy coś będzie wymagało wiedzy o wydarzeniu, którą nie wszyscy mogliby mieć.

Po zakończeniu obydwóch rozmów, ty jako przesłuchujący musisz powiedzieć, która rozmowa była z kolegą, a która z czatbotem. Twój kolega powinien powiedzieć ci czy zgadłeś.

Oto kilka pytań, które możesz rozważyć po zakończeniu testu Turinga:
- W jaki sposób byłeś w stanie powiedzieć kto był czatbotem, a kto twoim kolegą?
- Czy pojawiły się pytania, które zadałeś, które były „nieuczciwe” – takie które zależały od wiedzy, którą ma twój kolega, ale nie kto inny już mógł jej nie mieć(komputer czy osoba)
- Co zdradziło tajemnicę: treść odpowiedzi lub sposób, w jaki treść została wyrażona?


{panel end}

{image filename="turing-test-dating-show.png" alt="Randkowy test Turinga"}

## Całość tematu!

Do tej pory w tym rozdziale rozmawialiśmy jedynie o jednym zastosowaniu SI. SI zawiera o wiele więcej ekscytujących zastosowań, takich jak komputery, które mogą grać w grach planszowych przeciwko ludziom, komputery, które się uczą, komputery, które są w stanie kontrolować roboty, które autonomicznie eksplorują środowisko, które jest zbyt niebezpieczne aby weszli tam ludzie.

W końcu kolejne paragrafy z innymi tematami z SI będą oddane do tego rozdziału.

## Dalsza lektura

- [Artificial Intelligence Strong and Weak - I Programmer](http://www.i-programmer.info/babbages-bag/297-artificial-intelligence.html)
- [The Paradox of Artificial Intelligence - I Programmer](http://www.i-programmer.info/programming/artificial-intelligence/2437-the-paradox-of-artificial-intelligence.html)

### Użyteczne linki

- [CS Unplugged - Programming Languages - Harold the Robot](http://csunplugged.org/harold-the-robot-2/)- związany z tym dlaczego AI jest taka trudna
- [CS Unplugged - The Turing Test - Conversations with Computers](http://csunplugged.org/the-turing-test/)
- [Wikipedia- Outline of Artificial Intelligence](https://en.wikipedia.org/wiki/Outline_of_artificial_intelligence)
- [Wikipedia - Turing Test](https://en.wikipedia.org/wiki/Turing_test)
- [Wikipedia - Machine Learning](https://en.wikipedia.org/wiki/Machine_learning)
- [CS 4 FUN - Meet the Chatterbots](http://www.cs4fn.org/ai/meetthechatterbots.php)
- [CS 4 FUN - The Illusion of Intelligence](http://www.cs4fn.org/ai/illusionintelligence.php)
- [Alice Bot](http://www.alicebot.org/)
- [IEEE Spectrum](http://spectrum.ieee.org/robotics/artificial-intelligence)
- [TED Conversations matching Artificial Intelligence](https://www.ted.com/topics/ai)
