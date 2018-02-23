# Wprowadzenie

{panel type="teacher-note" summary="Wprowadzenie dla nauczycieli"}

Celem tego przewodnika (interaktywnego podręcznika) jest wsparcie procesu nauczania informatyki w szkołach średnich.
Pierwotnie podręcznik był tworzony w związku z wprowadzeniem zajęć informatyki do szkół średnich w Nowej Zelandii w latach 2011-2013.

W wersji dla nauczyciela w specjalnych ramkach znajdują się dodatkowe informacje oraz odpowiedzi i wskazówki do zadań. Z tego względu ta wersja podręcznika nie powininna być udostępniana uczniom (jednakże ze względu na to, iż do tego materiału jest darmowy bardziej rezolutni uczniowie mogą znaleźć go na własną rękę).

{panel end}

{video url="https://wwww.youtube.com/embed/v5yeq5u2RMI?rel=0"}

## Z lotu ptaka

Dlaczego jest tak, że ludzie albo kochają komputery, albo ich nienawidzą? Dlaczego niektórzy nie wyobrażają sobie życia bez różnego rodzaju urządzeń komputerowych, a  inni na samą myśl o takich urządzeniach irytują się, a nawet gotowi są zniszczyć je? I co to ma wspólnego z informatyką? A co właściwie jest informatyka?

Dobrze, że zadajesz takie pytania!

Wielu ludzi myli informatykę z programowaniem. Ktoś kiedyś powiedział „Informatyka ma tyle samo wspólnego z programowaniem, co astronomia z teleskopami” ([Mike Fellows](http://en.wikiquote.org/wiki/Computer_science)). 
Programowanie to narzędzie, którym informatycy posługują się, aby urzeczywistnić różne wspaniałe pomysły, które mogą zmienić życie ludzi na lepsze. Jednak znajomość języka programowania nie wystarczy, by tworzyć oprogramowanie szybkie, przyjazne w użyciu, niezawodne, bezpieczne, użyteczne i do tego zabawne! 

Oto przykład: Komputery potrafią wykonywać miliardy operacji w ciągu sekundy, a ciągle możemy usłyszeć narzekania, że są zbyt powolne. Człowiek jest w stanie dostrzec zmiany dokonujące się w czasie 1/10 sekundy. Jeśli na odpowiedź programu komputerowego ktoś czeka dłużej, to może uznać program za powolny, działający mało płynnie i frustrujący. Aby zadowolić użytkownika, reakcja programu na polecenie użytkownika powinna pojawić się o wiele szybciej niż w ciągu sekundy. Jeśli stworzony przez Ciebie program ma przeszukać miliony pozycji w bazie danych lub wyświetlić miliony pikseli na ekranie, to nie możesz pozwolić sobie na to, aby działał w sposób nieefektywny. Nie możesz po prostu powiedzieć użytkownikowi, by kupił szybszy komputer&hellip; Skończyłoby się to prawdopodobnie tym, że użytkownik podziękuje ci za współpracę i pójdzie kupić u konkurencji szybsze oprogramowanie!

Oto rada pochodząca od Freda Wilsona, który zainwestował wiele w firmy z branży komputerowej:

> Po pierwsze i najważniejsze, wierzymy, że szybkość to coś więcej niż zwykła cecha. Szybkość jest najważniejszą cechą. Jeśli twoje oprogramowanie działa powoli, ludzie nie będą go używać. Dotyczy to zwłaszcza zwykłych użytkowników. Myślę, że użytkownicy, którzy korzystają z zaawansowanych funkcji danego oprogramowania, są czasami bardziej wyrozumiali, ale według mnie typowy użytkownik jest jak moja żona i dzieci: jeśli coś działa powoli, to oni po prostu odchodzą&hellip;. Szybkość to coś więcej niż cecha. To jest niezbędne wymaganie.

> -- [Fred Wilson](https://en.wikipedia.org/wiki/Fred_Wilson_(financier\)) ([Source](http://triple-networks.com/2011/12/06/10-golden-principles-of-successful-web-apps/))

Kluczowym wyzwaniem w informatyce jest stworzyć oprogramowanie działające szybko! Zwłaszcza jeśli ma działać na urządzeniach (np. smartfonach) starszej generacji lub ma być uruchamiane w jakimś centrum obliczeniowym, gdzie użytkownik ma płacić za każdą minutę czasu dostępu do komputerów. 
Nie można powiedzieć klientom, by kupili szybsze urządzenia -- trzeba dostarczyć efektywne oprogramowanie.

## Szybkość to nie wszystko

W informatyce nie chodzi jedynie o szybkość.
Spróbuj wykonać jakieś proste obliczenia, posługując się dwoma kalkulatorami, udostępnionymi poniżej. Oba mają tę samą funkcjonalność (można na nich wykonać te same obliczenia), ale jeden z nich jest bardziej przyjazny w obsłudze. Dlaczego?

(W podręczniku jest wiele podobnych interaktywnych narzędzi. Aby ich używać, będziesz potrzebować aktualnych wersji przeglądarek internetowych.)

{interactive name="awful-calculator" type="in-page"}

Drugi kalkulator działa wolniej i to może być frustrujące. Ale ma bardziej ekstrawagancki interfejs -- klawisze są wyświetlane w powiększeniu po wskazaniu ich myszką. Czy to ułatwia posługiwanie się kalkulatorem? Czy umieszczenie bardzo blisko siebie klawiszy „C” i 	„=” nie było źródłem dodatkowych problemów

Projektowanie przyjaznych w użyciu interfejsów jest istotne w informatyce. Estetyka (wygląd i grafika) interfejsu jest ważna, ale ważniejsze jest uwzględnienie w nim psychologii zachowań użytkownika.  Oto przykład: Wyobraź sobie, że przyciski „OK” i „Anuluj” od czasu do czasu w oknach dialogowych będą zamienione miejscami. W konsekwencji użytkownik musi zachować szczególną ostrożność, zamiast działać instynktownie, nauczony wcześniejszymi doświadczeniami.

Problem skalowalności oprogramowania to inny ważny temat. Wyobraź sobie, że jesteś twórcą witryny internetowej, którą odwiedzają tysiące użytkowników. Wszystko idzie dobrze, aż do chwili, gdy gwałtownie zwiększa się liczba użytkowników i są ich miliony. Jeśli twój serwis okaże się przeciążony, ludzie będą się irytować czekaniem na odpowiedź serwera i kolejnego dnia możesz stracić wszystkich użytkowników -- przeniosą się do serwisu stworzonego przez kogoś innego. Ale jeśli twoje programy są tak zaprojektowane, że nigdy nie dojdzie do przeciążenia, to  możesz się spodziewać, że  pojawią się zainteresowani kupnem twojej firmy!

Niektóre z problemów można rozwiązać przez zakup większej ilości sprzętu komputerowego (serwerów), ale to może być kosztowna i rozrzutna opcja. Do tego takie rozwiązanie ma niekorzystny wpływ na środowisko, gdyż wiąże się ze zwiększeniem zapotrzebowania na energię elektryczną (potrzebną m.in. do chłodzenia urządzeń). W przypadku urządzeń przenośnych wymagania, aby oprogramowanie działało szybko i wykorzystywało zasoby w sposób ekonomiczny (energooszczędny) mają jeszcze większe znaczenie. Nieefektywne przetwarzanie oznacza nie tylko większe zużycie baterii, ale i większe zapotrzebowanie oprogramowania na pamięć, czyli w konsekwencji zwiększenie rozmiaru i wagi urządzenia, a więc i kosztów związanych np. z chłodzeniem. 

Załóżmy optymistycznie, że Twój serwis internetowy nigdy nie jest przeciążony i znakomicie sobie radzi z obsługą milionów użytkowników. Pojawia się kolejne pytanie: czy Twoja witryna jest bezpieczna? Czy zostały zastosowane odpowiednie zabezpieczenia, aby nikt nie mógł się włamać do serwisu i wykraść dane użytkowników? W jaki sposób należy projektować systemy, aby zapewnić poufność informacji o klientach i ich transakcjach?

Informatyka zajmuje się szukaniem odpowiedzi na takie i inne pytania.
Celem tego przewodnika jest przedstawienie w sposób przystępny różnych pojęć i koncepcji informatycznych, aby poszerzyć twoją wiedzę na temat informatyki i dać ci lepsze wyobrażenie różnych zagadnień informatycznych. Ten podręcznik ma pomóc ci w rozeznaniu, czy informatyka to jest dziedzina dla ciebie na tyle interesująca, by wiązać z nią swoją przyszłość zawodową.
Przewodnik jest skierowany z myślą o uczniach starszych klas szkół podstawowych i szkół ponadpodstawowych. 

Podzieliliśmy całość na wiele zagadnień, które ukazują informatykę z różnych stron. Są to m.in. algorytmy, interakcja człowiek -- komputer, kompresja danych, kryptografia, grafika komputerowa i sztuczna inteligencja. Trzeba podkreślić, że te tematy są ze sobą powiązane i należy o tym pamiętać w czasie zaznajamiani się z nimi. 

Przewodnik ma wystarczający poziom szczegółowości, by zorientować się, czym jest informatyka. Przewodnik ma  dobrze przygotowywać do późniejszych pogłębionych studiów na lekcjach w szkole średniej, czy na studiach. W tekście znajduje się wiele odnośników do stron internetowych i książek, w których można znaleźć bardziej szczegółowe informacje.

## Programowanie

Co z programowaniem? Nie wymagamy umiejętności programowania od korzystających z przewodnika. W niektórych miejscach będziemy zachęcać jednak potrafiących programować do wykonania pewnych zadań programistycznych. Nie można zapominać, że wszystkie koncepcje przedstawione w przewodniku mają zastosowanie praktyczne i zostały kiedyś zastosowane w takim, czy innym oprogramowaniu. Dlatego zachęcamy, aby równolegle z poszerzaniem wiedzy na temat różnych zagadnień informatycznych, uczyć się programowania. W Internecie jest wiele kursów programowania, również darmowych. Jest też wiele książek na ten temat. Warto zacząć od strony [code.org](http://www.code.org/) lub działu informatycznego projektu [Khan Academy](http://pl.khanacademy.org//cs/).

Programowanie to jedna z wielu umiejętności wymaganych od informatyka. Ten przewodnik da ci wyobrażenie na temat innych kompetencji ważnych w informatyce, np. matematycznych czy tych z zakresu psychologii i komunikacji interpersonalnej.

## Zasady korzystania

Rozdziały przewodnika zostały tak zaprojektowane, że można je czytać w dowolnej kolejności. We wstępie do niektórych rozdziałów zaznaczono, że wskazane jest zapoznanie się najpierw z innym rozdziałem. Warto rozpocząć naukę od rozdziału na temat binarnego zapisu informacji, gdyż system dwójkowy (binarny) ma zasadnicze znaczenie w wielu obszarach informatyki.

Każdy z rozdziałów rozpoczyna się podrozdziałem „Z lotu ptaka”. Omawiamy w nim informacje, które mają ukazać znaczenie danego zagadnienia i jego praktyczne zastosowania oraz staramy się zmotywować do dalszej lektury. Kluczowe pojęcia i koncepcje są wyjaśnione na przykładach, często uproszczonych wersjach rzeczywistych problemów, którymi zajmują się informatycy. Niekiedy tekstowi towarzyszą interaktywne narzędzia, które powalają na eksperymentowanie, by sprawdzić zrozumienie tekstu. Zachęcamy do tego, by robić z nich dobry użytek!

Na końcu każdego rozdziału znajduje się podrozdział „Podsumowanie”, która zawiery wzmianki na temat wątków pominiętych w tekście głównym. Czasami są to zagadnienia, których zrozumienie będzie wymagać znajomości matematyki na trochę wyższym poziomie czy umiejętności programowania. 

W przewodniku zaproponowano projekty, których wykonanie może być np. podstawą do otrzymania ocen szkolnych.

## O przewodniku

Przewodnik jest udostępniany za darmo. Dostęp do wersji źródłowej materiałów jest możliwy poprzez GitHub.

Zasady licencji *Creative Commons Attribution-NonCommercial-ShareAlike licence* pozwalają na wprowadzanie zmian i udoskonaleń. W takim przypadku prosimy o zachowanie informacji o lokalizacji oryginalnej wersji przewodnika. Zmodyfikowana wersja musi pozostać dostępna za darmo.

Oryginalna, angielska wersja przewodnika znajduje się na http://www.csfieldguide.org.nz/". Polska wersja powstała w ramach projektu CS4HS firmy Google, przy wsparciu Uniwersytetu im. Adama Mickiewicza w Poznaniu.

Niektóre fragmenty w wersji polskiej różnią się od oryginału, aby były bardziej zrozumiałe dla polskiego czytelnika. Przewodnik zawiera wiele odnośników do źródeł w języku angielskim (dla czytelników pragnących poszerzyć wiedzę), zatem znajomość języka angielskiego będzie przydatna. Jednak nie jest ona konieczna i nawet bez znajomości angielskiego czytelnik może bez przeszkód z przewodnika korzystać.

## Dalsze lektury
Każdy rozdział kończy się propozycjami lektur, które pozwolą na pogłębienie wiedzy. Często są to odnośniki do stron internetowych.
Jest wiele książek o szerokiej tematyce informatycznej, napisanych z myślą o ukazaniu w miarę pełnego obrazu tej dziedziny. Autorzy przewodnika polecają szczególnie:

- Dawid Harel, *Algorithmics. The spirit of computing* (tłumaczenie polskie: *Algorytmika. Rzecz o istocie informatyki*)
- Jeremy Kubica, [Computational fairy tales](http://computationaltales.blogspot.co.nz) 
- Jurag Hromkovic, *Algorithmic adventures: from knowledge to magic* 
- A. K. Dewdney, *The Turing Omnibus*

Godne uwagi są też artykuły Wikipedii oraz wiele innych stron internetowych. Wśród tych w języku angielsku polecamy szczególnie:

- [Computer Science For Fun](http://www.cs4fn.org) 
- [Babbage's bag](http://www.i-programmer.info/babbages-bag/) 
- [CS Bytes](http://www.nsf.gov/cise/csbytes/) 
- [Thriving in our digital world](http://www.cs.utexas.edu/~engage/) 
- [CS animated](http://www.csanimated.com/) 
- [CS for All](http://www.cs.hmc.edu/csforall/)

