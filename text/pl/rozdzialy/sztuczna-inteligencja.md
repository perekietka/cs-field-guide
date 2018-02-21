# Sztuczna inteligencja

{video url="https://www.youtube.com/watch?v=ia-oYtacJHE"}

## Z lotu ptaka

Myśląc o sztucznej inteligencji, prawdopodobnie myślisz o przyjaznych systemach, które mogą z tobą rozmawiać i rozwiązywać trudne problemy albo o maniakalnych robotach, które są skłonne do dominacji nad światem. Naukowcy obiecują nam autonomiczne samochody, które będą bezpieczniejsze niż człowiek prowadzący auto. Możemy także usłyszeć o obawach o systemy wspomagania medycznego, które utrzymują życie ludzi w wirtualnych rękach. Sztuczna inteligencja jest obiecująco rozwiajającą się gałęzią informatyki, ale też stwarza wiele obaw. Może być używana do podejmowania decyzji w systemach tak dużych jak samolot czy [automatyczna wywrotka](http://www.komatsu.com/CompanyInfo/profile/product_supports/), jak i małych, takich jak telefony komórkowe, które potrafią prezycyjnie przewidzieć wpisywany tekst. Ich wspólną cechą jest to, że próbują naśladować ludzką inteligencję. I co ważne, takie systemy mogą być znaczącym ułatwieniem w życiu codziennym.

Sztuczna inteligencja (w skrócie SI lub po angielsku AI) znana także jako inteligentne systemy, jest przede wszystkim nauką informatyczną, ale czerpie wiele pomysłów z innych dziedzin, w szczególności z [matematyki](https://pl.wikipedia.org/wiki/Matematyka) (głównie logiki, kombinatoryki, statystyki, prawdopodobieństwa i teorii optymalizacji), [biologii](https://pl.wikipedia.org/wiki/Biologia), [psychologii](https://pl.wikipedia.org/wiki/Psychologia), [językoznawstwa](https://pl.wikipedia.org/wiki/Lingwistyka), [neurobiologii](https://pl.wikipedia.org/wiki/Neurobiologia) i [filozofii](https://pl.wikipedia.org/wiki/Filozofia).

W tym rozdziale omówimy kilka inteligentnych systemów. Wiąże się to nieuchronnie z rozpatrzeniem również aspektów etycznych i filozoficznych — Czy naprawdę chcemy, aby maszyny przejmowany niektóre z naszych zawodów? Czy możemy im ufać? Czy pewnego dnia nie przekroczymy bariery i nie zrobimy jednego kroku za daleko? Co tak naprawdę rozumiemy przez powiedzenie, że komputer jest inteligentny? Nie odpowiemy na te pytania bezpośrednio w tym rozdziale. Jednakże zdobycie wiedzy technicznej na temat SI pozwoli ci podejmować bardziej świadome decyzje dotyczące bardziej skomplikowanych problemów.

## Czatboty i test Turinga

{image filename="computer-studying-turing-test.png" alt="Komputer czyta książkę pod tytułem „Rozmawiać jak człowiek”"}

Dla wielu ludzi jest oczywiste, że mogą łatwo rozmawiać z drugą osobą i wypowiedzieć własne zdanie o tej rozmowie. Zdolność do tego jest formą inteligencji. Dla komputerów nie jest to takie proste! Podjęto wiele prób zaprojektowania programów komputerowych, które mogą prowadzić rozmowę z człowiekiem i brzmieć inteligetnie. Te programy komputerowe nazywane są *czatbotami* (ang. *chatbot*, *chatterbot*) albo *linguabotami*.

Czatboty możesz spotkać w internecie w takich sytuacjach jak np. udzielanie pomocy na stronie rezerwacji biletu. 
Czasami nawet trudno stwierdzić, czy otrzymujesz automatyczną odpowiedź, czy rozmawiasz online z konsultantem. 
Zaczniemy od spojrzenia na kilka bardzo prostych czatbotów, które zostały zaprojektowane raczej jako eksperyment niż do oferowania poważnej pomocy.

### Terapeutyczna sesja z Elizą

{panel type="teacher-note" summary="Czatboty na lekcji"}
Jeśli ten materiał jest używany w klasie i czas jest ograniczony, upewnij się, że uczniowie nie spędzają za dużo czasu, rozmawiając z każdym z czatbotów. 15 minut to maksymalny czas na rozmowę z każdym czatbotem — Elizą, Mitsuku i Cleverbotem (w sumie 45 minut) oraz dodatkowe 15 — 45 minut (w zależności od ograniczeń czasowych) dla uczniów na poszukanie innych czatbotów.
{panel end}

Jednym z takich czatbotów jest **Eliza**, która stara się naśladować psychoterapeutkę rogeriańską i brzmi najbardziej inteligentnie w rozmowach, które miałyby miejsce podczas sesji terapeutycznej. ([Psychoterapia rogeriańska](https://pl.wikipedia.org/wiki/Psychoterapia_zorientowana_na_klienta) – jest to technika, która polega na próbie zrozumienia pacjenta poprzez zadawanie pytań i przetwarzaniu fragmentów jego wypowiedzi w celu upewnienia go, że zostały one poprawnie zrozumiane). 

{panel type="caution" summary="Czatboty i informacje osobiste!"}
Eliza jest systemem, który został stworzony, aby pokazać ludziom świat SI i nie powinna być używana do prawdziwych sesji terapeutycznych. Nigdy nie powinieneś podawać osobistych informacji komputerowi, tzn. takich, które nie chciałbyś, aby inni przeczytali. Nigdy nie możesz być pewien, że strona internetowa nie zbiera informacji i nie przekazuje ich dalej. Nie pisz Elizie takich rzeczy, które prawdziwy pacjent powiedziałby na sesji terapeutycznej — w czasie rozmowy z nią zmyślaj. Z tego samego powodu nie przekazuj żadnemu czatbotowi żadnych innych osobistych informacji, w szczególności imienia i nazwiska, daty urodzenia lub adresu.
{panel end}

Kliknij na poniższy link i rozpocznij rozmowę z Elizą w języku angielskim, (pamiętając, że została zaprojektowana jako psychoterapeutka rogeriańska, więc będzie odpowiadała w tym stylu).
[Naciśnij tutaj, aby porozmawiać z  Elizą na stronie nlp-addiction.com](http://nlp-addiction.com/eliza/)

{image filename="eliza-chatbot-screenshot.png" alt="Czatbot Eliza na stronie nlp-addiction.com"}

Myślisz, że Eliza jest tak samo mądra jak człowiek? Czy uwierzyłbyś, że Eliza jest człowiekiem, jeśli ktoś inny by ci tak powiedział?? 

Prawdopodobnie zgodzisz się, że chociaż Eliza brzmi czasami trochę inteligentnie, to zadaje ona bardzo niejasne i ogólnikowe pytania. Zapomina o wcześniejszej części rozmowy i czasami mówi rzeczy, które brzmią bardzo dziwnie! Jako przykład przeanalizuj poniższą rozmowę:


**Eliza**: Cześć, Jestem Eliza.
**Człowiek**: Cześć, jestem człowiekiem.
**Eliza**: Czy wierzysz to, że to normalne być człowiekiem?
**Człowiek**: Tak.
**Eliza**: Jesteś pewny?
**Człowiek**: Tak.
**Eliza**: Dlaczego powtarzasz się?


Wypowiedzi Elizy są bardzo ogólnikowe. Korzysta z wbudowanych wzorów wypowiedzi lub opiera się tylko na ostatniej wpisanej przez ciebie linijce tekstu. Prowadzi to często do bardzo dziwnych konwersacji, takich jak ta powyżej! W tym przypadku, gdy powiedziałem, że jestem człowiekiem, wtedy Eliza użyła dopasowania wzorców do słów kluczowych i zapytała „Czy wierzysz w to, że to normalne być człowiekiem?”. Jeśli powiedziałbym „Jestem bananem”, wtedy ta sama reguła wygenerowałaby pytanie „Czy wierzysz w to, że to normalne być bananem?”. Gdy odpowiedziałem „Tak”, to właściwie Eliza nie zrozumiała znaczenia mojej wypowiedzi, więc po prostu zapytała mnie, czy byłem tego pewny. Ma ona generalną zasadę, że gdy ktoś mówi „Tak”, to dobrze jest go zapytać czy na pewno. Eliza ma także wzorce, które są wywoływane, gdy ktoś powtarza się. Eliza tak naprawdę nie rozumie tego, co do niej piszesz (znaczenia tekstu), zamiast tego trzyma się reguł, które podpowiadają, co może być właściwą odpowiedzią. W żaden sposób nie jest w stanie stwierdzić, że dwukrotna odpowiedź „Tak” była dla mnie naprawdę ważna! To właściwie duża wskazówka, że Eliza nie jest tak naprawdę inteligentna i nie rozumie kontekstu rozmowy, a nawet tego, czy odpowiedź na jej pytanie jest lub nie jest sensowna.

{panel type="teacher-note" summary="Odpowiedzi Elizy"}
Te odpowiedzi, które daje Eliza, są nazywane *odpowiedziami predefiniowanymi* (ang. canned responses).
{panel end}


Teraz przeprowadź kolejną konwersację z Elizą. Jest wiele innych przykładów podobnych do konwersacji powyżej, pokazujących, że Eliza mówi bez sensu. Ile możesz znaleźć takich przykładów? Sprawdź, jak Eliza odpowiada, gdy używasz takich strategii rozmowy:

- Spróbuj być „papugą”, która tylko powtarza wszystko, co powiedziała Eliza.
- Co się dzieje, gdy nie dajesz sensownych odpowiedzi na jej pytania? 
- Jeśli mówisz te same rzeczy, które powiedziałeś wcześniej, czy Eliza zawsze reaguje w ten sam sposób?
- Co się stanie, gdy zaczniesz mówić o rzeczach, które nie pojawiłyby się raczej na sesji terapeutycznej -- będziesz starał się rozmawiać z Elizą na ogólne tematy (pamiętaj, że Eliza operuje w specjalistycznej dziedzinie, to znaczy ona zakłada, że jest terapeutką)?

### Czatbot Mitsuku

Jak już wspomnieliśmy, Eliza jest czatbotem, który pracuje w specjalistycznej dziedzinie (próbuje być terapeutką). Stara się brzmieć inteligentnie poprzez zadawanie ogólnikowych pytań. Dzięki temu szybko zapewne odkryłeś, że Eliza nie jest w ogóle inteligentna i będzie powtarzała te same rzeczy w kółko.

Spróbuj przeprowadzić rozmowę z kolejnym czatbotem — Mitsuku.

Pierwowzorem czabota Mitsuku była [ALICE] (https://pl.wikipedia.org/wiki/ALICE_(sztuczna_inteligencja)). Mitsuku zawiera całą bazę wiedzy AIML czatbota Alice (w angielskiej wersji przewodnika autorzy proponują rozmowę z Alice, lecz podany odnośnik jest nieaktualny [przyp. tłum.]).

[Naciśnij tutaj, aby przejść do Mitsuku na stronie pandorabots.com](https://pandorabots.com/mitsuku/)

Czy Mitsuku brzmi bardziej inteligentnie od Elizy? Czy brzmi równie inteligentnie jak człowiek lub czy możesz sprawić, że będzie mówiła bezsensowne rzeczy? Spróbuj użyć tych samych wskazówek, których używałeś w przypadku Elizy i zobacz, czy działają one na Mitsuku (spójrz na listę punktów w podrozdziale poświęconym Elizie). 

Mitsuku oraz Eliza używają reguł do budowania swoich wypowiedzi, jednakże Mitsuku ma ich więcej. Algorytm odpowiedzialny za wybranie tego co powiedzieć, jest w tym przypadku bardziej wyrafinowany. Jeśli chcesz się dowiedzieć, jak skonsturowana jest Mitsuku, po prostu ją zapytaj, a ona da ci odpowiedź!

Poniżej zamieszczamy możliwe reguły stosowane przez Mitsuku:
- Jeśli jest wspomniany “ulubiony kolor”, powiedz „niebieski”
- Jeśli wspomniany jest członek rodziny (np. „mama”, „tata” lub „brat”), powiedz coś związanego z rodziną.

Aby użyć reguł, czatbot analizuje twoje ostatnie zdanie (i możliwe, że również wcześniejsze zdania) poprzez dopasowanie zdania do wzorców, które ma zapisane. Jeśli zdanie pasuje do wzorca w regułach, wtedy dana reguła jest „aktywowana”. Reguła określa odpowiedź. Czasami jest ona po prostu szablonem zdania i czatbot analizuje tekst, który wpisałeś i wybiera słowa, które mogą być wpisane w szablon. To dlatego czasami odpowiedzi są konstruowane w ten sposób, że używane są części tekstu wpisanego przez człowieka..

Jakość tych reguł determinuje to, jak inteligentnie czatbot będzie brzmiał.

Mitsuku jest bez wątpienia bardziej inteligentna od Elizy, jednak nadal ma ograniczenia. Czasami sama się do nich przyznaje!!

**Człowiek**: Co wydarzy się w roku 2000?
**Mitsuku**: Nie mogę przewidzieć przyszłości.
**Człowiek**: To jest przeszłość.
**Mitsuku**: Tak, to jest coś z przeszłości.
**Człowiek**: Więc dlaczego powiedziałaś, że nie możesz przewidzieć przyszłości?
**Mitsuku**: To była wstępnie zaprogramowana odpowiedź, całkowicie zdeterminowana przez twoje stwierdzenie.


Człowiek w tej rozmowie musiał być trochę złośliwy, oszukując ją i mówiąc „co wydarzy się”. Jej zasady nie przewidują, że człowiek może ją w taki sposób traktować. 

### Uczące się czatboty

W poprzednich podrozdziałach widzieliśmy przykłady dwóch czatbotów, które mają reguły pomagające konstruować wypowiedzi. Jeden z nich działa w specjalistycznej dziedzinie, symulując terapeutę i nie jest w stanie prowadzić bardzo ogólnej konwersacji. Drugi jest w stanie prowadzić bardziej ogólną rozmowę. Obydwa czatboty mają swoje reguły, które zostały wbudowane w nie przez ich twórców. Te zasady mogą się zmienić tylko wtedy, gdy ich twórca o tym zdecyduje i zaktualizuje oprogramowanie czatbota.

Istnieją innego rodzaju czatboty, które są w stanie uczyć się zasad od ludzi w czasie konwersacji. Poprzez analizowanie tego, co pisze człowiek, czatbot próbuje nauczyć się, jak powinien odpowiadać w różnych sytuacjach. Założeniem jest, że jeśli odpowiada w sposób podobny do człowieka, wtedy może będzie brzmiał jak człowiek. Celem większości tych czatbotów jest prowadzenie ogólnej konwersacji, tzn. nie są one ograniczone do jednej dziedziny, tak jak terapeutka Eliza.

Twórcy uczących się czatbotów przyjęli zasadę, że gdy próbujesz symulować ludzką inteligencję, wtedy prawdopodobnie uczenie się od ludzi jest drogą do celu.

{panel type="caution" summary="Interakcja z czarbotami, które się uczą"}
Poniższe ćwiczenie wymaga interakcji z jednym z czatbotów, które się uczą. Ponieważ czatbot uczy się od ludzi, z dość dużym prawdopodobieństwem nauczył się mówić rzeczy, które dla ciebie mogą być bardzo obraźliwe. Mimo, że staraliśmy się wybrać czatboty, które nie wypowiadają się obraźliwie, nie możemy zagwarantować, że nie usłyszysz czegoś niepożądanego; zachowaj zatem dystans do tego, co się wydarzy. Możesz także pominąć to ćwiczenie i nadal zrozumieć główne założenia tego rozdziału. Ponieważ Eliza i Mitsuku nie uczą się od ludzi, nigdy nie powiedzą obraźliwych rzeczy, dopóki ty nie zrobisz tego pierwszy!

Przypominamy znowu, nie używaj w konwersacji z czatbotami twoich danych personalnych (takich jak imię i nazwisko, data urodzenia, adres i żadnej innej informacji, której nie chciałbyś nikomu udostępnić). Gdy potrzeba, zmyślaj. Bardzo prawdopodobne, że czatbot, który uczy się od ludzi, przekaże, to co powiedziałeś, innym ludziom, żeby brzmieć inteligentnie w stosunku do *nich*.

Te ostrzeżenia będą bardziej sensowne, wtedy gdy nauczysz się, jak działają czatboty.
{panel end}

Przykładem czatbota, który uczy się od ludzi jest Cleverbot.

[Kliknij w ten link, aby porozmawiać z Cleverbotem](http://www.cleverbot.com/) (po angielsku).

{image filename="cleverbot-chatbot-screenshot.png" alt="Czatbot Cleverbot"}

W przeciwieństwie do Elizy i Mitsuku, których reguły były określone przez programistów, Cleverbot uczy się zasad, opierając się na tym, co powiedzą ludzie. Na przykład, gdy Cleverbot mówi „cześć” do człowieka, to śledzi wszystkie reakcje, takie jak „hej”, „hello!”, „siema”, „co tam?” (angielskie „hi”, „hello!”, „hey ya”, „sup!”). Zasada działa w ten sposób: gdy ktoś powie „cześć" do Cleverbota, to Cleverbot powie to, co na ogół ludzie mówili w odpowiedzi do Cleverbota na „cześć”. Z kolei gdy Cleberbot mówi coś w rodzaju „co tam?” lub „hello!”, to wtedy będzie przyglądał się temu, jak ludzie odpowiadają na to i w ten sposób uczy się właściwej odpowiedzi. To pozwala zbudować Celverbotowi coraz większą bazę danych odpowiedzi.

{comment}
Być może musimy dołączyć wykres, który pokazuje proces uczenia się, tak aby uczniowie, którzy preferują wykresy, a nie tekst, mieli szansę zrozumienia tego. To jest poniekąd rekurencyjne i jest to trochę mylące!
{comment end}

Fundamentem dla Cleverbota jest założenie, że ludzie są rzeczywiście inteligentni i będą uczyli go mówienia inteligentnych rzeczy. Jeśli na przykład człowiek powie Cleverbotowi coś jak „szkoła jest nudna” w odpowiedzi na „hej”, Cleverbot może nauczyć się, że gdy osoba powie „hej”, to właściwą odpowiedzią Clverbota jest „Szkoła jest nudna”!

{panel type="curiosity" summary="Krótki film stworzony przez Cleverbota"}

Obejrzyj krótki film ["Do You Love Me"](https://www.youtube.com/watch?v=QkNA7sy5M5s) (około 3 min), którego scenariusz napisał Cleverbot wraz z Chrisem R. Wilsonem.

{panel end}

### Jeszcze więcej czatbotów!

Istnieje wiele czatbotów, z którymi możesz rozmawiać. Możesz zajrzeć na [listę w angielskiej Wikipedii](https://en.wikipedia.org/wiki/List_of_chatterbots) lub wyszukać je w Internecie za pomocą wyszukiwarki. Każdy czatbot na liście ma swoją stronę na Wikipedii. Część z tych czatbotów będzie miała reguły zdefiniowane przez programistów, część będzie miała reguły, które powstały poprzez uczenie się od ludzi.

Jeśli masz urządzenie z systemem Apple iOS (np. iPhone), spójrz na czatbota [Siri](https://pl.wikipedia.org/wiki/Siri), który znajduje się w systemie pomocy urządzenia. Siri jest przykładem czatbota, którego zadaniem jest *pomoc* człowiekowi, w przeciwieństwie do większości czatbotów, których celem jest po prostu rozrywka internetowa. Siri ma również wbudowane rozpoznawanie głosu, dlatego możesz do niej mówić, a nie tylko pisać.

### Test Turinga

W podrozdziałach powyżej zaznajomiłeś się z niektórymi czatbotami i (mamy nadzieję!), wyciągnąłeś wniosek, że nie są one całkowicie przekonujące, udając człowieka (choć niektóre są lepsze od innych!). Ale może wkrótce pojawią się nowe czatboty, które nie będą miały tych ograniczeń. Czy powinniśmy uważać je za inteligentne? W jaki sposób moglibyśmy to stwierdzić? Czy istnieje formalny sposób, w jaki możemy ustalić, czy czatbot jest na poziomie ludzkiej inteligencji?

Bardzo znany informatyk, [Alan Turing](https://pl.wikipedia.org/wiki/Alan_Turing), odpowiedział na to pytanie w 1950 roku, zanim istniał pierwszy czatbot! Alan Turing miał niezwykłą wizję przyszłości i wiedział, że wymyślenie inteligentnych komputerów jest tylko kwestią czasu i że będziemy potrzebować metody sprawdzającej, czy udało nam się stworzyć naprawdę inteligentny komputer.

Zastanawiał się nad tym, jak można byłoby zdefiniować inteligencję (określenie inteligencji jest zaskakująco trudne!) i stwierdził, że jednym ze sposobów byłoby uznanie, że komputer jest inteligenty, jeśli potrafi konwersować z człowiekiem jak człowiek. Definicja ta nie obejmuje całej inteligencji, ponieważ uwzględnia jedynie to, co osoba lub komputer mówi i ignoruje inne elementy inteligencji, takie jak określenie najlepszego sposobu na przejście przez budynek (lub labirynt) lub zdecydowanie, jak działać w konkretnej sytuacji (na przykład na imprezie towarzyskiej, przy podejmowaniu decyzji o tym, jaką kolejną rzecz zrobić w pracy lub co zrobić, gdy ktoś się zgubi). Jednakże komunikacja jest nadal bardzo istotnym elementem ludzkiej inteligencji.

Aby sprawdzić, czy program komputerowy może lub nie może komunikować się jak człowiek, Turing zaproponował test. Oprócz programu komputerowego, do przeprowadzenia testu wymagane są dwie osoby. Jedna z osób działa jako „przesłuchujący”, a druga jako „człowiek”, do porównania z programem komputerowym. Przesłuchującego umieszcza się w innym pomieszczeniu niż komputer i „człowiek”. Przesłuchujący rozmawia zarówno z człowiekiem, jak i z programem komputerowym, ale nie wie z kim rozmawia w danej chwili. Rozmowy przeprowadzane są na zasadzie podobnej do komunikatora tekstowego, dzięki czemu program komputerowy nie potrzebuje komunikować się głosowo. Podczas rozmów zarówno człowiek, jak i komputer próbują przekonać przesłuchującego, że są człowiekiem. Po zakończeniu rozmów przesłuchujący musi powiedzieć, który z rozmówców był komputerem, a który człowiekiem. Jeśli nie jest w stanie tego z dużą pewnością stwierdzić, oznacza to, że komputer przeszedł pomyślnie test.

Test zaproponowany przez Turinga stał się w końcu sławny i otrzymał nazwę „testu Turinga”. Jedną z motywacji do tworzenia czatbotów jest próba stworzenia takiego, który zda test Turinga. Niestety nie został jeszcze stworzony czatbot, który zdałby ów test, a kwestią otwartą w informatyce jest to, czy jest to w ogóle możliwe, podobnie jak inne pytania o sztuczną inteligencję, które napotkasz dalej w tym rozdziale. 

Istnieją również inne formy testu Turinga. Gry akcji mają czasami postać sterowaną komputerowo, która walczy z twoją postacią, zamiast drugiej, kontrolowanej przez człowieka postaci. Odmianę testu Turinga można wykorzystać do określenia tego, czy komputerowo kontrolowany gracz wydaje się posiadać (lub nie) ludzką inteligencję, prosząc przesłuchującego, aby grał zarówno przeciwko postaci komputerowej, jak i ludzkiej, i aby sprawdzić, czy potrafi odróżnić je od siebie.

W rzeczywistości wiele aspektów ludzkiej inteligencji mogłoby zostać przetestowanych przed odmianę testu Turinga. Jeśli chciałbyś mieć komputerowego szachistę, który wyglądałby jak człowiek, a nie komputer (niektórzy ludzie woleliby grać przeciwko człowiekowi, a nie komputerowi), możesz również użyć do tego testu Turinga! Jakie inne możliwe testy Turinga możesz wymyślić?

{panel type="curiosity" summary="Prawdziwy test Turinga"}
Alan Turing zaczął od zaproponowania prostej gry towarzyskiej wymagającej trzech graczy, w której pierwszym graczem była kobieta, drugim graczem był mężczyzna, a trzecim graczem mógł być zarówno mężczyzna, jak i kobieta i przejmował on rolę „przesłuchującego”. Przesłuchujący znajdował się w innym pokoju niż pozostała dwójka graczy i mógł komunikować się z nimi tylko przekazując notatki (np. przez przekazywanie notatek pod drzwiami). Mężczyzna musiał spróbować przekonać przesłuchującego, że jest tak naprawdę kobietą, a kobieta — że jest kobietą. Na koniec przesłuchujący musiał powiedzieć, kto był mężczyzną, a kto kobietą i jeśli odgadł niepoprawnie, to mężczyzna „wygrywał”.
{panel end}

{panel type="project" summary="Uruchom swój własny test Turinga na czatbocie"}

Ten projekt wymaga przeprowadzenia testu Turinga. Przeczytaj uważnie ten podrozdział (jak i poprzedni, jeśli jeszcze tego nie zrobiłeś) i upewnij się, że rozumiesz wszystko.

Na przedmiotach przyrodniczych, takich jak biologia, fizyka i chemia, często wykonuje się eksperymenty. Jeśli masz takie zajęcia, prawdopodobnie będziesz wiedział, że jeśli eksperyment nie zostanie przeprowadzony prawidłowo (np. w chemii niektórzy uczniowie chcieliby umieścić więcej substancji chemicznej niż mówi polecenie), wtedy wyniki niekoniecznie będą tymi, których szukasz, a twój eksperyment jest w zasadzie bezsensowny i bezcelowy. Musisz również uważać, aby inne czynniki nie wpływały na wyniki, np. trzeba kontrolować temperaturę i wilgotność w eksperymentach biologicznych, które obejmują rosnące mikroorganizmy.

Przeprowadzenie testu Turinga jest przeprowadzeniem eksperymentu, tak jak przeprowadzanie eksperymentów na lekcjach chemii. Podobnie jak w przypadku eksperymentów chemicznych, przeprowadzanie testu Turinga wymaga zachowania ostrożności przy prawidłowym wykonywaniu poleceń i kontrolowania czynników, które mogą potencjalnie wpływać na wyniki, ale nie są częścią tego, co jest sprawdzane. Powinieneś o tym pamiętać podczas realizacji tego projektu.

Np. większość czatbotów komunikuje się w formie tekstowej, a nie słownej. Komunikacja w formie ustnej polega nie tylko na wybieraniu brzmiących inteligentnie rzeczy do powiedzenia, ale także wymaga przekonującego głosu i prawidłowego wymawiania słów. Ton głosu lub akcent mógłby potencjalnie sprawić, że dla przesłuchującego będzie bardzo oczywiste, która rozmowa była z człowiekiem, a która z komputerem, bez konieczności nawet rozważania, co zostało powiedziane w rozmowie. Nie to ma być sprawdzone testem Turinga! Dlatego w teście Turinga komputer i człowiek będą komunikować się w formie pisemnej z przesłuchującym. 

Innym przykładem, który mógłby mieć wpływ na wynik testu, może być szybkość reakcji. Komputer prawdopodobnie będzie w stanie odpowiedzieć natychmiast, podczas gdy człowiek będzie potrzebował czasu na przemyślenie, a następnie napisanie odpowiedzi. Aby uniemożliwić przesłuchującemu podejmowanie decyzji w oparciu o szybkość, a nie treść, szybkość reakcji również musi być kontrolowana. Sposób przeprowadzania testu Turinga opisany poniżej próbuje kontrolować te dodatkowe czynniki.

Wybierz czatbota z listy na Wikipedii (zobacz powyższy podrozdział o czatbotach) lub ewentualnie użyj Mitsuku lub Cleverbota (Eliza nie jest do tego zalecana). Przyjmiesz rolę przesłuchującego, ale będziesz potrzebował innej osoby, aby działała jako „człowiek”. W tym celu zaleca się wybrać osobę w klasie, której nie znasz zbyt dobrze. Nie wybieraj swojego najlepszego przyjaciela z klasy, ponieważ poznasz go szybko po odpowiedziach na pytania, więc będziesz w stanie odróżnić go od czatbota w oparciu o jego osobowość, a nie o jakość czatbota.

Oprócz czatbota i twojego kolegi z klasy, który będzie działał jako człowiek, będziesz potrzebować dostępu do klasy z komputerem z Internetem, drugiego pokoju (choćby korytarza), kawałków papieru, długopisów oraz monety lub kostki.

Czatbot powinien zostać uruchomiony na komputerze, a twój kolega z klasy powinien znajdować się w tym samym pokoju z komputerem. Ty powinieneś być poza tym pokojem. Jako przesłuchujący będziesz najpierw rozmawiał albo z kolegą, albo z komputerem, a następnie z drugim. Nie powinieneś wiedzieć, w jakiej kolejności będziesz z nimi rozmawiał; aby ustalić, z kim rozmawiasz jako pierwszym, twój kolega powinien użyć kostki lub monety, aby losowo o tym zdecydować.

Aby przeprowadzić rozmowy, zacznij od napisania czegoś na górze kartki, na przykład „cześć”, „hej” lub „jak się masz?”. Umieść znak obok linijki, aby było jasne, że linijka została napisana przez CIEBIE. Podaj kartkę papieru do pokoju, w którym znajduje się twój kolega i komputer (jeśli możesz, wsuń ją pod drzwi), gdzie twój kolega napisze na niej odpowiedź i przekaże ci ją. Powinieneś wtedy napisać odpowiedź i powtórzyć proces. Każda rozmowa powinna znajdować się na oddzielnym arkuszu papieru i mieć długość od 20 do 40 linijek (co oznacza, że każda osoba / komputer powinna napisać około 10 — 20 linijek w każdej rozmowie). Umieść znak obok każdej linii, którą ty napisałeś, aby było jasne, kto napisał które linie.

Jeśli teraz to twój kolega rozmawia z tobą (a nie czatbot), to napisze odpowiedź na podstawie tego, co by normalnie odpowiedział.

Jeśli teraz to czatbot rozmawia z tobą, twój kolega powinien napisać czatbotowi to, co powiedziałeś i następnie napisać odpowiedź czatbota na kartce papieru. Przed wysłaniem wypowiedzi do czatbota, powinien sprawdzić, czy na pewno wpisał ją poprawnie.

Problem polega na tym, że rozmowa pomiędzy tobą a czatbotem potrwa dłużej niż między tobą a kolegą, ponieważ twój kolega musi wpisywać to, co mówisz do czatbota. Nie chciałbyś, żeby stało się oczywiste, która rozmowa była z komputrem a która z człowiekiem z tego powodu! Aby poradzić sobie z tym, kolega powinien celowo opóźniać każdą odpowiedź, tak aby każda z nich trwała dokładnie jedną minutę.

Tematy rozmów mogą być dowolne, ale pamiętaj, aby przyjąć założenie, że nie znasz swojego kolegi, więc nie odwołuj się do tego, co obydwoje wiecie, co się stało w przeszłości w klasie lub w weekend. Byłoby to niesprawiedliwe dla czatbota, który nie będzie wiedzieć o tych rzeczach. Pamiętaj, że oceniasz czatbota pod kątem jego zdolności do pokazania ludzkiej inteligencji, a nie tego, czego nie wie.

Dobrymi tematami rozmowy będą ulubione kolory, gry, jedzenie, pogoda i takie tematy, które mogłyby się ci przytrafić w rozmowie z osobą, której nie znasz, spotkaną w pracy, w sklepie lub na imprezie. Wymyślenie dobrych pytań jest trudne, ale próbuj!

Po zakończeniu obydwu rozmów, ty jako przesłuchujący musisz powiedzieć, która rozmowa była z kolegą, a która z czatbotem. Twój kolega powinien powiedzieć ci, czy zgadłeś.

Oto kilka pytań, które możesz rozważyć po zakończeniu testu Turinga:
- Po czym poznałeś, kto był czatbotem, a kto twoim kolegą?
- Czy zadałeś pytania, które zadałeś, które były „nieuczciwe” — takie które zależały od wiedzy, którą ma twój kolega, a inni (komputer lub osoba) najprawdopodobniej nie?
- Co zdradziło tajemnicę: treść odpowiedzi czy sposób, w jaki treść została wyrażona?

{panel end}

{image filename="turing-test-dating-show.png" alt="Randkowy test Turinga"}

## Podsumowanie
W tym rozdziale pisaliśmy jedynie o jednym zastosowaniu SI. Ten dział informatyki zawiera o wiele więcej ekscytujących zastosowań, takich jak komputery, które mogą grać w gry planszowe przeciwko ludziom, komputery, które się uczą, komputery, które są w stanie kontrolować roboty, które eksplorują środowisko zbyt niebezpieczne, aby weszli tam ludzie.

W przyszłości ten rozdział będzie rozbudowany.

## Dalsza lektura

- [O sztucznej inteligencji na stronie i-Programmer](http://www.i-programmer.info/babbages-bag/297-artificial-intelligence.html)
- [Paradoks sztucznej inteligencji i-Programmer](http://www.i-programmer.info/programming/artificial-intelligence/2437-the-paradox-of-artificial-intelligence.html)

### Ciekawe odnośniki
Wszystkie materiały są po angielsku.

- [Robot Harold](http://csunplugged.org/harold-the-robot-2/) — materiały dodatkowe na stronie CS Unplugged, o tym, dlaczego SI jest taka trudna.
- [Test Turinga](http://csunplugged.org/the-turing-test/) — materiały dodatkowe na stronie CS Unplugged.
- [Wikipedia- Outline of Artificial Intelligence](https://en.wikipedia.org/wiki/Outline_of_artificial_intelligence)
- [Wikipedia - Turing Test](https://en.wikipedia.org/wiki/Turing_test)
- [Wikipedia - Machine Learning](https://en.wikipedia.org/wiki/Machine_learning)
- [CS4FUN - O czatbotach](http://www.cs4fn.org/ai/meetthechatterbots.php)
- [CS4FUN - O teście Turinga](http://www.cs4fn.org/ai/illusionintelligence.php)
- [Czatbot Mitsuku](https://pandorabots.com/mitsuku/)
- [IEEE Spectrum — O sztucznej inteligencji.](http://spectrum.ieee.org/robotics/artificial-intelligence)
- [TED — filmy z wykładami na temat sztucznej inteligencji.](https://www.ted.com/topics/ai)
