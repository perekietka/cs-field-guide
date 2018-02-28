# Interakcja człowiek — komputer

## Z lotu ptaka

{panel type="teacher-note" title="Dla nauczyciela" summary="Zakres interfejsów użytkownika"}
Materiał w tym rozdziale odnosi się do „urządzeń cyfrowych”. Chociaż zdecydowanie odnosi się to do konwencjonalnych komputerów, ma również zastosowanie do wszelkiego rodzaju innych gadżetów, takich jak budziki, klimatyzatory, kuchenki mikrofalowe, stopery, instrumenty elektroniczne, punkty kasowe, parkometry i alarmy przeciwwłamaniowe. W rzeczywistości większość ćwiczeń dla większości będzie o wiele łatwiejsza do wykonania na urządzeniu z zaledwie kilkoma funkcjami, ponieważ umożliwia to łatwiejsze zbadanie i ocenienie takich urządzeń. Ocena systemu Microsoft Windows lub urządzenia iPad jest zbyt trudna, ponieważ każdy z podsystemów zasługiwałby na osobną analizę (jak działa menu, jak znaleźć pliki, jak otworzyć program, może nawet jak go włączyć!)
{panel end}

Ludzie są często sfrustrowani komputerami i innymi urządzeniami cyfrowymi.
W pewnym momencie korzystania z tych urządzeń być może zaczniesz
denerować się, że system zrobił coś, czego nie chcesz
lub że nie możesz wymyślić, jak zmusić komputer do zrobienia tego, co chcesz. Dlaczego tak jest?
Ludzie stworzyli komputery, więc dlaczego są one często tak frustrujące w użytkowaniu dla człowieka?

Z dekady na dekadę komputery stają się setki razy potężniejsze, ale jest jeden ważny element systemu komputerowego, który nie zmienił się znacząco w wydajności od czasu, gdy pierwsze komputery zostały opracowane w latach czterdziestych: człowiek. Aby system komputerowy działał naprawdę dobrze, musi być zaprojektowany przez ludzi, którzy dobrze rozumieją ludzką część systemu.

W tym rozdziale przyjrzymy się czynnikom sprawiającym, że interfejs jest dobry lub zły. Chodzi o to, abyś był wyczulony na główne problemy, abyś mógł patrzeć krytycznie na istniejące interfejsy i zacząć myśleć o tym, jak zaprojektować dobry interfejs.

Często programiści tworzą oprogramowanie, które wymaga od użytkownika spędzenia dużo czasu na naukę. 
Interfejs może być łatwy w użyciu dla programistów, ponieważ znają oni system naprawdę dobrze, ale użytkownik chce po prostu wykonać pracę, bez czasochłonnych przygotowań (i może szybko zmienić program na inny, jeśli obecny jest za trudny w użyciu).
Programista może myśleć o programie i użytkowniku oddzielnie, ale użytkownik jest częścią systemu i programista musi brać to pod uwagę. Program powinien być intuicyjny i przyjazny.

Interakcja człowiek — komputer (ang. Human — Computer Interaction, w skrócie HCI) polega na tym, aby dostosować programy do oczekiwań ludzi. Wykracza to daleko poza wybór wzorców, kolorów i czcionek dla interfejsu.

Aby zrozumieć, jak ludzie używają urządzeń cyfrowych, trzeba brać pod uwagę aspekt psychologiczny, sposób postrzegania przez nich rzeczy, poszukiwać czynników sprawiających, że użytkownik uważa, że system jest mu pomocą, a nie przeszkodą. 
Dzięki zrozumieniu HCI programista ma większe szanse stworzyć program efektywny i popularny. 

Wypróbuj następujące narzędzie interaktywne i poproś również znajomych, aby je wypróbowali:

{interactive name="deceiver" type="in-page"}

Czy ktoś z was dał złą odpowiedź na pytanie, mimo że był przekonany, że daje dobrą?
Być może zauważyłeś, że przyciski „EVEN” (parzysty) i „ODD” (nieparzysty) czasami zamieniają się miejscami.
Niespójność w interfejsie jest na ogół czymś niepożądanym, ponieważ może łatwo zmylić użytkownika, który przez to popełni błąd.

Jedyną sytuacją, w której może być to pożądane, jest celowe uczynienie gry komputerowej bardziej interesującą (w której powyższa interakcja mogłaby wystąpić).
Wyobraź sobie, że masz formularz internetowy, w którym przyciski „wyczyść” i „prześlij” często zmieniają się miejscami.
Użytkownicy często czyściliby formularz, gdy zamierzaliby go przesłać, lub przesyłaliby formularz, gdyby chcieli go wyczyścić!

{panel type="teacher-note" title="Dla nauczyciela" summary="Dokładność vs szybkość w powyższej interakcji"}
Interaktywne narzędzie zmieniające parzysty / nieparzysty może nie oszukać wszystkich uczniów, ale dla niektórych będzie bardzo frustrujące. Jeśli zdecydują się użyć go powoli i ostrożnie, mogą uzyskać poprawnie wybory parzysty / nieparzysty. Jednocześnie uzyskają także niższe wyniki (tj. niższą produktywność, jeśli byłby to prawdziwy interfejs).
{panel end}

Badanie interakcji człowieka z komputerem wiąże się z wykorzystaniem wielu mechanizmów psychologicznych, ponieważ ma to wpływ na sposób korzystania z systemu. Prosty przykład: ludzka pamięć krótkotrwała przechowuje informacje tylko kilka sekund (nawet u młodych ludzi!).
Jeśli urządzenie odpowiada po więcej niż około 10 sekundach, użytkownik musi podjąć wysiłek, aby pamiętać, co robił. To jest dodatkowa praca dla użytkownika (co z jego punktu widzenia powoduje, że system jest bardziej męczący w użyciu). Innym przykładem jest to, że ludzie nabierają nawyków — po pewnym czasie zaczynają robić coś automatycznie: jeśli zaczniesz jeździć na rowerze po trasie, którą pokonujesz każdego dnia, wkrótce osiągniesz cel bez myślenia o każdym zakręcie po drodze. Jest to normalne, chyba że masz wstąpić gdzieś po drodze lub jeśli niedawno przeprowadziłeś się do nowego domu, lub zmieniłeś miejsce pracy. Podobny efekt występuje w dialogowych okienkach potwierdzających; może często przypadkowo zamykasz plik bez zapisywania go, a system pyta się „Czy chcesz to zapisać?”, więc naciskasz „Tak”. Po wykonaniu tej czynności kilka razy zaczniesz ją wykonywać bez zastanowienia. Może się wtedy zdarzyć, że np. gdy nie chcesz zastąpić starego pliku, możesz przypadkowo kliknąć „Tak”.

{panel type="curiosity" title="Dla ciekawych" summary="Błędy nawyku"}
Przyzwyczajenie się do standardowej trasy lub procedury, a co za tym idzie zapominanie czegoś innego, co trzeba było zrobić tego dnia, nazywa się *błędem nawyku* (ang. capture error).
Na ogół nawyk jest dobrą rzeczą, ponieważ oszczędza ci ciężaru myślenia o codziennych czynnościach (co mogłoby być jeszcze bardziej męczące),
ale może również skłonić cię do zrobienia czegoś, czego nie zamierzałeś.
Dobry projektant interfejsu będzie tego świadomy i uniknie wykonania interfejsu tak, że użytkownik jest narażony na odruchowe zrobienie czegoś.
{panel end}

Wiele osób może obwiniać siebie za takie błędy, ale podstawy psychologii mówią, że jest to naturalny błąd. Dobry system powinien chronić użytkowników przed tym (na przykład umożliwiając cofnięcie danej operacji).

{comment}
Rozważ spojrzenie na cechy przycisku jako przykład drobnych szczegółów (zsuń kursor z przycisku, naciskając itp.);
może dodać interaktywność z prostym (normalnym) polem wyboru i przyciskiem (a może i menu), aby czytelnik mógł eksperymentować z tym, co się dzieje (np. kliknąć, ale zsunąć przed zwolenieniem przycisku)
{comment end}

Projektowanie dobrych interfejsów jest *bardzo* trudne. Właśnie wtedy, gdy myślisz, że masz świetny pomysł, przekonasz się, że potem cała grupa ludzi będzie zastanawiać się, jak z niego korzystać, a w niektórych sytuacjach spali to na panewce. Co gorsza, niektórzy programiści uważają, że ich użytkownicy są bałwanami i że wszelkie problemy z interfejsem są winą użytkownika, a nie programisty. Jednak prawdziwym problemem jest to, że programista zna system bardzo dobrze, podczas gdy użytkownik chce po prostu wykonać swoją pracę bez konieczności spędzania dużej ilości czasu na nauce oprogramowania — jeśli oprogramowanie jest zbyt trudne w użyciu i użytkownik ma wybór, znajdzie po prostu coś prostszego w użyciu. Dobre interfejsy są bardzo cenne!

Istnieje wiele sposobów oceniania i dostosowywania interfejsów. W tym rozdziale przyjrzymy się niektórym z nich. Warto pamiętać, że jedną z najgorszych osób do oceny interfejsu jest osoba, która go zaprojektowała i zaprogramowała. Zna ona dokładnie swój system, prawdopodobnie myślała o nim tygodniami, zna opcje, które nie powinny być wybrane, i oczywiście ma osobisty interes w znalezieniu tego, co jest *właściwe*, a nie tego, co jest *złe*. Ważne jest również, aby interfejs był oceniany przez osobę, która będzie typowym użytkownikiem; jeśli poprosisz 12-latka, aby ocenił system planowania emerytalnego, może nie wiedzieć, co będzie ważne w tym systemie dla typowego użytkownika; a jeśli nauczyciel wypróbuje system przeznaczony dla ucznia, nie będzie się być może zachowywał jak uczeń, bo zna odpowiedź i wie, jak do niej dojść.

Często interfejsy są oceniane wstępnie przez typowych użytkowników, a projektanci starannie odnotowują wszelkie problemy, które wystąpią. Są firmy, które płacą grupom ludzi, aby wypróbowali prototypowy produkt. Raport na temat produktu jest następnie generowany i przekazywany ludziom, którzy nad nim pracują. Jest to kosztowny proces, ale sprawia, że produkt jest o wiele lepszy i może uzyskać ogromną przewagę nad konkurencją. Ocenianie go przez zewnętrzną firmę sprawia, że unika się uprzedzeń ze strony osób tworzących system, które będą chciały udowodnić (nawet podświadomie), że wykonały dobrą robotę, zamiast odkrywać wszelkie problemy z oprogramowaniem, które będą irytować użytkowników.

## Użytkownicy i zadania

Bardzo ważną kwestią przy projektowaniu lub ocenie interfejsu jest to, kim mogą być użytkownicy. Na przykład wiek typowego użytkownika może być znaczący: bardzo małe dzieci mogą mieć trudności z czytaniem niektórych słów i preferować obrazy oraz animacje, podczas gdy ktoś w środowisku komercyjnym, kto często korzysta z interfejsu, będzie chciał, aby był bardzo szybki w użyciu, np. umożliwiał używanie skrótów klawiaturowych.

Zastanów się, jakie kwestie należy rozważyć w przypadku następujących grup użytkowników.

- seniorzy
- gracze
- zwykli użytkownicy
- obcokrajowcy

{panel type="spoiler" title="Spojler" summary="Niektóre z możliwych odpowiedzi: Nie otwieraj, dopóki nie pomyślałeś o tym!"}
- Seniorzy: wola dużą czcionkę, oprogramowanie powinno mieć tylko kilka funkcji i nie powinno wymagać pamiętania wielu rzeczy; przydadzą się ułatwienia w związku z gorszym wzrokiem i sprawnością ruchową użytkownika (np. duże przyciski pomocy), nie należy zakładać wcześniejszych doświadczeń z komputerami.
- Gracze: mają wcześniejsze doświadczenia z typowymi interfejsami gier, są wymagajacy, prawdopodobnie mają urządzenia z najwyższej półki.
- Zwykli użytkownicy: potrzebują interfejsu łatwego w obsłudze, być może opartego na powszechnie używanych systemach, wymagają jasnych wskazówek.
- Obcokrajowcy: lepiej używąć prostego języka i ułatwiających obsługę ikonek.
{panel end}

Interfejs jest jedyną częścią programu, którą widzi użytkownik (to definicja interfejsu!), więc jeśli interfejs nie działa, dla użytkownika oznacza to, że program nie działa.

Kolejną ważną rzeczą podczas projektowania i oceniania interfejsu jest zastanowienie się, do jakich zadań jest on używany. Reklamy urządzeń cyfrowych często zachwalają funkcje, jakie posiada urządzienie, np. smartfon jest reklamowany jako aparat o wysokiej rozdzielczości. Jednak oceniający interfejs nie powinnien skupiać się na rozdzielczości, ale na zadaniach, jakim aparat w smartfonie będzie służył. Załóżmy, że ktoś chce zrobić zdjęcie czegoś, co właśnie widzi i przesłać je znajomemu. Smartfon może znajdować się w kieszeni lub torbie, a jeśli ktoś zobaczy, że dzieje się coś fajnego, musi go wyciągnąć, być może odblokować, otworzyć aplikację aparatu, dostosować oświetlenie i inne ustawienia, nacisnąć przycisk (czy łatwo go znaleźć, gdy trzymasz urządzenie pionowo?), następnie wybrać zdjęcie, sposób udostępniania, wybrać znajomego, któremu ma się udostępnić zdjęcie (czy oprogramowanie pomoże ci w tym?), wysłać (co się dzieje, gdy jesteś poza zasięgiem sieci?), a następnie odłożyć telefon. Jeśli którykolwiek z tych kroków jest powolny lub trudny do zapamiętania, całe doświadczenie może być frustrujące i możliwe, że przez to nie zdążysz czegoś sfotografować lub z innego powodu znajomy nie otrzyma zdjęcia.

Podczas oceny interfejsu ważne jest przemyślenie wszystkich części zadania, jako że jest ogromna różnica między używaniem interfejsu w rzeczywistej sytuacji w porównaniu z demonstrowanem niektórych funkcji urządzenia.

{panel type="challenge" title="Wyzwanie" summary="Myślenie o kontekście zadań"}
Bardzo ważne jest, aby myśleć o całym kontekście podczas opisywania zadania. Jako ćwiczenie możesz podać szczegółowy opis wszystkich czynności, jakie człowiek musi wykonać (uwzględniając kontekst, czyli sytuację, w jakiej osoba się znajduje), aby wykonać takie zadania::

- ustawienie budzika,
- pokazanie prezentacji slajdów (Powerpoint).

Przedyskutuj swoje odpowiedzi z kolegą z klasy lub znajomym. To powinno pomóc ci w ocenieniu twojej odpowiedzi i rozważeniu innych możliwych przykładów.
{panel end}

{panel type="teacher-note" title="Dla nauczyciela" summary="Możliwe odpowiedzi na powyższe wyzwania"}
Celem edukacyjnym dla uczniów jest dostrzeżenie ogromnej przepaści między naiwnym widokiem „budzika” jako wystarczającym opisem zadania, a konkretnym scenariuszem, który nadaje temu zadaniu więcej sensu. Być może szczegółowe rozpracowanie zadania będzie wymagało trochę wysiłku; jeśli wcześniej uczniowie podobne zadanie robili, mogli już zapomnieć, jakie mieli trudności, a jeśli zadania nigdy nie robili, mogą uznać, że jest oczywiste. Możesz podsunąć im takie pomysły: 

- Ustaw budzik: zadanie jest często wykonywane późno w nocy, a jeśli popełnisz błąd, użytkownik może przegapić ważne spotkanie lub samolot rano, więc zadanie jest bardzo ważne. W zależności od zegara (może to być na smartfonie lub fizyczny zegar), użytkownik musi ustawić czas alarmu (w tym prawidłowe ustawienie oznaczenia am/pm w przypadku zegarów dwunastogodzinowych), włączyć dźwięk alarmu (być może upewniając się, że urządzenie nie jest wyciszone) i upewnić się, że bateria nie wyczerpie się do rana. Wszystko to dzieje się, podczas gdy użytkownik jest zmęczony, a błąd może być kosztowny!

- Pokaż prezentację slajdów (Powerpoint): zadanie to często odbywa się przed publicznością i na jego wykonanie może być ograniczony czas, np. jeśli sala nie będzie dostępna na więcej niż kilka minut przed prezentacją. Może być konieczne podłączenie komputera do projektora (wyzwanie samo w sobie dla całego interfejsu), oprogramowanie ustawione musi być w tryb prezentacji, z odpowiednim obrazem gotowym do uruchomienia, użytkownik musi mieć możliwość przejścia do następnego slajdu i powrotu po naciśnięciu złego klawisza.
Projektor zwykle wymaga czasu, aby się rozgrzać, i może być trudno określić, co dzieje się w tym czasie.
{panel end}

{panel type="curiosity" title="Ciekawostka" summary="Głupi użytkownicy czy głupie interfejsy?"}
Systemy komputerowe często sprawiają, że ludzie czują się głupimi — w rzeczywistości dostępnych jest wiele książek „dla głupich”, takich jak „iPad dla głupich” (ang. „iPad for dummies”) lub „Przewodnik dla kompletnych idiotów po Microsoft Windows 8” (ang. „The Complete Idiot's Guide to Microsoft Windows 8”).
Te książki sprzedają się w milionach egzemplarzy, ale są szanse, że ludzie, którzy je kupują, są całkiem inteligentni — po prostu interfejsy mogą sprawiać, że ludzie są tak sfrustrowani, że czują się jak głupki.
Prawda jest taka, że ​jeśli interfejs powoduje, że ​​wielu ludzi czuje się jak idiota, istnieje poważny problem z interfejsem, a nie użytkownikiem.
W przeszłości programiści, którzy zaprojektowali dane oprogramowanie, mogli sobie pozwolić na obwinianie użytkowników za wszelkie problemy.
Obecenie użytkownicy mają duży wybór oprogramowania i istnieją konkurenci gotowi zaoferować lepszy interfejs, więc jeśli programista nieustannie obwinia użytkowników za problemy, jest szansa, że ​​to programista jest kompletnym idiotą!
Jeśli słyszysz ludzi używających obraźliwych terminów, takich jak użyszkodnik, [PEBKAC](http://ars.userfriendly.org/cartoons/?id=19980506) lub błąd ID-10T (błąd idioty), może to być zabawne, ale zwykle lekceważą oni znaczenie właściwego interfejsu i nie biorą pod uwagę, że system jest źle zaprojektowany.

{panel end}

{panel type="project" title="Projekt" summary="Wysyłanie emaila z wielu urządzeń"}
W tym projekcie spróbuj wysłać wiadomość email z komputera oraz telefonu komórkowego. Zapamiętaj wszystkie kroki, które musiałeś wykonać, od momentu rozpoczęcia korzystania z urządzenia do wysłania wiadomości email.

Prawdopodobnie zauważysz sporo różnic między tymi dwoma interfejsami.

Zachowaj swoje notatki na później, ponieważ możesz je dalej analizować po przeczytaniu dalszej części tego rozdziału.
{panel end}

{panel type="project" title="Projekt" summary="Projektowanie płyt kuchennych i klamek do drzwi"}
{image filename="poor-door-design-cartoon.jpg" alt="Konflikt użytkownika otwierającego drzwi." position="right"}

W przypadku tego projektu zaprojektujesz górną część kuchenki lub uchwyty na drzwiach.
To nie jest system komputerowy, ale pomoże zademonstrować niektóre z pojawiających się problemów.
Głównym zadaniem jest szkicowanie trzech różnych konfiguracji płyty kuchennej, która obejmuje rozmieszczenie 4 elementów i 4 gałki kontrolne.

Zadanie to jest szczegółowo opisane w rozdziale 19 *Projektowanie interfejsu* [zbioru scenariuszy lekcji ,,O informatyce bez komputera''](http://jasijoasia.edu.pl/csu2.pdf) lub w multimedialnych [materiałach w języku angielskim](https://classic.csunplugged.org/human-interface-design/).
{panel end}

## Użyteczność interfejsu

{panel type="teacher-note" title="Dla nauczyciela" summary="Niektóre z kluczowych celów edukacyjnych tego rozdziału"}
Kluczowe idee, które powinni wyłowić uczniowie, obejmują:

- „System”, który musi działać dobrze, to komputer i człowiek *razem*.
- Wiele osób denerwuje się urządzeniami cyfrowymi. Czasami muszą to znosić, ponieważ jest to jedyna dostępna opcja, ale w innych przypadkach urządzenia i oprogramowanie z dobrymi interfejsami sprzedają się znacznie lepiej lub mogą mieć wyższe ceny, ponieważ pomagają użytkownikowi w wykonaniu pracy.
- Najgorszą osobą do oceny interfejsu jest osoba, która go zaprojektowała. Wie dokładnie, jak to powinno działać; dopiero jeśli ktoś inny wypróbuje urządzenie, dowiesz się, jak wygląda typowy użytkownik (z tego powodu tutaj nie proponujemy, żeby uczeń napisał własny program i ocenił jego interfejs — to byłoby wbrew zasadom!).
- Do wykonania danego zadania używany jest interfejs, dlatego najlepiej jest zidentyfikować zadania, dla których ten interfejs jest przeznaczony, a następnie rozważyć, jak są trudne. Najczęstszym błędem jest skupienie się na funkcjach interfejsu, podczas gdy w świecie rzeczywistym ważniejsze jest, czy te funkcje pomagają wykonać zadanie od początku do końca.
{panel end}

Urządzenia są często reklamowane jako „przyjazne dla użytkownika” i „intuicyjne”, niestety są to niejasne terminy, które trudno sprecyzować. W tym podrozdziale wykorzystamy bardziej techniczny termin [użyteczność](https://pl.wikipedia.org/wiki/U%BFyteczno%B6%E6_(informatyka)), który jest dobrze rozumiany przez ekspertów HCI i daje nam kilka sposobów oceniania, jak bardzo odpowiedni jest interfejs do określonego zadania. Użyteczność nie polega tylko na tym, że interfejs jest przyjemny w użyciu: słaba użyteczność może prowadzić do poważnych problemów i jest przyczyną poważnych katastrof, takich jak wypadki samolotów, katastrofy finansowe i wypadki medyczne. Trzeba mieć na uwadze, że interfejs wymagający dużej zręczności, szybkich reakcji lub dobrej pamięci czyni go mniej dostępnym dla dużej części społeczeństwa, podczas gdy dostępność może być zarówno moralnym, jak i prawnym oczekiwaniem społecznym

{panel type="curiosity" title="Ciekawostka" summary="Kiedy interfejs został źle wykonany"}
- 87 osób zginęło, gdy [lot lini Air Inter nr 148 rozbił się](https://pl.wikipedia.org/wiki/Katastrofa_lotu_Air_Inter_148), ponieważ piloci wpisali na pulpicie „33”, aby uzyskać kąt schodzenia 3,3 stopnia, ale autopilot zinterpretował to jako prędkość zniżania: „3300 stóp na minutę". Okazało się, że ten sam interfejs był używany do ustawiania zarówno kąta, jak i prędkości zniżania. Ten problem z interfejsem nazywany jest „błędem trybu” (opisany będzie poniżej). Więcej informacji [tutaj](http://blog.martindoms.com/2011/01/24/poor-ui-design-can-kill/).
- 13 osób zginęło, a wiele innych zostało rannych, gdy piloci [lotu Varig 254](https://en.wikipedia.org/wiki/Varig_Flight_254) wpisali niepoprawny kierunek. Plan lotu określał kierunek 0270, co kapitan zinterpretował i wprowadził do komputera pokładowego jako 270 stopni. W rzeczywistości oznaczało to 027,0 stopni. To zamieszanie nastąpiło z powodu zmiany formatu kierunków i pozycji separatora dziesiętnego w planach lotów, a kapitan o tym nie wiedział. Niestety, drugi pilot bezmyślnie skopiował kierunek kapitana zamiast odczytać go z planu lotu, tak jak powinien. Samolot przeleciał przez kilka godzin na autopilocie. Niestety, [efekt potwierdzenia](https://pl.wikipedia.org/wiki/Efekt_potwierdzenia) wziął górę nad procedurami bezpieczeństwa. Piloci byli przekonani, że są blisko celu, podczas gdy w rzeczywistości byli setki kilometrów dalej. Samolotowi zabrakło paliwa i rozbił się w dżungli amazońskiej. Projektowanie systemów lotniczych, które są wykorzystywane przez ludzi, jest dużym wyzwaniem i jest częścią szerszego obszaru badań nad czynnikami ludzkimi.
- Pracownik banku [przypadkowo udzielił klientowi pożyczki w wysokości 10 milionów dolarów zamiast 100 000 dolarów](http://edition.cnn.com/2012/08/24/world/asia/new-zealand-accidental-millionaire-sentenced/). Klient wypłacił większość pieniędzy i uciekł do Azji, bank stracił w tym czasie miliony dolarów, a kasjer bankowy miał traumatyczne przeżycia. Błąd był spowodowany tym, że pracownik wpisał dwa dodatkowe zera, prawdopodobnie dlatego, że niektóre interfejsy automatycznie wstawiały kropkę dziesiętną (można wpisać 524, aby wprowadzić 5,25 USD), a inne nie. Ten błąd można wytłumaczyć w kategoriach braku spójności interfejsu.
- U 43-letniej kobiety zatrzymał się oddech po tym, jak pielęgniarka przypadkowo wpisała 5 zamiast 0,5 dawki morfiny. Interfejs powinien utrudnić popełnienie błędu wpisania dziesięciokrotnie większej dawki. Istnieje [artykuł na ten temat](http://www.ncbi.nlm.nih.gov/pubmed/16738293) oraz artykuł [o problemie z interfejsem](http://hrcak.srce.hr/file/95851). Opisany przypadek błędu to tak zwany „błąd o jeden” (ang. off by one error), w którym jedna dodatkowa cyfra została pominięta lub dodana. Podobne problemy mogą wystąpić w każdym systemie sterowania, w którym operator wpisuje wartość. Lepszy interfejs zmusiłby operatora do naciśnięcia przycisku „w górę” i „w dół”, aby duże zmiany wymagały dużo pracy (odnosi się do zasady współmiernego wysiłku).

We wszystkich tych przypadkach winę za popełnienie błędu można przypisać użytkownikowi (pilotom, kasjerowi i pielęgniarce), ale dobrze zaprojektowany interfejs, który nie powoduje poważnych konsekwencji błędów, które ludzie mogą łatwo popełnić, byłby o wiele lepszy.
{panel end}

Istnieje wiele elementów, które można wziąć pod uwagę w użyteczności; my wspomnimy o kilku, które można napotkać podczas oceniania codziennych interfejsów. Pamiętaj, że interfejs ma nie tylko komputer — każdego urządzenia cyfrowego, takiego jak budzik, zdalne sterowanie klimatyzacją, kuchenka mikrofalowa lub alarmy antywłamaniowe może dotyczyć problem z użytecznością.

### Konsekwencja

„Złotą zasadą” użyteczności jest *konsekwencja*. Jeśli system ciągle się zmienia, korzystanie z niego będzie frustrujące. Wcześniej mieliśmy przykład pary przycisków „parzysty”/„nieparzysty”, które sporadycznie zamieniały się miejscami. Pozytywnym przykładem jest konsekwentne stosowanie „CONTROL-C” i „CONTROL-V” w wielu różnych programach do kopiowania i wklejania tekstu lub obrazów. Pomaga to także *automatyzacji czynności*: gdy nauczysz się kopiować i wklejać w jednym programie, wiesz, jak to robić w wielu innych. Wyobraź sobie, że każdy program używałby do tego różnych poleceń menu i klawiszy!

Powiązanym problemem jest *błąd trybu* [ang. *mode error*](https://pl.wikipedia.org/wiki/Mode_error#Mode_errors), w którym akcja zależy od trybu, w którym się znajdujesz. Prostym przykładem jest wciśnięty klawisz CAPS LOCK (w szczególności przy wprowadzaniu hasła, gdzie nie widać efektu wpisywania). Klasycznym przykładem są arkusze kalkulacyjne Excel, w których efekt kliknięcia komórki zależy od trybu: czasami wybiera komórkę, a innym razem umieszcza nazwę komórki, którą kliknąłeś w innej komórce. Tryby są uważane za złe praktyki w projektowaniu interfejsu, ponieważ mogą one łatwo spowodować, że użytkownik wykona niewłaściwą rzecz i powinny być w miarę możliwości unikane.

### Czas odpowiedzi
Szybkość, z jaką interfejs reaguje (jego *czas reakcji*) ma znaczny wpływ na użyteczność.
Sposób, w jaki ludzie postrzegają czas, nie zawsze jest proporcjonalny do czasu, w którym coś się dzieje.
Jeśli coś dzieje się wystarczająco szybko, będziemy postrzegać to jako natychmiastowe.
Jeśli musimy czekać i nie możemy nic zrobić podczas oczekiwania, czas może wydawać się wolniejszy!

Poniższe narzędzie interaktywne pozwala dowiedzieć się, co znaczy „natychmiastowy” dla ciebie.
Gdy klikniesz na każdą komórkę, czasami wystąpi losowe opóźnienie, zanim coś pojawi się; inne komórki nie będą miały opóźnienia. Kliknij każdą komórkę i jeśli wydaje się, że reaguje natychmiast, pozostaw ją bez zmian.
Jeśli jednak zauważysz małe opóźnienie przed pojawieniem się obrazu, kliknij ją ponownie (co spowoduje, że komórka zmieni kolor na zielony). Wystarczy, że wykonasz szybką decyzję na poziomie intuicyjnym przy pierwszym kliknięciu każdej komórki — nie przemyślaj jej.
Opóźnienie może być bardzo krótkie, jednak gdy je tylko zauważysz, wtedy kliknij w komórkę, aby zmieniła ona kolor na zielony.

{interactive name="delay-analyser" type="whole-page" text="Interaktywny tester opóźnień"}

Po ukończeniu zadania kliknij „View statistics” (Wyświetl statystyki), aby porównać opoźnienia zauważalne z niezauważalnymi.
Dla większośći osób punktem, w którym zaczynają dostrzegać opóźnienie, jest 100 ms (100 milisekund) czyli jedna dziesiąta sekundy.
Cokolwiek krótszego (szczególnie około 50 ms) jest bardzo trudne do zauważenia. Dłuższe opóźnienia (na przykład 350 ms, czyli ponad jedna trzecia sekundy) są bardzo łatwe do zauważenia.

Chodzi o to, że dowolny element interfejsu (taki jak przycisk lub pole wyboru), który potrzebuje więcej niż 100 ms, by odpowiedzieć, może być postrzegany przez użytkownika jako niedziałający i użytkownik może go kliknąć ponownie. W przypadku pola wyboru może to spowodować, że pozostanie ono wyłączone (z powodu dwóch kliknięć), co spowoduje, że użytkownik pomyśli, że nie działa.
Spróbuj kliknąć to pole wyboru tyle razy, aby zostało zaznaczone jako wybrane.
{interactive name="delayed-checkbox" type="in-page"}

Oceniając interfejsy, pamiętaj, że nawet bardzo małe opóźnienia mogą sprawić, że system będzie trudny w użyciu.

Poniższy film przedstawia eksperyment przeprowadzony z użyciem gogli wirtualnej rzeczywistości w celu symulowania opóźnień w Internecie, ale na przykładzie rzeczywistych sytuacji.
Ma angielskie napisy, ale najciekawsze jest to, co się w nim dzieje.

{video url="https://www.youtube.com/watch?v=_fNp37zFn9Q"}

### Ludzka pamięć krótkotrwała

Kolejnym ważnym czynnikiem, o którym należy pamiętać, jest nasza *pamięć krótkotrwała*, która zwykle jest kwestią sekund. Aby zapamiętać coś na dłużej, użytkownik musi to ćwiczyć (powtórzyć) lub zanotować informacje, na przykład zapisać je. Jeśli system potrzebuje trochę czasu na odpowiedź (powiedzmy 10 sekund), prawdopodobnie użytkownik zapomni, co dokładnie zamierza zrobić z systemem. Na przykład, jeśli masz numer telefonu do wpisania, który ktoś właśnie ci podyktował, a dostęp do spisu kontaktów w telefonie zajmuje 12 sekund, możesz zapomnieć o numerze. Jeśli możesz uzyskać dostęp do kontaktów w celu wpisania numeru w ciągu kilku sekund, możesz prawdopodobnie wprowadzić numer bez większego wysiłku. Z tego powodu każda część systemu, która potrzebuje więcej niż 10 sekund na odpowiedź, zmusza użytkownika do powtarzania lub zapisania kluczowych informacji, co jest bardziej męczące.

Więcej informacji na temat „limitów czasowych” dla interfejsów znajdziesz w [tym artykule Jakoba Nielsena](http://www.nngroup.com/articles/response-times-3-important-limits/) (po angielsku).

### Ludzka pamięć przestrzenna

Kolejną ważną kwestią związaną z użytecznością jest *pamięć przestrzenna* — nasza zdolność do pamiętania, gdzie znajdują się rzeczy (np. gdzie znajduje się przycisk lub ikonka). Ludzka pamięć przestrzenna ma dużą pojemność (prawdopodobnie pamiętasz położenie wielu miejsc i obiektów), jest długotrwała (ludzie odwiedzający miasto, w którym dorastali, często pamiętają jego topografię) i możemy bardzo szybko zapamiętać rozmieszczenie przestrzenne rzeczy. Z tego wynika bardzo prosty aspekt użyteczności — mianowicie rozmieszczenie elementów interfejsu nie powinnno się zmieniać. Narzędzie interaktywne na początku tego rozdziału zostało celowo skonfigurowane jako frustrujące przez sporadyczną zamianę dwóch przycisków. Powodem, dla którego ludzie często popełniają błąd w tej sytuacji, jest to, że uaktywnia się ich pamięć przestrzenna, więc położenie przycisku jest ważniejsze niż to, co jest na nim napisane. Systemy, które nie są spójne w rozmieszczeniu przestrzennym przycisków „OK” i „Anuluj”, mogą łatwo spowodować naciśnięcie niewłaściwego przycisku.

Innym miejscem, w którym rozmieszczenie elementów interfejsu szybko się zmienia, jest obrót tabletu lub smartfona. Niektóre urządzenia zmieniają kolejność ikon dla nowej orientacji, która zmienia układ przestrzenny, podczas gdy inne zachowują ją (choć ikonki mogą nie wyglądać dobrze w nowym ułożeniu). Wypróbuj kilka różnych urządzeń i zobacz, które zmieniają rozmieszczenie po obróceniu.

{panel type="curiosity" title="Ciekawostka" summary="Typowe sytuacje, w których rozmieszczenia niespodziewanie się zmieniają"}
Istnieje wiele innych sytuacji, w których rozmieszczenie może nagle zmienić się i spowodować zamieszanie. Oto kilka przykładów:
- Rozmieszczenie może się zmienić, jeśli projektor jest podłączany do komputera, a rozdzielczość ekranu się zmienia (co jest szczególnie frustrujące, ponieważ użytkownik chce zaprezentować coś publiczności i nie może znaleźć ikonki, ludzie czekają).
- Jeśli zmienisz rozmiar urządzenia (takie jak większy monitor lub inny smartfon), będziesz musiał ponownie nauczyć się, gdzie wszystko jest.
- Układy często zmieniają się wraz z nowymi wersjami oprogramowania (co jest jednym z powodów, dla których aktualizacja za każdym razem, gdy pojawi się nowa wersja oprogramowania, może nie być najlepszym pomysłem).
- To samo oprogramowanie w innym systemie operacyjnym może mieć nieco inny układ (np. jeśli osoba używała przeglądarki Chrome cały czas w systemie Windows i zaczyna używać Chrome w systemie MacOS). Może to być szczególnie frustrujące, ponieważ położenie wspólnych elementów sterujących (okno zamknięcia / maksymalizacji, a nawet klawisz kontrolny na klawiaturze) jest inne, co sprawia, że użytkownik, kierujący się pamięcią przestrzenną, zaczyna być zagubiony.
- [Wstążka](https://pl.wikipedia.org/wiki/Wst%C4%85%C5%BCka_(informatyka)) Microsoft Word była szczególnie frustrująca dla użytkowników, gdy pojawiła po raz pierwszy — pozycja każdego elementu menu była zupełnie inna niż w poprzednich wersjach.
- interfejsy automatycznie dopasowujące się do zachowań użytkownika również mogą stanowić problem; może się wydawać, że dobrym pomysłem jest zmienianie menu w programie, tak aby często używane opcje były wyżej niż te używane rzadziej lub nieużywane przedmioty były ukryte, ale może to prowadzić do frustrującego poszukiwania opcji, przypominającego niekiedy poszukiwanie skarbów.
{panel end}

Powiązana z pamięcią przestrzenną jest nasza *pamięć ruchowa*, która pomaga nam zlokalizować przedmioty bez konieczności uważnego patrzenia. Być może wybierasz niekiedy typowy przycisk za pomocą myszy, przesuwając dłoń na odległość taką jak zwykle, bez patrzenia.
Praca z nową klawiaturą może oznaczać konieczność ponownego nabycia pewnych nawyków ruchowych, a więc może trochę spowolnić pracę lub spowodować naciśnięcie niewłaściwych klawiszy.

### Brakujący przycisk

Jednym z powszechnych błędów człowieka, który musi być rozważony przy projektowaniu inferfejsu, jest *błąd o jeden* (ang. *off by one error*), w którym użytkownik przypadkowo klika lub wpisuje element obok tego, w którym zamierzał.
Na przykład, jeśli element menu „zapisz” znajduje się obok pozycji menu „usuń”, jest to ryzykowne, ponieważ jedno małe przesunięcie może spowodować, że użytkownik usunie plik zamiast go zapisać.
Podobny problem występuje na klawiaturach; na przykład gdyby CONTROL-W zamykał tylko jedno okno w przeglądarce, a CONTROL-Q zamykał całą przeglądarkę, to na klawiaturze, w której te dwa przyciski sąsiadują, byłby to problem. Oczywiście można to naprawić poprzez zapytanie użytkownika, czy kończy pracę, czy zapisać wszystkie okna, aby użytkownik mógł odzyskać to, nad czym pracował, po ponownym otworzeniu przeglądarki. Może się to również zdarzyć w formularzach internetowych, w których obok przycisku wysyłania znajduje się przycisk czyszczenia, a błąd o jeden powoduje, że użytkownik traci wszystkie dane, które właśnie wprowadził.

{image filename="reset-submit.png" alt="Ryzykowny inferfejs."}


{comment}
.. xjrm dodał w menu „Akcje”, z „Zamów pizzę”, „Uruchom atak nuklearny”, „Uruchom helikopter zabawkowy”. Każdy po prostu natychmiastowo wyświetla okno dialogowe z napisem „Pizza zamówiona” itd.
{comment end}

### Niebiezpieczne zadanie — duży wysiłek

Innym pomysłem stosowanym przez projektantów HCI jest *zasada współmiernego wysiłku*, która mówi, że często wykonywane, proste zadania powinny być łatwe do zrobienia, ale dobrze jest wymagać skomplikowanej procedury złożonego zadania. Na przykład w edytorze tekstu drukowanie strony w takiej postaci, w jakiej jest wyświetlana, powinno być łatwe, ale jest w porządku, jeśli wymaga pewnego wysiłku drukowanie dwustronnie, dwie strony na jednej, ze zszywką w lewym górnym rogu itp. W rzeczywistości czasami więcej wysiłku należy *wymagać*, jeśli polecenie ma poważne konsekwencje, takie jak usunięcie pliku, wyczyszczenie urządzenia lub usunięcie konta. W takich przypadkach można dodać sztuczne zadania, takie jak pytanie „Czy jesteś pewien?”. Można też sprawić, by ustawienie nietypowej dla urządzenia wartości (np. ustawienie napięcia zasilania) wymagało wielokrotnego naciśnięcia przycisku „w górę”, a nie pozwalać użytkownikowi na wpisanie dodatkowych kilku zer.

{interactive name="action-menu" type="in-page"}

### W skrócie

To tylko kilka pomysłów z HCI, które pomogą ci zdać sobie sprawę z tego, z jakimi problemami możemy mieć do czynienia, tworząc interfejsy.
W poniższym projekcie możesz zaobserwować tego typu problemy z pierwszej ręki, oglądając *kogoś innego* używającego interfejsu, zauważając wszelkie problemy, które ta osoba ma.
O wiele łatwiej jest obserwować kogoś innego niż to zrobić samemu; częściowo dlatego, że ciężko jest skoncentrować się na interfejsie i robić notatki w tym samym czasie, a częściowo dlatego, że już znasz interfejs i nauczyłeś się pokonywać niektóre trudności.

{panel type="project" title="Projekt" summary="Myśl na głos"}
W projekcie „Myśl na głos” obserwujesz kogoś, kto korzysta z interfejsu, który chcesz ocenić, i zachęcasz go do wyjaśnienia, co myśli na każdym kroku.
Będziesz robić notatki na temat tego, co mówi, i na tej podstawie oceniać interfejs (nagranie całego zdarzenia może być pomocne).

Ten sposób podejścia do problemu daje wgląd w to, co może być mylące w interfejsie i dlaczego.

Na przykład, jeśli ktoś ustawia budziki mówi „Naciskam przycisk w górę, aż dojdę do 7 rano — o nie! zatrzymał się na 7:09, teraz muszę iść dalej aby dojść do 7:00”, to już wiesz, jak interfejs może przeszkodzić użytkownikom w skutecznym wykonaniu zadania.

Takie podejście koncentruje się na obserwacji użytkownika wykonującego określone *zadanie*, aby uchwycić to, co dzieje się w rzeczywistości, gdy ludzie używają interfejsu.
*Zadania* często są mylone z *funkcjami*; używasz funkcji urządzenia do wykonania zadania.
Na przykład aparat może mieć funkcję robienia wielu zdjęć szybko, ale odpowiednim zadaniem jest „zrobienie zdjęcia jakiegoś zdarzenia, wybranie najlepszego zdjęcia i udostępnienie go”.
Może to obejmować wiele działań użytkownika: wchodzenie w tryb wielu zdjęć, konfigurowanie aparatu pod kątem warunków oświetleniowych, robienie zdjęć, wybieranie najlepszego, łączenie się z komputerem, przesyłanie zdjęcia na stronę internetową i udostępnianie go przyjacielowi.

Projekt będzie bardziej interesujący, jeśli osoba ci pomagająca nie jest w pełni zaznajomiona z systemem lub jeśli jest to system, który często jest mylący lub frustrujący dla użytkownika.
Twój zapis może być wykorzystany do podjęcia decyzji o ulepszeniu systemu w przyszłości.

Zadanie może polegać na ustawieniu czasu na zegarze, znalezieniu ostatnio wybranego numeru na nieznanym telefonie lub wybraniu programu telewizyjnego do nagrania.

Aby dokonać oceny, należy przekazać urządzenie swojemu pomocnikowi, objaśnić sposób działania i poprosić o wyjaśnienie, co myśli na każdym kroku.
Twój pomocnik może nie być do tego przyzwyczajony, więc możesz pomoc mu poprzez zadawanie pytań, na przykład takich:
  - Co zamierzasz teraz zrobić? Dlaczego?
  - Dlaczego wybrałeś ten przycisk?
  - Czego szukasz?
  - Czy masz trudności? Jaki jest problem?
  - Czy widzisz, co poszło nie tak?
  - Co o tym myślisz?

Jeśli zrozumie on „myślenie na głos”, po prostu milcz i rób notatki.

Bardzo ważne jest, aby nie krytykować ani nie zastraszać pomocnika!
Jeśli popełni błąd, spróbuj dowiedzieć się, w jaki sposób interfejs spowodował, że zrobił coś niewłaściwego, zamiast go obwiniać.
Wszelkie popełnione przez niego błędy będą cenne dla twojego projektu!
Jeśli wszystko zrobi dobrze, nie będzie to zbyt interesujące.

Gdy skończysz notować, przejrzyj notatki i zastanów się, dlaczego użytkownik miał problemy. Przykłady przedstawione w tym rozdziale wyczulą cię na problemy związane z interfejsem i pomogą znaleźć sposoby jego ulepszenia.

Więcej informacji o metodzie myślenia na głos znajdziesz w artykułach po angielsku: w [Wikipedii](https://en.wikipedia.org/wiki/Think_aloud_protocol), na [stronie Jakoba Nielsena](https://www.nngroup.com/articles/thinking-aloud-the-1-usability-tool/) i w notatkach [studentów zajmujących się HCI](http://www.psy.gla.ac.uk/~steve/HCI/cscln/trail1/Lecture5.html).
{panel end}


{panel type="project" title="Projekt" summary="Przejście poznawcze"}
Innym sposobem oceny interfejsu jest *przejście poznawcze* (ang. *Cognitive Walkthrough*).
Zwykle robi się to bez angażowania kogoś innego, ale my proponujemy dla uproszczenia włączyć w projekt innego użytkownika.
*Przejście poznawcze* to technika, której używają eksperci HCI do szybkiej oceny interfejsu.
Jest to szczególnie przydatne przy ocenie interfejsów o kilku krokach, które są wykorzystywane przez nowych lub okazjonalnych użytkowników (np. osoby korzystające z automatu biletowego na lotnisku, ustawiające budzik w pokoju hotelowym lub używające wyświetlacza muzealnego).

Pierwszym krokiem jest wybranie typowego zadania, przy którym ktoś używałby oceniany interfejs (np. wydrukowanie biletu 2-godzinnego, ustawienie alarmu na 5:20 rano lub wyszukanie danego eksponatu w muzeum).

Celem przejścia poznawczego jest ustalenie: czy użytkownik widzi wskazówki, co należy zrobić na każdym etapie, czy jest coś mylącego lub niejednoznacznego (na przykład przycisk, który należy nacisnąć), czy użytkownik jest pewien, że wykonana została prawidłowa rzecz.

Doświadczony oceniający zrobiłby to samodzielnie, wyobrażając sobie, co zrobiłby użytkownik na każdym kroku, ale dla ciebie zapewne będzie łatwiej oglądać interfejs cudzymi oczami, obserwując użytkownika (np. twojego przyjaciela).

Zadanie powinno mieć 3 lub 4 kroki (np. naciśnięcia przycisków), a na każdym etapie będziesz zadawać trzy pytania i robić notatki na temat udzielonych odpowiedzi.
Powinieneś wiedzieć, jak wykonać to zadanie samemu, ponieważ jeśli użytkownik zboczy z trasy, możesz mu pomóc, zamiast obserwować, jak próbuje wydostać się z problemu HCI, który nie jest przedmiotem twoich badań w tym momencie.
Zadanie może polegać na nagrywaniu 10-sekundowego filmu wideo na telefonie komórkowym, usuwaniu wiadomości tekstowej lub ustawianiu kuchenki mikrofalowej w celu ponownego podgrzania jedzenia na 45 sekund.

Przedstaw interfejs swojemu pomocnikowi, nie udzielając żadnych instrukcji na jego temat i powiedz mu, jaki jest cel zadania.
Zanim podejmie on jakieś działanie, zapytaj:
  - Czy wiesz, co powinieneś zrobić na tym etapie?
Następnie poproś go o spojrzenie na interfejs i zapytaj:
  - Czy widzisz, jak to zrobić?
Następnie niech wykona akcję, którą zasugerował, i zapytaj:
  - Czy jesteś w stanie powiedzieć, że zrobiłeś to co trzeba?

Jeśli jego decyzje spowodują zejście ze ścieżki, możesz zresetować interfejs i zacząć od nowa, wyjaśniając, co zrobić w przypadku niewłaściwego kroku (ale notując, że to nie było oczywiste dla niego — będzie to punkt do rozważenia przy ulepszaniu interfejsu.)

Po zakończeniu pierwszego etapu powtórz powyższą procedurę w etapie drugim (może to być naciśnięcie przycisku lub wyregulowanie kontrolki).
Jeszcze raz zadaj trzy powyższe pytania.

W praktyce drugie pytanie (Czy widzisz, jak to zrobić?) jest zwykle podzielone na dwie części: czy użytkownik w ogóle zauważa daną kontrolkę, a jeśli tak, to czy zdaje sobie sprawę, że jest potrzebna?
W tym ćwiczeniu uprościliśmy je do jednego pytania.

[Więcej informacji (po angielsku) o tym, jak wykonać przejście poznawcze, znajduje się na stronie CS4FN](http://www.cs4fn.org/usability/cogwalkthrough.php).

Informacje można też znaleźć [w angielskiej Wikipedii, pod hasłem Cognitive Walkthrough](https://en.wikipedia.org/wiki/Cognitive_walkthrough).
{panel end}

## Heurystyki użyteczności

{panel type="teacher-note" title="Dla nauczyciela" summary="Plakaty HCI dla twojej klasy!"}
Zestaw plakatów na tematy poruszone w tym rodziale opublikowała Jennifer Gottschalk. [Są one dostępne (w wersji angielskiej) formacie PDF tutaj](files/HCI-posters.pdf).
{panel end}

Ocenianie interfejsu najlepiej wykonać, zbierając opinie od wielu potencjalnych użytkowników. Jednak może to być kosztowne i czasochłonne, dlatego eksperci HCI wymyślili kilka szybkich reguł, które pomagają nam szybko wykryć oczywiste problemy. Formalne słowo określające prostą regułę pomagającą działać w skomplikowanych sytuacjach to *heurystyka*. W tej części przyjrzymy się pewnym typowym heurystykom, które można wykorzystać do oceny interfejsu.

Istnieją różne zestawy heurystyk, które ludzie zaproponowali do oceny interfejsów, ale duński badacz Jakob Nielsen wymyślił zestaw 10 wskazówek, które stały się bardzo szeroko stosowane i opiszemy je w tym podrozdziale. Jeśli napotkasz problem z użytecznością w interfejsie, prawie na pewno zauważysz, że nie zastosowano przynajmniej jednego z zaleceń Nielsena. Nie jest łatwo zaprojektować system, który jest zgodny ze wszystkimi tymi wskazówkami, czasem wręcz możesz nie chcieć ich stosować z ważnych powodów, dlatego nazywa się je wskazówkami, a nie prawami.

Oto przykład, świadczący o tym, że autorzy interfejsu nie podążali za wskazówkami Nielsena. Wyświetlony komunikat nie pomaga uzytkownikowi usunąć błąd (rzeczywisty błąd dotyczy tu ustawień sieciowych, a komunikat mówi coś o błędzie powodującym migotanie światła!). Ponadto przyciski „Pomiń”, „Anuluj” oraz „Ignoruj” nie nie są zrozumiałe dla użytkownika (intefejs musi być dopasowany do świata rzeczywistego!).

{image filename="time-capsule.png" alt="Mylenie się na wielu poziomach." side="right_wrap"}


### Widoczność statusu systemu

*System powinien zawsze informować użytkowników o tym, co się dzieje, poprzez odpowiednią informację zwrotną w rozsądnym czasie.*

Ta wskazówka mówi, że użytkownik powinien zawsze widzieć, co robi urządzenie (znać stan systemu). Nie chodzi tylko o to, by użytkownik wiedział, czy urządzenie jest włącznone, ale miał informacje o wielu innych procesach. Klasycznym przykładem jest klawisz CAPS LOCK, który powinien być wyraźnie widoczny, jeśli jest włączony, w przeciwnym wypadku podczas wpisywania hasła użytkownik może nie wiedzieć, dlaczego hasło zostało uznane za niepoprawne; pozytywnym przykładem tego jest sytuacja, gdy pole do wprowadzania hasła ostrzega cię, że klawisz CAPS LOCK jest włączony.

Jeden z najprostszych stanów dla urządzenia jest status włączony lub wyłączony, który zwykle jest oznaczony kolorowym światłem na zewnątrz komputera. Jednak niektóre urządzenia wymagają trochę czasu, aby pokazać status (na przykład niektóre odtwarzacze DVD potrzebują czasu, aby zareagować po włączeniu), a użytkownik może ponownie nacisnąć przycisk zasilania lub w inny sposób pomylić się co do stanu, w jakim jest obecnie urządzenie.

Istnieje wiele zadań, które użytkownicy chcą wykonać na komputerze, a które wymagają trochę czasu, w tym kopiowanie dokumentów, pobieranie plików i ładowanie gier wideo. W tej sytuacji jednym z najczęstszych sposobów informowania użytkownika o zadaniu jest pasek postępu.

{image filename="windows-busy-cursor-animation.gif" alt="Kursor zajęty w Windows" wrap="right"}
{image filename="apple-busy-cursor-animation.gif" alt="Kursor zajęty w Apple" wrap="right" remove-preceeding-line-break="true"}

Jednak wskaźniki postępu nie zawsze są pomocne; powyższe wskaźniki na załączonym obrazku nie wskazują, czy będziesz musiał poczekać kilka sekund, czy kilka minut (czy nawet godzin) na wykonanie zadania, co może być frustrujące.

Przekazywanie informacji w „rozsądnym czasie” jest naprawdę ważne, a „rozsądny czas” jest często krótszy niż myślisz. W jednym z poprzednich podrozdziałów zachęciliśmy cię do eksperymentu badającego, w którym momencie dostrzeżesz opóźnienie reakcji; prawdopodobnie odkryłeś, że była to około jedna dziesiąta sekundy. Jeśli komputer potrzebuje więcej czasu na odpowiedź, może to być frustrujący w użyciu.

{image filename="xkcd-estimation.png" hover-text="Mogliby powiedzieć, że „połączenie jest prawdopodobnie stracone”, ale fajniej jest robić naiwne uśrednienie czasu, by dać ci nadzieję, że jeśli poczekasz około 1 163 godzin, to w końcu operacja zostanie wykonana." alt="Autor windowsowego okienka kopiowania odwiedza znajomych i nie może zdecydować, kiedy przybędzie." source="https://xkcd.com/612/"}

W ocenie interfejsu trzeba brać pod uwagę również inne czasy opóźnionych reakcji: opóźnienie około 1 sekundy srawia, że naturalna rozmowa staje się uciążliwa, a około 10 sekund nakłada na użytkownika duże obciążenie, aby zapamiętać, co robi. Polecamy [artykuł (po ang.) na ten temat](http://www.nngroup.com/articles/response-times-3-important-limits/). Jeśli chcesz przetestować, jak to wszystko wpływa na człowieka, spróbuj porozmawiać z kimś, czekając 3 sekundy przed każdą odpowiedzią lub przerywając od czasu do czasu na 10 sekund wypowiadanie zdania!

A jeśli jeszcze tego nie wypróbowałeś, skorzystaj z poniższego narzędzia interaktywnego.

{interactive name="delay-analyser" type="whole-page" text="Interaktywny tester opóźnień"}

Szybka reakcja komputera zależy często od zastosowanych algorytmów (omówionych w rozdziale dotyczącym algorytmów) i może również zależeć od sposobu, w jaki dany program działa (np. czy przechowuje dane na dysku, czy oczekuje na odpowiedź serwera przed kontynuowaniem itp.) Jest to szczególnie widoczne na małych urządzeniach, takich jak smartfony, które mają ograniczoną moc obliczeniową — może zająć sekundę lub dwie, aby otworzyć aplikację lub odpowiedzieć na niektóre dane wejściowe. Nietrudno jest znaleźć takie opóźnienia w systemach podczas ich oceny.

### Dopasuj system do świata rzeczywistego

*System powinien posługiwać się językiem użytkowników, słowami, wyrażeniami i pojęciami znanymi użytkownikowi, a nie systemowymi. Podążaj za powszechnymi w świecie rzeczywistym konwencjami, dzięki czemu informacje pojawiają się w naturalnej i logicznej kolejności.*

Język, kolory i zapisy w interfejsie powinny pasować do świata użytkownika, a choć wydaje się to oczywiste i sensowne, często bywa pomijane. Weźmy na przykład następujące dwa przyciski — czy widzisz, co w nich jest mylące?

{interactive name="confused-buttons" type="in-page"}

{panel type="teacher-note" title="Dla nauczyciela" summary="Odpowiedź na to, co jest nie tak z przyciskami"}
Przyciski mają zamienione kolory; kolor dla anulowania jest zielony (zwykle używany do przejścia dalej), a kolor potwierdzenia jest czerwony (zwykle używany do zatrzymania lub ostrzeżenia).
{panel end}

Poniższy interfejs pochodzi z systemu bankowego służącego do płacenia. Załóżmy, że otrzymujesz email z prośbą o zapłacenie 1699,50 USD za używany samochód; spróbuj wpisać w polu $1699.50.

{interactive name="payment-interface" type="in-page"}

Notacja „$1699.50” jest popularnym sposobem wyrażenia kwoty w dolarach, ale system ten zmusza do przestrzegania własnych konwencji (prawdopodobnie po to, aby ułatwić coś programiście, który napisał system).

Spróbuj znaleźć inne kwoty, które są po ludzku prawidłowe, ale system je odrzuca. W idealnej sytuacji system powinien być elastyczny w stosunku do wprowadzanego tekstu, aby zapobiec błędom.

{panel type="spoiler" title="Spojler" summary="Odpowiedzi do powyższego, spróbuj sam przed przeczytaniem tego!"}
Okienko dialogowe odrzuca także przecinki (jako anglosaski separator tysięcy) w danych wejściowych, np. „1,000”, mimo że bywają stosowane, by łatwiej było przeczytać duże kwoty (w Polsce częściej używane są w tej roli odstępy [przyp. tłum.]) Nie pozwala także na spację przed lub po liczbie, ale jeśli liczba została skopiowana i wklejona z wiadomości email, może wyglądać zupełnie dobrze. Mniej leniwy programista pozwoliłby na takie sytuację; zamiast tego prawdopodobnie użył prostego systemu konwersji liczb, aby sobie oszczędzić dodatkowego programowania...
{panel end}

### Kontrola użytkownika i wolność

*Użytkownicy często przez pomyłkę wybierają jakąś funkcję w systemie i będą potrzebować wyraźnie oznaczonego „wyjścia awaryjnego”, aby opuścić niepożądany stan bez przydługiego dialogu z systemem. Trzeba umożliwić uzytkownikowi cofanie i ponawianie akcji.*

Bardzo frustrujące jest popełnienie błędu i brak wyjścia. Jest to szczególnie złe, jeśli jedna mała operacja może wymazać wiele godzin pracy, której nie można odzyskać. Przycisk resetowania w niektórych formularzach internetowych cieszy się z tego powodu złą sławą — często jest obok przycisku wysyłania i możesz wyczyścić wszystkie dane poprzez „błąd o jeden”.

Powszechnym sposobem na zapewnienie swobody użytkownikowi jest funkcja „cofania”, co oznacza, że nie tylko można łatwo naprawić błędy, ale zachęca się użytkownika by eksperymentował, wypróbowując funkcje interfejsu, wiedząc, że może je po prostu „cofnąć”, zamiast martwić się, że znajdzie się w stanie, którego nie może naprawić. Jeśli dostępne jest również „powtórzenie”, użytkownik może poruszać się w przód i w tył, decydując, który wybór jest najlepszy. (,,Powtórz'' jest tak naprawdę cofnięciem cofnięcia!)

Oto przykład przycisku, który nie zapewnia kontroli użytkownika; jeśli go naciśniesz, stracisz całą tę stronę i będziesz musiał znaleźć drogę powrotną (ostrzegaliśmy cię!):

{interactive name="close-window" type="in-page"}

{panel type="teacher-note" title="Dla nauczyciela" summary="OSTRZEGALIŚMY cię..."}
Naciśnięcie przycisku „tak” może być bardzo frustrujące! Większość nowoczesnych przeglądarek internetowych zapewnia pewną kontrolę i swobodę w tym przypadku — jeśli twoi uczniowie są sfrustrowani naciśnięciem przycisku, strona prawdopodobnie znajdzie się w ich menu historii (a niektóre przeglądarki mają nawet funkcję przywracania ostatniej strony zamkniętej).
{panel end}

Czasami interfejs może zmusić użytkownika do zrobienia czegoś, czego nie chce robić. Na przykład często zdarza się, że systemy operacyjne lub programy automatycznie wykonują aktualizacje, które wymagają ponownego uruchomienia. Czasami interfejs może nie dać użytkownikowi możliwości anulowania lub opóźnienia i zrestartować się. Jest to złe, ponieważ użytkownik może stracić całą niezapisaną pracę lub oczekiwać na ponowne uruchomienie systemu w czasie, gdy musi coś zaprezentować.

Inną powszechną formą tego problemu jest brak możliwości zamknięcia systemu. Pozytywnym przykładem jest przycisk „home” na smartfonach, który prawie zawsze zatrzymuje bieżącą aplikację.

### Spójność i standardy

*Użytkownicy nie powinni się zastanawiać, czy różne słowa, sytuacje lub działania oznaczają to samo. Przestrzegaj konwencji*.

Spójność (coś, co za każdym razem jest takie samo) jest niezwykle przydatna dla osób używających interfejsów i jest czasami nazywana „złotą regułą HCI”. Jeśli interfejs jest spójny z innymi interfejsami, nauka w jednym interfejsie przenosi się bezpośrednio do drugiego. Jednym z najlepszych przykładów spójności programów komputerowych jest kopiowanie i wklejanie, które działa w ten sam sposób w większości programów, więc użytkownicy muszą tylko raz nauczyć się tej czynności. Klawisze skrótów do kopiowania i wklejania są również dość spójne między programami. Jesli w programie kopiowanie / wklejanie zachowuje się inaczej, będzie to mylące dla użytkowników.

Niespójności można doświadczyć, pracując na arkuszu kalkulacyjnym, gdzie wynik naciśnięcia „CONTROL-A” (wybierz wszystko) zależy od tego, czy edytujesz komórkę, czy tylko wybierzesz komórkę (ten konkretny problem jest problemem „trybu”). Chociaż może to mieć sens dla użytkownika doświadczonego w arkuszach kalkulacyjnych, nowy użytkownik może być bardzo zdezorientowany, gdy to samo polecenie powoduje inną odpowiedź.

{image filename="xkcd-standards-cartoon.png" hover-text="Na szczęście, ładowanie urządzeń już nie jest problemem, gdy wszyscy stosujemy mini-USB. A może to miało być micro-USB? O nie!" alt="Komiks xkcd o standardach" source="https://xkcd.com/927/"}

Brak spójności często powoduje, że ludzie nie lubią nowego systemu. Jest szczególnie zauważalny dla użytkowników Mac i Windows; ktoś, kto używał tylko jednego systemu, może odbierać drugi jako bardzo frustrujący w użyciu, ponieważ wiele rzeczy jest inaczej zorganizowanych (chociażby elementy sterujące dla okienek, które znajdują się w innym miejscu i mają inne ikony). Doświadczony użytkownik jednego interfejsu, który uważa, że wszystko jest „oczywiste”, nie może zrozumieć, dlaczego druga osoba uważa to za frustrujące, a to może prowadzić do burzliwej dyskusji, który interfejs jest najlepszy. Podobne problemy wystepują, gdy na rynek wchodzi radykalnie odmienna wersja systemu operacyjnego (na przykład Windows 8); użytkownikom przestaje pomagać doświadczenie wypracowane w poprzednim systemie, a brak spójności (tj. utrata wcześniejszej wiedzy) jest frustrujący.

### Zapobieganie błędom

*Jeszcze lepsze niż dobre komunikaty o błędach, jest zapobieganie występowaniu błędów. Wyeliminuj sytuacje sprzyjające błędom lub wymagaj od użytkownika potwierdzenia wyboru, po którym będzie narażony na popełnienie błędu.*

Program komputerowy nie powinien ułatwiać ludziom popełniania poważnych błędów. Przykładem zapobiegania błędom w wielu programach jest „wyszarzenie” lub deaktywacja konkretnej pozycji menu na pasku narzędziu lub w rozwijanym menu. Uniemożliwia to użytkownikowi korzystanie z funkcji, która nie powinna być używana w tej sytuacji, np. próba skopiowania, gdy nic nie jest wybrane. Dobry program informuje również użytkownika, dlaczego dany element nie jest dostępny (na przykład w etykiecie danego narzędzia).

Poniżej znajduje się selektor dat; czy widzisz, jakie błędy można przez niego zrobić?

{interactive name="date-picker" type="in-page"}

{panel type="spoiler" title="Spojler" summary="Niektóre z błędów, które mogłeś zaobserwować"}
Selektor daty umożliwia użytkownikowi wybranie nieprawidłowych dat, np. 30 lutego lub 31 listopada. Trudno uzyskać poprawny trójelementowy selektor daty. Wprawdzie każdy element menu ogranicza to, co może być w innych, ale każdy może być zmieniony. Na przykład możesz wybrać 29 lutego 2008 r. (poprawna data), a następnie zmienić rok na 2009 (niepoprawna data), a następnie wrócić do 2008 r. Po wybraniu roku 2009 numer dnia musiałby zmienić się na 28, aby zapobiec błędom, ale jeśli to był tylko przypadek, a użytkownik zmienia z powrotem rok na 2008, zmieniony dzień mógłby zostać niezauważony. Lepiej jest użyć bardziej wyrafinowanego selektora dat, który pokazuje kalendarz, a użytkownik może klikać tylko poprawne daty (wiele stron to oferuje). Systemy do wyboru dat zwykle stanowią bogaty materiał do badań problemów z interfejsem!

{panel end}

Powiązanym problemem jest sytuacja, gdy użytkownik musi wybrać datę początkową i końcową (na przykład w czasie rezerwacji lotów lub hotelu); system powinien zablokować możliwość wybrania daty końcowej wcześniejszej niż początkowa.

Oto menu, który oferuje kilka opcji:

{interactive name="available-menu-items" type="in-page"}

Za każdym razem, gdy pojawia się okno dialogowe z informacją, że nie wolno ci wykonać określonej czynności, jest to frustrujące i znacznie lepiej by było, gdyby uzytkownik nie mógł wybrac niedozwolenej opcji. Oczywiście zapobieganie takim sytuacjom jest trudne, bo nie sposób przewidzieć wszystkich zachowań uzytkownika.

Dobrym przykładem do rozważenia jest bankomat, który może wydawać tylko banknoty 20 zł.
Jeśli pozwala wprowadzić dowolną kwotę (np. 53,92 zł lub nawet 50 zł), wystąpi błąd.
Jakiego rodzaju zabieczenia przed takimi błędami spotkałeś w bankomatach?

{panel type="teacher-note" title="Dla nauczyciela" summary="Zapobieganie błędom bankomatów"}
Niektóre bankomaty uniemożliwiają wprowadzenie nieprawidłowej kwoty, oferując jedynie konkretne kwoty do wypłaty i / lub wyświetlając przyciski takie jak +20 zł i - 20 zł.
Wyszukanie w Internecie obrazów „wpisywanie kwoty w bankomacie” może przypomnieć ci kilka różnych sposobów, jak interfejsy radzą sobie z tym problemem (lub powodują problem!). 
Interfejs dotyczący wpłaty jest diametralnie inny, ale przez to zmniejsza spójność!
{panel end}

Oto kolejny przykład: poniższy kalkulator ma tryb binarny, w którym wykonuje obliczenia na liczbach binarnych.
Problem polega na tym, że w tym trybie można nadal wpisywać cyfry dziesiętne, co powoduje błąd podczas wykonywania obliczeń.
Użytkownik może po prostu nie zauważyć, że jest w trybie binarnym, a komunikat o błędzie nie jest szczególnie pomocny!

{image filename="binary-calculator-screenshot.png" alt="Kalkulator w trybie binarnym, który nadal pozwala wpisywać cyfry inne niż 0 i 1, ale wyświetla błąd później."}

### Widzieć zamiast pamiętać
*Zminimalizuj obciążenie pamięci użytkownika, wyświetlając dostępne obiekty, akcje i opcje. Przy wyświetlaniu okienka dialogowego nie każ użytkownikowi pamiętać, co było w okienku poprzednim. Instrukcja użytkowania systemu powinna być widoczne lub łatwa do odzyskania w razie potrzeby.*

Ludzie są na ogół bardzo dobrzy w rozpoznawaniu przedmiotów, za to komputery lepiej je „pamiętają”. Dobrym tego przykładem jest system menu; jeśli klikniesz na menu „Edycja” zobaczysz wszystkie dostępne opcje edycyjne i łatwo wybierzesz interesującą cię opcję.
Jeśli zamiast tego musiałbyś wpisać polecenie z pamięci, byłoby to dla ciebie bardziej uciążliwe.
Ogólnie rzecz biorąc, dobrze jest, aby komputer „zapamiętywał” szczegóły, a użytkownik mógł wyświetlać opcje, zamiast je pamiętać.
Wyjątkiem jest system, który jest cały czas używany przez eksperta, który zna wszystkie opcje; w tym przypadku bezpośrednie wprowadzanie poleceń może być bardziej elastyczne i szybsze niż wybór z listy.

Na przykład, gdy wpiszesz nazwę miejsca na mapie online, system może zacząć sugerować nazwy w oparciu o to, co piszesz, uwzględniając twoją lokalizację lub poprzednie wyszukiwania.
Widzimy na poniższym obrazku, że system podpowiedział nazwy miejsc, na podstawie wpisanych przez użytkownika czterch liter. Dzięki temu uwolnił uzytkownika od konieczności wpisywania całego wyrazu „Taumatawhakatangihangakoauauotamateapokaiwhenuakitanatahu”; użytkownik może go po prostu wybrać.
Podobna funkcja w przeglądarkach internetowych chroni użytkowników przed koniecznością zapamiętania dokładnych adresów URL, z których korzystali w przeszłości; system, który wymagałby wpisania dokładnych nazw miejsc przed ich wyszukaniem, byłby dość frustrujący.

{image filename="recognition-place-names.png" alt="Mapa podpowiadająca nazwy miejsc"}

### Elastyczność i wydajność użytkowania

*Akceleratory — nieznane początkującemu użytkownikowi — bezcenne dla eksperta. Pozwól użytkownikom dostosowywać system do swoich potrzeb.*

Kiedy ktoś korzysta z oprogramowania każdego dnia, wkrótce zacznie powtarzać pewne sekwencje operacji (np. „Otwórz plik, znajdź następne puste miejsce, wpisz w rejestr to, co właśnie się stało”). Dobrze jest zaproponować sposoby szybkiego wykonania tej czynności, takie jak „makra”, które wykonują sekwencję czynności za jednym naciśnięciem klawisza.

Podobnie, dobrze jest móc dostosować oprogramowanie, przypisując klawisze do częstych działań (takich jak „zapisz tę wiadomość email w folderze oczekujące”).
Typowe zadania, takie jak kopiowanie i wklejanie, zwykle mają dodane do nich klawisze, które umożliwiają doświadczonym użytkownikom wykonywanie zadań bez konieczności sięgania po mysz.

Ważnym obszarem badań w HCI jest wypracowywanie sposobów łatwego uczenia się na skróty.
Nie chcesz, aby przeszkadzały one początkującym, ale nie chcesz, aby doświadczeni użytkownicy byli ich pozbawieni.
Prostym sposobem na to jest posiadanie w menu skrótów klawiszowych (akceleratorów) dla poszczególnych pozycji menu. Wyświetlone menu pokazuje, że SHIFT-COMMAND-O otworzy nowy projekt, aby użytkownik mógł nauczyć się tej sekwencji, jeśli często używa tego polecenia.
{image filename="menu-keystroke-equivalent.png" alt ="Menu ze skrótami klawiszowymi" wrap ="left"}
Elastyczny system pozwoliłby użytkownikowi dodać skrót klawiszowy np. dla polecenia „Zamknij panel”, gdyby okazało się, że jest często używany.
System może nawet podpowiadać uzytkownikowi utworzenie skrótu, jeśli zauważy, że czynność jest wykonywana często.
Innym rozwiązaniem jest przesuwanie przez system do góry menu opcji najczęściej używanych.

### Estetyczny i minimalistyczny wygląd

*Okna dialogowe nie powinny zawierać informacji, które są nieistotne lub rzadko potrzebne. Każda dodatkowa jednostka informacji w okienku konkuruje z ważnymi jednostkami informacji i zmniejsza ich względną widoczność.*

Oprogramowanie może zawierać wiele funkcji, a jeśli wszystkie są widoczne w tym samym czasie (na przykład na pasku narzędzi), może to być przytłaczające, szczególnie dla nowego użytkownika.

Pilot do telewizora często stanowi świetny przykład skomplikowanego interfejsu.
Jednym z powodów, dla których ma tak wiele przycisków, jest to, że może sprawić, że urządzenie będzie wyglądało imponująco w sklepie. Jednak gdy będziesz go używać w domu, wiele przycisków będzie zbędnych lub mylących.
{image filename="remote-complex.jpg" alt="Złożony pilot TV" wrap="left"}
Pokazany tutaj pilot zdalnego sterowania ma kilka przycisków, które mogą potencjalnie zrobić to samo: „Direct Navigator”, „Guide”, „Function Menu”, „Status” i „Option” dają dostęp do różnych funkcji, ale trudno przewidzieć, które jest która.
Ten pilot ma w sumie około 55 przycisków!

{image filename="remote-simple.jpg" alt="Prosty pilot." wrap="left"}
Natomiast pilot Apple ma bardzo mało przycisków i jest dobrym przykładem minimalistycznego interfejsu.
Jest tylko jedno „Menu” do wyboru, więc jest dość oczywiste, co zrobić, aby wybrać potrzebne ustawienia.
Oczywiście prosty pilot sprawi, że wyświetli się menu na ekranie, a ono ma potencjał, aby uczynić rzeczy bardziej skomplikowanymi.

{image filename="remote-adapted.jpg" alt="Dostosowany pilot TV." wrap="left"}
Na trzecim rysunku widzimy, jak można uprościć skomplikowany pilota, aby użytkownik nie musiał czytać rozległych informacji w instrukcji obsługi.
To trochę drastyczne, ale może zaoszczędzić użytkownikowi dostępu do trybów, z których nie może się wydostać!
Niektóre piloty starają się oferować najlepsze z obu światów, mając małą klapkę, którą można otworzyć, aby mieć dostęp do wszystkich funkcji.


{panel type="curiosity" title="Ciekawostka" summary="Przerażające interfejsy"}
Oto witryna z listą „najbardziej przerażających” interfejsów, z których niektóre są świetnymi przykładami *nie*posiadania minimalistycznego wzornictwa: [najbardziej przerażające interfejsy](http://okcancel.com/archives/article/2005/11/the-scariest-interface-part-ii.html).

Rysownik [Roz Chast](http://rozchast.com/) w swojej kreskówce [„Jak babcia widzi pilota”](http://www.art.com/products/p15063313199-sa-i6845922/roz-chast-how-grandma-sees-the-remote-new-yorker-cartoon.htm) ilustruje, jak przerażający może być pilot.

{panel end}



### Pomóż użytkownikom rozpoznać, zdiagnozować i naprawić błędy

*Komunikaty o błędach powinny być wyrażone w prostym języku (bez kodów), dokładnie wskazywać problem i konstruktywnie proponować rozwiązanie.*

Nie jest trudno znaleźć komunikaty o błędach, które tak naprawdę nie mówią, co jest nie tak!
Najczęstsze przykłady to komunikaty typu „Nieznany błąd, „Numer błędu -2431”” lub „Błąd jednej z wartości wejściowych”. Zmuszają one użytkownika do przeprowadzenia *procedury debugowania*, aby dowiedzieć się, co poszło nie tak, a może to być cokolwiek, od rozłączonego kabla lub problemu kompatybilności do brakującej cyfry w liczbie.

Na przykład pewne oprogramowanie do rozwiązywania problemów wygenerowało poniżej „nieoczekiwany” błąd.
Komunikat o błędzie jest szczególnie nieprzydatny, ponieważ oprogramowanie miało pomóc w znalezieniu problemów, ale zamiast tego dało użytkownikowi nowy problem do rozwiązania!
Na obrazku nie pokazujemy wszystkich szczegółów, ale było tam jeszcze kilka dodatkowych informacji, takich jak „Ścieżka: Nieznana” i „Kod błędu: 0x80070002”.
Wyszukiwanie kodu błędu w sieci może pomogłoby użytkownikowi, ale mogłoby też doprowadzić do znalezienia szkodliwego rozwiązania (np. zainstalowania czegoś z niewiarygodnego źródła). Nie udostępniając przydatnych informacji o odzyskiwaniu błędów, system zostawił użytkownika na łasce dostępnych porad internetowych!

{image filename="error-vague.png" alt="Nieprawidłowy komunikat o błędzie: Wystąpił nieoczekiwany błąd."}

Innym przykładem kiepskiej obsługi błedów jest wyświetlanie komunikatu z alternatywą, typu „Plik może nie istnieć lub może już być w użyciu”.
Poprawny komunikat pozwoliłby użytkownikowi na ustalenie, który z nich jest problemem.

A teraz pozytywny przykład, na podstawie budzika na smartfonie z systemem Android.
Na rysunku widać, że czas alarmu ustawiony jest na „9:00”.
W kraju, który korzysta z 12-godzinnego czasu, użytkownik może pomylić to z 21:00, a alarm włączy się w niewłaściwym czasie.
{image filename="android-alarm-9am.png" alt="Alarm w Androidzie ustawiony na 9:00."}

Interfejs daje jednak możliwość zauważenia tego, ponieważ wyświetlacz wskazuje, jak długo potrwa, zanim alarm się włączy, dzięki czemu łatwiej będzie rozpoznać błąd wyboru niewłaściwego czasu (lub dnia).
{image filename="android-alarm-message.png" alt="Komunikat Androida z budzikiem pokazujący, jak długo potrwa wywołanie alarmu."}


### Pomoc i dokumentacja

Oczywiście najlepiej by było, gdyby do korzystania z systemu nie była potrzebna instrukcja, ale nawet wtedy należy zapewnić użytkownikowi pomoc i dostęp do dokumentacji. Wszelkie takie informacje powinny być łatwe do wyszukania, skoncentrowane na tym, co użytkownik ma do zrobienia, wymieniać konkretne kroki do wykonania i nie być zbyt obszerne. Poniższe interaktywne narzędzie ilustruje sytuację, w której mogłeś się kiedyś znaleźć!
{interactive name="no-help" type="in-page"}

Często instrukcja obsługi koncentruje się na funkcjach (na przykład na katalogu pozycji menu), a nie skupia się na zadaniach (nie podaje co zrobić krok po kroku, by wykonać typowe zadanie). Gdy użytkownik potrzebuje pomocy, zwykle ma do wykonania zadanie (takie jak przesłanie zdjęć z aparatu), a dobra dokumentacja powinna wyjaśniać, jak to zrobić, zamiast wyjaśniać każdą funkcję (np. „Ustawienie trybu aparatu na USB”).


### Aby dowiedzieć się więcej

Możesz znaleźć więcej informacji o [heurystyce użyteczności na stronie Jakoba Nielsena](http://www.nngroup.com/articles/ten-usability-heuristics/) (po angielsku).

## Podsumowanie

W tym rozdziale mówiliśmy o tym, czym się kierować przy ocenie interfejsów, ale nie mówiliśmy wiele o tym, jak zaprojektować dobre interfejsy. Jest to zupełnie inna historia, chociaż możliwość zobaczenia, co może być złego w interfejsie, jest dobrą podstawą do projektowania dobrych interfejsów. Wiele komercyjnych systemów testuje się, wykorzystując powyższe pomysły, aby sprawdzić, czy ludzie uznają je za łatwe w użyciu; w rzeczywistości przed wydaniem nowej aplikacji często są one testowane wielokrotnie z wieloma użytkownikami.
Robi się poprawki, a następnie kolejne testy, aby sprawdzić, czy ulepszenia nie pogorszyły pod jakimś wzgledem interfejsu!
Nic dziwnego, że dobre oprogramowanie może być drogie — wiele osób dużo czasu poświęca się na upewnienie się, że jest ono łatwe w użyciu.


Istnieje wiele innych zagadnień z psychologii, fizjologii, socjologii, a nawet antropologii, które muszą znać eksperci HCI. Oto kilka z nich (wszystkie artykuły są po angielsku): [modele mentalne ](https://en.wikipedia.org/wiki/Mental_model), o tym jak system działa w mniemaniu ludzi w porównaniu z tym, jak system działa naprawdę (np. ludzie często klikają dwa razy na ikonkę, podczas gdy wystarczy kliknąć ją raz); 
[prawo Fittsa](https://pl.wikipedia.org/wiki/Prawo_Fittsa), o tym, ile czasu zajmuje wskazanie obiektów na ekranie (np. kliknięcie małego przycisku);
[prawo Hicka](https://en.wikipedia.org/wiki/Hick's_law), o tym, ile czasu zajmuje dokonanie wyboru między wieloma opcjami (np. z menu);
[prawo Millera](https://pl.wikipedia.org/wiki/Liczba_Millera) o liczbie przedmiotów, o których dana osoba może myśleć na raz;
[afordancje](https://pl.wikipedia.org/wiki/Afordancje), o tym, jak właściwości obiektu pomagają nam posługiwać się nim;
[projektowanie interakcji (IxD)](https://pl.wikipedia.org/wiki/Projektowanie_interakcji), o tworzeniu urządzeń cyfrowych;
[NASA TLX (wskaźnik obciążenia zadaniami)](https://en.wikipedia.org/wiki/NASA-TLX) do oceniania postrzeganego obciążenia pracą.

{comment}
.. xtcb sprawdź grupę HCI; mógłby dodać powyższe: hipoteza Sapira-Whorfa <https://pl.wikipedia.org/wiki/Hipoteza_Sapira-Whorfa>`, o tym, jak struktura języka wpływa na postrzeganie świata,
{comment end}

### Dalsza lektura

- Książka „Projektowanie z myślą o umyśle” (ang. „Designing with the mind in mind”) Jeffa Johnsona porusza wiele zagadnień omawianych w tym rozdziale.

- [Strona CS4FN](http://www.cs4fn.org/fundamentals/hci.php) (po angielsku) zawiera wiele artykułów i ćwiczeń o interakcji człowiek — komputer, takich jak [problemy związane z raportowaniem problemó z interfejsem](http://www.cs4fn.org/chi-med/reportingincidents.php), [problemy kulturowe w projektowaniu interfejsów](http://www.cs4fn.org/usability/tzeltal.php), o [znaczeniu Sushi](http://www.cs4fn.org/usability/importanceofsushi.php).

- Klasyczną książką o użyteczności jest „Psychologia rzeczy codziennych” (ang. „The psychology of everyday things”), której tytuł zmieniono później na „Projekt codziennych rzeczy” (ang. „The design of everyday things”) Dona Normana. Opowiada o przedmiotach codziennego użytku, takich jak drzwi i telefony i zawiera wiele prowokujących i często humorystycznych przykładów.

### Ciekawe odnośniki

- [Dziesięć wskazówekj Nielsena](http://www.nngroup.com/articles/ten-usability-heuristics/) (po angielsku) i [zbiór artykułów na temat heurystyki użyteczności](http://www.nngroup.com/topic/heuristic-evaluation/) (również po angielsku).
- [Materiały na temat HCI na stronie internetowej CS4FN](http://www.cs4fn.org/fundamentals/hci.php) (po angielsku).
- [Glosariusz terminów użyteczności w języku angielskim](http://www.usabilityfirst.com/glossary/).

{comment}
.. xjrm wszystko stąd wydaje się być surownym materiałem; Powinienem to kiedyś przejrzeć (!), ale czy możesz to łatwo skomentować? inaczej umieść to gdzieś indziej z linkiem tutaj, aby łatwo było go znaleźć? -tim

.. xtcb umieść materiały stąd w tekście notatki/teksty nauczyciela

 Pomysły na materiał:
 Proces myślenia na głos: Obserwator musi nacisnąć uczestnika, aby wyjaśnić swój proces. Może być zawstydzające i łatwe aby być wzburzonym
 Eksperyment kooperacyjny: 2 osoby i proces zamienia się w dialog i stają się krytyczni wobec procesu.
{comment end}
