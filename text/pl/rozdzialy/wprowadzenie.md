# Wprowadzenie

{panel type="teacher-note" summary="Wprowadzenie dla nauczycieli"}

Celem tego przewodnika (interaktywnego podręcznika) jest wsparcie procesu nauczania informatyki w szkołach średnich.
Pierwotnie podręcznik był tworzony w związku z wprowadzeniem zajęć informatyki do szkół średnich w Nowej Zelandii w latach 2011-2013.

W wersji dla nauczyciela w specjalnych ramkach znajdują się dodatkowe informacje oraz odpowiedzi i wskazówki do zadań. Z tego względu podręcznik ten nie powinien być udestępniany uczniom (jednakże ze względy na to, iż materiał ten jest open-source bardziej rezolutni uczniowie mogą znaleźć do na własną rękę).

{panel end}

{video url="https://wwww.youtube.com/embed/v5yeq5u2RMI?rel=0"}

## Z lotu ptaka

Dlaczego jest tak, że ludzie albo kochają komputery albo ich nienawidzą? Dlaczego niektórzy nie wyobrażają sobie życia bez różnego rodzaju urządzeń komputerowych, a  inni na samą myśl o takich urządzeniach są poirytowani i są nawet gotowi zniszczyć sprzęt komputerowy? I co to ma wspólnego z informatyką? I co to jest w ogóle informatyka?

Dobrze, że zadajesz takie pytania!

Wielu ludzi myli informatykę z programowaniem. Ktoś kiedyś powiedział „Informatyka ma tyle samo wspólnego z programowaniem, co astronomia z teleskopami” ([Mike Fellows](http://en.wikiquote.org/wiki/Computer_science)). 
Programowanie to narzędzie, którym informatycy posługują się, aby urzeczywistnić różne wspaniałe pomysły, które mogą zmienić życie ludzi na lepsze. Jednak wyłącznie znajomość składni języka programowania nie wystarczy, by tworzyć oprogramowanie szybkie, przyjazne w użyciu, niezawodne, bezpieczne, użyteczne i do tego zabawne! 

Oto przykład: Komputery potrafią wykonywać miliardy operacji w ciągu sekundy, a ciągle możemy usłyszeć narzekania, że są zbyt powolne. Człowiek jest w stanie dostrzec ułamek czasu rzędu 1/10 sekundy. Jeśli na odpowiedź programu komputerowego ktoś czeka dłużej, to może uznać program za powolny, działający mało płynnie i frustrujący. Aby zadowolić użytkownika, reakcja programu na polecenie użytkownika powinna pojawić się o wiele szybciej niż w ciągu sekundy! Jeśli stworzony przez Ciebie program przeszukuje miliony pozycji w danych lub wyświetla miliony pikseli (megapiksele), to nie możesz pozwolić sobie na to, aby działał w sposób nieefektywny. Nie możesz po prostu powiedzieć użytkownikowi, by kupił szybszy komputer ...skończy się prawdopodobnie tym, że użytkownik podziękuje Ci za współpracę i pójdzie kupić u konkurencji szybsze oprogramowanie!

Oto rada pochodząca od Freda Wilsona, który zainwestował wiele w firmy z branży komputerowej:

> Po pierwsze i najważniejsze, wierzymy, że szybkość to coś więcej niż cecha (właściwość). Szybkość jest najważniejszą cechą. Jeśli twoje oprogramowanie działa powoli, ludzie nie będą go używać. Dotyczy to zwłaszcza zwykłych użytkowników. Myślę, że użytkownicy, którzy korzystają z zaawansowanych funkcji danego oprogramowania, są czasami bardziej wyrozumiali, ale kiedy patrzę na moją żonę i moje dzieci, to oni są dla mnie jak zwykli, typowi użytkownicy. Jeśli coś działa powoli, to oni po prostu odchodzą. ...Szybkość to coś więcej niż cecha. To jest niezbędne wymaganie.

> -- [Fred Wilson](https://en.wikipedia.org/wiki/Fred_Wilson_(financier\)) ([Source](http://triple-networks.com/2011/12/06/10-golden-principles-of-successful-web-apps/))

Kluczowym wyzwaniem w informatyce jest stworzyć oprogramowanie działające szybko! Zwłaszcza jeśli ma działać na urządzeniach (np. smartfonach) starszej generacji lub ma być uruchamiane je w jakimś centrum obliczeniowym (superkomputerowym), gdzie użytkownik ma płacić za każdą minutę czasu dostępu do komputerów. 
Nie można powiedzieć klientom, by kupili szybsze urządzenia --- trzeba dostarczyć efektywne oprogramowanie.

## Szybkość to nie wszystko

W informatyce nie chodzi jedynie o szybkość.
Spróbuj wykonać jakieś proste obliczenia, posługując się dwoma kalkulatorami, udostępnionymi poniżej. Oba mają tę samą funkcjonalność (można na nich wykonać te same obliczenia), ale jeden z nich jest bardziej przyjazny w obsłudze. Dlaczego?

(W podręczniku jest wiele podobnych interaktywnych narzędzi. Aby ich używać, będziesz potrzebować aktualnych wersji przeglądarek internetowych.)

{interactive name="awful-calculator" type="in-page"}

Drugi kalkulator działa wolniej i to może być frustrujące. Ale ma bardziej ekstrawagancki interfejs – klawisze są wyświetlane w powiększeniu po wskazaniu ich myszką. Czy to ułatwia posługiwanie się kalkulatorem? Czy umieszczenie bardzo blisko siebie klawiszy "C" i "=" nie było źródłem dodatkowych problemów

Projektowanie przyjaznych w użyciu interfejsów jest istotne w informatyce. Estetyka (wygląd i grafika) interfejsu jest ważna, ale bardziej istotne jest uwzględnienie w nim zasad psychologii  zachowań użytkownika.  Oto przykład: Wyobraź sobie, że przyciski "OK" i "Anuluj" od czasu do czasu w oknach dialogowych będą zamienione miejscami. W konsekwencji użytkownik musi zachować szczególną ostrożność, zamiast działać instynktownie nauczony wcześniej w niezliczonej liczbie podobnych przypadków. 

Problem skalowalności oprogramowania to inny ważny temat. Wyobraź sobie, że jesteś twórcą witryny internetowej, którą odwiedzają tysiące użytkowników. Wszystko idzie dobrze, aż do chwili, gdy gwałtownie zwiększa się liczba użytkowników i są ich miliony. Jeśli twój serwis okaże się przeciążony, ludzie będą się irytować czekaniem na odpowiedź serwera, i kolejnego dnia możesz stracić wszystkich użytkowników – przeniosą się do serwisu,  stworzonego przez kogoś innego. Ale jeśli twoje programy są tak zaprojektowane, że nigdy nie dojdzie do przeciążenia, to  możesz się spodziewać, że  pojawią się zainteresowani kupnem twojej firmy!

Niektóre z problemów można rozwiązań przez zakup większej ilości sprzętu komputerowego (serwerów), ale to może być kosztowna i rozrzutna opcja. Do tego takie rozwiązanie ma niekorzystny wpływ na środowisko, gdyż wiąże się ze zwiększeniem zapotrzebowania na energię elektryczną (potrzebną m.in. do chłodzenia urządzeń). W przypadku urządzeń przenośnych wymagania, aby oprogramowanie działało szybko i wykorzystywało zasoby w sposób ekonomiczny (energooszczędny) mają jeszcze większe znaczenie. Nieefektywne przetwarzanie oznacza nie tylko większe zużycie baterii, ale i większe zapotrzebowanie oprogramowania na pamięć, czyli w konsekwencji zwiększenie rozmiaru i wagi urządzenia, a więc i kosztów związanych np. z chłodzeniem. 

Załóżmy optymistycznie, że Twój serwis internetowy nigdy nie jest przeciążony i znakomicie sobie radzi z obsługą milionów użytkowników. Pojawia się kolejne pytanie: czy Twoja witryna jest bezpieczna? Czy zostały zastosowane odpowiednie zabezpieczenia, aby nikt nie mógł się włamać do serwisu i wykraść dane użytkowników? W jaki sposób należy projektować systemy, aby zapewnić poufność informacji o klientach i ich transakcjach?

Informatyka zajmuje się szukaniem odpowiedzi na takie i inne pytania.
Celem tego przewodnika jest przedstawienie w sposób przystępny różnych pojęć i koncepcji informatycznych, aby poszerzyć twoją wiedzę na temat informatyki i dać ci lepsze wyobrażenie temat różnych zagadnień informatycznych.  Ten podręcznik ma pomóc ci w rozeznaniu, czy informatyka to jest dziedzina dla ciebie na tyle interesująca, by wiązać z nią swoją przyszłość zawodową.
Przewodnik jest skierowany do uczniów szkół ponadpodstawowych. 

Podzieliliśmy całość na wiele zagadnień, które razem tworzą całość curriculum z informatyki. Są to m.in. algorytmy, interakcja człowiek — komputer, kompresja danych, kryptografia, grafika komputerowa i sztuczna inteligencja. Trzeba podkreślić, że te tematy są ze sobą powiązane i należy o tym pamiętać w czasie zaznajamiani się z nimi. 

Przewodnik ma taki poziom szczegółowości, że pozwoli ci uzyskać niezłe pojęcie o tym, czym jest informatyka. Przewodnik ma  dobrze przygotowywać do późniejszych pogłębionych studiów na lekcjach w szkole średniej, czy szkole wyższej. W tekście znajduje się wiele odnośników do stron internetowych i podane są informacje o książkach, w których możesz znaleźć bardziej szczegółowe informacje.

## Programowanie

Co z programowaniem? Nie wymagamy umiejętności programowania od korzystających z przewodnika? W niektórych miejscach będziemy zachęcać jednak potrafiących programować do wykonania pewnych zadań programistycznych. Nie można zapominać, że wszystkie koncepcje przedstawione w przewodniku mają zastosowanie praktyczne i zostały kiedyś zastosowane w takim, czy innym oprogramowaniu. Dlatego zachęcamy, aby równolegle z poszerzaniem wiedzy na temat różnych zagadnień informatycznych, uczyć się programowania. W Internecie jest wiele kursów programowania, również darmowych. Jest też wiele książek na ten temat. Warto zacząć od strony [code.org](http://www.code.org/) lub działu informatycznego projektu [Khan Academy](http://www.khanacademy.org/cs/)

Umiejętność programowania to tylko jedna z umiejętności wymaganych od informatyka. Ten przewodnik da Ci wyobrażenie na temat innych kompetencji ważnych w informatyce, np. matematycznych czy tych z zakresu psychologii i komunikacji interpersonalnej.

## Zasady korzystania

Rozdziały przewodnika zostały tak zaprojektowane, że można je było czytać w dowolnej kolejności. We wstępie do niektórych rozdziałów zaznaczono, że wskazane jest zapoznanie się najpierw z innym rozdziałem. Warto rozpocząć naukę od rozdziału na temat binarnego zapisu informacji, gdyż system dwójkowy (binarny) ma zasadnicze znaczenie w wielu obszarach informatyki.

Każdy z rozdziałów rozpoczyna się sekcją „Z lotu ptaka”. W nich przedstawione są informacje, które mają ukazać znaczenie danego zagadnienia i jego praktyczne zastosowania oraz zmotywować do dalszej lektury. Kluczowe pojęcia i koncepcje są wyjaśnione na przykładach, często uproszczonych wersjach rzeczywistych problemów, którymi zajmują się informatycy. Jeśli to tylko możliwe, tekstowi towarzyszą interaktywne narzędzia, które powalają na eksperymentowanie, by sprawdzić zrozumienie tekstu. Zachęcamy do tego, by robić z nich dobry użytek!

Na końcu każdego rozdziału znajduje się sekcja „Podsumowanie”, która zawiera wzmianki na temat wątków pominiętych w tekście głównym. Czasami są to zagadnienia, których zrozumienie będzie wymagać znajomości matematyki na trochę wyższym poziomie czy umiejętności programowania. 

W tekście przewodnika zaproponowano pomysły projektów, których wykonanie może być np. podstawą do otrzymania ocen szkolnych.

## O przewodniku

Przewodnik jest udostępniany za darmo. Dostęp do wersji źródłowej materiałów jest możliwy poprzez GitHub.

Zasady licencji Creative Commons Attribution-NonCommercial-ShareAlike licence pozwalają na wprowadzanie zmian i udoskonaleń. W takim przypadku prosimy o zachowanie informacji o lokalizacji oryginalnej wersji przewodnika. Zmodyfikowana wersja musi pozostać dostępna za darmo.

Powstanie przewodnika było możliwe dzięki wsparciu Google Inc. oraz University of Canterbury.

## Dalsze lektury
Każdy rozdział kończy się propozycjami lektur, które pozwolą na pogłębienie wiedzy. Jest wiele książek o szerokiej tematyce informatycznej, które zostały napisane z myślą o ukazaniu w miarę pełnego obrazu tej dziedziny. Autorzy przewodnika polecają szczególnie:

- Algorithmics, by David Harel (tłumaczenie polskie: Algorytmika. Rzecz o istocie informatyki).
- [Computational fairy tales](http://computationaltales.blogspot.co.nz), autor: Jeremy Kubica
- Algorithmic adventures: from knowledge to magic, autor: Jurag Hromkovic
- The Turing Omnibus, autor: A.K. Dewdney

Godne uwagi są też artykuły Wikipedii oraz wiele innych stron internetowych. Wśród tych w języku angielsku polecamy szczególnie:

- [Computer Science For Fun](http://www.cs4fn.org) 
- [Babbage's bag](http://www.i-programmer.info/babbages-bag/) 
- [CS Bytes](http://www.nsf.gov/cise/csbytes/) 
- [Thriving in our digital world](http://www.cs.utexas.edu/~engage/) 
- [CS animated](http://www.csanimated.com/) 
- [CS for All](http://www.cs.hmc.edu/csforall/)

