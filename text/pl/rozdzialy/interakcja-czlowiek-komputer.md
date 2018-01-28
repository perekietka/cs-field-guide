# Interakcja człowiek - komputer

## Z perspektywy

{panel type="teacher-note" summary="Zakres interfejsów użytkownika"}
Materiał w tym rozdziale odnosi się do „urządzeń cyfrowych”. Chociaż zdecydowanie odnosi się to do konwencjonalnych komputerów, ma również zastosowanie do wszelkiego rodzaju innych gadżetów, takich jak budziki, klimatyzatory, kuchenki mikrofalowe, stopery, instrumenty elektroniczne, punkty kasowe, parkometry i alarmy przeciwwłamaniowe. W rzeczywistości większość ćwiczeń dla większości będzie o wiele łatwiejsza do wykonania na urządzeniu z zaledwie kilkoma funkcjami, ponieważ umożliwia to łatwiejsze zbadanie i ocenienie takich urządzeń. Ocena systemu „Microsoft Windows” lub urządzenia „iPad” jest zbyt trudna, ponieważ każdy z podsystemów zasługiwałby na osobną analizę (jak działa menu, jak znaleźć pliki, jak otworzyć program, może nawet jak go włączyć!)
{panel end}

Ludzie są często sfrustrowani komputerami i innymi urządzeniami cyfrowymi.
W pewnym momencie korzystania z tych urządzeń być może zaczniesz,
denerować się, że system zrobił coś, czego nie chcesz
lub nie możesz wymyślić, jak zmusić komputer do zrobienia tego, co chcesz. Dlaczego tak jest?
Ludzie stworzyli komputery, więc dlaczego są one często tak frustrujące w użytkowaniu przez człowieka?

Z dekady na dekadę, komputery stają się setki razy potężniejsze, ale jest jeden ważny element systemu komputerowego, który nie zmienił się znacząco w wydajności od czasu, gdy pierwsze komputery zostały opracowane w latach czterdziestych: człowiek. Aby system komputerowy działał naprawdę dobrze, musi być zaprojektowany przez ludzi, którzy dobrze rozumieją ludzką część systemu.

W tym rozdziale przyjrzymy się, czynnikom sprawiającym, że interfejs jest dobry lub zły. Chodzi o to, abyś był wyczulony na główne problemy, abyś mógł patrzeć krytycznie na istniejące interfejsy i zacząć myśleć o tym, jak zaprojektować dobry interfejs.

Często programiści tworzą oprogramowanie, które wymaga od użytkownika spędzenia dużo czasu na naukę jak ono działa. 
Interfejs może być łatwy w użyciu dla programistów, ponieważ znają oni system naprawdę dobrze, ale użytkownik chce po prostu wykonać pracę, bez czasochłonnych przygotowań (i może on szybko zmienić program na inny, jeśli obecny jest za trudny w użytku).
Programista może myśleć o programie i użytkowniku oddzielnie, ale użytkownik jest częścią systemu i programista musi brać to pod uwagę. Program powinien być intuicyjny i przyjazny.

Interakcja człowiek - komputer (ang. Human - computer interaction, HCI) polega na tym, aby dostosować programy do ludzi. Wykracza to daleko poza wybór wzorców, kolorów i czcionek dla interfejsu.

Aby zrozumieć, jak ludzie używają urządzeń cyfrowych, trzeba brać pod uwagę aspekt  psychologiczny, sposób postrzegania przez nich rzeczy, poszukiwać czynników sprawiających, że użytkownik uważa, że  system jest mu pomocą, a nie przeszkodą. 
Dzięki zrozumieniu HCI programista ma większe szanse stworzyć program efektywny i popularny. 

Wypróbuj następujące narzędzie interaktywne i poproś również znajomych, aby je wypróbowali:

{interactive name="deceiver" type="in-page"}

Czy ktoś z was dostał nieprawidłową odpowiedź na pytanie, mimo że sądził, że jest to prawda?
Być może zauważyłeś, że przyciski „parzysty” i „nieparzysty” czasami zamieniają się miejscami.
Niespójność w interfejsie jest na ogół czymś nieporządanym, ponieważ może łatwo zmylić użytkownika, który przez to popełni błąd.

Jedyną sytuacją, w której może być to pożądane, jest celowe uczynienie gry komputerowej bardziej interesującą (w której powyższa interakcja mogłaby wystąpić).
Wyobraź sobie, że masz formularz internetowy, w którym przyciski „wyczyść” i „prześlij” często zmieniają się miejscami.
Użytkownicy często czyściliby formularz, gdy zamierzaliby go przesłać, lub przesyłaliby formularz, gdyby chcieli go wyczyścić!

{panel type="teacher-note" summary="Dokładność vs szybkość w powyższej interakcji"}
Interaktywna narzędzie zamiany parzysty/nieparzysty może nie oszukać wszystkich uczniów, ale dla niektórych będzie bardzo frustrujące. Jeśli zdecydują się użyć go powoli i ostrożnie, mogą uzyskać poprawnie wybory parzysty/nieparzysty. Jednocześnie uzyskają także niższe wyniki (tj. niższą produktywność, jeśli byłby to prawdziwy interfejs).
{panel end}

Badanie interakcji człowieka z komputerem wiąże się z wykorzystaniem dużej ilości psychologii (jak ludzie się zachowują), ponieważ ma to wpływ na sposób korzystania z systemu. Prosty przykład: ludzka pamięć krótkotrwała przechowuje informacje tylko kilka sekund (nawet u młodych ludzi!).
Jeśli urządzenie odpowiada po więcej niż około 10 sekundach, użytkownik musi podjąć wysiłek, aby pamiętać, co robił. To jest dodatkowa praca dla użytkownika (co z jego punktu widzenia powoduje, że system jest bardziej męczący w użyciu). Innym przykładem jest to, że ludzie zostają „schwytani w nawyk” - robienie czegoś na pamięć: jeśli zaczniesz jeździć na rowerze po trasie, którą pokonujesz każdego dnia, wkrótce osiągniesz cel bez myślenia o każdym zakręcie po drodze. Jest to normalne, chyba że masz wstąpić gdzieś po drodze lub jeśli niedawno przeprowadziłeś się do nowego domu lub zmieniłeś miejsce pracy. Podobny efekt występuje w dialogowych okienkach potwierdzających; może często przypadkowo zamykasz plik bez zapisywania go, a system pyta się „Czy chcesz to zapisać?”, więc naciskasz „Tak”. Po wykonaniu tej czynności kilka razy zaczniesz ją wykonywać bez zastanowienia. Może się wtedy zdarzyć, że np. gdy nie chcesz zastąpić starego pliku, możesz przypadkowo kliknąć „Tak”.

{panel type="ciekawostka" summary="Przechwytywanie błędów"}
Przyzwyczajenie się do standardowej trasy lub procedury, a co za tym idzie zapominanie czegoś innego, co trzeba było zrobić tego dnia, nazywa się *błędem przechwytywania* (ang. capture error).
Jest to łatwe do zapamiętania, ponieważ zostajesz „schwytany” w swój typowy bieg wydarzeń (nawyk).
Na ogół jest to dobrą rzeczą, ponieważ oszczędza ci ciężaru myślenia o codziennych czynnościach (co mogłoby być jeszcze bardziej męczące),
ale może również skłonić cię do zrobienia czegoś, czego nie zamierzałeś.
Dobry projektant interfejsu będzie tego świadomy i uniknie wykonania interfejsu tak, aby użytkownik mógł zostać schwytany i zrobić coś, czego nie można już cofnąć.
{panel end}

Wiele osób może obwiniać siebie za takie błędy, ale podstawy psychologii mówią, że jest to naturalny błąd. Za to dobry system powinien chronić użytkowników przed tym (na przykład umożliwiając cofnięcie danej operacji).

{comment}
Rozważ spojrzenie na cechy przycisku jako przykład drobnych szczegółów (zsuń kursor z przycisku, naciskając itp.);
może dodać interaktywność z prostym (normalnym) polem wyboru i przyciskiem (a może i menu), aby czytelnik mógł eksperymentować z tym, co się dzieje (np. kliknąć, ale zsunąć przed zwolenieniem przycisku)
{comment end}

Projektowanie dobrych interfejsów jest *bardzo* trudne. Właśnie wtedy, gdy myślisz, że masz świetny pomysł, przekonasz się, że potem cała grupa ludzi będzie zastanawiać się, jak z niego korzystać, a w niektórych sytuacjach spali to na panewce. Co gorsza, niektórzy programiści uważają, że ich użytkownicy są bałwanami i że wszelkie problemy z interfejsem są winą użytkownika, a nie programisty. Jednak prawdziwym problemem jest to, że programista zna system bardzo dobrze, podczas gdy użytkownik chce po prostu wykonać swoją pracę bez konieczności spędzania dużej ilości czasu na nauce oprogramowania - jeśli oprogramowanie jest zbyt trudne w użyciu i użytkownik ma wybór, znajdzie po prostu coś prostszego w użyciu. Dobre interfejsy są bardzo cenne!

Istnieje wiele sposobów oceniania i dostosowywania interfejsów. W tym rozdziale przyjrzymy się niektórym z nich. Ważną zasadą jest to, że jedną z najgorszych osób do oceny interfejsu jest osoba, która go zaprojektowała i zaprogramowała. Zna ona dokładnie swój system, prawdopodobnie myślała o nim tygodniami, zna fragmenty, których nie wolno dotykać i opcje, które nie powinny być wybrane, i oczywiście, że ma osobisty interes w znalezieniu tego, co jest *właściwe*, a nie w tym, co jest *złe*. Ważne jest również, aby interfejs był oceniany przez osobę, która będzie typowym użytkownikiem; jeśli poprosisz 12-latka, aby ocenił system planowania emerytalnego, może on nie wiedzieć, co będzie ważne w tym systemie dla typowego użytkownika; a jeśli nauczyciel wypróbuje system, z którego będą korzystać uczniowie, będą oni znali odpowiedzi.

Często interfejsy są oceniane pozyskanie typowych użytkowników, aby je wypróbować i starannie odnotować wszelkie problemy, które wystąpią. Są firmy, które nie robią nic poza tego rodzaju testami. Dostają one prototypowy produkt i płacą grupom ludzi, aby go wypróbowali. Raport na temat produktu jest następnie generowany i przekazywany ludziom, którzy nad nim pracują. Jest to kosztowny proces, ale sprawia, że produkt jest o wiele lepszy i może uzyskać ogromną przewagę nad konkurencją. Ocenianie go przez zewnętrzną firmę oznacza, że unika się uprzedzeń ze strony osób z firmy tworzącej system, które będą chciały udowodnić (nawet podświadomie), że wykonały dobrą robotę projektując go, zamiast odkrywać wszelkie problemy z oprogramowaniem, które będą irytować użytkowników.

Zanim przyjrzymy się różnym sposobom oceniania interfejsów, musimy zastanowić się, co dzieje się z interfejsem.

## Użytkownicy i zadania

Bardzo ważną kwestią przy projektowaniu lub ocenie interfejsu jest to, kim mogą być użytkownicy. Na przykład wiek typowego użytkownika może być znaczący: bardzo małe dzieci mogą mieć trudności z czytaniem niektórych słów i preferować obrazy oraz animacje, podczas gdy ktoś w środowisku komercyjnym, kto często korzysta z interfejsu, będzie chciał, aby był bardzo szybki w użyciu, np używając tylko skrótów klawiaturowych.

Zastanów się, jakie kwestie należy rozważyć w przypadku następujących grup użytkowników.

- seniorzy
- gracze
- zwykli użytkownicy
- obcokrajowcy

{panel type="spoiler" summary="Niektóre z możliwych odpowiedzi: Nie otwieraj, dopóki nie pomyślałeś o tym!"}
- Seniorzy: korzystaj z dużej czcionki, oprogramowanie powinno mieć tylko kilka funkcji, nie polegaj tak bardzo na pamięci, wprowadź ułatwienia w związku z gorszym wzrokiem i sprawnością ruchową użytkownika (np. duże przyciski pomocy), nie zakładaj wcześniejszych doświadczeń z komputerami
- Gracze: wykorzystaj wcześniejsze doświadczenia z typowymi interfejsami gier, spodziewaj się się wyzwań, prawdopodobnie gracz ma urządzenie z najwyższej półki
- Zwykli użytkownicy: interfejs musi być bardzo łatwy do obsługo, być może oparty na powszechnie używanych systemach, wymaga jasnych wskazówek
- Obcokrajowcy: użyj prostego języka i ułatwiających obsługę obrazów/ikon
{panel end}

Interfejs jest jedyną częścią programu, który widzi użytkownik (to definicja interfejsu!), Więc jeśli dla użytkownika interfejs nie działa, to znaczy, że program nie działa.

Kolejną ważną rzeczą do wykonania podczas projektowania i oceniania interfejsu jest zastanowienie się, do jakich zadań jest on używany. Reklamy urządzeń cyfrowych często ukrywają złożoność wykonania jakiegoś zadania i po prostu wskazują funkcje dostępne do jego wykonania. Załóżmy na przykład, że smartfon jest reklamowany jako aparat o wysokiej rozdzielczości. Prawdziwym zadaniem, które ktoś może chcieć zrobić, jest zrobienie zdjęcia czegoś, co właśnie zauważył, i przesłanie go znajomemu. Jeśli spojrzysz na to, co dzieje się w rzeczywistości, smartfon może znajdować się w kieszeni lub torbie, a jeśli ktoś zobaczy, że dzieje się coś fajnego, muszi go wyciągnąć, być może odblokować, otworzyć aplikację aparatu, dostosować oświetlenie i inne ustawienia, nacisnąć przycisk (czy łatwo go znaleźć, gdy trzymasz urządzenie pionowo?), następnie wybrać zdjęcie, sposób udostępniania, wybrać znajomego, któremu ma się udostępnić zdjęcie(czy oprogramowanie pomoże ci w tym?), wysłać (co się dzieje, gdy jesteś poza zasięgiem sieci?), a następnie odłożyć telefon. Jeśli którykolwiek z tych kroków jest powolny lub trudny do zapamiętania, całe doświadczenie może być frustrujące i możliwe, że przez to nie zdążysz czegoś sfotografować lub z innego powodu znajomy nie otrzyma zdjęcia.

Podczas procesu omawiania interfejsu ważne jest przemyślenie wszystkich części zadania, jako, że jest to niewielki krok w zadaniu, który powoduje dużą różnicę między używaniem interfejsu w rzeczywistej sytuacji w porównaniu z demonstracją niektórych funkcji urządzenia.

{panel type="Wyzwanie" summary="Myślenie o kontekście zadań"}
Bardzo ważne jest, aby myśleć o całym kontekście podczas opisywania zadania. Jako ćwiczenie możesz podać przykład prawdziwego zadania, w tym kontekstu, dla prawdziwej osoby dla każdego z poniższych:

- ustawienie budzika
- pokazanie prezentacji slajdów (Powerpoint)

Przedyskutuj swoje odpowiedzi z kolegą z klasy lub znajomym. To powinno pomóc ci w ocenieniu twojej własnej odpowiedzi i rozważeniu innych możliwych przykładów.
{panel end}

{panel type="teacher-note" summary="Możliwe odpowiedzi na poniższe wyzwania"}
Celem edukacyjnym dla uczniów jest dostrzeżenie ogromnej przepaści między naiwnym widokiem „budzika” jako wystarczającym opisem zadania, a konkretnym scenariuszem, który nadaje temu zadaniu więcej sensu. Może to wymagać od uczniów, aby rozpisali zadanie w jego krytycznych krokach; jeśli wykonali zadanie, zanim prawdopodobnie stali się mistrzami w tej dziedzinie to zapomnieli o początkowych trudnościach, a jeśli nie wykonali zadania, mogą założyć, że jest to łatwe. Niektóre z pomysłów, o które możesz poprosić, to:

- ustaw budzik: zadanie jest często wykonywane późno w nocy, a jeśli popełnisz błąd, użytkownik może przegapić ważne spotkanie lub samolot rano, więc zadanie jest bardzo ważne. W zależności od zegara (może to być na smartfonie lub fizyczny zegar), użytkownik musi ustawić czas alarmu (w tym prawidłowe ustawienie oznaczenia am/pm w przypadku zegarów dwunastogodzinowych), włączyć dźwięk alarmu (być może upewniając się, że urządzenie nie jest wyciszone) i upewnić się, że ma wystarczająco dużo baterii do rana. Wszystko to dzieje się podczas gdy użytkownik jest zmęczony, a błąd może być kosztowny!

- pokaż prezentację slajdów (Powerpoint): zadanie to często odbywa się przed publicznością i na jego wykonanie może być ograniczony czas, np. jeśli sala nie będzie dostępna na więcej niż kilka minut przed prezentacją. Może być konieczne podłączenie komputera do projektora (wyzwanie samo w sobie dla całego interfejsu), oprogramowanie ustawione musi być w tryb prezentacji z odpowiednim obrazem gotowym do uruchomienia, użytkownik musi mieć możliwość przejścia do następnego slajdu i powrotu po naciśnięciu złego klawisza.
Aby utrudnić wyzwanie, to projektor zwykle wymaga czasu, aby się rozgrzać, i może być trudno określić, co dzieje się w tym czasie.
{panel end}

{panel type="Ciekawostka" summary="Głupi użytkownicy czy głupie interfejsy?"}
Systemy komputerowe często sprawiają, że ludzie czują się głupimi - w rzeczywistości dostępnych jest wiele książek „dla głupich”, takich jak „iPad dla głupich” (ang. „iPad for dummies”) lub „Kompletny przedowdnik dla idiotów po Microsoft Windows 8” (ang. „The Complete Idiot's Guide to Microsoft Windows 8”).
Te książki sprzedają się w milionach egzemplarzy, ale są szanse, że ludzie, którzy je kupują, są całkiem inteligentni --- po prostu interfejsy mogą sprawiać, że ludzie są tak sfrustrowani, że czują się jak głupek.
Prawda jest taka, że ​​jeśli interfejs powoduje, że ​​wielu ludzi czuje się jak idiota, istnieje poważny problem z interfejsem, a nie użytkownikiem.
W przeszłości istniała zasada, że to programiści, którzy zaprojektowali dane oprogramowanie, mogli sobie pozwolić na obwinianie użytkowników za wszelkie problemy.
Obecenie użytkownicy mają duży wybór oprogramowania i istnieją konkurenci gotowi zaoferować lepszy interfejs, więc jeśli programista nieustannie obwinia użytkowników za problemy, jest szansa, że ​​to programista jest kompletnym idiotą!
Jeśli słyszysz ludzi używających obraźliwych terminów, takich jak luser, [PEBKAC] (http://ars.userfriendly.org/cartoons/?id=19980506) lub błąd ID-10T (błąd idioty), może to być zabawne, ale zwykle lekceważą oni znaczenia właściwego interfejsu i są to oznaką, że system jest źle zaprojektowany

{panel end}

{panel type="projekt" summary="Wysyłanie e-maila z wielu urządzeń"}
W tym projekcie spróbuj wysłać wiadomość e-mail z komputera oraz telefonu komórkowego. Zapamiętaj wszystkie kroki, które musiałeś wykonać, od momentu rozpoczęcia korzystania z urządzenia do czasu wysłania wiadomości e-mail.

Prawdopodobnie zauważysz sporo różnic między tymi dwoma interfejsami.

Zachowaj swoje notatki na później, ponieważ możesz je dalej analizować po przeczytaniu dalszej części tego rozdziału.
{panel end}

{panel type="projekt" summary="Projektowanie płyt kuchennych i klamek do drzwi"}
{image filename="poor-door-design-cartoon.jpg" alt="Konflikt użytkownika otwierającego drzwi." position="right"}

W przypadku tego projektu zaprojektujesz górną część kuchenki lub uchwyty na drzwiach.
To nie jest system komputerowy, ale pomoże zademonstrować niektóre z pojawiających się problemów.
Głównym zadaniem jest szkicowanie trzech różnych konfiguracji płyty kuchennej, która obejmuje rozmieszczenie 4 elementów i 4 gałki kontrolne.

Zadanie to jest [szczegółowo opisane w działaniach związanych z projektowaniem interfejsu CS Unplugged] (http://csunplugged.org/human-interface-design).
{panel end}

## Użyteczność interfejsu

{panel type="teacher-note" summary="Niektóre z kluczowych celów edukacyjnych tego rozdziału"}
Kluczowe idee, które powinni wyłowić uczniowie, obejmują:

- „System”, który musi działać dobrze, to komputer i człowiek *razem*.
- Wiele osób denerwuje się urządzeniami cyfrowymi. Czasami muszą to znosić, ponieważ jest to jedyna dostępna opcja, ale w innych przypadkach urządzenia i oprogramowanie z dobrymi interfejsami sprzedają się znacznie lepiej lub mogą mieć wyższe ceny, ponieważ pomagają użytkownikowi w wykonaniu pracy.
- Najgorszą osobą do oceny interfejsu jest osoba, która go zaprojektowała. Wie dokładnie, jak to powinno działać; ale jeśli ktoś inny wypróbuje urządzenie, dowiesz się, jak wygląda typowy użytkownik (z tego powodu tutaj nie chodzi o to, żeby uczeń napisał własny program i oceni jego interfejs - to byłby dowód, że nie zrozumie oceny HCI!)
- Do wykonania danego zadania używany jest interfejs, dlatego najlepiej jest zidentyfikować zadania, dla których ten interfejs jest przeznaczony, a następnie rozważyć, jak one są trudne. Najczęstszym błędem jest skupienie się na funkcjach interfejsu, ale w świecie rzeczywistym pytanie brzmi, czy te funkcje mogą być używane do wykonywania zadań od początku do końca.
{panel end}

Urządzenia są często sprzedawane przy użyciu zwrotów takich jak „przyjazny dla użytkownika” i „intuicyjny”, niestety są to niejasne terminy, które trudno określić. W tej sekcji wykorzystamy bardziej techniczny termin. [Użyteczność] (https://pl.wikipedia.org/wiki/U%BFyteczno%B6%E6_(informatyka)), który jest dobrze rozumiany przez ekspertów HCI, i daje nam kilka sposobów oceniania, jak bardzo odpowiedni jest interfejs do określonego zadania. Użyteczność nie polega tylko na tym, że interfejs jest przyjemny w użyciu: słaba użyteczność może prowadzić do poważnych problemów i jest przyczyną poważnych katastrof, takich jak wypadki samolotów, katastrofy finansowe i wypadki medyczne. Jest to również ważne, ponieważ interfejs wymagający dużej zręczności, szybkich reakcji lub dobrej pamięci czyni go mniej dostępnym dla dużej części społeczeństwa, gdy dostępność może być zarówno moralnym, jak i prawnym oczekiwaniem.

{panel type="Ciekawostka" summary="Kiedy inerfejs został źle wykonany"}
- 87 osób zginęło, gdy [lot lini Air Inter nr 148 rozbił się] (https://pl.wikipedia.org/wiki/Katastrofa_lotu_Air_Inter_148), ponieważ piloci schodzili „33”, aby uzyskać kąt schodzenia 3,3 stopnia, ale ten sam interfejs był używany do wprowadzenia szybkość]ci zniżania, którą autopilot interpretuje jako 3300 stóp na minutę. Ten problem z interfejsem nazywany jest „błędem trybu” (opisany będzie poniżej). Więcej informacji [tutaj] (http://blog.martindoms.com/2011/01/24/poor-ui-design-can-kill/).
- 13 osób zginęło, a wiele innych zostało rannych, gdy piloci [lotu Varig 254] (https://en.wikipedia.org/wiki/Varig_Flight_254) wpisali niepoprawny kierunek. Plan lotu określał kierunek 0270, którą kapitan zinterpretował i wprowadził do komputera pokładowego jako 270 stopni. W rzeczywistości oznaczało to 027,0 stopni. To zamieszanie nastąpiło z powodu zmiany formatu kierunków i pozycji separatora dziesiętne w planach lotów, a kapitan o tym nie wiedział. Niestety, drugi pilot bezmyślnie skopiował kierunek kapitana zamiast odczytać go z planu lotu, tak jak powinien. Samolot przeleciał przez kilka godzin na autopilocie. Niestety, [efekt potwierdzenia] (https://pl.wikipedia.org/wiki/Efekt_potwierdzenia) wziął górę nad pilotami, którzy byli przekonani, że są blisko celu, podczas gdy w rzeczywistości byli setki kilometrów dalej. Samolotowi zabrakło paliwa i rozbił się w dżungli amazońskiej. Projektowanie systemów lotniczych, które są wykorzystywane przez ludzi, jest dużym wyzwaniem i jest częścią szerszego obszaru badań nad czynnikami ludzkimi.
- Pracownik banku [przypadkowo udzielił klientowi pożyczki w wysokości 10 milionów dolarów zamiast 100 000 dolarów] (http://edition.cnn.com/2012/08/24/world/asia/new-zealand-accidental-millionaire-sentenced/). Klient wypłacił większość pieniędzy i uciekł do Azji, bank stracił w tym czasie miliony dolarów, a kasjer bankowy miał traumatyczne przeżycia. Błąd był spowodowany tym, że pracownik wpisał dwa dodatkowe zera, prawdopodobnie dlatego, że niektóre interfejsy automatycznie wstawiały kropkę dziesiętną (można wpisać 524, aby wprowadzić 5,25 USD), a inne nie. Ten błąd można wytłumaczyć w kategoriach braku spójności interfejsu, co powoduje błąd trybu.
- U 43-letniej kobiety zatrzymał się oddech po tym, jak pielęgniarka przypadkowo wpisała 5 zamiast 0,5 dawki morfiny. Interfejs powinien utrudnić popełnienie błędu wpisania dziesięcikrotnie większej dawki. Istnieje [artykuł na ten temat] (http://www.ncbi.nlm.nih.gov/pubmed/16738293) oraz artykuł [o problemie z interfejsem] (http://hrcak.srce.hr/file/95851). Podobne problemy mogą wystąpić w każdym systemie sterowania, w którym operator wpisuje wartość; lepszy interfejs zmusiłby operatora do naciśnięcia przycisku „w górę” i „w dół”, więc duże zmiany wymagają dużo pracy (jest to przykład „błędu o jeden” (ang. off by one error), w którym jedna dodatkowa cyfra została pominięta lub dodana, a także odnosi się do zasady współmiernego wysiłku)

We wszystkich tych przypadkach winę za popełnienie błędu można przypisać użytkownikowi (pilotom, kasjerowi i pielęgniarce), ale dobrze zaprojektowany interfejs, który nie powoduje poważnych konsekwencji z błędów, które ludzie mogą łatwo popełnić, byłby o wiele lepszy.
{panel end}

Istnieje wiele elementów, które można wziąć pod uwagę w użyteczności, a wspomnimy o kilku, które można napotkać podczas oceniania codziennych interfejsów. Pamiętaj, że interfejsy to nie tylko komputer - każde urządzenie cyfrowe, takie jak budzik, zdalne sterowanie klimatyzacją, kuchenka mikrofalowa lub alarmy antywłamaniowe mogą sprawiać z użytecznością.

### Konsekwencja

„Złotą zasadą” użyteczności jest *konsekwencja*. Jeśli system ciągle się zmienia, korzystanie z niego będzie frustrujące. Wcześniej mieliśmy przykład pary przycisków „parzysty”/„nieparzysty”, które sporadycznie zamieniały się miejscami. Pozytywnym przykładem jest konsekwentne stosowanie „control-C” i „control-V” w wielu różnych programach do kopiowania i wklejania tekstu lub obrazów. Pomaga to także *bezmyślności*: gdy nauczysz się kopiować i wklejać w jednym programie, wiesz, jak to robić w wielu innych. Wyobraź sobie, że każdy program używałby do tego różnych poleceń menu i klawiszy!

Powiązanym problemem jest *błąd trybu* [ang. *Mode error*] (https://pl.wikipedia.org/wiki/Mode_error#Mode_errors), w którym akcja zależy od trybu, w którym się znajdujesz. Prostym przykładem jest wciśnięty klawisz caps lock (w szczególności przy wprowadzaniu hasła, gdzie nie widać efektu wpisywania). Klasycznym przykładem są arkusze kalkulacyjne Excel, w których efekt kliknięcia komórki zależy od trybu: czasami wybiera komórkę, a innym razem umieszcza nazwę komórki, którą kliknąłeś w innej komórce. Tryby są uważane za złe praktyki w projektowaniu interfejsu, ponieważ mogą one łatwo spowodować, że użytkownik wykona niewłaściwą rzecz i powinny być w miarę możliwości unikane.

### Czas odpowiedzi
Szybkość, z jaką interfejs reaguje (jego *czas reakcji*) ma znaczny wpływ na użyteczność.
Sposób, w jaki ludzie postrzegają czas, nie zawsze jest proporcjonalny do czasu, w którym coś się dzieje.
Jeśli coś dzieje się wystarczająco szybko, będziemy postrzegać to jako natychmiastowe.
Jeśli musimy czekać i nie możemy nic zrobić podczas oczekiwania, czas może wydawać się wolniejszy!

Poniższa narzędzie interaktywne pozwala dowiedzieć się, co znaczy „natychmiastowy” dla ciebie.
Gdy klikniesz na każdą komórkę, czasami wystąpi losowe opóźnienie, zanim coś pojawi się; inne komórki nie będą miały opóźnienia. Kliknij każdą komórkę i jeśli wydaje się, że reaguje natychmiast, pozostaw ją bez zmian.
Jeśli jednak zauważysz małe opóźnienie przed pojawieniem się obrazu, kliknij go ponownie (co spowoduje, że komórka zmieni kolor na zielony). Wystarczy, że wykonasz szybką decyzję na poziomie intuicyjnym przy pierwszym kliknięciu każdej komórki - nie przemyślaj jej.
Opóźnienie może być bardzo krótkie, jednak gdy je tylko zauważysz, to kliknij w komórkę, aby zmieniła ona kolor na zielony.

{interactive name="delay-analyser" type="whole-page" text="Interaktywny analizer opóźnień"}

Po ukończeniu zadania kliknij „Wyświetl statystyki”, aby zobaczyć, jak długo opóźnienia były porównywane z twoją percepcją.
Dla większośći osób, punktem, w którym zaczynają dostrzegać opóźnienie jest 100 ms (100 milisekund) czyli jedna dziesiąta sekundy.
Cokolwiek krótszego (szczególnie około 50 ms) jest bardzo trudne do zauważenia. Dłuższe opóźnienia (na przykład 350 ms, czyli ponad jedna trzecia sekundy) są bardzo łatwe do zauważenia.

Chodzi o to, że dowolny element interfejsu (taki jak przycisk lub pole wyboru), który potrzebuje więcej niż 100 ms, by odpowiedzieć, może być postrzegany przez użytkownika jako niedziałający i użytkownik może go kliknąć ponownie. W przypadku pola wyboru może to spowodować, że pozostanie ono wyłączone (z powodu dwóch kliknięć), co spowoduje, że użytkownik pomyśli, że nie działa.
Spróbuj kliknąć to pole wyboru tyle razy, aby pokazać je jako wybrane.
{interactive name="delayed-checkbox" type="in-page"}

Oceniając interfejsy, pamiętaj, że nawet bardzo małe opóźnienia mogą sprawić, że system będzie trudny w użyciu.

Poniższy film przedstawia eksperyment przeprowadzony z użyciem gogli wirtualnej rzeczywistości w celu symulowania opóźnień w Internecie w rzeczywistych sytuacjach.
Ma angielskie napisy, ale najciekawsze jest to, co się w nim dzieje.

{video url="https://www.youtube.com/watch?v=_fNp37zFn9Q"}

### Ludzka pamięć krótkotrwała

Kolejną ważną chwilą, której należy pamiętać, jest nasza *pamięć krótkotrwała*, która zwykle jest kwestią sekund. Aby zapamiętać coś na dłużej, użytkownik musi to ćwiczyć (powtórzyć) lub zanotować informacje, na przykład zapisać je. Jeśli system potrzebuje trochę czasu na odpowiedź (powiedzmy 10 sekund), prawdopodobnie użytkownik zapomniał co dokładnie zamierza zrobić z systemem. Na przykład, jeśli masz numer telefonu do wpisania, który ktoś właśnie ci podytktował, a jego wpisanie zajmuje 12 sekund, możesz zapomnieć o numerze. Jeśli możesz uzyskać dostęp do kontaktów w celu wpisania numeru w ciągu kilku sekund, możesz prawdopodobnie wprowadzić numer bez większego wysiłku. Z tego powodu każda część systemu, która potrzebuje więcej niż 10 sekund na odpowiedź, zmusza użytkownika do powtarzania lub zapisania kluczowych informacji, co jest bardziej męczące.

Jest więcej informacji na temat „limitów czasowych” dla interfejsów w [tym artykule Jakoba Nielsena](http://www.nngroup.com/articles/response-times-3-important-limits/).

### Ludzka pamięć przestrzenna

Kolejną ważną kwestią związaną z użytecznością jest *pamięć przestrzenna* - nasza zdolność do pamiętania, gdzie znajdują się rzeczy (np. gdzie znajduje się przycisk lub ikona). Ludzka pamięć przestrzenna ma dużą pojemność (prawdopodobnie pamiętasz położenie wielu miejsc i obiektów), jest długotrwała (ludzie odwiedzający miasto, w którym dorastali, często pamiętają jego rozmieszczenie przestrzenne) i możemy bardzo szybko zapamiętać rzeczy. Z tego wynika bardzo prosty aspekt użyteczności - mianowicie - rozmieszczenie interfejsu nie powinien się zmieniać. Narzędzie interaktywne na początku tego rozdziału zostało celowo skonfigurowane jako frustrujące przez sporadyczną zamianę dwóch przycisków. Powodem, dla którego ludzie często popełniają błąd w tej sytuacji, jest to, że uaktywnia się ich pamięćprzestrzenna, więc położenie przycisku jest ważniejsze niż to, co jest na nim napisane. Systemy, które nie są spójne w rozmieszczeniu przestrzennym przycisków „OK” i „Anuluj”, mogą łatwo spowodować naciśnięcie niewłaściwego przycisku.

Innym miejscem, w którym rozmieszczenie interfejsu szybko się zmienia, jest obrót tabletu lub smartfona. Niektóre urządzenia zmieniają kolejność ikon dla nowej orientacji, która zmienia układ przestrzenny, podczas gdy inne zachowują je tak samo (z wyjątkiem tego, że mogą nie wyglądać dobrze w nowym ułożeniu). Wypróbuj kilka różnych urządzeń i zobacz, które zmieniają rozmieszczenie po obróceniu.

{panel type="ciekawostka" summary="Typowe sytuacje, w których rozmieszczenia niespodziewanie się zmieniają"}
Istnieje wiele innych sytuacji, w których rozmieszczenie może nagle zmienić się dla użytkownika i spowodować zamieszanie. Oto kilka przykładów:
- Rozmieszczenie może się zmienić, jeśli projektor danych jest podłączony, a rozdzielczość ekranu się zmienia (co jest szczególnie frustrujące, ponieważ użytkownik może wkrótce zaprezentować coś publiczności i nie może znaleźć ikony co powoduje dodatkową niezręcznością, bo wiele ludzie czekają).
- Jeśli zmienisz rozmiar urządzenia (takie jak większy monitor lub inny smartfon), będziesz musiał ponownie nauczyć się, gdzie jest wszystko.
- Układy często zmieniają się wraz z nowymi wersjami oprogramowania (co jest jednym z powodów, dla których aktualizacja za każdym razem, gdy pojawi się nowa wersja oprogramowania, może nie być najlepszym planem).
- To samo oprogramowanie w innym systemie operacyjnym może mieć nieco inny układ (np. jeśli osoba używała przeglądarki Chrome cały czas w systemie Windows  i zaczyna używać Chrome w systemie MacOS). Może to być szczególnie frustrujące, ponieważ położenie wspólnych elementów sterujących (okno zamknięcia/maksymalizacji, a nawet klawisz kontrolny na klawiaturze) jest inne, co sprawia, że przestrzenna pamięć użytkownika zaczyna być zagubiona.
- „Wstążka” Microsoft Word była szczególnie frustrująca dla użytkowników, gdy pojawiła się z kilku już wspomnianych powodów - pozycja każdego elementu była zupełnie inna niż w poprzednich wersjach.
- interfejsy adaptacyjne również mogą stanowić problem; może się wydawać, że dobrym pomysłem jest stopniowe zmienianie menu w programie, tak aby często używane przedmioty znajdowały się w pobliżu lub nieużywane przedmioty były ukryte, ale może to prowadzić do frustrującego poszukiwania opcji przez użytkownika, ponieważ nie może on polegać na jego pamięci przestrzennej, aby znaleźć to czego oczekuje.
{panel end}

Powiązana z pamięcią przestrzenną jest nasza *pamięć mięśniowa*, która pomaga nam zlokalizować przedmioty bez konieczności uważnego patrzenia. Z pewną praktyką prawdopodobnie możesz wybrać typowy przycisk za pomocą myszy, przesuwając dłoń w takiej samej odległości, jaką zawsze masz, zamiast uważnie obserwować.
Praca z nową klawiaturą może oznaczać konieczność ponownego uczenia pamięci mięśniowej, którą opracowałeś, a więc może trochę spowolnić lub spowodować naciśnięcie niewłaściwych klawiszy.

### Brakujący przycisk

Jednym z powszechnych błędów człowieka, który musi być rozważaony przy projektowaniu inferfejsu jest *błąd o jeden* (ang. off by one error), w którym użytkownik przypadkowo klika lub wpisuje element obok tego, w którym zamierzał.
Na przykład, jeśli element menu „zapisz” znajduje się obok pozycji menu „usuń”, jest to ryzykowne, ponieważ jedno małe przesunięce może spowodować, że użytkownik usunie plik zamiast go zapisać.
Podobny problem występuje na klawiaturach; na przykład control-W może zamknąć tylko jedno okno w przeglądarce, a control-Q może zamknąć całą przeglądarkę, więc wybór tych dwóch sąsiednich klawiszy jest problemem. Oczywiście można to naprawić poprzez sprawdzenie czy użytkownik kończy pracę czy zapisać wszystkie okna, aby użytkownik mógł odzyskać to nad czym pracował po ponownym otworzeniu przeglądarki. Może się to również zdarzyć w formularzach internetowych, w których obok przycisku wysyłania znajduje się przycisk czyszczenia, a błąd o jeden powoduje, że użytkownik traci wszystkie dane, które właśnie wprowadził.

{image filename="reset-submit.png" alt="Ryzykowny inferfejs."}


{comment}
.. xjrm dodał w menu „Akcje”, z „Zamów pizzę”, „Uruchom atak nuklearny”, „Uruchom helikopter zabawkowy”. Każdy po prostu natychmiastowo wyświetla okno dialogowe z napisem „Pizza zamówiona” itd.
{comment end}

### Sprawne wykonywanie zadań jest trudniejsze

Innym pomysłem stosowanym przez projektantów HCI jest *zasada współmiernego wysiłku*, która mówi, że często wykonywane proste zadania powinny być łatwe do zrobienia, ale dobrze jest wymagać skomplikowanej procedury złożonego zadania. Na przykład w edytorze tekstu drukowanie strony w takiej postaci, w jakiej jest wyświetlane, powinno być łatwe, ale jest w porządku, jeśli wymaga pewnego wysiłku, aby wydrukować dwustronnie, dwie strony na jednej, ze zszywką w lewym górnym rogu itp. W rzeczywistości czasami więcej wysiłku należy *wymagać*, jeśli polecenie ma poważne konsekwencje, takie jak usunięcie pliku, wyczyszczenie urządzenia lub usunięcie konta. W takich przypadkach można dodać sztuczne zadania, takie jak pytanie „Czy jesteś pewien?” lub ustawienie skrajnego ustawienia na urządzeniu (np. ustawienie napięcia zasilania) może wymagać wielokrotnego naciśnięcia przycisku „w górę”, a nie pozwolenie użytkownikowi wpisania dodatkowych kilku zer.

{interactive name="action-menu" type="in-page"}

### W skrócie

To tylko kilka pomysłów z HCI, które pomogą ci zdawać sobie sprawę z tego, z jakimi problemami możemy mieć do czynienia tworząc interfejsy.
W poniższym projekcie możesz zaobserwować tego typu problemy z pierwszej ręki, oglądając *kogoś innego* używającego interfejsu, zauważając wszelkie problemy, które ta osoba ma.
O wiele łatwiej jest obserwować kogoś innego niż to zrobić samemu, częściowo dlatego, że ciężko jest skoncentrować się na interfejsie i robić notatki w tym samym czasie. Częściowo dlatego, że już znasz interfejs i nauczyłeś się pokonywać niektóre z mniej przydatnych funkcji.

{panel type="projekt" summary="Protokół myśl na głos"}
W protokole „myśl na głos” obserwujesz kogoś, kto korzysta z interfejsu, który chcesz ocenić, i zachęcasz go do wyjaśnienia, co myśli na każdym kroku.
Będziesz robić notatki na temat tego, co mówi, i możesz zastanowić się nad tym, aby następnie ocenić interfejs (jeśli to możliwe, to nagranie całego zdarzenia może być pomocne).

Ten sposób podejścia do problemu daje wgląd w to, co może być mylące w interfejsie i dlaczego.

Na przykład, jeśli ktoś ustawia budzik mówi „Naciskam przycisk w górę, aż dojdę do 7 rano - o nie! zatrzymał się na 7:09, teraz muszę iść dalej aby dojść do 7:00”, co daje wgląd w to, jak interfejs może przeszkodzić użytkownikom w skutecznym wykonaniu zadania.

Takie podejście koncentruje się na obserwacji użytkownika wykonującego określone *zadanie*, aby uchwycić to, co dzieje się w rzeczywistości, gdy ludzie używają interfejsu.
*Zadania* często są mylone z *funkcjami*; używasz funkcji urządzenia do wykonania zadania.
Na przykład aparat może mieć funkcję robienia wielu zdjęć szybko, ale odpowiednim zadaniem jest „zrobienie zdjęcia jakiegoś zdarzenia, wybranie najlepszego zdjęcia i udostępnienie go”.
Może to obejmować wiele działań użytkownika: wchodzenie w tryb wielu zdjęć, konfigurowanie kamery pod kątem warunków oświetleniowych, robienie zdjęć, wybieranie najlepszego, łączenie się z komputerem, przesyłanie zdjęcia do strony internetowej i udostępnianie go przyjacielowi.

Projekt będzie bardziej interesujący, jeśli osoba tobie pomagająca nie jest w pełni zaznajomiony z systemem lub jeśli jest to system, który często jest mylący lub frustrujący dla użytkownika.
Twój zapis może być wykorzystany do podjęcia decyzji o ulepszeniu systemu w przyszłości.

Zadanie może polegać na ustawieniu czasu na zegarze, znalezieniu ostatnio wybranego numeru na nieznanym telefonie lub wybraniu programu telewizyjnego do nagrania.

Aby dokonać oceny, należy przekazać urządzenie swojemu pomocnikowi,objaśnić sposób działania i poprosić o wyjaśnienie, co myśli na każdym kroku.
Twój pomocnik może nie być do tego przyzwyczajony, więc możesz pomoc mu poprzez zadawanie na przykład takich:
   - co zamierzasz teraz zrobić? Dlaczego?
   - dlaczego wybrałeś ten przycisk?
   - czego szukasz?
   - czy masz trudności? Jaki jest problem?
   - czy widzisz, co poszło nie tak?
   - jak się z tym czujesz?

Jeśli zrozumie on „myślenie na głos"”, po prostu milcz i rób notatki o tym, co mówi.

Bardzo ważne jest, aby nie krytykować ani nie zastraszać pomocnika!
Jeśli popełni błąd, spróbuj dowiedzieć się, w jaki sposób interfejs spowodował, że zrobił coś niewłaściwego, zamiast go obwiniać.
Wszelkie popełnione przez niego błędy będą cenne dla twojego projektu!
Jeśli wszystko zrobi dobrze nie będzie to zbyt interesujące.

Gdy już zauważysz, co się stało, przejdź do tego, szukając wyjaśnień, gdzie użytkownik miał trudności.
Przykłady z wcześniejszych przykładów w tym rozdziale pomogą tobie być wrażliwym na to, jak interfejsy mogą zniechęcić użytkownika i znaleźć sposoby na ulepszenie.

Tutaj jest [więcej informacji o protokole myślenia na głos](https://en.wikipedia.org/wiki/Think_aloud_protocol),
na [stronie Nielsena](https://www.nngroup.com/articles/thinking-aloud-the-1-usability-tool/),
i
[niektóre notatki złożone razem przez uczniów HCT](http://www.psy.gla.ac.uk/~steve/HCI/cscln/trail1/Lecture5.html).
{panel end}


{panel type="projekt" summary="Przejście poznawcze"}
Innym sposobem oceny interfejsu jest „Przejście poznawcze” (ang. „Cognitive Walkthrough”).
Zwykle robi się to bez angażowania kogoś innego, chociaż nasz opis został dostosowany do zaangażowania innego użytkownika, aby uczynić go nieco prostszym, jeśli nie masz doświadczenia w ocenie HCI.
*Przejście poznawcze* to technika, której używają eksperci HCI do szybkiej oceny interfejsu.
Jest to szczególnie przydatne przy ocenie interfejsów o kilku krokach, które są wykorzystywane przez nowych lub okazjonalnych użytkowników (np. osoby korzystające z automatu biletowego na lotnisku, ustawiania budzika w pokoju hotelowym lub przy użyciu wyświetlacza muzealnego).

Pierwszym krokiem jest wybranie typowego zadania, które ktoś mógłby zrobić z ocenianym interfejsem (np. wydrukować bilet 2-godzinny, ustawić alarm na 5:20 rano lub dowiedzieć się, gdzie znajduje się dany eksponat w muzeum).

Celem przejścia poznawczego jest ustalenie, czy użytkownik może zobaczyć, co należy zrobić na każdym etapie, a zwłaszcza, aby zauważyć, że jest coś mylącego lub niejednoznacznego (na przykład przycisk, który należy nacisnąć), i dowiedzieć się, czy „Jestem pewien, że wykonana została prawidłowa rzecz”.

Doświadczony ewaluator HCI zrobiłby to samodzielnie, wyobrażając sobie, co zrobiłby użytkownik na każdym kroku, ale może to być łatwiejsze dla ciebie, gdy ktoś inny używa interfejsu, ponieważ pozwala to zobaczyć interfejs przez czyjeś oczy.
Zalecamy więc poproszenie znajomego o wykonanie zadania dla ciebie.

Zadanie musi mieć tylko około 3 lub 4 kroki (np. Naciśnięcia przycisków), ponieważ na każdym etapie będziesz zadawać trzy pytania i robić notatki na temat udzielonych odpowiedzi, więc może to chwilę potrwać.
Powinieneś wiedzieć, jak wykonać to zadanie samemu, ponieważ skupimy się na kilku krokach potrzebnych do wykonania zadania; jeśli użytkownik zboczy z trasy, możesz mu pomóc, zamiast obserwować, jak próbuje wydostać się z problemu HCI, który nie jest dla nas w tym momencie ważny.
Zadanie może polegać na nagrywaniu 10-sekundowego filmu wideo na telefonie komórkowym, usuwaniu wiadomości tekstowej lub ustawianiu kuchenki mikrofalowej w celu ponownego podgrzania jedzenia na 45 sekund.

Przedstaw interfejs swojemu pomocnikowi, nie udzielając żadnych instrukcji na jego temat, i powiedz mu, jaki jest cel zadania.
Zanim podejmie on jakieś działanie, zapytaj:
   - czy wiesz, co powinieneś zrobić na tym etapie?
Następnie poproś go o spojrzenie na interfejs i zapytaj:
   - czy widzisz, jak to zrobić?
Następnie niech wykona akcję, którą zasugerował, i zapytaj:
   - czy jesteś w stanie powiedzieć, że zrobiłeś to co trzeba?

Jeśli jego decyzje spowodują zejście ze ścieżki, możesz zresetować interfejs i zacząć od nowa, wyjaśniając jeśli potrzebne, co zrobić w przypadku niewłaściwego kroku (ale notując, że to nie było oczywiste dla niego - będzie to punkt do rozważenia do ulepszania interfejsu.)

Po zakończeniu pierwszej czynności powtórz to z następną wymaganą akcją (może to być naciśnięcie przycisku lub wyregulowanie kontrolki).
Jeszcze raz, zadaj trzy powyższe pytania w procesie.

W praktyce drugie pytanie (czy widzisz, jak to zrobić?) jest zwykle podzielone na dwie części: czy użytkownik w ogóle zauważa daną kontrolkę, a jeśli tak, to czy zdają sobie sprawę, że jest to potrzebna?
W tym ćwiczeniu uprościmy je do jednego pytania.

[Więcej informacji o tym, jak wykonać przejście poznawcze, znajduje się na stronie cs4fn](http://www.cs4fn.org/usability/cogwalkthrough.php).

Jest również więcej informacji na [angielskiej Wikipedii w haśle Cognitive Walkthrough](https://en.wikipedia.org/wiki/Cognitive_walkthrough).
{panel end}

## Heurystyki użyteczności

{panel type="teacher-note" summary="Plakaty HCI posters dla twojej klasy!"}
Zestaw plakatów wspierających tę sekcję opublikowała Jennifer Gottschalk. [Są one dostępne w formacie PDF tutaj](files/HCI-posters.pdf).
{panel end}

Ocenianie interfejsu najlepiej wykonać, zbierając opinie od wielu potencjalnych użytkowników. Jednak może to być kosztowne i czasochłonne, dlatego eksperci HCI wymyślili kilka szybkich reguł, które pomagają nam szybko wykryć oczywiste problemy. Formalne słowo określające regułę to *heurystyczny*, a w tej części przyjrzymy się pewnym typowym heurystykom, które można wykorzystać do oceny interfejsu.

Istnieją różne zestawy heurystyk, które ludzie zaproponowali do oceny interfejsów, ale duński badacz o nazwie Jakob Nielsen wymyślił zestaw 10 heurystyk, które stały się bardzo szeroko stosowane i opiszemy je w tej sekcji. Jeśli napotkasz problem z użytecznością w interfejsie, prawie na pewno spotkasz się jedną z tych heurystyk i być może z kilkoma z nich. Nie jest łatwo zaprojektować system, który nie złamie żadnej heurystyki, a czasami nie będziesz chciał ich ściśle przestrzegać - dlatego nazywa się je heurystykami, a nie regułami.

Często myląca funkcja w projekcie interfejsu powoduje przerwanie wielu heurystyk. Na przykład następujący komunikat o błędzie (to jest na serio) nie pomaga użytkownikom w uwolnieniu się od błędów (prawdziwy błąd to ustawienie sieciowe, ale jest wyjaśniony jako powodujący miganie światła!), A przyciski „Pomiń”, „Anuluj” oraz „Ignoruj” nie nie są zrozumiałe dla użytkownika (intefejs musi być dopasowany do świata rzeczywistego!).

{image filename="time-capsule.png" alt="Mylenie się na wielu poziomach." side="right_wrap"}


### Widoczność statusu systemu

*System powinien zawsze informować użytkowników o tym, co się dzieje, poprzez odpowiednią informację zwrotną w rozsądnym czasie.*

Ta heurystyka stwierdza, że użytkownik powinien zawsze być w stanie zobaczyć, co robi urządzenie (znać stan systemu). To różni się to od tego, czy użytkownik może stwierdzić, czy urządzenie jest włączone, czy wyłączone do szerego innych czynności. Klasycznym przykładem jest klawisz Caps Lock, który może nie być wyraźnie widoczny, jeśli jest włączony, a podczas wpisywania hasła użytkownik może nie wiedzieć, dlaczego hasło zostało uznane za niepoprawne; pozytywnym przykładem tego jest sytuacja, gdy pole do wprowadzania hasła ostrzega cię, że klawisz Caps lock jest włączony.

Jeden z najprostszych stanów dla urządzenia jest status włączony lub wyłączony, który zwykle jest oznaczone kolorowym światłem na zewnątrz komputera. Jednak niektóre urządzenia wymagają trochę czasu, aby pokazać status (na przykład niektóre odtwarzacze DVD potrzebują czasu, aby zareagować po włączeniu), a użytkownik może ponownie nacisnąć przycisk zasilania lub w inny sposób pomylić się w jakim stanie jest obecnie urządzenie.

Istnieje wiele zadań, które użytkownicy chcą wykonać na komputerze, a które wymagają trochę czasu, w tym kopiowania dokumentów, pobierania plików i ładowania gier wideo. W tej sytuacji jednym z najczęstszych sposobów informowania użytkownika o zadaniu jest pasek postępu.

{image filename="windows-busy-cursor-animation.gif" alt="Kursor zajęty w Windows" wrap="right"}
{image filename="apple-busy-cursor-animation.gif" alt="Kursor zajęty w Apple" wrap="right" remove-preceeding-line-break="true"}

Jednak wskaźniki postępu nie zawsze są pomocne; powyższe kursory nie wskazują, czy będziesz musiał poczekać kilka sekund lub kilka minut (lub nawet godzin) na wykonanie zadania, co może być frustrujące.

Przekazywanie informacji w „rozsądnym czasie” jest naprawdę ważne, a „rozsądny czas” jest często krótszy niż myślisz. W powyższej sekcji przeprowadzono eksperyment, aby dowiedzieć się, w którym momencie ludzie postrzegają opóźnioną reakcję; prawdopodobnie odkryłeś, że była to około jedna dziesiąta sekundy. Jeśli komputer potrzebuje więcej czasu na odpowiedź, może być on mylący w użytku. Więcej na ten temat w poprzedniej sekcji.

{image filename="xkcd-estimation.png" hover-text="Mogliby powiedzieć, że „połączenie jest prawdopodobnie stracone”, ale fajniej jest robić naiwne uśrednienie czasu, by dać ci nadzieję, że jeśli poczekasz około 1 163 godzin, to w końcu operacja zostanie wykonana." alt="Autor windowsowego okienka kopiowania odwiedza znajomych i nie może zdecydować kiedy przybędzie." source="https://xkcd.com/612/"}

W ocenie interfejsu istnieją inne ważne okresy opóźnienia: opóźnienie około 1 sekundy to sytuacja, w której naturalne okienka dialogowe zaczynają się robić niezgrabne, a około 10 sekund nakłada na użytkownika duże obciążenie, aby zapamiętać, co robi. Nielsen ma [artykuł na temat znaczenia tych okresów czasu] (http://www.nngroup.com/articles/response-times-3-important-limits/). Jeśli chcesz przetestować te pomysły, spróbuj porozmawiać z kimś, czekając 3 sekundy przed każdą odpowiedzią; lub wstawiaj losowe 10-sekundowe opóźnienia podczas wypowiadania zdania!

A jeśli jeszcze tego nie wypróbowałeś, skorzystaj z poniższego narzędzia interaktywnego.

{interactive name="delay-analyser" type="whole-page" text="Interaktywny analizator opóźnień"}

Szybka reakcja komputera zależy często od zastosowanych algorytmów (omówionych w rozdziale dotyczącym algorytmów) i może również zależeć od projektu programu (np. takich jak czy przechowuje dane na dysku lub oczekuje na odpowiedź serwera przed kontynuowaniem). Jest to szczególnie widoczne na małych urządzeniach, takich jak smartfony, które mają ograniczoną moc obliczeniową i może zająć sekundę lub dwie, aby otworzyć aplikację lub odpowiedzieć na niektóre dane wejściowe. Niełatwo jest znaleźć takie opóźnienia w systemach podczas ich oceny.

### Dopasuj system do świata rzeczywistego

*System powinien posługiwać się językiem użytkowników, słowami, wyrażeniami i pojęciami znanymi użytkownikowi, a nie systemowymi. Podążaj za rzeczywistymi konwencjami, dzięki czemu informacje pojawiają się w naturalnej i logicznej kolejności.*

Język, kolory i zapisy w interfejsie powinny pasować do świata użytkownika, a choć wydaje się to oczywiste i sensowne, często jest to coś, co jest pomijane. Weźmy na przykład następujące dwa przyciski - czy widzisz, co w nich jest mylące?

{interactive name="confused-buttons" type="in-page"}

{panel type="teacher-note" summary="Odpowiedź na to, co jest nie tak z przyciskami"}
Przyciski mają zamienione kolory, kolor dla anulowania jest zielony (zwykle używany do przejścia dalej), a kolor potwierdzenia jest czerwony (zwykle używany do zatrzymania lub ostrzeżenia).
{panel end}

Poniższy interfejs pochodzi z systemu bankowego służącego do płacenia innej osobie. Załóżmy, że otrzymujesz e-mail z prośbą o zapłacenie 1699,50 USD za używany samochód; spróbuj wpisać w polu „$1699.50”.

{interactive name="payment-interface" type="in-page"}

Notacja „$1699.50” jest popularnym sposobem wyrażenia kwoty w dolarach, ale system ten zmusza do przestrzegania własnych konwencji (prawdopodobnie po to, aby ułatwić rzeczy programiście, który napisał system).

Spróbuj znaleźć inne kwoty, które powinny być prawidłowe, ale ten system wydaje się odrzucać. W idealnej sytuacji system powinien być elastyczny w stosunku do wprowadzanego tekstu, aby zapobiec błędom.

{panel type="spoiler" summary="Odpowiedzi do powyższego, spróbuj przed przeczytaniem tego!"}
Okienko dialogowe odrzuca także przecinki (jako anglosaski separator tysięcy) w danych wejściowych, np. „1,000”, mimo że są bardzo przydatnym sposobem odczytywania kwot w dolarach, np. ciężko jest rozróżnić 1000000 do 100000, ale to może zrobić ogromną różnicę! Nie pozwala także na spację przed lub po liczbie, ale jeśli liczba została skopiowana i wklejona z wiadomości e-mail, może wyglądać zupełnie dobrze. Mniej leniwy programista pozwoliłby na takie sytuację; obecna wersja prawdopodobnie używa prostego systemu konwersji liczb, który oszczędza konieczność dodatkowego programowania ...
{panel end}

### Kontrola użytkownika i wolność

*Użytkownicy często przez pomyłkę wybierają funkcje systemu i będą potrzebować wyraźnie oznaczonego „wyjścia awaryjnego”, aby opuścić niepożądany stan bez konieczności przejśćia przez przedłużany dialog z systemem. Obsługa cofania i ponawiania.*

Bardzo frustrujące jest popełnienie błędu i nie być w stanie wydostać się z niego. Jest to szczególnie złe, jeśli jedna mała operacja może wymazać wiele pracy, której nie można odzyskać. Przycisk resetowania w niektórych formularzach internetowych jest z tego powodu niepopularny - często jest obok przycisku wysyłania i możesz wyczyścić wszystkie dane poprzez „błąd o jeden”.

Powszechnym sposobem na zapewnienie swobody użytkownikowi jest funkcja „cofania”, co oznacza, że nie tylko można łatwo naprawić błędy, ale zachęca się użytkownika do eksperymentowania, wypróbowując funkcje interfejsu wiedząc, że może je po prostu „cofnąć” aby powrócić do tego, co było przedtem, zamiast martwić się, że znajdzie się w stanie, którego nie może naprawić. Jeśli dostępne jest również „powtórzenie”, użytkownik może poruszać się w przód i w tył, decydując, który z nich jest najlepszy. (W rzeczywistości, powtórz jest naprawdę cofnięciem się cofnięcia!)

Oto przykład przycisku, który nie zapewnia kontroli użytkownika; jeśli go naciśniesz, stracisz całą tę stronę i będziesz musiał znaleźć drogę powrotną (ostrzegaliśmy cię!)

{interactive name="close-window" type="in-page"}

{panel type="teacher-note" summary="OSTRZEGALIŚMY cię..."}
Naciśnięcie przycisku „tak” poniżej może być bardzo frustrujące! Większość nowoczesnych przeglądarek internetowych zapewnia pewną kontrolę i swobodę w tym przypadku - jeśli twoi uczniowie są sfrustrowani naciśnięciem przycisku, strona prawdopodobnie znajdzie się w ich menu historii (a niektóre przeglądarki mają nawet funkcję przywracania ostatniej strony zamkniętej).
{panel end}

Czasami interfejs może zmusić użytkownika do zrobienia czegoś, czego nie chce robić. Na przykład często zdarza się, że systemy operacyjne lub programy automatycznie wykonują aktualizacje, które wymagają ponownego uruchomienia. Czasami interfejs może nie dać użytkownikowi możliwości anulowania lub opóźnienia i zrestartować się. Jest to złe ponieważ użytkownik może stracić całą niezapisaną pracę lub oczekiwac na ponowne uruchomienie się systemu w czasie gdy musi coś zaprezentować.

Inną powszechną formą tego problemu jest brak możliwości zamknięcia systemu. Pozytywnym przykładem jest przycisk „home” na smartfonach, który prawie zawsze zatrzymuje bieżącą aplikację, która jest w użyciu.

### Spójność i standardy

*Użytkownicy nie powinni się zastanawiać, czy różne słowa, sytuacje lub działania oznaczają to samo. Przestrzegaj konwencji platformy*.

Spójność (coś, co za każdym razem jest takie samo) jest niezwykle przydatna dla osób używających interfejsów i jest czasami nazywana „złotą regułą HCI”. Jeśli interfejs jest spójny z innymi interfejsami, nauka w jednym interfejsie przenosi się bezpośrednio do drugiego. Jednym z największych przykładów spójności programów komputerowych jest kopiowanie i wklejanie, które działa w ten sam sposób w większości programów, więc użytkownicy muszą tylko raz nauczyć się tej koncepcji. Klawisze skrótów do kopiowania i wklejania są również dość spójne między programami. Ale w niektórych programach kopiowanie/wklejanie zachowuje się inaczej, co może być mylące dla użytkowników.

Przykład niespójności jest zwykle spotykany w programach arkusza kalkulacyjnego, gdzie wynik naciśnięcia „control-A” (wybierz wszystko) zależy od tego, czy edytujesz komórkę, czy tylko wybierzesz komórkę (ten konkretny problem jest problemem „trybu”). Chociaż może to mieć sens dla użytkownika doświadczonego w arkuszach kalkulacyjnych, nowy użytkownik może być bardzo zdezorientowany, gdy to samo polecenie powoduje inną odpowiedź.

{image filename="xkcd-standards-cartoon.png" hover-text="Na szczęście, ładowanie urządzeń zostało rozwiązane, gdy wszyscy standaryzujemy na mini-USB. Czy to jest micro-USB? O nie!." alt="Komiks xkcd o standardach" source="https://xkcd.com/927/"}

Brak spójności często powoduje, że ludzie nie lubią nowego systemu. Jest szczególnie zauważalny między użytkownikami Mac i Windows; ktoś, kto używał tylko jednego systemu, może odbierać drugi jako bardzo frustrujący w użyciu, ponieważ tak wiele rzeczy jest inaczej zorganizowanych (np na początek rozważ elementy sterujące dla okienek, które znajdują się w innym miejscu i mają inne ikony). Doświadczony użytkownik jednego interfejsu pomyśli, że jest to „oczywiste” i nie może zrozumieć, dlaczego druga osoba uważa to za frustrujące, co może prowadzić do dyskusji o religijnym zapale, który interfejs jest najlepszy. Podobne problemy mogą wystąpić, gdy wyjdzie radykalnie odmienna wersja systemu operacyjnego (na przykład Windows 8); wiele nauki, która została wykonana w poprzednim systemie, musi zostać cofnięte, a brak spójności (tj. utrata wcześniejszej wiedzy) jest frustrujący.

### Zapobieganie błędom

*Jeszcze lepsze niż dobre komunikaty o błędach to staranna konstrukcja, która zapobiega występowaniu problemu w pierwszej kolejności. Wyeliminuj podatne na błędy warunki lub sprawdź je i przedstaw użytkownikom opcję potwierdzenia przed ich zatwierdzeniem.*

Program komputerowy nie powinien ułatwiać ludziom popełniania poważnych błędów. Przykładem zapobiegania błędom w wielu programach jest „wyszarzenie” lub deaktywacja konkretnej pozycji menu na pasku narzędziu lub w rozwijanym menu. Uniemożliwia to użytkownikowi korzystanie z funkcji, która nie powinna być używana w tej sytuacji, np. Próba skopiowania, gdy nic nie jest wybrane. Dobry program informuje również użytkownika, dlaczego dany element nie jest dostępny (na przykład w etykiecie danego narzędzia).

Poniżej znajduje się selektor dat; czy widzisz, jakie błędy można z niego wygenerować?

{interactive name="date-picker" type="in-page"}

{panel type="spoiler" summary="NIektóre z błędów, które mogłeś zaobserwować"}
Selektor daty umożliwia użytkownikowi wybranie nieprawidłowych dat, np. 30 lutego lub 31 listopada. Trudno uzyskać poprawny trójelementowy selektor daty, ponieważ każdy element menu ogranicza to, co może być w innych, ale każdy może być zmieniony. Na przykład możesz wybrać 29 lutego 2008 r. (poprawna data), a następnie zmienić rok na 2009 (niepoprawna data), a następnie wrócić do 2008 r. Po wybraniu roku 2009 numer dnia musiałby zmienić się na 28, aby zapobiec błędom, ale jeśli to był tylko wypadek, a użytkownik zmienia powrotem na 2008 rok, liczba zmieniłaby się i może zostać niezauważona. Lepiej jest użyć bardziej wyrafinowanego selektora dat, który pokazuje kalendarz, więc użytkownik może klikać tylko poprawne daty (wiele stron to oferuje). Systemy do wyboru dat zwykle stanowią bogaty przykład na badanie problemów z interfejsem!

{panel end}

Powiązanym problemem jest sytuacja, gdy użytkownik musi wybrać datę początkową i końcową (na przykład w czasie rezerwacji lotów lub hotelu); system powinien zablokować możliwość wybrania wcześniejszej daty końcowej niż początkowa.

Oto menu, który oferuje kilka opcji:

{interactive name="available-menu-items" type="in-page"}

Za każdym razem, gdy pojawia się okno dialogowe z informacją, że nie wolno ci wykonać określonej czynności, jest to frustrujące, ponieważ system nie zdołał zapobiec błędowi. Oczywiście może to być trudne, ponieważ błąd może zależeć od tak wielu wyborów użytkownika, choć dobrze, że system nie oferuje czegoś, czego nie może zrobić.

Innym przykładem zapobiegania błędom jest bankomat (bankomat), który może wydawać tylko banknoty 20 zł.
Jeśli pozwala wprowadzić dowolną kwotę (np. 53,92zł lub nawet 50zł), prawdopodobnie wystąpi błąd.
Jakie techniki widziałeś w oprogramowaniu bankomatów, aby zapobiec tego rodzaju błędom?

{panel type="teacher-note" summary="Zapobieganie błędom bankomatów"}
Niektóre bankomaty uniemożliwiają wprowadzenie nieprawidłowej kwoty, oferując jedynie konkretne kwoty do wypłaty i/lub mając przyciski takie jak +20 zł i - 20 zł.
Wyszukanie w Internecie obrazów „wpisywanie kwoty w bankomacie” może przypomnieć kilka różnych sposobów, lub interfejsy radzą sobie z tym problemem (lub powodują problem!)
Wpisanie kwoty *wpłaty* jest oczywiście inne, ponieważ może to być dowolna kwota, więc prawdopodobnie użyje ono interfejsu,
co pomaga w zapobieganiu błędom, ale teraz zmniejsza spójność!
{panel end}

Oto kolejny przykład, tym razem ze wskazówką informatyczną: poniższy kalkulator ma tryb binarny, w którym wykonuje obliczenia na liczbach binarnych.
Problem polega na tym, że w tym trybie można nadal wpisywać cyfry dziesiętne, co powoduje błąd podczas wykonywania obliczeń.
Użytkownik może po prostu nie zauważyć, że jest w trybie binarnym, a komunikat o błędzie nie jest szczególnie pomocny!

{image filename="binary-calculator-screenshot.png" alt="Kalkulator w trybie binarnym, który nadal pozwala wpisywać cyfry inne niż 0 i 1, ale wyświetla błąd później."}

### Rozpoznanie zamiast przywołania

*Zminimalizuj obciążenie pamięci użytkownika, wyświetlając widoczne obiekty, akcje i opcje. Użytkownik nie powinien pamiętać informacji z jednego okienka dialogowego w drugim. Instrukcje dla użytkowania systemu powinny być widoczne lub łatwe do odzyskania w razie potrzeby.*

Ludzie są ogólnie bardzo dobrzy w rozpoznawaniu przedmiotów, ale komputery dobrze pamiętają je dokładnie. Dobrym tego przykładem jest system menu; jeśli klikniesz na menu „Edycja” w oprogramowaniu, przypomnisz sobie o wszystkich dostępnych opcjach edycyjnych i łatwo wybierzesz interesującą cię opcję.
Jeśli zamiast tego musiałbyś wpisać polecenie z pamięci, to spowodowałoby większe obciążenie dla użytkownika.
Ogólnie rzecz biorąc, dobrze jest, aby komputer „zapamiętywał” szczegóły, a użytkownik mógł wyświetlać opcje, zamiast je pamiętać.
Wyjątkiem jest system, który jest cały czas używany przez eksperta, który zna wszystkie opcje; w tym przypadku bezpośrednie wprowadzanie poleceń może czasami być bardziej elastyczne i szybsze niż wybór z listy.

Na przykład, gdy wpiszesz nazwę miejsca w mapie online, system może zacząć sugerować nazwy w oparciu o to, co piszesz, i prawdopodobne dostosowanie, skupiając się na twojej lokalizacji lub poprzednich wyszukiwaniach.
Poniższy obraz pochodzi z map Google, które sugerują nazwę miejsca, które może próbujesz wpisać (w tym przypadku użytkownik musiał wpisać tylko 4 litery, a system uwolnił go od od konieczności przywołania poprawnej pisowni „Taumatawhakatangihangakoauauotamateapokaiwhenuakitanatahu”, ponieważ użytkownik może następnie to wybrać.)
Podobna funkcja w przeglądarkach internetowych chroni użytkowników przed koniecznością zapamiętania dokładnych szczegółów adresu URL, z którego korzystali w przeszłości; system, który wymagałby wpisania nazw miejsc dokładnie przed ich wyszukaniem, stałby się dość frustrujący.

{image filename="recognition-place-names.png" alt="Mapa przewidująca możliwe nazwy miejsc"}

### Elastyczność i wydajność użytkowania

*Akceleratory -- niewidoczne dla początkującego użytkownika -- często mogą przyspieszyć interakcję dla eksperta, tak aby system mógł obsłużyć zarówno niedoświadczonych, jak i doświadczonych użytkowników. Pozwól użytkownikom dostosowywać częste działania.*

Kiedy ktoś korzysta z oprogramowania każdego dnia, wkrótce wytworzy te same sekwencje operacji, które wykonuje (np. „Otwórz plik, znajdź następne puste miejsce, wpisz w rejestr to, co właśnie się stało”). Dobrze jest zaproponować sposoby szybkiego wykonania tej czynności, takie jak „makra”, które wykonują sekwencję czynności za jednym naciśnięciem klawisza.

Podobnie, dobrze jest móc dostosować oprogramowanie, przypisując klawisze do częstych działań (takich jak „zapisz tę wiadomość e-mail w folderze oczekujące”).
Typowe zadania, takie jak kopiowanie i wklejanie, zwykle mają dodane do nich klawisze, które umożliwiają doświadczonym użytkownikom wykonywanie zadań bez konieczności sięgania po mysz.

Ważnym obszarem badań w HCI jest wypracowywanie sposobów łatwego uczenia się na skróty.
Nie chcesz, aby przeszkadzały one początkującym, ale nie chcesz, aby doświadczeni użytkownicy nie byli ich świadomi.
Prostym sposobem na to jest posiadanie ekwiwalentów klawiszy w menu (akceleratorze); wyświetlone menu pokazuje, że shift-command-O otworzy nowy projekt, aby użytkownik mógł nauczyć się tej sekwencji, jeśli często używa tego polecenia.
{image filename = "menu-keystroke-equivalent.png" alt = "Menu ze skrótami klawiszowymi" wrap = "left"}
Elastyczny system pozwoliłby użytkownikowi dodać ekwiwalent naciśnięcia klawisza dla samego polecenia „Zamknij panel”, gdyby okazało się, że jest często używany.
Inne systemy mogą oferować użytkownikowi sugestie, jeśli zauważą, że czynność jest wykonywana często.
Pokrewne podejście oferuje ostatnie wybory z menu u góry listy opcji.

### Estetyczny i minimalistyczny design

*Okna dialogowe nie powinny zawierać informacji, które są nieistotne lub rzadko potrzebne. Każda dodatkowa jednostka informacji w okienku konkuruje z odpowiednimi jednostkami informacji i zmniejsza ich względną widoczność.*

Oprogramowanie może zawierać wiele funkcji, a jeśli wszystkie są widoczne w tym samym czasie (na przykład na pasku narzędzi), może to być przytłaczające, szczególnie dla nowego użytkownika.

Piloty do telewizora często stanowią świetny przykład skomplikowanego interfejsu.
Jednym z powodów, dla których ma tak wiele przycisków, jest to, że może sprawić, że urządzenie będzie wyglądało imponująco w sklepie, ale gdy będziesz go używać w domu, wiele przycisków staje się zbędnych lub mylących.
{image filename="remote-complex.jpg" alt="Złożony pilot TV" wrap="left"}
Pokazany tutaj pilot zdalnego sterowania ma kilka przycisków, które mogą potencjalnie zrobić to samo: „Direct Navigator”, „Guide”, „Function Menu”, „Status” i „Option” dają dostęp do różnych funkcji, ale trudno przewidzieć, które jest która.
Ten pilot ma w sumie około 55 przycisków!

{image filename="remote-simple.jpg" alt="Prosty pilot." wrap="left"}
Natomiast pilot Apple ma bardzo mało przycisków i jest dobrym przykładem minimalistycznego interfejsu.
Jest tylko jedno „Menu” do wyboru, więc jest dość oczywiste, co zrobić, aby wybrać potrzebne ustawienia.
Oczywiście, prosty pilot polega na wyświetlaniu menu na ekranie, a te mają potencjał, aby uczynić rzeczy bardziej skomplikowanymi.

{image filename="remote-adapted.jpg" alt="Dostosowany pilot TV." wrap="left"}
Trzeci pilot TV, pokazuje rozwiązanie, w celu upraszczenia go, aby użytkownik nie musiał czytać rozległych informacji w instrukcji obsługi.
To trochę drastyczne, ale może zaoszczędzić użytkownikowi dostępu do trybów, z których nie może się wydostać!
Niektóre osoby zgłosiły postulat usunięcie klawiszy z telefonów komórkowych lub przyklejenie guzików, aby użytkownik nie mógł doprowadzić urządzenia do stanu, do którego nie powinien.
Niektóre piloty starają się oferować najlepsze z obu światów, mając małą klapkę, którą można otworzyć, aby pokazać więcej funkcji.


{panel type="ciekawostka" summary="Przerażające interfejsy"}
Następująca witryna zidentyfikowała niektóre z „najbardziej przerażających” interfejsów, z których niektóre są świetnymi przykładami  *nie* posiadania minimalistycznego wzornictwa:[OK/Anuluj najbardziej przerażające interfejsy](http://okcancel.com/archives/article/2005/11/the-scariest-interface-part-ii.html).

Rysownik [Roz Chast](http://rozchast.com/) ilustruje, jak przerażający może być pilot w jego kreskówkach
[„Jak babcia widzi pilota”](http://www.art.com/products/p15063313199-sa-i6845922/roz-chast-how-grandma-sees-the-remote-new-yorker-cartoon.htm).
{panel end}



### Pomóż użytkownikom rozpoznać, zdiagnozować i naprawić błędy

*Komunikaty o błędach powinny być wyrażone w prostym języku (bez kodów), dokładnie wskazywać problem i konstruktywnie proponować rozwiązanie.*

Nie jest trudno znaleźć komunikaty o błędach, które tak naprawdę nie mówią, co jest nie tak!
Najczęstsze przykłady to komunikaty typu „Błąd różny”, „Numer błędu -2431” lub „Błąd jednej z wartości wejściowych”. Zmuszają one użytkownika do przeprowadzenia procedury debugowania, aby dowiedzieć się, co poszło nie tak, a może to być cokolwiek, od rozłączonego kabla lub problemu kompatybilności do brakującej cyfry w liczbie.

Na przykład niektóre oprogramowanie do rozwiązywania problemów wygenerowało poniżej „nieoczekiwany” błąd.
Komunikat o błędzie jest szczególnie nieprzydatny, ponieważ oprogramowanie miało pomóc w znalezieniu problemów, ale zamiast tego dało użytkownikowi nowy problem do rozwiązania!
Poniżej przedstawiono kilka dodatkowych informacji, takich jak „Ścieżka: Nieznana” i „Kod błędu: 0x80070002”.
Wyszukiwanie kodu błędu może prowadzić do sugerowanych rozwiązań, ale prowadzi również do oprogramowania typu scam, które tylko twierdzi, że rozwiązuje problem.
Nie udostępniając przydatnych informacji o odzyskiwaniu błędów, system zostawił użytkownika na łasce dostępnych porad online!

{image filename="error-vague.png" alt="Nieprawidłowy komunikat o błędzie: Wystąpił nieoczekiwany błąd."}

Wariant nieprzydatnych komunikatów o błędach to taki, który daje dwie alternatywy, takie jak „Plik może nie istnieć lub może już być w użyciu”.
Bardziej poprawny komunikat pozwoliłby użytkownikowi na ustalenie, który z nich jest problemem.

Pozytywny przykład można znaleźć w niektórych budzikach, takich jak następujący, na smartfonie z systemem Android.
Na przykład tutaj czas alarmu jest pokazany na „9:00”.
W kraju, który korzysta z 12-godzinnego czasu, użytkownik może pomylić to z 21:00, a alarm włączy się w niewłaściwym czasie.
{image filename="android-alarm-9am.png" alt="Alarm w Androidzie ustawiony na 9:00."}

Interfejs daje jednak możliwość jego zauważenia, ponieważ wyświetlacz wskazuje, jak długo potrwa, zanim alarm się wyłączy, dzięki czemu łatwiej będzie rozpoznać błąd wyboru niewłaściwego czasu (lub dnia).
{image filename="android-alarm-message.png" alt="Komunikat Androida z budzikiem pokazujący, jak długo potrwa wywołanie alarmu."}


### Pomoc i dokumentacja

Nawet jeśli jest lepiej, jeśli system może być używany bez dokumentacji, może być konieczne dostarczenie pomocy i dokumentacji. Wszelkie takie informacje powinny być łatwe do wyszukania, skoncentrowane na tym co użytkownik ma do zrobienia, wymieniać konkretne kroki do wykonania i nie być zbyt obszerne. Poniższa interaktywne narzędzie ilustruje sytuację, na którą mogłeś się przedtem natknąć!
{interactive name="no-help" type="in-page"}

Często pomoc jest refleksją po, i zazwyczaj koncentruje się na funkcji (na przykład na katalogu pozycji menu), a nie skupia się na zadaniu (seria działań potrzebnych do wykonania typowych zadań, która jest bardziej przydatna dla użytkownika). Gdy użytkownik potrzebuje pomocy, zwykle ma do wykonania zadanie (takie jak przesłanie zdjęć z aparatu), a dobra dokumentacja powinna wyjaśniać, jak wykonywać typowe zadania, zamiast wyjaśniać każdą funkcję (np. „Ustawienie trybu aparatu na USB”).


### Aby dowiedzieć się więcej o heurystyce

Możesz znaleźć więcej informacji o [heurystykach online na stronie Jakoba Nielsena](http://www.nngroup.com/articles/ten-usability-heuristics/).

## Podsumowanie

W tym rozdziale przyjrzeliśmy się głównie sposobom oceny interfejsów, ale nie mówiliśmy wiele o tym, jak zaprojektować dobre interfejsy. Jest to zupełnie nowy problem, chociaż możliwość zobaczenia, co może być złego z interfejsem, jest dobrą podstawą do projektowania dobrych interfejsów. Wiele komercyjnych systemów testuje się, wykorzystując powyższe pomysły, aby sprawdzić, czy ludzie uznają je za łatwe w użyciu; w rzeczywistości przed wydaniem nowej aplikacji często są one testowane wielokrotnie z wieloma użytkownikami.
Ulepszenia są dokonywane, a następnie trzeba wykonać więcej testów, aby sprawdzić, czy ulepszenia nie pogorszyły bardziej jakiegoś jednego aspektu interfejsu!
Nic dziwnego, że dobre oprogramowanie może być drogie - wiele osób i dużo czasu poświęca się na upewnienie się, że jest ono łatwe w użyciu, zanim zostanie wydane.


Istnieje wiele innych pomysłów z psychologii, fizjologii, socjologii, a nawet antropologii, z których muszą korzystać eksperci HCI. Rzeczy, które wchodzą w grę obejmują [modele mentalne ](https://en.wikipedia.org/wiki/Mental_model), o tym, jak ktoś wierzy, że system działa w porównaniu do tego, jak to działa (prawie nigdy nie są one takie same, np. podwójne kliknięcie ikony, która wymaga tylko jednego kliknięcia),
[Prawo Fittsa](https://pl.wikipedia.org/wiki/Prawo_Fittsa), o tym, ile czasu zajmuje wskazanie obiektów na ekranie (np. kliknięcie małego przycisku),
[Prawo Hicka](https://en.wikipedia.org/wiki/Hick's_law), o tym, ile czasu zajmuje podejmowanie decyzji między wieloma opcjami (np. z menu),
[Prawo Millera](https://pl.wikipedia.org/wiki/Liczba_Millera) o liczbie przedmiotów, o których dana osoba może myśleć na raz,
[afordancje](https://pl.wikipedia.org/wiki/Afordancje), o tym, jak właściwości obiektu pomagają nam wykonywać na nim działania,
[projektowanie interakcji(IxD)](https://pl.wikipedia.org/wiki/Projektowanie_interakcji), atworzenie cyfrowych urządzeń, które będą działać dla ludzi, którzy będą korzystać z produktu,
[NASA TLX (Wskaźnik obciążenia zadaniami)](https://en.wikipedia.org/wiki/NASA-TLX) do oceniania postrzeganego obciążenia pracą, które zadanie nakłada na użytkownika,
oraz wiele innych praw, obserwacji i wytycznych dotyczących projektowania interfejsów, które uwzględniają ludzkie zachowania i funkcjonowanie ludzkiego ciała.

{comment}
.. xtcb sprawdź grupę HCI; mógłby dodać powyższe: hipoteza Sapira-Whorfa <https://pl.wikipedia.org/wiki/Hipoteza_Sapira-Whorfa>`, o tym, jak struktura języka wpływa na postrzeganie świata,
{comment end}

### Do dalszej lektury

- Książka „Projektowanie z myślą o umyśle” (ang. „Designing with the mind in mind”) Jeffa Johnsona zapewnia doskonały podkład dla wielu zagadnień omawianych w tym rozdziale

- [Strona cs4fn ma wiele artykułów i ćwiczeń o interakcji człowiek - komputer](http://www.cs4fn.org/fundamentals/hci.php), takich jak [problemy związane z raportowaniem problemamów z interfejsem](http://www.cs4fn.org/chi-med/reportingincidents.php), [problemy kulturowe w projektowaniu interfejsów](http://www.cs4fn.org/usability/tzeltal.php), i [znaczenie Sushi](http://www.cs4fn.org/usability/importanceofsushi.php).

- Klasyczną książką o użyteczności jest „Psychologia rzeczy codziennych” (ang. „The psychology of everyday things”) (później nazywana „Projekt codziennych rzeczy” (ang. „The design of everyday things”)) Dona Normana. Chodzi o przedmioty codziennego użytku, takie jak drzwi i telefony, i została to napisane jakiś czas temu, ale zawiera wiele prowokujących i często humorystycznych przykładów.

### Użyteczne linki

- [Dziesięć heurystyk użyteczności na stronie internetowej Nielsena](http://www.nngroup.com/articles/ten-usability-heuristics/), i [zbiór artykułów na temat heurystyki użyteczności](http://www.nngroup.com/topic/heuristic-evaluation/)
-  Tutaj jest  [aktywność CS Unplugged odnośnie HCI](http://csunplugged.org/wp-content/uploads/2014/12/unplugged-19-human_interface_design_0.pdf) która zawiera podstawowe informacje
- Tutaj jest [eobszerne materiały na temat HCI na stronie internetowej cs4fn](http://www.cs4fn.org/fundamentals/hci.php)
- [Glosariusz terminów użyteczności](http://www.usabilityfirst.com/glossary/)

{comment}
.. xjrm wszystko stąd wydaje się być surownym materiałem; Powinienem to kiedyś przejrzeć (!), ale czy możesz to łatwo skomentować? inaczej umieść to gdzieś indziej z linkiem tutaj, aby łatwo było go znaleźć? -tim

.. xtcb umieść materiały stąd w tekście notatki/teksty nauczyciela

  Pomysły na materiał:
  Proces myślenia na głos: Obserwator musi nacisnąć uczestnika, aby wyjaśnić swój proces. Może być zawstydzające i łatwe aby być wzburzonym
  Eksperyment kooperacyjny: 2 osoby i proces zamienia się w dialog i stają się krytyczni wobec procesu.
{comment end}
