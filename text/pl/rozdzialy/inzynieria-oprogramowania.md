# Inżynieria oprogramowania

{panel type="teacher-note" summary="Wyzwania związanie z nauczaniem inżynierii oprogramowania"}
Inżynieria oprogramowania jest trudnym zagadnieniem do nauczenia z kilku powodów. Jednym z nich jest fakt, że wiele, jeśli nie większość, podręczników nie jest pisana przez praktyków i często zawierają nieaktualne informacje, które na dodatek są trudne do zrozumienia dla studentów (na przykład model wodospadu jest często nauczany na początku, który nie działa w praktyce, a właściwie powinien służyć jako przykład tego jak *nie* robić inżynierii oprogramowania).

Ponadto zdobycie prawdziwego doświadczenia w dziedzinie inżynierii oprogramowania wymagałoby zaangażowania zespołu wykwalifikowanych inżynierów pracujących nad projektem o niejasnych i zmieniających się potrzebach. Jest to bardzo trudne w środowisku edukacyjnym, gdzie normą jest indywidualna praca wykonywana przez niedoświadczonych uczniów, którym podano jasne kryteria, na podstawie których będą oceniani.

W tym rozdziale staraliśmy się uchwycić to, co naprawdę dzieje się w branży, i zaproponować zadania, które pozwolą uczniom zrozumieć na czym polega to zagadnienie.
{panel end}

{video url="https://www.youtube.com/embed/ZNMbEbz2dys?rel=0"}

## ??What's the big picture?

Błędy w oprogramowaniu zdarzały się zawsze. Czasami jest to mały błąd, który sprawia, że program jest trudny w użyciu; innym razem błąd może spowodować awarię całego komputera. Niektóre błędy w oprogramowaniu są bardziej spektakularne niż inne.

W 1996 roku rakieta ARIANE 5 Europejskiej Agencji Kosmicznej została wysłana w swój pierwszy lot testowy: Odliczanie, zapłon, płomień i dym, wzbijająca się rakieta... następnie BANG! Mnóstwo małych kawałków rozsianych po południowoamerykańskim lesie deszczowym. Badacze musieli połączyć fragmenty rakiety, aby wyśledzić drobny błąd, który spowodował katastrofę. Fragment oprogramowania na pokładzie rakiety, który nie był nawet potrzebny, zgłosił błąd i rozpoczął sekwencję samozniszczenia. Na szczęście nikogo nie było na pokładzie, ale awaria spowodowała straty o wartości 370 mln USD.

{video url="https://www.youtube.com/embed/gp_D8r-2hwk?rel=0"}

{image filename="ariane-rocket-cartoon.png" alt="Kreskówka o Ariane"}

W skrajnych przypadkach błędy oprogramowania mogą stanowić zagrożenie dla życia. Taki przypadek miał miejsce w latach 80., gdy [urządzenie do radioterapii] (https://en.wikipedia.org/wiki/Therac) spowodowało śmierć 3 pacjentów, dając 100-krotność zamierzonej dawki promieniowania. W 1979 r. Komputer armii amerykańskiej prawie rozpoczął wojnę nuklearną, błędnie interpretując test pocisku przez Związek Radziecki jako atak! (Jeśli jesteś zainteresowany innymi błędami oprogramowania, [CS4FN] (http://www.cs4fn.org/softwareengineering/backtodrawingboard.php) wymienia najbardziej spektakularne!)

Dzisiejsze społeczeństwo jest tak uzależnione od oprogramowania, że nie możemy sobie nawet wyobrazić życia bez niego. Pod wieloma względami programy ułatwiły nam życie: piszemy e-maile, rozmawiamy z przyjaciółmi na Facebooku, gramy w gry komputerowe i szukamy informacji w Google. Oprogramowanie stało się niewidoczne, często nie wiemy, że z niego korzystamy. Mamy z nim do czynienia w samochodach, sygnalizacji świetlnej, telewizorach, pralkach, japońskich toaletach i aparatach słuchowych. Przyzwyczailiśmy się oprogramowania, oczekujemy, że będzie działało przez cały czas!

Dlaczego zatem nie działa? Dlaczego właściwie otrzymujemy komunikaty o błędach? Jak się okazuje, pisanie oprogramowania jest niesamowicie trudne. Oprogramowanie nie jest produktem fizycznym, więc nie możemy po prostu na nie spojrzeć, aby sprawdzić, czy działa poprawnie. Dodatkowo, większość oprogramowania, z którego korzystamy na co dzień, jest niezwykle złożona. Windows Vista podobno ma około 50 milionów linii kodu; MacOS X ma 86 milionów. Jeśli wydrukujemy systemu Vista, otrzymamy stos kartek wysokości 88m! Stos tak wysoki jak 22 piętrowy budynek lub Statua Wolności w Nowym Jorku! Jeśli chciałbyś przeczytać kod źródłowy systemu Vista i spróbować zrozumieć jak działa (przy prędkości 120 linii na godzinę), to musiałbyś poświęcić na to 417,000 godzin lub 47 ½ lat! (I to tylko aby przeczytać, nie wspominając o napisaniu czegoś podobnego.)

{image filename="stacks-of-code-cartoon.png" alt="Kreskówka stosy kodu"}

Inżynieria oprogramowania zajmuje się tym, w jaki sposób tworzyć oprogramowanie pomimo ogromnych rozmiarów i złożoności tak, aby ostatecznie otrzymać działający produkt. Po raz pierwszy wprowadzono to zagadnienie do informatyki w latach 60. w czasie tak zwanego "kryzysu oprogramowania". Wtedy to zdano sobie sprawę z faktu, że zdolność do tworzenia oprogramowania nie nadąża za rosnącymi możliwościami sprzętu.

Jak sugeruje nazwa inżynieria oprogramowania, będziemy wykorzystywać pojęcia i procesy z innych dziedzin inżynierii (takich jak budowanie mostów lub sprzętu komputerowego) i stosować je do oprogramowania. Posiadanie zorganizowanego procesu tworzenia oprogramowania okazuje się niezwykle ważne, ponieważ pozwala nam zarządzać rozmiarem i złożonością oprogramowania. Wraz z postępem metod inżynierii oprogramowania, mamy do czynienia z rosnąca liczbą udanych, dużych i złożonych systemów informatycznych, które nie tylko działają dobrze, ale zawierają niewiele błędów. Weźmy za przykład firmę Google, która ma ogromne projekty (wyszukiwarka Google, Gmail, ...) i tysiące inżynierów pracujących nad nimi, ale wciąż udaje się stworzyć oprogramowanie, które robi to, co powinno.

Od lat sześćdziesiątych inżynieria oprogramowania stała się bardzo ważną częścią informatyki, do tego stopnia, że dzisiejsi programiści rzadko są nazywani w języku angielskim programistami, lecz inżynierami oprogramowania (ang. software enginneers). Wynika to faktu, że tworzenie oprogramowania to coś więcej niż tylko programowanie. Istnieje ogromna liczba miejsc pracy dla inżynierów oprogramowania, a popyt na wykwalifikowanych pracowników stale rośnie. Wielką zaletą bycia inżynierem oprogramowania jest to, że możesz pracować w dużych zespołach, aby produkować produkty, które będą miały wpływ na życie milionów ludzi! Chociaż można by pomyśleć, że inżynierowie oprogramowania musieliby być bardzo inteligentni i nieco geekowi, umiejętności komunikacji i pracy zespołowej są w rzeczywistości ważniejsze; inżynierowie oprogramowania muszą pracować w zespołach i komunikować się ze swoimi kolegami z drużyny. Umiejętność pracy z ludźmi jest co najmniej tak samo ważna jak umiejętność pracy z komputerem.

Wraz ze wzrostem rozmiaru kodu programów, zespoły pracujące nad nim zwiększały się, jednocześnie dobre umiejętności komunikacyjne stawały się jeszcze ważniejsze niż kiedykolwiek.
Co więcej, systemy komputerowe są przydatne tylko wtedy, gdy ułatwiają nam życie, dlatego programiści muszą dobrze rozumieć użytkowników.
Z biegiem czasu, gdy komputery stają się mniejsze i tańsze (zgodnie z prawem Moore'a), odeszliśmy od współdzielenia komputerów, do których trzeba czekać w kolejce. Obecnie często posiadamy wiele urządzeń cyfrowych, i to urządzenia muszą czekać na człowieka.
W systemie cyfrowym człowiek jest najważniejszym elementem!

{panel type="curiosity" summary="Prawo Moore'a"}
W 1965 roku Gordon Moore zauważył, że liczba tranzystorów na układach scalonych podwajał się co dwa lata. Oznacza to, że moc obliczeniowa komputerów również podwoiła się w tym okresie (czasami podawane jest okres 18 miesięcy, gdyż przeważnie wzrostowi liczby tranzystorów towarzyszy zwiększenie częstości wykonywania instrukcji). Moore powiedział, że spodziewa się kontynuacji tego trendu przez co najmniej 10 lat.

Co ciekawe, prawo Moore'a nie trwało tylko 10 lat, ale nadal działa prawie 50 lat później (chociaż przewiduje się spowolnienie w ciągu najbliższych kilku lat). Oznacza to, że dzisiejsze komputery są ponad 100 milionów razy szybsze niż w 1965 roku! (W 2015 roku minęło 50 lat od 1965 roku, co oznacza, że według prawa Moore'a moc obliczeniowa podwoiła się około 25 razy, {math}2 ^{25}{math end} wynosi 16 777 216, więc jeśli komputery mogły uruchomić jedną instrukcję na sekundę w 1965 roku, to teraz mogą ich uruchomić 33 544 432). Oznacza to również, że jeśli kupisz dziś komputer, możesz żałować za dwa lata, gdy nowe komputery będą dwa razy szybsze. Prawo Moore'a odnosi się także do innych ulepszeń w urządzeniach cyfrowych, takich jak moc przetwarzania w telefonach komórkowych i liczba pikseli w matrycach aparatów cyfrowych.

Dokładne liczby powyżej będą zależeć od tego, co opisują, ale najważniejsze jest to, że moc obliczeniowa wzrasta *wykładniczo* &mdash; wykładniczy wzrost nie oznacza, że coś dzieje się o wiele szybciej, ale że dzieje się to niewiarygodnie szybko; nic w historii ludzkości nie rozwinęło się tak szybko! Aby zilustrować to w drugą stronę, czas otwarcia aplikacji na smartfonie może wynosić dziś pół sekundy, ale smartfonie z 1965 roku zajęłoby to ponad rok (a telefon prawdopodobnie byłby wielkości boiska do piłki nożnej). Nic dziwnego, że smartfony nie były popularne w latach sześćdziesiątych.
{panel end}

Mimo że inżynieria oprogramowania przeszła długą drogę w ostatnich dziesięcioleciach, pisanie oprogramowania jest nadal trudne. Jako użytkownik widzisz tylko te programy, które zostały ukończone, a nie te, które się nie powiodły. W 2009 r. Prawie jedna trzecia wszystkich projektów informatycznych odniosła sukces, podczas gdy prawie jedna czwarta nie powiodła się całkowicie lub została anulowana przed dostarczeniem oprogramowania. Pozostałe projekty zostały zakończone z opóźnieniem, przekroczyły budżet lub brakowało funkcjonalności. Słynną niedawną porażką projektu informatycznego było oprogramowanie systemu obsługi bagażu na nowym lotnisku w Denver. System okazał się bardziej złożony, niż spodziewali się tego inżynierowie; w końcu całe lotnisko było gotowe, ale musiało czekać 16 miesięcy, zanim można było je otworzyć, ponieważ oprogramowanie do systemu bagażowego nie działało. Ostatecznie, lotnisko traciło milion dolarów dziennie podczas tych 16 miesięcy!

W tym rozdziale przyjrzymy się podstawom inżynierii oprogramowania. Wprowadzony zostanie temat *analizy* problemu, który pozwoli poznań rodzaj oprogramowanie jaki należy zbudować; omówimy pokrótce, jak zbudować i *zaprojektować* oprogramowanie, a następnie poświęcimy nieco czasu *testowaniu* oprogramowania, które jest jednym z najważniejszych kroków, w celu uniknięcia błędów. Jak widać poniżej, analiza, projektowanie i testowanie to ważne kroki przy tworzeniu oprogramowania. Właściwe programowanie zajmuje zwykle tylko 20% czasu w projekcie (w tym rozdziale prawie nie będziemy o tym wspominać)! Na koniec przyjrzymy się procesom, które organizują działania, w tym analizę, projektowanie i testowanie, tak abyśmy zawsze wiedzieli, co robić.

{panel type="curiosity" summary="Więcej informacji o błędach w oprogramowaniu"}
O ile każdy chce aby jego projekt się powiódł, wiele można się nauczyć od błędów! Oto niektóre strony, które dostarczają dalszych materiałów na ten temat.

- [??Back to the drawing board - CS4FN](http://www.cs4fn.org/softwareengineering/backtodrawingboard.php)
- [Why software fails - IEEE](http://spectrum.ieee.org/computing/software/why-software-fails)
- [Learning from software failure - IEEE](http://spectrum.ieee.org/computing/software/learning-from-software-failure)
- [Engineering Disasters 13: Software Flaws](http://youtu.be/EMVBLg2MrLs) is an excerpt from Engineering Disaster Episode 13 explaining software flaws in Ariane 5 and Patriot Missiles
{panel end}

## Analiza: Co budujemy?

Aby móc zacząć programowanie, musimy wcześniej zdecydować, co chcemy właściwie chcemy osiągnąć. Ten etap projektu będziemy nazywać *analizą*, ponieważ dokładnie analizujemy, co nasze oprogramowanie musi robić. Chociaż brzmi to banalnie, uzyskanie prawidłowych wymagań jest dość trudne. Gdyby ktoś poprosił cię o zaprojektowanie obiektu fizycznego, takiego jak krzesło lub toster, prawdopodobnie dobrze byś wiedział, jaki będzie gotowy produkt. Bez względu na to, ile nóg zdecydujesz się użyć w swoim krześle, nadal będzie musiał utrzymać osobę. Podczas projektowania oprogramowania często nie mamy możliwości tworzenia znanych obiektów, a często nawet nie znamy ograniczeń, takich jak prawa fizyki. Jeśli twoje oprogramowanie było, powiedzmy, programem pomagającym autorom wymyślać wyimaginowane światy, od czego byś zaczął? Co możesz uznać za pewnik?

Analiza jest niezmiernie istotna. Oczywiście, jeśli popełnimy błąd na tym etapie projektu,  to powstanie oprogramowanie, które nie spełnia oczekiwań; wszystkie inne prace związane z projektowaniem, budowaniem i testowaniem oprogramowania mogą być spisane na straty.

Na przykład, wyobraź sobie, że twoja przyjaciółka Anna prosi cię o napisanie programu, który pomoże jej dostać się rano do szkoły. Piszesz świetny system nawigacji GPS i pokazujesz to Annie, ale okazuje się, że ona jeździ do szkoły autobusem. Zatem to, czego naprawdę potrzebowała, to oprogramowanie pokazujące aktualny rozkład jazdy autobusów. Cała twoja ciężka praca była daremna, ponieważ nie wydobyłeś odpowiednich informacji na samym początku!

Czasami tworzymy oprogramowanie na własna potrzeby; w takim przypadku możemy po prostu zdecydować, co powinien robić program. (Bądź jednak ostrożny: nawet jeśli myślisz, że wiesz, co ma robić oprogramowanie, gdy zaczniesz je tworzyć, prawdopodobnie zmienisz zdanie na temat jego funkcjonalność do czasu ukończenia projektu. Wynika to z faktu, że pewne wymagania zauważamy dopiero jak zaczynamy korzystać z programu. Na przykład ludzie produkujący smartfony i oprogramowanie dla smartfonów prawdopodobnie nie przewidzieli, ile osób będzie chciało użyć telefonu jako latarki!)

W wielu przypadkach tworzymy oprogramowanie dla innych osób. Możesz stworzyć stronę sklepu odzieżowego cioci lub napisać oprogramowanie, które pomoże twoim przyjaciołom w odrabianiu lekcji z matematyki. Firma produkująca oprogramowanie może tworzyć oprogramowanie dla lokalnej rady miejskiej lub lekarza rodzinnego. Google i Microsoft tworzą oprogramowanie używane przez miliony ludzi na całym świecie. Tak czy inaczej, niezależnie od tego, czy piszesz program dla swoich przyjaciół, czy dla milionów ludzi, najpierw musisz dowiedzieć się od swoich klientów, czego naprawdę potrzebują.

Każdego, kto jest zainteresowany oprogramowaniem będziemy nazywać *interesariuszem* (ang. stakeholder). Są to osoby, z którymi należy prowadzić dialog podczas etapu analizy projektu, w celu uzyskania listy wymagań.

Wyobraź sobie, że tworzysz aplikację mobilną, która umożliwia uczniom wstępne zamawianie jedzenia w szkolnej stołówce. Mogą korzystać z aplikacji, aby poprosić o jedzenie rano, a następnie po prostu iść i odebrać jedzenie w porze lunchu. Chodzi o pomoc w usprawnieniu wydawania posiłków i zmniejszeniu kolejek w stołówce. Oczywistymi interesariuszami dla twojego projektu są studenci (którzy będą korzystali z aplikacji na telefon) i pracownicy kafeterii (którzy będą otrzymywać zamówienia za pośrednictwem aplikacji). Mniej oczywistymi (i pośrednimi) interesariuszami są rodzice ("muszę kupić mojemu dziecku smartfon, aby mogli korzystać z tej aplikacji?"), administrator szkoły ("telefonów nie powinno się używać na terenie szkoły!") oraz szkolne wsparcie IT, które musi radzić sobie z wszystkimi uczniami, którzy nie potrafią zrozumieć, jak pracować z aplikacją lub połączyć się z siecią. Różni interesariusze mogą mieć bardzo różne pomysły na funkcjonalność aplikacji.

Aby dowiedzieć się, czego potrzebują interesariusze, zwykle przeprowadzamy rozmowę. Zadajemy im pytania, aby znaleźć wymagania *funkcjonalne* i *niefunkcjonalne* dla oprogramowania. Wymagania funkcjonalne to czynności, które oprogramowanie musi wykonać. Na przykład aplikacja mobilna musi umożliwiać uczniom wybór żywności, którą chcą zamówić. Następnie powinna wysłać zamówienie do stołówki wraz z nazwiskiem ucznia, aby można go było łatwo zidentyfikować podczas odbioru posiłku.

Z drugiej strony, wymagania niefunkcjonalne nie mówią nam *co* program ma robić, ale *jak* ma to robić. Jak wydajny musi być? Jak niezawodny? Jakiego komputera (lub telefonu) trzeba, aby go uruchomić? Jak łatwy w użyciu powinien być?

W pierwszej kolejności musimy ustalić kim są nasi interesariusze. Następnie przeprowadzamy z nimi rozmowy, aby znaleźć wymagania dotyczące programu. To pewnie nie wydaje się trudne, prawda? Niestety, komunikacja z klientem często okazuje się najtrudniejsza.

Pierwszy problem polega na tym, że klienci i programiści często nie mówią tym samym językiem. Oczywiście, nie chcemy powiedzieć, że nie mówią po polsku, lecz to, że informatycy używają języka technicznego, podczas gdy klienci używają języka specyficznego dla ich branży. Na przykład lekarze mogą używać wielu przerażających terminów medycznych, których nie zrozumiesz.

Wyobraź sobie, że jesteś poproszony o opracowanie systemu punktacji dla (fikcyjnej) dyscypliny sportowej Whacky-Flob. Klient mówi: "To naprawdę proste. Trzeba tylko zapisywać foo-whacki, lecz nie bar-whacki, chyba że Flob krąży". Po tym opisie jesteś prawdopodobnie bardzo zdezorientowany, ponieważ nie wiesz nic o sporcie Whacky-Flob i nie znasz konkretnych terminów. (Czym są foo-whacki???) Aby zacząć, powinieneś wziąć udział w kilku grach Whacky-Flob i obserwować, jak przebiega gra i jak odbywa się punktacja. W ten sposób będziesz w stanie więcej wydobyć z klienta, ponieważ masz pewną wiedzę na temat dziedziny problemu. (Nawiasem mówiąc, jest to jedna z najfajniejszych rzeczy związanych z byciem programistą: masz kontakt z różnymi, ekscytującymi dziedzinami problemów: jeden projekt może śledzić niedźwiedzie grizzly, następny może identyfikować cyberterrorystów lub sprawiać, że samochód sam jeździ.)

Nie należy również zakładać, że klient zna techniczne pojęcia, takie jak JPEG, baza danych, a może nawet system operacyjny. Stwierdzenie "Hierarchia podklasy metaklasy była ograniczona, aby być analogiczna do hierarchii klas i podklas, które są ich instancjami" może mieć sens dla programisty, ale klient będzie po prostu patrzeć na ciebie bardzo zdezorientowany! Jeden z autorów wziął kiedyś udział w wywiadzie dla klienta, w którym zapytano zainteresowanego, czy chce korzystać z systemu za pośrednictwem przeglądarki. Niestety klient nie miał pojęcia, czym jest przeglądarka. Czasami klienci mogą nie chcieć przyznać, że nie mają pojęcia o czym mówisz i po prostu powiedzieć "tak". Pamiętaj, że to ty jesteś odpowiedzialny, za to, że rozumiecie się z klientem nawzajem i że odpowiedzi od klienta są przydatne!

{image filename="overwhelming-the-user-cartoon.png" alt="Przytłaczanie użytkownika pytaniami - rysunek"}

Nawet jeśli uda Ci się komunikować z klientem, może się okazać, że tak naprawdę nie wiedzą, co chcą zrobić lub nie mogą tego wyrazić. Mogą powiedzieć, że chcą "oprogramowania, które usprawni ich działalność" lub "sprawią, że ich praca będzie bardziej wydajna", ale nie jest to zbyt szczegółowe. (Jest świetny rysunek z [Dilbert](http://dilbert.com/strips/comic/2006-01-29/), który ilustruje ten punkt!) Kiedy pokazujesz im oprogramowanie, które zbudowałeś, zazwyczaj mogą ci powiedzieć jeśli tego właśnie chcieli, lub co im się podobało i nie lubią tego. Z tego powodu warto tworzyć małe prototypy podczas opracowywania systemu i wyświetlać je klientom, aby uzyskać od nich informacje zwrotne.

Często się zdarza, że klienci mają specyficzny proces, którym wykonują i chcą, aby oprogramowanie dopasowało się do niego. Byliśmy kiedyś zaangażowani w projekt wykonywany przez studentów na potrzeby biblioteki. Personel zapisywał informacje o wypożyczonych książkach trzykrotnie na papierowym formularzu, wycinał formularz i wysyłał części w różne miejsca jako zapis do przechowywania. Kiedy studenci wypytywali pracowników biblioteki o wymagania zostali poproszeni o ekran, w którym mogliby wprowadzić informacje również trzy razy (pomimo tego, że w systemie informatycznym nie ma to większego sensu)!

Klienci są zwykle ekspertami w swojej dziedzinie i dlatego mogą pominąć informacje, które ich zdaniem są oczywiste, ale mogą nie być oczywiste dla programisty. Innym razem nie rozumieją, co można i czego nie można zrobić przy pomocy komputera i mogą nie wspomnieć o czymś, ponieważ nie zdają sobie sprawy, że można to zrobić za pomocą komputera. Znów, od ciebie zależy, czy otrzymasz od nich istotne informacje.

{image filename="xkcd-tasks.png" hover-text="W latach 60-tych Marvin Minsky wyznaczył kilku studentów do spędzenia lata na programowaniu komputera w celu użycia kamery do identyfikacji obiektów. Wydawało mu się, że problem zostanie rozwiązany pod koniec lata. Pół wieku później wciąż nad tym pracujemy." alt="Rysunek xkcd na temat zadań programistycznych" source="https://xkcd.com/1425/"}

{panel type="curiosity" summary="Łatwe dla komputerów i trudne dla ludzi, a trudne dla komputerów i łatwe dla ludzi"}
Tekst z powyższego rysunku (trzeba go faktycznie obejrzeć na [stronie xkcd](https://xkcd.com/1425/)) jest również wart przeczytania. Rozpoznawanie obrazów to problem, który początkowo wydawał się prosty, prawdopodobnie dlatego, że ludzie uważają to za łatwe. Interesujące jest to, że wiele problemów jest łatwych dla komputerów, chociaż wydają się trudne dla ludzi. Na przykład pomnożenie dwóch dużych liczb. Z drugiej strony, istnieje wiele innych problemów, których komputery nie potrafią rozwiązać, natomiast dla ludzi nie stanowią one problemu, na przykład rozpoznanie, że zdjęcie przedstawia kota.
{panel end} 

Jeśli projekt dotyczy wielu interesariuszy, mogą pojawić się sprzeczne punkty widzenia. Na przykład, gdy rozmawiasz z ludźmi z kafeterii o aplikacji zamawiającej produkty spożywcze, mogą zasugerować, że każdy uczeń powinien mieć możliwość zamawiania jedzenia o wartości 10 USD. W ten sposób mogą uniknąć niepoważnych zamówień. Nauczyciele mogą zgodzić się z tą sugestią. Nie chcą, aby jeden uczeń mógł zostać zmuszony do zamawiania jedzenia dla wielu innych uczniów. Uczniowie z kolei będą twierdzić, że chcą zamówić jedzenie dla swoich przyjaciół. Ich zdaniem limit 10 USD nie wystarcza nawet dla jednego studenta.

Co robisz z tymi sprzecznymi punktami widzenia? W zależności od sytuacji, interesariuszy i typu oprogramowania, może być trudno poradzić sobie z sprzecznościami. W tym przypadku potrzebujesz poparcia ze strony stołówki i nauczycieli, aby Twoje oprogramowanie działało, ale może uda ci się wynegocjować nieco wyższy limit zamówień wynoszący 20 USD, aby spróbować zadowolić wszystkich swoich interesariuszy.

Wreszcie, nawet jeśli zrobisz porządną analizę projektu, porozmawiaj ze wszystkimi interesariuszami i ustal wszystkie wymagania dotyczące oprogramowania, wymagania mogą ulec zmianie podczas tworzenia oprogramowania. Duże projekty oprogramowania mogą trwać latami. Wyobraź sobie, ile zmian w świecie technologii ma miejsce w ciągu roku! Podczas pracy nad projektem może pojawić się nowy sprzęt (telefony, komputery, tablety, …) lub konkurencja może wypuścić oprogramowanie bardzo podobne do tego, co robisz. Twoje oprogramowanie może również zmienić sytuację na rynku: po dostarczeniu oprogramowania klient spróbuje z nim pracować i może zdawać sobie sprawę, że nie jest to tym, czego naprawdę chciał. Dlatego nigdy nie powinieneś zakładać, że wymagania będą ustalone raz na zawsze. Najlepiej byłoby regularnie rozmawiać z klientami podczas całego projektu i zawsze być gotowym na zmianę wymagań!

{panel type="project" summary="Wyszukiwanie wymagań"}
W przypadku tego projektu musisz znaleźć kogoś, dla kogo mógłbyś wykonać oprogramowanie. Może to być ktoś z twojej rodziny lub przyjaciel. Mogą na przykład potrzebować oprogramowania do zarządzania informacjami o klientach swoich firm lub klub squash może wymagać oprogramowania do planowania turniejów squasha lub pomóc w ustalaniu harmonogramu treningów. (W przypadku tego projektu faktycznie nie będziesz tworzyć oprogramowania, tylko przyglądać się wymaganiom. Jeśli projekt jest na tyle mały, że możesz go samemu zaprogramować, prawdopodobnie nie jest wystarczająco duży, żeby być dobrym przykładem dla inżynierii oprogramowania!)

Po znalezieniu projektu zacznij od zidentyfikowania i opisania interesariuszy. (Ten projekt będzie najbardziej pouczający, jeśli masz co najmniej dwóch różnych interesariuszy.) Spróbuj ustalić wszystkich interesariuszy, pamiętając, że niektórzy z nich mogą mieć jedynie pośrednie zainteresowanie twoim oprogramowaniem. Na przykład, jeśli tworzysz bazę danych do przechowywania informacji o klientach, klienci, których dane są przechowywane, mają pewne zainteresowanie twoim oprogramowaniem, nawet jeśli nigdy nie używają go bezpośrednio; na przykład będą chcieli, aby oprogramowanie było bezpieczne, aby ich dane nie mogły zostać skradzione. Stwórz opis każdego interesariusza, podając jak najwięcej szczegółów. Kim oni są? Jakie cele mogą uzyskać dzięki oprogramowaniu? Ile mają wiedzy technicznej? …

Przepytaj *jednego* z interesariuszy, aby dowiedzieć się, jakie są jego oczekiwania odnośnie oprogramowania. Zapisz wymagania dotyczące oprogramowania, podając pewne szczegóły dotyczące każdego z nich. Spróbuj rozróżnić wymagania funkcjonalne i niefunkcjonalne. Upewnij się, że dowiesz się od swojego interesariusza, jakie rzeczy są dla niego najważniejsze. W ten sposób możesz nadać każdemu wymaganiu priorytet (na przykład wysoki, średni, niski), tak aby, gdybyś faktycznie zaczął realizować projekt, to mógłbyś zacząć od najważniejszych funkcji.

Dla pozostałych interesariuszy spróbuj wyobrazić sobie, jakie byłyby ich wymagania. W szczególności spróbuj ustalić, w jaki sposób wymagania różnią się od innych interesariuszy. Możliwe, że dwóch interesariuszy ma te same wymagania, ale czy mogą mieć różne priorytety dla każdego z nich? Sprawdź, czy możesz wymienić potencjalne rozbieżności lub konflikty między zainteresowanymi stronami? Jeśli tak, to jak byś je rozwiązał?
{panel end}

{panel type="teacher-note" summary="Wybór dobrego tematu dla projektu"}
Temat projekt będzie dobrze dobrany, jeśli będzie dość złożony z wieloma różnymi interesariuszami i wymaganiami. Prosta baza danych klientów dla firmy prawdopodobnie nie wygeneruje wielu interesujących wymagań.
{panel end}

## Projekt: Jak to zbudujemy?

Kiedy już zdecydujesz, co twoje oprogramowanie ma zrobić, możesz je zbudować. Zaczynanie projektu "na ślepo" może wpędzić cię w kłopoty; pamiętaj, że większość oprogramowania jest ogromna i bardzo złożona. Musisz jakoś zminimalizować złożoność oprogramowania, inaczej kod programu stanie się niemożliwy do zrozumienia i utrzymania przez innych programistów w przyszłości.

Projektowanie oprogramowania sprowadza się do zarządzania jego złożonością i ciągłym upewnianiu się, że tworzone przez nas oprogramowanie ma dobrą strukturę. Zanim zaczniemy pisać dowolny kod, projektujemy strukturę naszego oprogramowania w fazie *projektowania* projektu. Kiedy mówisz o projektowaniu oprogramowania, wiele osób pomyśli, że mówisz o projektowaniu wyglądu oprogramowania. Tutaj zajmiemy się zaprojektowaniem *wewnętrznej* struktury oprogramowania.

Zatem a jaki sposób możemy zaprojektować oprogramowanie, aby nie stało się ono niezwykle złożone i niemożliwe do zrozumienia? Poniżej przedstawiamy dwa ważne podejścia: poddział i abstrakcję. To dość przerażające słowa, ale jak się wkrótce przekonacie, pojęcia za nimi stojące są zaskakująco proste.

Prawdopodobnie domyślasz się co oznacza pojęcie *podział*: Rozbijamy oprogramowanie na wiele mniejszych części, które można zbudować samodzielnie. Każda mniejsza część może zostać ponownie podzielona na jeszcze mniejsze części i tak dalej. Jak widzieliśmy we wstępie, wiele programów jest tak dużych i złożonych, że jedna osoba nie może tego wszystkiego pojąć; możemy łatwiej poradzić sobie z mniejszymi częściami. Złożone oprogramowanie jest tworzone przez duże zespoły, tak aby różne osoby mogły pracować nad różnymi częściami i rozwijać je równolegle, niezależnie od siebie. Na przykład, w przypadku projektu w kafeterii, możesz pracować nad stworzeniem bazy danych, która rejestruje, jakie jedzenie sprzedaje stołówka i ile kosztuje każdy przedmiot, podczas gdy twój przyjaciel pracuje nad rzeczywistą aplikacją mobilną, którą uczniowie będą używać do zamawiania jedzenia.

Once we have developed all the different parts, all we need to do is make them communicate with each other. If the different parts have been designed well, this is relatively easy. Each part has a so-called *interface* which other parts can use to communicate with it. For example, your part of the cafeteria project should provide a way for another part to find out what food is offered and how much each item costs. This way, your friend who is working on the phone app for students can simply send a request to your part and get this information. Your friend shouldn’t need to know exactly how your part of the system works; they should just be able to send off a request and trust that the answer they get from your part is correct. This way, each person working on the project only needs to understand how their own part of the software works.

Let’s talk about the second concept, *abstraction*. Have you ever thought about why you can drive a car without knowing how its engine works? Or how you can use a computer without knowing much about hardware? Maybe you know what a processor and a hard drive is but could you build your own computer? Could your parents? We don’t need to know exactly how computers or cars work internally to be able to use them thanks to abstraction!

If we look more closely at a computer, we can see that it actually has a number of *layers* of abstraction. Right at the bottom, we have the hardware, including the processor, RAM, hard disk and various complicated looking circuit boards, cables and plugs.

When you boot your computer, you start running the operating system. The operating system is in charge of communicating with the hardware, usually through special driver software. Once you’ve started your computer, you can run programs, for example your browser. The browser actually doesn’t communicate with the hardware directly but always goes through the operating system.

Finally, you’re the top layer of the system. You use the program but you will (hopefully) never have to interact with the more complicated parts of the operating system such as driver software, let alone the hardware. In this way, you can use the computer without ever having to worry about these things.

{image filename="computer-layers.png" alt="The computer can be broken down into multiple layers, starting with the user, then the programs, then the operating system, then finally the hardware." caption="The computer can be broken down into multiple layers, starting with the user, then the programs, then the operating system, then finally the hardware."}

We call a system like this a *layered system*. You can have any number of layers you want but each layer can only communicate with the one directly below it. The operating system can directly access the hardware but a program running on the computer can't. You can use programs but hopefully will never have to access the hardware or the more complex parts of the operating system such as drivers. This again reduces the complexity of the system because each layer only needs to know about the layer directly below it, not any others.

Each layer in the system needs to provide an interface so that the layer above it can communicate with it. For example, a processor provides a set of instructions to the operating system; the operating system provides commands to programs to create or delete files on the hard drive; a program provides buttons and commands so that you can interact with it.

One layer knows nothing about the internal workings of the layer below; it only needs to know how to use the layer’s interface. In this way, the complexity of lower layers is completely hidden, or *abstracted*. Each layer represents a higher level of abstraction.

So each layer hides some complexity, so that as we go up the layers things remain manageable. Another advantage of having layers is that we can change one layer without affecting the others, as long as we keep the layer’s interface the same of course. For example, your browser’s code might change but you might never notice as long as the browser still looks and works the same as before. Of course, if the browser stops working or new buttons appear suddenly you know that something has changed.

We can have the same “layered” approach inside a single program. For example, websites are often designed as so-called *three-tier* systems with three layers: a database layer, a logic layer and a presentation layer. The database layer usually consists of a database with the data that the website needs. For example, Facebook has a huge database where it keeps information about its users. For each user, it stores information about who their friends are, what they have posted on their wall, what photos they have added, and so on. The logic layer processes the data that it gets from the database. Facebook’s logic layer, for example, will decide which posts to show on your “Home” feed, which people to suggest as new friends, etc. Finally, the presentation layer gets information from the logic layer which it displays. Usually, the presentation layer doesn’t do much processing on the information it gets but simply creates the HTML pages that you see.

{image filename="facebook-three-tier-system.png" alt="Facebook can be broken down into a three tier system, comprising of the presentations layer, then the logic layer, then finally the data layer." caption="Facebook can be broken down into a three tier system, comprising of the presentations layer, then the logic layer, then finally the data layer."}

{panel type="curiosity" summary="Reuse - Kangaroos and Helicopters"}

Since building software is so difficult and time-consuming, a popular idea has been to reuse existing software. Not surprisingly, we call this *software reuse*. It’s a great idea in theory (why recreate something that already exists?) but turns out to be difficult to put into practice partly because existing software is also huge and complicated. Usually when you reuse software, you want only a small part of the existing software’s functionality, rather than everything.

An interesting story that illustrates the problems with software reuse (although it is unfortunately not completely accurate, see [http://www.snopes.com/humor/nonsense/kangaroo.asp](http://www.snopes.com/humor/nonsense/kangaroo.asp)) is that of helicopters and kangaroos. The Australian Air Force was developing a new helicopter simulator to train pilots. They wanted the simulator to be as realistic as possible and therefore decided to include herds of kangaroos in the simulation. To save time, they reused code from another simulator which included foot soldiers and simply changed the icons of the soldiers to kangaroos.

Once the program was finished, they demonstrated it to some pilots. One of the pilots decided to fly the helicopter close to a herd of kangaroos to see what would happen. The kangaroos scattered to take cover when the helicopter approached (so far so good) but then, to the pilot’s extreme surprise, pulled out their guns and missile launchers and fired at the helicopter. It seemed the programmer had forgotten to remove *that* part of the code from the original simulator.

{comment}
We could include a cartoon kangaroo in this curiosity box
{comment end}

{panel end}

{panel type="project" summary="Designing your software"}
Think back to the requirements you found in the analysis project described above. In this project, we will look at how to design the software.

Start by thinking about how the software you are trying to build can be broken up into smaller parts. Maybe there is a database or a user interface or a website? For example, imagine you are writing software to control a robot. The robot needs to use its sensors to follow a black line on the ground until it reach a target. The software for your robot should have a part that interacts with the sensors to get information about what they “see”. It should then pass this information to another part, which analyses the data and decides where to move next. Finally, you should have a part of the software which interacts with the robot’s wheels to make it move in a given direction.

Try to break down your software into as many parts as possible (remember, small components are much easier to build!) but don’t go too far - each part should perform a sensible task and be relatively independent from the rest of the system.

For each part that you have identified, write a brief description about what it does. Then think about how the parts would interact. For each part, ask yourself which other parts it needs to communicate with directly. Maybe a diagram could help visualise this?
{panel end}


## Testing: Did we Build the Right Thing and Does it Work?

{comment}
.. html5: some apps for testing to go below; the above applet at http://fac-staff.seattleu.edu/quinnm/web/education/JavaApplets/applets/SoftwareTesting.html may give some ideas
{comment end}

We’ve decided what our software should do (analysis) and designed its internal structure (design), and the system has been programmed according to the design. Now, of course, we have to test it to make sure it works correctly.

Testing is an incredibly important part of developing software. We cannot really release software that still has lots of bugs to our customers. (Well, we could but our customers wouldn’t be very happy about it.) Remember that software bugs can have both very small and very large effects. On the less serious end of the scale, they might make a program difficult to use or crash your computer. On the other hand, they can cost millions of dollars and even endanger human life. More testing might have prevented the Ariane 5 failure or might have discovered the Therac bug that ended up killing three patients.

Unfortunately, testing is again really difficult because of the size and complexity of software. If a piece of software would take years to read and understand, imagine how long it would take to fully test it!

When we test software, we try lots of different inputs and see what outputs or behaviour the software produces. If the output is incorrect, we have found a bug.

{panel type="curiosity" summary="Bugs and Moths"}

{image filename="harvard-mark-ii.jpg" alt="The Mark II at Harvard" caption="The Mark II at Harvard"}

In 1947, engineers working on a computer called the *Mark II* were investigating a computer error and found that it was caused by a moth which had become trapped inside the computer! This incident is and early example of using the word *bug* to refer to computer errors. Of course, today we use the word to refer to errors in programs, rather than actual insects trapped in the computer.
{panel end}

The problem with testing is that it can only show the presence of errors, not their absence! If you get an incorrect output from the program, you know that you have found a bug. But if you get a correct output, can you really conclude that the program is correct? Not really. The software might work in this particular case but you cannot assume that it will work in other cases. No matter how thoroughly you test a program, you can never really be 100% sure that it’s correct. In theory, you would have to test every possible input to your system, but that’s not usually possible. Imagine testing Google for everything that people could search for! But even if we can’t test everything, we can try as many different test cases as possible and hopefully at least decrease the probability of bugs.

As with design, we can’t possibly deal with the entire software at once, so we again just look at smaller pieces, testing one of them at a time. We call this approach *unit testing*. A unit test is usually done by a separate program which runs the tests on the program that you're writing. That way you can run the tests as often as you like --- perhaps once a day, or even every time there is a change to the program.

It's not unusual to write a unit test program before you write the actual program.
It might seem like wasted work to have to write two programs instead of one, but being able to have your system tested carefully any time you make a change greatly improves the reliability of your final product, and can save a lot of time trying to find bugs in the overall system, since you have some assurance that each unit is working correctly.

Once all the separate pieces have been tested thoroughly, we can test the whole system to check if all the different parts work together correctly. This is called *integration testing*. Some testing can be automated while other testing needs to be done manually by the software engineer.

If I give you a part of the software to test, how would you start? Which test inputs would you use? How many different test cases would you need? When would you feel reasonably sure that it all works correctly?

There are two basic approaches you can take, which we call *black-box testing* and *white-box testing*. With black-box testing, you simply treat the program as a black box and pretend you don’t know how it’s structured and how it works internally. You give it test inputs, get outputs and see if the program acts as you expected.

But how do you select useful test inputs? There are usually so many different ones to choose from. For example, imagine you are asked to test a program that takes a whole number and outputs its successor, the next larger number (e.g. give it 3 and you get 4, give it -10 and you get -9, etc). You can’t try the program for *all* numbers so which ones do you try?

You observe that many numbers are similar and if the program works for one of them it’s probably safe to assume it works for other similar numbers. For example, if the program works as you expect when you give it the number 3, it’s probably a waste of time to also try 4, 5, 6 and so on; they are just so similar to 3.

This is the concept of *equivalence classes*. Some inputs are so similar, you should only pick one or two and if the software works correctly for them you assume that it works for all other similar inputs. In the case of our successor program above, there are two big equivalence classes, positive numbers and negative numbers. You might also argue that zero is its own equivalence class, since it is neither positive nor negative.

For testing, we pick a couple of inputs from each equivalence class. The inputs at the boundary of equivalence classes are usually particularly interesting. Here, we should definitely test -1 (this should output 0), 0 (this should output 1) and 1 (this should output 2). We should also try another negative and positive number not from the boundary, such as -48 and 57. Finally, it can be interesting to try some very large numbers, so maybe we’ll take -2,338,678 and 10,462,873. We have only tested 7 different inputs, but these inputs will probably cover most of the interesting behaviour of our software and should reveal most bugs.

Of course, you might also want to try some invalid inputs, for example “hello” (a word) or “1,234” (a number with a comma in it) or “1.234” (a number with a decimal point). Often, test cases like these can get programs to behave in a very strange way or maybe even crash because the programmer hasn’t considered that the program might be given invalid inputs. Remember that especially human users can give you all sorts of weird inputs, for example if they misunderstand how the program should be used. In case of an invalid input, you probably want the program to tell the user that the input is invalid; you definitely don’t want it to crash!

{comment}

This was a teacher note, but need to check over it

There is a black-box testing interactive under development which you can try out here. Students should try testing [this program first](http://www.cosc.canterbury.ac.nz/csfieldguide/dev/teacher/_static/widgets/SE/formatCurrencyv3.html) by trying to get it to give wrong results or errors e.g. try numbers like "3.40.3" or even text instead of a number. The test case hints will help students to choose suitable test inputs.

Then you may get the students to [use this program](http://www.cosc.canterbury.ac.nz/csfieldguide/dev/teacher/_static/widgets/SE/validatorv3.html) to have a better understanding of black-box testing. In case of an invalid input, you probably want the program to tell the user that the input is invalid; you definitely don’t want it to crash!

Finally, [try the triangle problem](http://www.cosc.canterbury.ac.nz/csfieldguide/dev/teacher/_static/widgets/SE/triangle.html). Give it wrong values and see the output and judge whether it is working as intended. It should work in all cases because the program has bugs in it. Think and write down 10 test cases and then go to the [triangle test case validator](http://www.cosc.canterbury.ac.nz/csfieldguide/dev/teacher/_static/software_engineering/SE-triangle-test-cases.pdf) and input the test cases. The validator will indicate how many of the bugs the student's tess have found. Review the feedback to check how many cases they have got right. Enjoy testing!!

Challenge the students to try to find the problem(s) using as few test inputs as possible (by using the concept of equivalence classes).

A complete solution with all test cases that the interactive is looking for, with their equivalence classes, can be [obtained here](http://www.cosc.canterbury.ac.nz/csfieldguide/dev/teacher/_static/software_engineering/SE-triangle-test-cases-answers.pdf)
{comment end}

Black-box testing is easy to do but not always enough because sometimes finding the different equivalence classes can be difficult if you don’t know the internal structure of the program. When we do white-box testing, we look at the code we are testing and come up with test cases that will execute as many different lines of code as possible. If we execute each line at least once, we should be able to discover a lot of bugs. We call this approach *code coverage* and aim for 100% coverage, so that each line of code is run at least once. In reality, even 100% code coverage won’t necessarily find all bugs though, because one line of code might work differently depending on inputs and values of variables in a program. Still, it’s a pretty good start.

{comment}

 App for code coverage: Maybe take the app for blackbox testing as a starting point. For each of the examples, allow students to “step into the code”, a simple flow chart of the method. Then they can see their inputs “flowing” through the program, highlighting the tested paths as they go. In the end, this will show if they managed to test every path through the program and give a code coverage figure (e.g. 80%).
{comment end}

Unit testing is very useful for finding bugs. It helps us find out if the program works as *we* intended. Another important question during testing is if the software does what the *customer* wanted (Did we build the right thing?). *Acceptance testing* means showing your program to your stakeholders and getting feedback about what they like or don’t like. Any mistakes that we made in the analysis stage of the project will probably show up during acceptance testing. If we misunderstood the customer during the interview, our *unit tests* might pass (i.e. the software does what we thought it should) but we may still have an unhappy customer.

Different stakeholders can be very different, for example in terms of technical skills, or even could have given us conflicting requirements for the software. It’s therefore of course possible to get positive feedback from one stakeholder and negative feedback from another.


{panel type="project" summary="Acceptance Testing"}
For this project, choose a small program such as a Windows desktop app or an Apple dashboard widget.
Pick something that you find particularly interesting or useful (such as a timer, dictionary or calculator). Start by reading the description of the program to find out what it does *before* you try it out.

Next, think about a stakeholder for this software. Who would use it and why? Briefly write down some background information about the stakeholder (as in the analysis project) and their main requirements. Note which requirements would be most important to them and why.

Now, you can go ahead and install the program and play around with it. Try to imagine that you are the stakeholder that you described above. Put yourself in this person’s shoes. How would they feel about this program? Does it meet your requirements? What important features are missing? Try to see if you can find any particular problems or bugs in the program. (Tip: sometimes giving programs unexpected input, for example a word when they were expecting a number, can cause some interesting behaviour.)

Write up a brief acceptance test report about what you found. Try to link back to the requirements that you wrote down earlier, noting which have been met (or maybe partially met) and which haven’t. Do you think that overall the stakeholder would be happy with the software? Do you think that they would be likely to use it? Which features would you tell the software developers to implement next?
{panel end}

{panel type="teacher-note" summary="Reading the description"}

It’s important for this project that students read the description of the program and think about a stakeholder and requirements before actually trying out the software, otherwise their thinking about the stakeholder and requirements may be influenced by what they already know about the software.

{panel end}

{comment}
.. xtcb It would be nice to add a test-driven project one day. We could provide unit tests (in a couple of common languages) and they have to develop to meet the tests, documenting the process and the kinds of errors that get detected along the way. Could be software to read in a date, or $ amount.

.. xtcb new possible project: The following are example repositories of real defects for real projects in the software industry. Students may be benefitted by reviewing these examples to see how other experienced testers write defect reports.
.. ? https://bugzilla.mozilla.org
.. ? http://bugzilla.kernel.org
.. ? https://issues.apache.org/bugzilla
.. ? http://www.openoffice.org/issues/query.cgi
.. ? https://bugs.eclipse.org/bugs
.. The students can either perform a SUT test or track bugs using Bugzilla, or they may review examples of bug reports prepared by experienced testers. This will also allow them to compare different testing strategies and will give them some understanding about how real bugs are fixed
{comment end}

## Software processes

So far in this chapter, you’ve learned about different phases of software development: analysis, design and testing. But how do these phases fit together? At what time during the project do we do what activity? That’s the topic of *software processes*.

The obvious answer would be to start with analysis to figure out what we want to build, then design the structure of the software, implement everything and finally test the software. This is the simplest software process, called the *waterfall process*.

{image filename="waterfall-process-diagram.png" alt="Waterfall Diagram"}

The waterfall process is borrowed from other kinds of engineering. If we want to build a bridge, we go through the same phases of analysis, design, implementation and testing: we decide what sort of bridge we need (How long should it be? How wide? How much load should it be able to support?), design the bridge, build it and finally test it before we open it to the public. It’s been done that way for many decades and works very well, for bridges at least.

We call this process the waterfall process because once you “jump” from one phase of the project to the next, you can’t go back up to the previous one. In reality, a little bit of backtracking is allowed to fix problems from previous project phases but such backtracking is usually the exception. If during the testing phase of the project you suddenly find a problem with the requirements you certainly won’t be allowed to go back and rewrite the requirements.

{image filename="waterfall-process-cartoon.png" alt="Waterfall Cartoon"}

An advantage of the waterfall process is that it’s very simple and easy to follow. At any point in the project, it’s very clear what stage of the project you are at. This also helps with planning: if you’re in the testing stage you know you’re quite far into the project and should finish soon. For these reasons, the waterfall process is very popular with managers who like to feel in control of where the project is and where it’s heading.

{panel type="curiosity" summary="Hofstadter’s law"}
Your manager and customer will probably frequently ask you how much longer the project is going to take and when you will finally have the finished program. Unfortunately, it’s really difficult to know how much longer a project is going to take. According to Hofstadter’s law, “It always takes longer than you expect, even when you take into account Hofstadter's Law.”
Learning to make good estimates is an important part of software engineering.
{panel end}

Because it’s just so nice and simple, the waterfall process is still in many software engineering textbooks and is widely used in industry. The only problem with this is that the waterfall process just does not work for most software projects.

So why does the waterfall process not work for software when it clearly works very well for other engineering products like bridges (after all, most bridges seem to hold up pretty well...)? First of all, we need to remember that software is very different from bridges. It is far more complex. Understanding the plans for a single bridge and how it works might be possible for one person but the same is not true for software. We cannot easily look at software as a whole (other than the code) to see its structure. It is not physical and thus does not follow the laws of physics. Since software is so different from other engineering products, there really is no reason why the same process should necessarily work for both.

To understand why the waterfall process doesn’t work, think back to our section about analysis and remember how hard it is to find the right requirements for software. Even if you manage to communicate with the customers and resolve conflicts between the stakeholders, the requirements could still change while you’re developing the software. Therefore, it is very unlikely that you will get the complete and correct requirements for the software at the start of your project.

If you make mistakes during the analysis phase, most of them are usually found in the testing stage of the project, particularly when you show the customer your software during acceptance testing. At this point, the waterfall process doesn’t allow you to go back and fix the problems you find. Similarly, you can’t change the requirements halfway through the process. Once the analysis phase of the project is finished, the waterfall process “freezes” the requirements. In the end of your project, you will end up with software that hopefully fulfills *those* requirements, but it is unlikely that those will be the *correct* requirements.

You end up having to tell the customer that they got what they asked for, not what they needed. If they've hired you, they'll be annoyed; if it's software that you're selling (such as a smartphone app), people just won't bother buying it.
You can also get things wrong at other points in the project. For example, you might realise while you’re writing the code that the design you came up with doesn’t really work. But the waterfall process tells you that you have to stick with it anyway and make it work somehow.

{comment}
{image filename="software-engineering/se-tree-swing-cartoon.png" alt="Software Design of a Tree-Swing"}

Design by [Paragon Innovations](http://www.paragoninnovations.com/guide.shtml) and drawn by [Project Cartoon](http://www.projectcartoon.com/about/)
{comment end}

So if the waterfall process doesn’t work, what can we do instead? Most modern software development processes are based on the concept of iteration. We do a bit of analysis, followed by some design, some programming and some testing. (We call this one iteration.) This gives us a rather rough prototype of what the system will look like. We can play around with the prototype, show it to customers and see what works and what doesn’t. Then, we do the whole thing again. We refine our requirements and do some more design, programming and testing to make our prototype better (another iteration). Over time, the prototype grows into the final system, getting closer and closer to what we want.
Methodologies based on this idea are often referred to as *agile* --- they can easily adapt as changes become apparent.

{image filename="iterative-software-development-diagram.png" alt="The iterative software development cycle starts with feedback from showing the prototype to the customer with analysis, the back to design, implementation and testing, and then starting again with analysis."}

The advantage with this approach is that if you make a mistake, you will find it soon (probably when you show the prototype to the customer the next time) and have the opportunity to fix it. The same is true if requirements change suddenly; you are flexible and can respond to changes quickly. You also get a lot of feedback from the customers as they slowly figures out what they need.

There are a number of different software processes that use iteration (we call them *iterative processes*); a famous one is the *spiral model*. Although the details of the different processes vary, they all use the same iteration structure and tend to work very well for software.

Apart from the question of what we do at what point of the project, another interesting question addressed by software processes is how much time we should spend on the different project phases. You might think that the biggest part of a software project is programming, but in a typical project, programming usually takes up only about 20% of the total time! 40% is spent on analysis and design and another 40% on testing. This shows that software engineering is so much more than programming.

Once you’ve finished developing your program and given it to the customer, the main part of the software project is over. Still, it’s important that you don’t just stop working on it. The next part of the project, which can often go on for years, is called *maintenance*. During this phase you fix bugs, provide customer support and maybe add new features that customers need.

{panel type="curiosity" summary="Brooks' law"}
{glossary-definition term="Brooks' law" definition="An observation that adding more people to a project that is running late may actually slow it down more."}

Imagine that your project is running late and your customer is getting impatient. Your first instinct might be to ask some of your friends if they can help out so that you have more people working on the project. Brooks’ law, however, suggests that that is exactly the wrong thing to do!

{glossary-link term="Brooks’ law" reference-text="software engineering"}Brooks’ law{glossary-link end} states that “adding manpower to a late software project makes it later.” This might seem counterintuitive at first because you would assume that more people would get more work done. However, the overhead of getting new people started on the project (getting them to understand what you are trying to build, your design, the existing code, and so on) and of managing and coordinating the larger development team actually makes things slower rather than faster in the short term.

{panel end}

{panel type="project" summary="Fun with the Waterfall and Agile Processes"}
The waterfall process is simple and commonly used but doesn’t really work in practice. In this activity, you’ll get to see why. First, you will create a design which you then pass on to another group. They have to implement your design exactly and are not allowed to make any changes, even if it doesn’t work!

You need a deck of cards and at least 6 people. Start by dividing up into groups of about 3-4 people. You need to have at least 2 groups. Each group should grab two chairs and put them about 30cm apart. The challenge is to build a bridge between the two chairs using only the deck of cards!

Before you get to build an actual bridge, you need to think about how you are going to make a bridge out of cards. Discuss with you team members how you think this could work and write up a short description of your idea. Include a diagram to make your description understandable for others.

Now exchange your design with another group. Use the deck of cards to try to build your bridge to the exact specification of the other group. You may not alter their design in any way (you are following the waterfall process here!). As frustrating as this can be (especially if you know how to fix the design), if it doesn’t work, it doesn’t work!

If you managed to build the bridge, congratulations to you and the group that managed to write up such a good specification! If you didn’t, you now have a chance to talk to the other group and give them feedback about the design. Tell them about what problems you had and what worked or didn’t work. The other group will tell you about the problems they had with your design!

Now, take your design back and improve it, using what you just learnt about building bridges out of cards and what the other group told you. You can experiment with cards as you go, and keep changing the design as you learn about what works and what doesn't (this is an agile approach, which we are going to be looking at further shortly). Keep iterating (developing ideas) until you get something that works.

Which of these two approaches worked best --- designing everything first, or doing it in the agile way?
{panel end}


{panel type="teacher-note" summary="Further advice on the above project"}
Usually the point about agile design comes across very strongly; it's rare for a designed bridge to work, but it can usually be done with the iterative agile approach. Students might point out that they aren't experts with cards, but a software engineer should be an expert with software. However, the real issue is that the software engineer probably isn't an expert at the kind of system they're implementing, since the system probably hasn't been built before.

Another option is to get students to build card houses (the main point is that the students should be working in a domain they're not familiar with; if they've built card bridges before then the activity won't work!) A card house might be easier for younger students; the bridge is quite a challenge! You could challenge students to design and build a tower as high as possible out of cards. Alternatively, you could use Lego but cards are definitely more challenging and harder to design with.
{panel end}

{panel type="project" summary="A Navigation Language"}
In this activity, you will develop a language for navigating around your school. Imagine that you need to describe to your friend how to get to a particular classroom. This language will help you give a precise description that your friend can easily follow.

First, figure out what your language has to do (i.e. find the *requirements*). Will your language be for the entire school or only a small part? How exact will the descriptions be? How long will the descriptions be? How easy will they be to follow for someone who does / doesn’t know your language? How easy will it be to learn? …

Now, go ahead and *design* the language. Come up with different commands (e.g. turn left, go forward 10, …). Make sure you have all the commands you need to describe how to get from one place in your school to any other!

Finally, *test* the language using another student. Don’t tell them where they’re going, just give them instructions and see if they follow them correctly. Try out different cases until you are sure that your language works and that you have all the commands that you need. If you find any problems, go back and fix them and try again!

Note down how much time each of the different phases of the project take you. When you have finished, discuss how much time you spent on each phase and compare with other students. Which phase was the hardest? Which took the longest? Do you think you had more time for some of the phases? What problems did you encounter? What would you do differently next time around?
{panel end}

{panel type="project" summary="Block Building (Precise Communication)"}
Communicating clearly with other software engineers and customers is essential for software engineers. In this activity, you get to practice communicating as precisely as possible!

Divide up into pairs, with one *creator* and one *builder* in each pair. Each person needs a set of at least 10 coloured building blocks (e.g. lego blocks). Make sure that each pair has a matching set of blocks or this activity won’t work!

The two people in each pair should not be able to see each other but need to be able to hear each other to communicate. Put up a screen between the people in each pair or make them face in opposite directions. Now, the creator builds something with their blocks. The more creative you are the more interesting this activity will be!

When the creator has finished building, it’s the builder's turn. His or her aim is to build an exact replica of the creator's structure (but obviously without knowing what it looks like). The creator should describe exactly what they need to do with the blocks. For example, the creator could say “Put the small red block on the big blue block” or “Stand two long blue blocks up vertically with a one block spacing between them, and then balance a red block on top of them”. But the creator should not describe the building as a whole (“Make a doorframe.”).

When the builder thinks they are done, compare what you built! How precise was your communication? Which parts were difficult to describe for the creator / unclear for the builder? Switch roles so that you get to experience both sides!
{panel end}

## Agile software development

*Agile* software development has become popular over the last 10 years; two of the most famous agile processes are called [XP](https://en.wikipedia.org/wiki/Extreme_programming) and [Scrum](https://en.wikipedia.org/wiki/Scrum_(development\)). Agile software development is all about being extremely flexible and adaptive to change. Most other software processes try to manage and control changes to requirements during the process; agile processes accept and expect change. The following xkcd comic illustrates part of the apparent dilemma that agile processes aim to address. With Agile, we can develop software quickly, correctly, and be adaptive to change.

{image filename="xkcd-good-code.png" hover-text="You can either hang out in the Android Loop or the HURD loop." alt="A xkcd comic on good code" source="https://xkcd.com/844/"}

Agile processes work similarly to iterative processes in that they do a number of iterations of analysis, design, implementation and testing. However, these iterations are extremely short, each usually lasting only about 2 weeks.

In many other processes, documentation is important. We document the requirements so that we can look back at them; we document our design so that we can refer back to it when we program the system. Agile software processes expect things to change all the time. Therefore, they do very little planning and documentation because documenting things that will change anyway is a bit of a waste of time.

Agile processes include lots of interesting principles that are quite different from standard software development. We look at the most interesting ones here. If you want to find out more, have a look at [Agile Academy on Youtube](https://www.youtube.com/user/AgileAcademyAus) which has lots of videos about interesting agile practices! There’s also [another video here](https://www.youtube.com/watch?v=kqz_jDS0RWY) that explains the differences between agile software development and the waterfall process.

Here are some general principles used for agile programming:

### Pair-programming

Programming is done in pairs with one person coding while the other person watches and looks for bugs and special cases that the other might have missed. It’s simply about catching small errors before they become bugs. After all, 4 eyes see more than 2.

You might think that pair-programming is not very efficient and that it would be more productive to have programmers working separately; that way, they can write more code more quickly, right? Pair-programming is about reducing errors. Testing, finding and fixing bugs is hard; trying not to create them in the first place is easier. As a result, pair-programming has actually been shown to be more efficient than everyone programming by themselves!


### YAGNI

YAGNI stands for “You ain’t gonna need it” and tells developers to keep things simple and only design and implement the things that you know you are really going to need. It can be tempting to think that in the future you might need feature x and so you may as well already create it now. But remember that requirements are likely to change so chances are that you won’t need it after all.

{image filename="xkcd-the-general-problem.png" hover-text="I find that when someone's taking time to do something right in the present, they're a perfectionist with no ability to prioritize, whereas when someone took time to do something right in the past, they're a master artisan of great foresight." alt="A xkcd comic on the general problem" source="https://xkcd.com/974/"}

You ain’t gonna need it!


### Constant testing

Agile processes take testing very seriously. They usually rely on having lots of automated unit tests that are run at least once a day. That way, if a change is made (and this happens often), we can easily check if this change has introduced an unexpected bug.


### Refactoring

There are many different ways to design and program a system. YAGNI tells you to start by doing the simplest thing that’s possible. As the project develops, you might have to change the original, simple design. This is called *refactoring*.

Refactoring means to change your design or implementation without changing the program’s behaviour. After a refactoring, the program will work exactly the same, but will be better structured in some way. Unit tests really come in handy here because you can use them to check that the code works the same way before and after the refactoring.

Refactoring only works on software because it is “soft” and flexible. The same concept does not really work for physical engineering products. Imagine that when building a bridge, for example, you started off by doing the simplest possible thing (putting a plank over the river) and then continually refactored the bridge to get the final product.


### Test-driven development

In standard software development, we first write some code and then test it. This makes sense: we need the code before we can test it, right? Test-driven development tells you to do the exact opposite!

Before you write a piece of code, you should write a test for the code that you are about to write. This forces you to think about exactly what you’re trying to do and what special cases there are. Of course, if you try to run the test, it will fail (since the functionality it is testing does not yet exist). When you have a failing test, you can then write code to make the test pass.

### Programmer welfare

Software developers should not work more than 40 hours per week. If they do overtime one week they should not do more overtime the following week. This helps keep software developers happy, productive, creative and energetic, and makes sure they don’t get overworked.


### Customer involvement

A customer representative should be part of the developing team (ideally spending full-time with the team), on hand to answer questions or give feedback at all times. This is important to be able to quickly change the requirements or direction of the project. If you have to wait 2 weeks until you can get feedback from your customer, you will not be able to adapt to change very quickly!

Although having a customer on the development team is a great idea in theory, it is quite hard to achieve in practice. Most customers simply want to tell you their requirements, pay you and then get the software delivered 5 months later. It’s rare to find a customer who is willing and has the time to be more involved in the project. Sometimes companies will hire an expert to be part of the team; for example, a company working on health software might have a doctor on the team, or if they are working on educational software, they may hire a teacher. This sounds expensive, but since failed software can cost millions of dollars, paying the salary of an expert is a relatively small part of the overall cost, and much more likely to lead to success.

{panel type="curiosity" summary="Christopher Alexander"}
So far, we’ve mainly compared software development to engineering and building bridges, but you might have noticed that it’s also pretty similar to architecture. In fact, software development (in particular agile software development) has borrowed a lot of concepts from architecture. An architect called Christopher Alexander, for example, suggested involving customers in the design process. Sound familiar? Several other suggestions from Christopher Alexander were also picked up by the agile development community and as a result his thinking about architecture has shaped how we think about software development. This is despite the fact that Christopher Alexander knew nothing about software development. He was apparently very surprised when he found out how well known he is among software developers!
{panel end}

### Courage

“Courage” might seem like an odd concept in the context of software development. In agile processes, things change all the time and therefore programmers need to have the courage to make changes to the code as needed, fix the problems that need to be fixed, correct the design where needed, throw away code that doesn’t work, and so on. This might not seem like a big deal, but it can actually be quite scary to change code, particularly if the code is complicated or has been written by a different person. Unit tests really help by giving you courage: you’ll feel more confident to change the code if you have tests that you can run to check your work later.


{panel type="project" summary="Software processes"}
This project will provide insight into a real software engineering process, but you'll need to find a software engineer who is prepared to be interviewed about their work. It will be ideal if the person works in a medium to large size company, and they need to be part of a software engineering team (i.e. not a lone programmer).

The project revolves around interviewing the person about the process they went through for some software development they did recently. They may be reluctant to talk about company processes, in which case it may help to assure them that you will keep their information confidential (your project should only be viewed by you and those involved in supervising and marking it; you should state its confidential nature clearly at the start so that it doesn't get published later).

You need to do substantial preparation for the interview. Find out about the kind of software that the company makes. Read up about software engineering (in this chapter) so that you know the main terminology and techniques.

Now prepare a list of questions for the interviewee.
These should find out what kind of software development processes they use, what aspects your interviewee works on, and what the good and bad points are of the process, asking for examples to illustrate this.

You should take extensive notes during the interview (and record it if the person doesn't mind).

You then need to write up what you have learned, describing the process, discussing the techniques used, illustrating it with examples, and evaluating how well the process works.
{panel end}

## The whole story!

In this chapter, we’ve tried to give you an introduction to the challenges of creating software and some techniques that software engineers use to overcome them. We’ve really only scratched the surface of software analysis, design, testing and software processes; there are entire books about each of these areas!

It can be difficult to understand the importance of some of the problems and techniques we have described here if you have never worked on a larger software project yourself. Some may seem blindingly obvious to you, others may seem irrelevant. When you work on your first large project, come back to this chapter and hopefully you’ll recognise some of the problems we have described here!

## Further reading

### Useful Links
- [Wikipedia - Software engineering](https://en.wikipedia.org/wiki/Software_engineering)
- [CS4FN - Software engineering](http://www.cs4fn.org/fundamentals/softwareeng.php)
- [Teach ICT - Systems Life Cycle](http://www.teach-ict.com/as_a2_ict_new/ocr/A2_G063/331_systems_cycle/slc_stages/home_slc.html)
- [Wikipedia - Software crisis](https://en.wikipedia.org/wiki/Software_crisis)
- [IEEE - Why software fails](http://spectrum.ieee.org/computing/software/why-software-fails)
- [Wikipedia - Software design](https://en.wikipedia.org/wiki/Software_design)
- [Wikipedia - Abstraction](https://en.wikipedia.org/wiki/Abstraction_(computer_science\))
- [Wikipedia - Software testing](https://en.wikipedia.org/wiki/Software_testing)
- [Wikipedia - Software development process](https://en.wikipedia.org/wiki/Software_development_process)
- [Wikipedia - Waterfall model](https://en.wikipedia.org/wiki/Waterfall_model)
- [Wikipedia - Iterative and incremental development](https://en.wikipedia.org/wiki/Iterative_and_incremental_development)
- [Wikipedia - Agile software development](https://en.wikipedia.org/wiki/Agile_software_development)
- [Wikipedia - Test driven development](https://en.wikipedia.org/wiki/Test-driven_development)
