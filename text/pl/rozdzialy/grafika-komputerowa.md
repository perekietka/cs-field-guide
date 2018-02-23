# Grafika komputerowa

{video url="https://www.youtube.com/embed/5kuoRjgfCls"}

## Z lotu ptaka

Grafika komputerowa kojarzy się z grami, filmami i obrazami oraz niezwykłym oprogramowaniem do tworzenia i przetwarzania obrazów. Warto jednak zapytać: Jak to się dzieje, że to oprogramowanie tak świetnie działa? Jaką rolę mają informatycy? Oni nie są wyłącznie *użytkownikami* systemów graficznych, ale zajmują się *tworzeniem*, zwłaszcza obmyślaniem nowych technik.

Rozwój narzędzi do tworzenia grafiki komputerowej jest pochodną przemysłu rozrywkowego. Granice możliwości takiego oprogramowania nieustannie się poszerzają. Na początku były proste filmy animowane, zwane dziś 2D, a dziś na ekranach kin możemy oglądać postaci i obiekty w wersji 3D wygenerowane komputerowo, które momentami trudno odróżnych od tych istniejących w świecie rzeczywistym.
Wśród napisów końcowych filmów, w których używano komputerowo wygenerowanych animacji, można by odnaleźć liczne nazwiska informatyków. [Kilku z nich otrzymało nawet Nagrody Akademii Filmowej (Oscary)] (http://www.oscars.org/news/11-scientific-and-technical-achievements-be-honored-academy-awardsr)! 



Firmy z braży filmowej czy producenci gier komputerowych nie ograniczają się do korzystania z istniejącego oprogrogramowania graficznego. Czasami niezbędni są informatycy, którzy tworzą nowe, lepsze algorytmy i oprogramowanie, dzięki którym uzyskuje się nowatorskie efekty. Możliwości rozwoju w tej dziedzinie wydają się nieskończone!

Grafika komputerowa znajduje zastosowanie w wielu różnych sytuacjach. Tworzenie gier i filmów animowanych to ważne przykłady, ale jest ich znacznie więcej: wizualizacja informacji zawartych w wielkich zbiorach danych (np. dotyczących połączeń telefonicznych w konkretnym dniu albo relacji znajomości użytkowników sieci społecznościowej), graficzna strona interfejsów komunikacji człowieka z komputerem, modelowanie tzw. rzeczywistości wirtualnej czy rozszerzonej oraz wiele innych. 



{panel type="jargon-buster" summary="Piksele"}
{glossary-definition term="Piksel" definition="To słowo to spolszczona wersja słowa pixel, który powstał jako skrót od *picture element* (dosł. element obrazu), na oznaczenie małych kwadratów tworzacych jakby siatkę (ang. grid) komputerowej realizacji obrazu."}
Obraz cyfrowy wyświetlany na ekranie monitora lub wydrukowany na domowej drukarce jest skończonym zbiorem elementów, które łącznie tworzą jakby siatkę kwadratów bardzo małych rozmiarów, zwanych 
{glossary-link term="piksel" reference-text="definition"}pikselami{glossary-link end}.
Zazwyczaj nie da się ich dostrzec gołym okiem (inaczej obraz wyglądałby topornie).
Na zdjęciach liczba pikseli jest liczona w milionach (megapiksel to milion pikseli; np. ekran o 1080 pikselach w poziomie i 720 w pionie składa się z 777 600 pikseli, czyli ok. 0,78 megepikseli).

Pojęcie piksela jest podstawowe w grafice komputerowej, praca programistów w dziedzinie grafiki komputerowej to w dużej części praca nad abstrakcyjnymi modelami obiektów graficznych złożonych z pikseli i algorytmami działajacymi na nich.
Efektem działania aparatu cyfrowego jest zapisanie informacji o zarejestorwanych na elementach światłoczułych kolorach jako zbioru pikseli, które później będą wyświetlone na takim lub innym ekranie.
{panel end}

W tym rozdziale przyjrzymy się wybranym podstawowym technikom, które są używane w grafice komputerowej. Dzięki temu zorientujesz się z grubsza, z jakimi wyzwaniami mierzą się programiści grafiki.

W tym rozdziale będziemy używać systemu o nazwie WebGL, który pozwala na uzyskanie grafiki 3D w przeglądarce internetowej. Gdyby pojawił się problem z wydajnością lub inny, to pomocne mogą się okazać informacje zamieszczone [tutaj](further-information/interactives.html).

## Przekształcenia graficzne

Generowanie obrazów w grafice komputerowej wymaga wykonania wielu obliczeń matematycznych. Kolor każdego z pikseli tworzących obraz oglądany na monitorze jest ustalony w wyniku obliczeń, zwykle składających się z wielu etapów pośrednich.

Zaczniemy od kilku prostych, ale powszechnie stosowanych w programowaniu grafiki, przykładów obliczeń.
Zamieszczone poniżej interaktywne narzędzie pokazuje sześcian, który na trzech ze ścian ma coś napisane.
Możesz poruszać sześcianem, używając *przekształcenia*, które po prostu ustala na nowo położenie sześcianu w przestrzeni.
Wpisując współrzędne 3D, możesz oglądać ściany w poszukiwaniu symboli.

{comment}{include interactive computer-graphics-box-translation}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-box/CG-box-translation.html?info=In%20this%20example%20the%20only%20transforms%20we%27ve%20supplied%20are%20to%20%3Cem%3Etranslate%3C/em%3E%20it%20in%20three%20dimensions.%20The%20dimensions%20are%20%3Cem%3Ex%3C/em%3E%20(left%20and%20right),%20%3Cem%3Ey%3C/em%3E%20(up%20and%20down)%20and%20%3Cem%3Ez%3C/em%3E%20(in%20and%20out%20of%20the%20screen).%20Your%20goal%20is%20to%20type%20in%20how%20far%20it%20should%20be%20transformed%20in%20each%20of%20these%20directions%20so%20that%20you%20can%20see%20the%20symbol%20on%20each%20face,%20and%20put%20those%20symbols%20on%20the%20spinner%20wheels%20shown.%20(The%20order%20of%20the%20symbols%20doesn%27t%20matter)." text="Kliknij, aby uruchomić interaktywne narzędzie."}

W tej zabawie stosowano przekształcenie zwane *przesunięciem (translacją)*, co oznacza przemieszczenie obiektu w trzech wymiarach: w górę i w dół, do tyłu i do przodu oraz na boki.

Następne ćwiczenie wymaga obracania pudełkiem. Ponownie twoim zadaniem jest odnaleźć symbole na ściankach.

{comment}{include interactive computer-graphics-box-rotation}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-box/CG-box-rotation.html?info=Another%20common%20transform%20is%20%3Cem%3Erotation%3C/em%3E,%20which%20you%20can%20use%20in%20the%20following%20image%20to%20find%20the%20symbols%20(the%20rotation%20is%20measured%20in%20degrees)." text="Kliknij, aby uruchomić interaktywne narzędzie"}

Różnych typów przekształceń jest wiele, ale najczęściej stosowane to przesunięcie (translacja), obrót i skalowanie (zmiana rozmiaru).
Przekształcenia w grafice komputerowej dotyczą nie tylko obiektów tworzących obraz, ale również położenia tzw. kamery jak i źródeł oświetlenia.

W tym podrozdziale będziesz przekształcać obrazy. Zaczniemy od wprowadzenia zmian ręcznie, po jednym punkcie, ale potem przejdziemy do szybszej metody, która korzysta z matematycznego pojęcia *macierzy*. Na początek przyjrzymy się działaniu przekształcenia w dwóch wymiarach, by łatwiej było temat zrozumieć.

W interaktywnym narzędziu (poniżej) widzisz siedmiokąt tworzący jakby strzałkę, umieszczony w centralnej części układu współrzędnych, zwanego *kartezjańskim*. Po prawej stronie znajduje się m.in. lista par liczb (*x*,*y*), współrzędnych wierzchołków siedmiokąta (strzałki). Wartość *x* określa położenie punktu w poziomie (względem początku układu współrzędnych), a wartość *y* określa położenie punktu w pionie. Na przykład: pierwszy punkt na liście jest opisany parą liczb (0,2) i jest to punkt położony dwie jednostki powyżej punktu (0,0). Jakiemu punktowi odpowiada para liczb (2,0)? Co się dzieje, gdy wartość współrzędnej *x* jest liczbą ujemną?

{panel type="teacher-note" summary="Odpowiedzi"}
(2,0) to wierzochłek strzałki najbardziej wysunięty na prawo. Ujemna wartość *x* oznacza, że punkt położony jest po lewej stronie punktu (0,0). Podobnie ujemna wartość *y* oznacza, że punkt położony jest poniżej punktu (0,0).  
{panel end}

Oprócz listy współrzędnych wierzchołków, widzisz jeszcze druga listę, jakby kopię tej pierwszej. Możesz ją edytować, tzn. wpisywać inne od początkowych wartości. W układzie współrzędnych zobaczysz efekt przekształcenia. Innymi kolorami zaznaczono postać początkową i tę po  zmianach.

{comment}{include interactive computer-graphics-arrow parameters="&quiz=2 0 0 5 0 2 0 4 0 0 2 0 0 0 0 1 &hidetarget=true"}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-points.html?info=Your%20first%20challenge%20is%20to%20add%202%20to%20all%20the%20%3Cem%3Ex%3C/em%3E%20points,%20and%203%20to%20all%20the%20%3Cem%3Ey%3C/em%3E%20points%20(you%20can%20either%20type%20the%20new%20number%20or%20put%20the%20calculation%20in%20the%20box%20e.g.%20%220.5+2%22.%0AWhat%20effect%20does%20this%20have%20on%20the%20original%20arrow?%20(Be%20careful%20to%20add%20the%20negative%20numbers%20correctly;%20for%20example,%20adding%202%20to%20-0.5%20gives%201.5.)%20What%20happens%20if%20you%20subtract%203%20from%20each%20of%20the%20original%20coordinate%20values?%0A&quiz=2%200%200%205%200%202%200%204%200%200%202%200%200%200%200%201%20&hidetarget=true" text="Kliknij, aby uruchomić interaktywne narzędzie."}


{panel type="teacher-note" summary="Rozwiązanie"}
Pierwsze przekształcenie w ćwiczeniu przesuwa strzałkę o dwie jednostki w prawo i trzy jednostki w górę. 
Drugie -- o trzy jednostki w dół i w lewo.
{panel end}

Przekształcenie zwane *przesunięciem* służy do zmiany położenia punktu (zbioru punktów) w układzie współrzędnych. Ten typ przekształceń jest używany w grafice komputerowej do określenia położenia obiektu, ale również do innych celów, np. animowania przesunięcia obiektu wzdłuż jakiejś ścieżki, czy określenia położenia kamery (punktu obserwacyjnego). 

W następnym ćwiczeniu będziesz zmieniać rozmiar obrazu.

{comment}{include interactive computer-graphics-arrow parameters="&quiz=0.5 0 0 0 0 0.5 0 0 0 0 1 0 0 0 0 1 &hidetarget=true"}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-points.html?info=In%20this%20next%20interactive,%20try%20replacing%20the%20coordinates%20in%20the%20second%20list%20with%20all%20the%20original%20values%20multiplied%20by%202.%20What%20is%20the%20effect%20of%20this%20transform?%20What%20would%20happen%20if%20you%20multiply%20each%20value%20by%2010?%20How%20about%200.5?%20What%20if%20you%20only%20multiply%20the%20%3Cem%3Ex%3C/em%3E%20values?&quiz=0.5%200%200%200%200%200.5%200%200%200%200%201%200%200%200%200%201%20&hidetarget=true" text="Kliknij, aby uruchomić interaktywne narzędzie."}


{panel type="teacher-note" summary="Rozwiązanie"}
Pomnożenie przez 2 skutkuje dwukrotnym powiększeniem strzałki w każdym z wymiarów. Pomnożenie przez 10 większa rozmiar 10 razy i obiekt nie zmieści się w polu widzenia. Pomnożenie przez 0,5 zmniejszy strzałkę dwukrotnie. Pomnożenie tylko watości *x* skutkuje wyłącznie zmianą strzałki w poziomie.
{panel end}

To przykształcenie nosi nazwę *skalowania* i służy do ustalania rozmiaru obiektu. Wykorzystane w odpowiedni sposób pozwala na tworzenie efektów takich jak przybliżanie obiektu lub jego oddalanie (od punktu obserwacyjnego).

Poniżej znajduje się interaktywne narzędzie, które pozwala na nakładanie strzałek jedna na drugą. Należy zastosować zarówno operację skalowania, jak i przesunięcia.

{comment}{include interactive computer-graphics-arrow parameters="&quiz=2 0 0 5 0 2 0 4 0 0 2 0 0 0 0 1"}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-points.html?info=%20Try%20to%20get%20the%20blue%20arrow%20to%20match%20up%20with%20the%20red%20one.%20It%20will%20require%20a%20mixture%20of%20scaling%20and%20translation.&quiz=2%200%200%205%200%202%200%204%200%200%202%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

Co się stanie, gdy zamienimy miejscami wartości *x* i *y* wspólrzędnych punktu?

{comment}{include interactive computer-graphics-arrow parameters="&quiz=0 1 0 0 1 0 0 0 0 0 1 0 0 0 0 1 &hidetarget=true &zoom=-5.0"}{comment end}
{button link="http://csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-points.html?info=Next,%20see%20what%20happens%20if%20you%20swap%20the%20%3Cem%3Ex%3C/em%3E%20and%20%3Cem%3Ey%3C/em%3E%20value%20for%20each%20coordinate.&quiz=0%201%200%200%201%200%200%200%200%200%201%200%200%200%200%201%20&hidetarget=true%20&zoom=-5.0" text="Kliknij, aby uruchomić interaktywne narzędzie."}

Efekt wygląda jak obrót wokół punktu (0,0) o 90 stopni w prawo (zgodnie z ruchem wskazówek zegara). \[Gdyby nasza figura nie była taka „regularna”, na przykład przypominała literę L, zauważyłbyś, że efekt obrotem nie jest (przyp. tłum.).\] 
Takie przekształcenie może służyć również do symulacji zmiany ustawienia kamery (obserwatora).

Oczywiście ręczna zmiana wartości współrzędnych punktów, jednego po drugim, jest nieefektywna. Na szczęście jest na to sposób. 
O tym przeczytasz poniżej!


{comment}We won't mention reflection and shearing etc., but this can go in the "whole story" section.{comment end}

### Przekształcenia macierzowe

{panel type="teacher-note" summary="Wymagania co do wiedzy uczących się"}

Ten podrozdział jest wprowadzeniem do zastosowania macierzy w grafice komputerowej. Nie jest konieczne, aby uczący się znali pojęcie macierzy wcześniej. Gdyby wyjaśnienia zawarte w tekście były niewystarczające do zrozumienia tematu przez uczniów, to można im wskazać inne zasoby edukacyjne, np. nagrania wideo i zadania pochodzące z 
[Khan academy](https://www.khanacademy.org/math/precalculus/precalc-matrices).

Oto inne odnośniki do materiałów edukacyjnych (w języku angielskim):
- [Math is Fun - Mnożenie macierzy](http://www.mathsisfun.com/algebra/matrix-multiplying.html)
- [Math in Sight - Mnożenie macierzy](http://mathinsight.org/matrix_vector_multiplication)
- [Math Planet - Przekształcenia z użyciem macierzy](http://www.mathplanet.com/education/geometry/transformations/transformation-using-matrices)
- [Wikipedia o przekształceniach macierzowych](https://en.wikipedia.org/wiki/Transformation_matrix) - w tym artykule poziom szczegółowości jest już znaczący
{panel end}  


Istnieje o wiele prostszy sposób określenia paramatrów przekształcenia niż zmiana wartości współrzędnych punktów jednego po drugim. 
W grafice komputerowej używa się zwykle operacji na *macierzach*, które w istocie są skrótowym zapisem wykonania wielu prostych operacji arytmetycznych naraz. Macierz przekształceń dwuwymiarowych, które wykonaliśmy powyżej, składa się z czterech liczb. W konkretnym przypadku, gdy każdą ze współrzędnych mnożymy przez 2, macierz ma postać:

{math-block}
\begin{bmatrix}
2 & 0 \\  
0 & 2 \\  
\end{bmatrix}
{math-block end}

Aby lepiej to zrozumieć, otwórz interaktywne narzędzie, które jest poniżej:

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-matrix.html?info=You%20can%20type%20the%20scaling%20matrix%20into%20this%20interactive%20to%20see%20what%20it%20does%20(replace%20the%20ones%20with%20twos).%20The%20top%20left-hand%20value%20just%20means%20multiply%20all%20the%20%3Cem%3Ex%3C/em%3E%20values%20by%202,%20and%20the%20bottom%20right%20one%20means%20multiply%20all%20the%20%3Cem%3Ey%3C/em%3E%20values%20by%202.%20For%20the%20meantime,%20leave%20the%20translate%20values%20as%200.&quiz=2%200%200%200%200%202%200%200%200%200%202%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

(Na tym etapie czytania przewodnika warto pracować z dwoma oknami przeglądarki: w jednym czytasz tekst, a w drugim pracujesz z narzędziem.)

Zmień liczby w macierzy na takie:

{math-block}
\begin{bmatrix}
3 & 0 \\  
0 & 3 \\  
\end{bmatrix}
{math-block end}

lub

{math-block}
\begin{bmatrix}
0{,}2 & 0 \\  
0 & 0{,}2 \\  
\end{bmatrix}
{math-block end}

{panel type="teacher-note" summary="Wyjaśnienie"}

Efekty powinny być odpowiednio takie: strzałka powiększona trzy razy (w każdym z wymiarów) i strzałka pomniejszona do 1/5 wielkości (w każdym wymiarze).
{panel end}

Wartości wpisane do pola opisanego jako "add translate" są dodawane do współrzędnych *x* i *y*; sprawdź, jak to działa. Następnie postaraj się znaleźć takie wartości w tym polu (i w polu macierzy), aby w efekcie nałożyć strzałkę na strzałkę czerwoną.

{panel type="teacher-note" summary="Wyjaśnienie"}

Macierz powinna mieć postać {math}\begin{bmatrix}  2 & 0 \\   0 & 2 \\   \end{bmatrix}{math end}, a współrzędne x i y odpowiednio 5 i 4 (rozmiar strzałki dwa razy powiększony i przesunięcie 5 w prawo i 4 w górę).
{panel end}

Co stanie się, gdy użyjesz takiej macierzy, jak poniżej?

{math-block}
\begin{bmatrix}
2 & 0 \\  
0 & 4 \\  
\end{bmatrix}
{math-block end}

{panel type="teacher-note" summary="Wyjaśnienie"}

Wartość *x* jest dwa razy większa, ale wartość *y* jest powiększona cztery razy, więc w efekcie strzałka jest powiększona w pionie dwa razy bardziej niż w poziomie.
{panel end}

Teraz sprawdź efekt dla macierzy:

{math-block}
\begin{bmatrix}
0 & 1 \\  
1 & 0 \\  
\end{bmatrix}
{math-block end}

Efektem powinien być obrót strzałki w prawo.

Górny wiersz macierzy ma wpływ na zmianę współrzędnych *x* w taki sposób, że określa udział początkowych wartości *x* i *y* w wartości *x* po przekształceniu. W przykładzie:

{math-block}
\begin{bmatrix}
2 & 0 \\  
0 & 4 \\  
\end{bmatrix}
{math-block end}

Górny wiersz macierzy zawiera następującą informację: w skład wartości *x* wchodzi podwojona wartość początkowej wartości *x*, i nic więcej, bo wpływ *y* jest opisany w macierzy liczbą 0. Krótko mówiąc: wartość *x* zostaje podwojona. Drugi wiersz macierzy ma wpływ na wartość *y*: na nową wartość *y* nie ma wpływu wartość początkowa *x* (bo w macierzy jest 0), a tylko początkowa wartość *y*, którą należy pomnożyć przez 4.

W tym momencie jasny powinien być sens macierzy {math}\begin{bmatrix}  0 & 1 \\   1 & 0 \\   \end{bmatrix}{math end}. Nowa wartość *x* jest równa początkowej wartości *y* i vice versa. Przekształcenie opsiane przez macierz, w którym nastąpiła zamiana wartości przypisywanych współrzednym *x* i *y* jest tym samym, co obrót w prawo wokół punktu (0,0).  
\[Taki obrót to właściwie odbicie obiektu w symetrii względem prostej y = x. (Przypis tłumacza.)\]

Interesująca jest sytuacja, w której przekształcenie opisane jest np. taką macierzą:

{math-block}
\begin{bmatrix}
0{,}7 & 0{,}7 \\  
-0{,}7 & 0{,}7 \\  
\end{bmatrix}
{math-block end}

Efektem będzie pewien obrót. Teraz wartość *x* jest efektem jakby zmieszania 0,7 początkowych wartości *x* i *y*. 

W ogólnym przypadku do zapisu macierzy obrotu obiektu o kąt {math-block}\theta{math-block end} w lewo (przecwinie do ruchu wskazówek zegara), należy użyć funkcji trygonometrycznych sinus (skrót: sin) i cosinus (skrót: cos):

{math-block}
\begin{bmatrix}
\cos(\theta) & -\sin(\theta) \\  
\sin(\theta) & \cos(\theta) \\  
\end{bmatrix}
{math-block end}

{panel type="teacher-note" summary="Wyjaśnienie"}

Jeśli uczniowieę nie mają wiedzy o funkcjach trygnometrycznych, można poprzestać na przedstawieniu koncepcji: kąt mierzymy w stopniach, a wartości funkcji sinus i cosinus przyjmują wartości między -1 i 1.

{panel end}

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-matrix.html?info=You%20can%20type%20calculations%20directly%20into%20the%20interactive%20-%20if%20you%20type%20cos(60)%20it%20will%20work%20out%20the%20cosine%20of%2060%20degrees%20for%20you,%20which%20happens%20to%20be%20exactly%200.5.%20Or%20you%20can%20just%20type%20in%20the%20sin%20and%20cosine%20values;%20the%200.7%20numbers%20in%20the%20rotation%20matrix%20are%20just%20the%20values%20for%20sin(45)%20and%20so%20on%20(or%20at%20least,%20they%20approximately%20the%20value;%20it%27s%20actually%200.70710678...,%20which%20happens%20to%20be%20the%20square%20root%20of%200.5,%20but%200.7%20is%20close%20enough%20for%20our%20example).&quiz=0.7%200.7%200%205%20-0.7%200.7%200%204%200%200%201%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

Jaką postać ma macierz obrotu o 360 stopni?

{panel type="teacher-note" summary="Wyjaśnienie"}
Dla kąta 360 stopni otrzymamy macierz {math}\begin{bmatrix}  1 & 0 \\   0 & 1 \\   \end{bmatrix}{math end},
ponieważ
{math}\cos(360)=1{math end} i
{math}\sin(360)=0{math end}.
Taką macierz nazywa się tożsamościową (identycznościową), gdyż przekształcenie nią opisane nie zmienia niczego w położeniu obiektu. Taka macierz opisuje każdy z obrotów o kąt wielokrotności 360 stopni (również 0 stopni).
{panel end}

Macierz dla *skalowania* w ogólnej postaci jest trochę prostsza niż dla obrotu; jeśli chcesz, aby współczynnik zmiany rozmiaru obiektu był opisany liczbą *s*, to macierz ma postać: 

{math-block}
\begin{bmatrix}
s & 0 \\  
0 & s \\  
\end{bmatrix}
{math-block end}

Przekształcenia, jakim jest przesunięcie (translacja) nie można opisać macierzą tego typu. Dlatego narzędzie interaktywne zawiera dodatkowe pole do określenia wartości *x* i *y* przesunięcia obiektu.
Sprawdź działanie innego narzędzia:

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-matrix.html?info=Try%20translating%20the%20original%20arrow%20so%20that%20it%20matches%20up%20with%20the%20red%20arrow.&quiz=1%200%200%205%200%201%200%204%200%200%201%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}
Przesunięcie *x* o 5, a y o 4 (5 w prawo i 4 w górę). Macierz skalowania ma postać: {math}\begin{bmatrix}  1 & 0 \\   0 & 1 \\   \end{bmatrix}{math end}
{panel end}

Kolejne narzędzie pozwala na składanie dwóch przekształceń: przesunięcia i skalowania.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-matrix.html?info=Now%20try%20to%20scale%20the%20original%20arrow%20in%20the%20following,%20and%20translate%20it%20to%20match%20the%20red%20arrow.&quiz=2%200%200%204%200%202%200%203%200%200%202%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}
Macierz ma postać: {math}\begin{bmatrix}  2 & 0 \\   0 & 2 \\   \end{bmatrix}{math end} (podwojenie rozmiaru). Przesunięcie dla *x* to 4, a dla *y* to 3..
{panel end}

Kolejnośc składania przekształceń (przesunięcia i skalowania) ma znaczenie. 
Sprawdź!

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-matrix-reversed.html?info=The%20following%20interactive%20has%20the%20translation%20and%20scaling%20the%20other%20way%20around.%20Use%20this%20one%20to%20transform%20the%20blue%20arrow%20to%20the%20red%20arrow.%20The%20order%20in%20which%20the%20operations%20happen%20makes%20a%20difference!%20&quiz=2%200%200%205%200%202%200%204%200%200%202%200%200%200%200%201" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}
Macierz ma postać: {math}\begin{bmatrix}  2 & 0 \\   0 & 2 \\   \end{bmatrix}{math end} (znów podwojenie rozmiaru). Tym razem wartości opisujące przesunięcie są dwa razy mniejsze niż potrzebujemy, ponieważ po przesunięciu będzie jeszcze skalowanie. Dlatego dla *x* należy wpisać 2,5 a dla *y* -- 2.
{panel end}

Moża było zauważyć, że wartości opisujące przekształcenia zależą od odległości obiektu od punktu o współrzędnych (0,0), zwanym początkiem układu współrzędnych. 
Jeżeli chcesz, by obiekt się powiększył, ale jego środek pozostał w miejscu, najwygodniej zacząć od przesunięcia obiektu tak, by jego środek znalazł się w punkcie (0,0), potem przeskalować obiekt, a na końcu przesunąć z powrotem.  

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-transmatrix.html?info=The%20tip%20is%20at%20(-8,7),%20so%20you%20should%20translate%20it%20to%20(0,0),%20scale%20by%202,%20and%20translate%20back%20to%20(-8,%207).&zoom=-15.0%20&quiz=2%200%200%20-8%200%202%200%203%200%200%202%200%200%200%200%201%20&start=1%200%200%20-8%200%201%200%205%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}
Wartości dla przesunięcia to: 8 dla *x* i -7 dla *y*. W efekcie wierzchołek strzałki leży w punkcie 0 i podwojenie rozmiaru nie zmieni położenia tego wierzchołka. Macierz ma postać: {math}\begin{bmatrix}  2 & 0 \\   0 & 2 \\   \end{bmatrix}{math end}. Wartości dla przesunięcia strzałki z powrotem to: -8, 7.
{panel end}

Podobny problem pojawia się w przypadku obrotu.
Poniżej znajduje się interaktyne narzędzie, które pozwala poprzedzić skalowanie przesunięciem obiektu.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-transmatrix.html?info=Try%20rotating%20this%20image%20by%2045%20degrees.You%27ll%20need%20to%20translate%20the%20tip%20to%20the%20origin,%20apply%20the%20rotation,%20and%20translate%20it%20back.&zoom=-10.0%20&quiz=0.699999988079071%200.699999988079071%200%20-4.400000095367432%20-0.699999988079071%200.699999988079071%200%204.599999904632568%200%200%201%200%200%200%200%201%20&start=1%200%200%20-3%200%201%200%204%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie."}

Kolejne dwa przykłady pozwalają na składanie trzech przekształceń: obrotu, skalowania i przesunięcia. Możesz używać wielu macierzy, aby osiągnać cel: wynik działania jednej macierzy staje się danymi wejściowymi dla następnej. Przy okazji: szerokość strzałki jest podwojona, ale wysokość się zmieniła. 

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-doublematrix.html?info=Try%20matching%20the%20blue%20arrow%20to%20the%20red%20one%20using%20two%20matrices%20(one%20to%20scale%20and%20one%20to%20rotate),%20and%20adding%20a%20vector.&zoom=-10.0%20&quiz=0%201%200%204%202%200%200%20-2%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}

Istnieją dwa rozwiązania, w zależności od wyboru pierwszego przekształcenia: skalowania lub obrotu. W pierwszym przypadku macierz skalowania ma postać: {math}\begin{bmatrix}  2 & 0 \\   0 & 1 \\   \end{bmatrix}{math end}. Macierz obrotu to: {math}\begin{bmatrix}  0 & 1 \\   -1 & 0 \\   \end{bmatrix}{math end}. Wektor przesunięcia ma współrzedne 4, -2.

W drugim przypadku macierz obrotu ma postać: {math}\begin{bmatrix}  0 & 1 \\   -1 & 0 \\   \end{bmatrix}{math end} (90 stopni zgodnie z ruchem wskazówek zegara), ale macierz skalowanie jest inna: {math}\begin{bmatrix}  1 & 0 \\   0 & 2 \\   \end{bmatrix}{math end}, gdyż skalowanie musi tym razem być w kierunku *y*. Wektor przesunięcia ma współrzedne 4, -2.

Istnieje też rozwiązanie z jedną macierzą (opisującą obrót i skalowanie); to może być ciekawe wyzwanie dla zainteresowanych. Macierz będzie mieć postać: {math}\begin{bmatrix}  0 & 1 \\   2 & 0 \\   \end{bmatrix}{math end}. Wektor przesunięcia ma współrzedne 4, -2.

{panel end}

Oto jeszcze jedno ćwiczenie, grupujące wszystkie przekształcenia:

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-doublematrix.html?info=You%20will%20need%20to%20use%20all%20three%20operations%20to%20do%20this%20next%20one.&zoom=-6.0%20&quiz=0.3499999940395355%20-0.3499999940395355%200%20-1%200.3499999940395355%200.3499999940395355%200%20-2%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Rozwiązanie"}

Rozwiązań może być wiele. Najprostsze to: {math}\begin{bmatrix}  0{,}7 & -0{,}7 \\   0{,}7 & 0{,}7 \\   \end{bmatrix}{math end} jako (przybliżona) macierz obrotu, {math}\begin{bmatrix}  0{,}5 & 0 \\   0 & 0{,}5 \\   \end{bmatrix}{math end} jako macierz skalowania i -1, -2 jako wartości przesunięcia. 
{panel end}

Może się wydawać, że stosowanie wielu przekształceń jest żmudne, bo każdy punkt należący do obiektu należy poddać przekształceniom. Strzałka z przykładu to był wielokąt o 7 wierchołkach, a złożone obrazy składają się z tysięcy, czy nawet milionów punktów. Na szczęście operacje macierzowe można na początku złożyć w jedną operację i wykonać tylko tę jedną na każdym punkcie obiektu.

### Składanie przekształceń

Jeśli obraz ma zostać poddany kilku przekształceniom jedno po drugim, to wówczas ten zbiór przekształceń należy opisać jedną macierzą, gdyż prowadzi to zmniejszenia liczby obliczeń. Taką macierz wypadkową uzyskuje się przez „wymnożenie” macierzy opisujących każde ze składowych przekształceń. 

Wynikiem mnożenia dwóch macierzy nie jest macierz złożona z iloczynów wartości odpowiadająch sobie nawzajem elementów macierzy; poniżej przedstawiono przykład ilustrujący zasadę mnożenia dwóch macierzy:

{math-block}

\begin{bmatrix}
a_{11} & a_{21} \\  
a_{12} & a_{22} \\  
\end{bmatrix}
\times
\begin{bmatrix}
b_{11} & b_{21} \\  
b_{12} & b_{22} \\  
\end{bmatrix}
=
\begin{bmatrix}
a_{11}b_{11}+a_{21}b_{12} &  a_{11}b_{21}+a_{21}b_{22} \\  
a_{12}b_{11}+a_{22}b_{12} &  a_{12}b_{21}+a_{22}b_{22} \\  
\end{bmatrix}

{math-block end}

To może wydawać się trochę skomplikowane, ale trud zrozumienia opłaca się w praktyce: otrzymujemy jedną macierz, która opisuje złożenie dwóch przekształceń.

Rozważmy prosty przykład. Chcemy złożyć dwa przekształcenia: skalowanie (zmiana rozmiaru) przez 2 i obrót o (prawie) 45 stopni. Jak będzie wyglądać macierz opisująca złożenie tych przekształceń?

{math-block}

\begin{bmatrix}
2 & 0 \\  
0 & 2 \\  
\end{bmatrix}
\times
\begin{bmatrix}
0{,}7 & 0{,}7 \\  
-0{,}7 & 0{,}7 \\  
\end{bmatrix}
=
\begin{bmatrix}
2 \times 0.7+ 0 \times -0.7 &  2 \times 0.7+ 0 \times 0.7 \\  
0 \times 0.7+ 2 \times -0.7 &  0 \times 0.7+ 2 \times 0.7 \\  
\end{bmatrix}
=
\begin{bmatrix}
1{,}4 &  1{,}4  \\  
-1{,}4 &  1{,}4  \\  
\end{bmatrix}

{math-block end}

Możesz sprawdzić działanie takiej macierzy, korzystając z interaktynego narzędzia poniżej:


{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-singlematrix.html?info=Try%20putting%20in%20the%20final%20matrix%20here%20and%20see%20if%20it%20does%20scale%20by%202%20and%20rotate%20by%2045%20degrees.&zoom=-10.0%20&quiz=1.4%201.4%200%200%20-1.4%201.4%200%200%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie"}

Warto sprawdzić inne przykłady, aby lepiej zrozumieć temat. Możesz posłużyć się narzędziem udostępnionym poniżej.
Zwróć uwagę na to, że narzędzie pozwala na zmianę kolejności czynników (macierzy). Wystarczy przciągnąć pola np. myszką.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-arrow/CG-arrow-multiply2matrix.html?info=Now%20try%20multiplying%20two%20other%20transform%20matrices%20that%20you%20make%20up%20yourself,%20and%20see%20if%20they%20produce%20the%20expected%20result.&zoom=-10.0%20&quiz=1.4%201.4%200%200%20-1.4%201.4%200%200%200%200%201%200%200%200%200%201%20&allPrize=5" text="Kliknij, aby uruchomić interaktywne narzędzie"}

Systemy grafiki komputerowej zwykle wymagają wykonania złożonych przekształceń, które można przedstawić jako matematyczne złożenie wielu prostych przekształceń. Obliczeń nie wykonuje się etapami (efekt działania poprzedniego przekształcenia stanowi dane do wykonania kolejnego przekształcenia). Projektanci systemu, do opisu przekształcenia złożonego, jeśli to tylko możliwe, używają jednej macierzy, która jest iloczynem macierzy opisujących składowe przekształcenia. 
Trzeba pamiętać, że złożone przekształcenie stosuje się czasem i dla miliona punktów naraz. Koszt znalezienia macierzy wypadkowej dla grupy przekształceń jest niewielki w porównaniu z kosztem obliczeń dla nieefektywnego rozwiązania.

Poniej opisano projekt, który ma służyć pogłębieniu tego tematu. Podano tam link do interaktywnego narzędzia do ćwieczń.


### Przekształcenia 3D 

Do tej pory wykonywaliśmy tylko przekształcenia w dwóch wymiarach (na płaszczyźnie). Do opisu przekształceń w 3D potrzebujemy współrzędnej *z*, która opisuje trzeci wymiar, jakby głębość przestrzeni. 
Macierz dla operacji w 3D, gdzie każdy punkt ma przypisane trzy współrzędne, jest rozmiaru 3 na 3. Oto macierz opisująca podwojenie rozmiaru obiektu; każdą ze współrzędnych *x*, *y* i *z* mnożymy przez 2.


{math-block}

\begin{bmatrix}
2 & 0 & 0 \\  
0 & 2 & 0 \\  
0 & 0 & 2 \\  
\end{bmatrix}

{math-block end}

Poniżej narzędzie do ćwiczeń.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-mini-editor/main%20(cutdown).html?info=%0AIn%20this%20interactive,%20try%20changing%20the%20scaling%20on%20the%20image%20(it%20starts%20with%20a%20scaling%20factor%20of%2010%20in%20all%20three%20dimensions)." text="Kliknij, aby uruchomić interaktywne narzędzie."}

Obraz czajniczka składa się z 3644 punktów. Przekształcenie opisane macierzą jest wykonywane na każdym z nich.

Kolejne narzędzie pozwala na przesuwanie obiektu (z użyciem wektora).
Zachęcamy do wykonania ćwiczeń. 

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-mini-editor/main%20(cutdown).html?info=%0ATranslation%20requires%203%20values,%20which%20are%20added%20to%20the%20*x*,%20*y*%20and%20*z*%20coordinates%20of%20each%20point%20in%20an%20object.%3Cp%3EIn%20the%20following%20interactive,%20try%20moving%20the%20teapot%20left%20and%20right%20(%20%3Cem%3Ex%3C/em%3E%20),%20up%20and%20down%20(%20%3Cem%3Ey%3C/em%3E%20),%20and%20in%20and%20out%20of%20the%20screen%20(%20%3Cem%3Ez%3C/em%3E%20)%20by%20adding%20a%20%E2%80%9Cvector%E2%80%9D%20to%20the%20operations.%20Then%20try%20combining%20all%20three.%3C/p%3E%0A" text="Kliknij, aby uruchomić interaktywne narzędzie"}

Obrót jest trudniej opisać, gdyż w przestrzeni są trzy stopnie swobody. Na płaszczyźnie obroty wykonywane są wokół punktu (0,0), a w przestrzeni obroty wykonuje się wokół prostej (albo osi *X*, albo osi *Y*, albo osi *Z*, skierowanej jakby „w głąb” ekranu).

Do obracania w trzech kierunkach używa się takiej macierzy:

{math-block}

\begin{bmatrix}
\cos(\theta) & -\sin(\theta) & 0 \\  
\sin(\theta) & \cos(\theta)  & 0 \\  
0   &  0  &  1\\
\end{bmatrix}

{math-block end}

Spróbuj zastosować tę macierz do obrazu z ćwiczenia interaktywnego.
Ta macierz stanowi opis obrotu wokół osi *Z* (prostej skierowanej „w głąb” ekranu); w istocie ten przykład to obrót w płaszczyźnie.
Ostatni wiersz macierzy (0, 0, 1) pozostawia wartość bez zmian.

Poniżej znajduje się macierz opisującą obrót wokół osi *X* (współrzędna *x* pozostaje bez zmian: w pierwszym wierszu macierzy jest 1, 0, 0):

{math-block}

\begin{bmatrix}
1   &  0  &  0 \\
0 &  \cos(\theta) & -\sin(\theta)  \\  
0 & \sin(\theta) & \cos(\theta)   \\  
\end{bmatrix}

{math-block end}

A poniżej macierz dla obrotu wokół osi y:

{math-block}

 \begin{bmatrix}
 \cos(\theta) & 0 &\sin(\theta)  \\  
 0   &  1  &  0\\
 -\sin(\theta) & 0 & \cos(\theta)   \\  
 \end{bmatrix}

{math-block end}

Poniżej znajduje się interaktyne narzędzie, które pozwala na składanie macierzy dla przekształceń 3D.

{comment}

.. xTCB put in a sidebox on deriving the rotation matrices (one day) (maybe in the 2d part)

{comment end}

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-mini-editor/main%20(cutdown).html?info=%0AYou%20can%20experiment%20with%20moving%20the%20teapot%20around%20in%20space,%20changing%20its%20size,%20and%20angle.%3Cdl%20class=%22docutils%22%3E%0A%3Cdt%3EThink%20about%20the%20order%20in%20which%20you%20need%20to%20combine%20the%20transforms%20to%20get%20a%20particular%20image%20that%20you%20want.%3C/dt%3E%0A%3Cdd%3EFor%20example,%20if%20you%20translate%20an%20image%20and%20then%20scale%20it,%20you%E2%80%99ll%20get%20a%20different%20effect%20to%20scaling%20it%20then%20translating%20it.%0AIf%20you%20want%20to%20rotate%20or%20scale%20around%20a%20particular%20point,%20you%20can%20do%20this%20in%20three%20steps%20(as%20with%20the%202D%20case%20above):%20(1)%20translate%20the%20object%20so%20that%20the%20point%20you%20want%20to%20scale%20or%20rotate%20around%20is%20the%20origin%20(where%20the%20x,%20y%20and%20z%20axes%20meet),%20(2)%20do%20the%20scaling/rotation,%20(3)%20translate%20the%20object%20back%20to%20where%20it%20was.%20If%20you%20just%20scale%20an%20object%20where%20it%20is,%20its%20distance%20from%20the%20origin%20will%20also%20be%20scaled%20up.%3C/dd%3E%0A%3C/dl%3E%0A" text="Kliknij, aby uruchomić interaktywne narzędzie."}

W tych przykładach, gdy dla pojedynczego punktu nalezałoby użyć kilku macierzy kolejnych przekształceń, można zaoszczędzić dużo czasu przez zastąpienie kilku macierzy jedną, która opisuje złożenie tych przekształceń. Poniżej znajdziesz narzędzie do ćwiczeń.

Na przykład, zapisz macierz skalowania razy 2, zmieniając 1 na przekątnej na 2, a następnie inną macierz, skalowania razy 3 (na przekątnej liczby 3).
Narzędzie interaktywne pozwala zobaczyć po prawej stronie macierz, będącą opisem złożenia tych dwóch przekształceń. Co można zauważyć?

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-matrix-simplifier/CG-matrix-simplifier.html?info=Multiple%20transforms" text="Kliknij, aby uruchomić interaktywne narzędzie."}

{panel type="teacher-note" summary="Wyjaśnienie"}

Efekt złożenia przekształceń skalowania razy 2 i razy 3 jest identyczny z efektem skalowania razy 6. 

{panel end}
{comment}
.. xTCB One teacher noted that students where need to know that the it requires transform matrix and one translation; not sure if this is now applicable
{comment end}

Narzędzie pozwala też dodać przekształcenie, jakim jest przesunięcie.
Sprawdź, jak działa składanie skalowania i przesunięcia. Co będzie, jeśli dodasz obrót -- czy kolejność przekształceń ma znaczenie?

{panel type="curiosity" summary="Mnożenie macierzy w 3D"}
Ktoś może być ciekaw, jak powstała macierz przekształcenia wypadkowego. Jest ona wynikiem mnożenia macierzy. Sposób, w jaki mnoży się macierze, jest opisany poniżej. Wydaje się skomplikowany, ale takie mnożenie jest bardzo użyteczne w grafice komputerowej, ponieważ pozwala wiele kolejno wykonywanych przekształceń opisać jedną macierzą, która jest stosowania dla każdego punktu obiektu. To redukuje w znaczący sposób liczbę obliczeń.  

{comment}
.. xTCB give an example for the following one day?
{comment end}

{math-block}
\begin{bmatrix}
a_{11} & a_{21} & a_{31}\\  
a_{12} & a_{22} & a_{32}\\  
a_{13} & a_{23} & a_{33}\\  
\end{bmatrix}
\times
\begin{bmatrix}
b_{11} & b_{21} & b_{31}\\  
b_{12} & b_{22} & b_{32}\\  
b_{13} & b_{23} & b_{33}\\  
\end{bmatrix}
=\\
\begin{bmatrix}
a_{11}b_{11}+a_{21}b_{12}+a_{31}b_{13} &
a_{11}b_{21}+a_{21}b_{22}+a_{31}b_{23} &  
a_{11}b_{31}+a_{21}b_{32}+a_{31}b_{33}\\  
a_{12}b_{11}+a_{22}b_{12}+a_{32}b_{13} &
a_{12}b_{21}+a_{22}b_{22}+a_{32}b_{23} &
a_{12}b_{31}+a_{22}b_{32}+a_{32}b_{33} \\  
a_{13}b_{11}+a_{23}b_{12}+a_{33}b_{13} &
a_{13}b_{21}+a_{23}b_{22}+a_{33}b_{23}&
a_{13}b_{31}+a_{23}b_{32}+a_{33}b_{33} \\  
\end{bmatrix}
{math-block end}
{panel end}

{panel type="project" summary="przekształcenia 3D"}
A teraz proponujemy wykonanie projektu, pozwalającego pokazać efekty nauki. Zadanie będzie polegać na zaprentowaniu i opisie przekształceń 3D kilku obiektów. 
Należy pamiętać o wykonaniu zrzutów ekranu po każdym kroku, bo interaktywne narzędzia, których będziesz uzywał, nie pozwalają na zapis grafiki.


Poniższe narzędzie pozwala na wybór obiektów (i ich kolorów etc.) i zastosowanie jednego z przekształceń.
Wyzwaniem będzie zastosowanie całej serii przekształceń (np. skalowanie, potem obrót, a następnie przesunięcie) i w końcu znalezienie „uproszczenia” w postaci jednego wypadkowego przekształcenia.

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-mini-editor/main.html?info=Multiple%20transforms" text="Kliknij, aby uruchomić interaktywne narzędzie."}

To narzędzie pomoże znaleźć przekształcenie wypadkowe:

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/CG/CG-matrix-simplifier/CG-matrix-simplifier.html?info=Multiple%20transforms" text="Kliknij, aby uruchomić interaktywne narzędzie."}

Prezentację wyników swojej pracy poprzedź przykładami obrazów 3D, na przykład pochodzących z filmów nagrodzonych za grafikę. Opowiedz, co w nich innowacyjnego.

Aby wykazać się rozumieniem podstaw grafiki komputerowej, zaplanuj rozmieszczenie kilku obiektów na obrazku (np. czajniczek obok kilku filiżanek)  i spróbuj je odzwierciedlić w narzędziu interaktywnym. Wyjaśnij istotę zastosowanych przekształceń, pokazując macierze opisujące przekształcenia.

Podaj proste przykłady różnych przekształceń, również złożenia kilku przekształceń.

Pokaż, jak macierze składowe można zastąpić jedną macierzą wypadkową i objaśnij, używając konkretnych ilustracji, na czym polega efektywność tego rozwiązania.

{panel end}
{comment}
End of 3D transform project
{comment end}

{panel type="project" summary="WebGL and OpenGL"}
Biegli w programowaniu, chcący zgłębiać temat przekształceń graficznych w praktyce, mogą wykonać projekt używając jednego z systemów programowania grafiki:
[WebGL](https://en.wikipedia.org/wiki/WebGL) (użyty do przygotowania narzędzi wyżej udostępnionych)
lub powszechnie stosowany system
[OpenGL](https://en.wikipedia.org/wiki/OpenGL).
Interaktywny samouczek OpenGL można znaleźć tutaj:
[JPOT](http://www.cs.uwm.edu/%7Egrafix2/).

Wykonanie projektu w jednym z tych systemów może być bardzo czasochłonne. Trzeba się wiele nauczyć, zanim uda się uzyskać ciekawe efekty.
{panel end}
{comment}
End of WebGL project
{comment end}


{comment}
.. ## Colour models

.. this section is yet to be written

.. RGB, CMY, HSV, ... tricolour stimulus

.. For example, see:
.. http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html colours RGB, HSV

{comment end}

## Rysowanie odcinków i okręgów

Podstawową operacją w grafice komputerowej jest rysowanie odcinków i okręgów.
Na przykład kształt czcionki na ekranie jest opisany m.in. przez odcinki i łuki okręgów.
Litera *g* jest zbiorem odcinków i fragmentów krzywych. Gdy wyświetlamy ją w powiększeniu na ekranie, wtedy kształt litery jest rysowany od nowa. Możemy ją powiększać bez obawy o utratę jakości, gdyż obraz litery nie jest skończonym zbiorem pikseli, nie ma stałej rozdzielczości rozdzielczości, a jest tzw. grafiką wektorową.

{comment}

 .. xTCB to add sometime, Jargonbuster: pixel (somewhere in the chapter) - also mention pel and bitmap, and origins of the terms. see www.foveon.com/files/ABriefHistoryofPixel2.pdf

{comment end}

{image filename="vector-letter-with-outline.png" caption="The points used to create the letter 'g' in Google's logo"}

W przypadku grafiki 3D kształty obiektow są często zbiorem ocinkow i krzywych, które stanowią krawędzie małych płaskich powierzchni (zwykle trójkątów), zwykle niedostrzegalnych dla oka.

{image filename="dolphin-triangle-mesh.png"}
{comment}
Public domain image: https://en.wikipedia.org/wiki/Triangle_mesh#/media/File:Dolphin_triangle_mesh.png
{comment end}

Odcinki i okręgi, które są składowymi obiektów, są zwykle w pamięci komputera zapisane jako liczby (np. dla odcinka zapisuje się punkty będące jego końcami, dla okręgu -- jego środek i promień). Program graficzny musi na tej podstawie określić piksele, które będą reprezentować odcinki i okręgi na ekraniu monitora. Czasem program musi określić położenie odcinka bez rysowania go.

Poniżej widzisz powiększoną siatkę pikseli binarnego obrazu, na której znajduje się 5 odcinków.
Wiersze i kolumny są ponumerowane. Odcinek pionowy ma początek w punkcie (2,9) i koniec w punkcie (2,16).
Oczywiście taka grafika przedstawia tylko mały fragment ekranu. Monitory komputerowe wyświetlają zwykle ponad 1000 pikseli, zarówno w poziomie, jak i w pionie. Również na ekranach smarfonów odcinki składają się z setek pikseli.

{image filename="grid-20x20-example.png" alt="Przykład z 5 odcinkami na siatce pikseli."}

Na papierze, używając linijki i cyrkla, można łatwo rysować figury geometryczne. Wyświetlenie takiej figury na ekranie komputera wymaga wykonania obliczeń dla wyznaczenia współrzędnych każdego z pikseli tworzących obraz figury. Wybór kiepskiej metody do wykonania takich obliczeń wpłynie na czas potrzebny na wyświetlenie zbioru pikseli i będzie miał fatalne skutki np. w przypadku animacji.

W tym podrozdziale przyjrzymy się bardzo prostym, ale sprytnym algorytmom, które pozwalają komputerowi szybko wykonać niezbędne obliczenia.

### Rysowanie odcinków

{panel type="teacher-note" summary="Materiały dla uczniów"}
Do wykonania ćwiczeń uczniowie będą potrzebować kartek z wydrukowaną siatką kwadratową lub zwykłych kartek ze szkolnego zeszytu w kratkę.
{panel end}

Aby narysować odcinek, komputer musi wybrać piksele tak, aby ich zbiór wyglądał jak fragment linii prostej. 
Warto wykonać kilka prób samodzielnie, na papierze w kratkę (oczywiście kratki są wielokrotnie większych rozmiarów niż piksel na monitorze czy kropka na wydruku).
Wybrany zbiór pikseli będziemy określać za pomocą dwóch wartości (*x*,*y*), gdzie *x* to odległość od lewego brzegu kartki, a *y* to odległość od dolnego brzegu kartki.
Piksel w lewym dolnym rogu ma współrzędne (0,0), a piksel w prawym górnym roku ma współrzędną (19,19).

Na siatce kwadratowej 19 x 19 spróbuj narysować odcinki (jako zbiory zamalowanych kwadratów) łączące punkty:
- (2, 17) i (10, 17)
- (18, 2) i (18, 14)
- (1, 5) i (8, 12)

{image filename="grid-20x20-blank.png" alt="Grid for drawing line from A to B"}

{comment}

.. xHTML5 The grids in this section could be interactive, click on each pixel, and get it to check if the line is correct

{comment end}

{panel type="teacher-note" summary="Rozwiązanie"}

Te odcinki było łatwo narysować, gdyż tworzące je piksele są równoległe do brzegów siatki lub leżą na przekątnej kwadratu (siatki).

{image filename="grid-20x20-answer-1.png" alt="Answer for previous question on grid"}

{panel end}

Rysowanie linii równoległych do krawędzi ekranu lub leżących na głównej przekątnej ekranu jest łatwe; z narysowaniem odcinków, które tworzą z krawędzią ekranu inne kąty jest trudniej, gdyż trzeba wykonać odpowiednie obliczenia.

Potrafisz, bez użycia linijki, wybrać i zamalować odpowiednie pliksele tak, aby tworzyły odcinek z A do B? Spróbuj.

{image filename="grid-20x20-diagonal-question.png" alt="Grid for drawing line from A to B"}

Sprawdź efekt, przykładając linijkę do rysunku. Umieść ją tak, aby krawędź linijki przechodziła przez środki małych kwadratów A i B. Czy linijka przechodzi przez wszystkie zamalowane piksele?

### Rysowanie odcinka z użyciem równania prostej

Prostą w układzie współrzędnych XY można opisać równaniem {math}y = mx + c{math end}.
Używając tego równania, możemy wyznaczyć wartość współrzędnej *y* dla wartości współrzednej *x*.
Wcześniej trzeba określić wartość współczynnika opisującego
{glossary-link term="slope" reference-text="computer graphics"}nachylenie prostej{glossary-link end}, którym jest {math}m{math end},
oraz punkt, w którym prosta przecina oś Y, czyli (0, *y*). Współrzędna *y* tego punktu w równaniu jest oznaczona jako {math}c{math end}.
Innymi słowy, rysując linię prostą wybieramy piksele o współrzędnych ({math}x{math end}, {math}mx + c{math end}) dla kolejnych wartości *x*.

Na przykład, wybierając {math}m=2{math end} and {math}c=3{math end} otrzymujemy prostą przechodzącą przez punkty (0,3), (1,5), (2,7), (3,9) itd.
Zauważ, że dla kolejnych punktów współrzędne *x*  rosną o 1, a współrzędne *y* -- o 2 (bo {math}m=2{math end}). Pierwszy piksel jest położony 3 jednostki powyżej brzegu siatki (bo {math}c=3{math end}).

Poćwicz na innych przykładach, dla różnych wartości  {math}m{math end} i {math}c{math end} (na przykład zacznij od {math}c=0{math end} i sprawdź trzy przypadki *m*: {math}m=1{math end}, {math}m=0{,}5{math end} i {math}m=0{math end}).
Jakie są kąty nachylenia prostych?

{panel type="teacher-note" summary="Rozwiązanie"}
Wartość {math}m=0{math end} odpowiada prostej równoległej do dolnej krawędzi, wartość {math}m=1{math end} to przypadek prostej o kącie nachylenia 45 stopni (przesunięciu o 1 piksel w poziomie odpowiada przesunięcie o jeden piksel w pionie).
Wartość {math}m=0.5{math end} opisuje prostą o kącie nachylenia mniejszym niż 27 stopni.
[Narzędzie interaktywne](http://www.mathopenref.com/coordslope.html) może być pomocne w zrozumieniu związku wartości *m* z kątem nachylenia.)
{panel end}

Równanie {math}mx + c{math end} może być użyte do wybrania pikseli dla cyfrowej reprezentacji odcinka łączącego punkty {math}(x_1, y_1){math end} i {math}(x_2, y_2){math end}.
Jakie wartości mają współrzędne {math}(x_1, y_1){math end} i {math}(x_2, y_2){math end} w przykładzie poniżej?

{panel type="teacher-note" summary="Rozwiązanie"}
Końce odcinka to punkty: {math}A = (3,4){math end} i {math}B = (16,9){math end}. To znaczy, że {math}x_1 = 3, y_1 = 4, x_2=16{math end} i {math}y_2 = 9{math end}.
{panel end}

Potrafisz wyznaczyć wartości {math}m{math end} i {math}b{math end} dla równania prostej przechodzącej przez punkty *A* i *B*? Możesz użyć następujących wzorów:

{math-block}

m = \frac{(y_2 - y_1)}{(x_2 - x_1)}\\
b = \frac{(y_1x_2 - y_2x_1)}{(x_2-x_1)}

{math-block end}

{panel type="teacher-note" summary="Rozwiązanie"}
Oto wyniki obliczeń:

\\[
m = \frac{(9 - 4)}{(16 - 3)}  = 5/13 \approx 0.384615
b = \frac{(4 \times 16 - 9 \times 3)}{(16-3)} = 37/13 \approx 2.846154
\\]


Równanie ma więc postać {math}y \approx 0.384615x + 2.846154{math end}.

W kolejnym ćwiczeniu warto użyć arkusza kalkulacyjnego do określenia wartości *y*.

| *x* | *y* |
|-----|-----|
| 3  |  4.000 |
| 4  |  4.385 |
| 5  |  4.769 |
| 6  |  5.154 |
| 7  |  5.538 |
| 8  |  5.923 |
| 9  |  6.308 |
| 10 |  6.692 |
| 11 |  7.077 |
| 12 |  7.462 |
| 13 |  7.846 |
| 14 |  8.231 |
| 15 |  8.615 |
| 16 |  9.000 |

{panel end}

Teraz w celu narysowania odcinka między punktami *A* i *B* (z poprzedniego ćwiczenia) wykonaj obliczenia, używając równania {math}y = mx + c{math end}. Wyznacz odpowiednie wartości {math}y{math end} dla kolejnych wartości {math}x{math end} z zakresu od {math}x_1{math end} do {math}x_2{math end}. Dla wskazania (jakby zapalenia na ekranie) odpowiednich pikseli, wartości *y* trzeba będzie zaokrąglić do najbliższej liczby całkowitej.
Wartości {math}y{math end} powinny być liczbami pomiędzy  {math}y_1{math end} i {math}y_2{math end}.

{image filename="grid-20x20-diagonal-question.png" alt="Siatka pikseli dla odcinka"}

{panel type="teacher-note" summary="Rozwiązanie"}

Efekt końcowy jest pokazany na rysunku:
{image filename="grid-20x20-diagonal-answer.png" alt="Siatka pikseli dla odcinka"}

{panel end}

Po wykonaniu ćwiczenia sprawdź linijką, czy wynik jest lepszy od tego z pierwszej próby.

Zastanów się nad tym, ile obliczeń było niezbędnych do wyznaczenia każdego punktu (i wyboru piksela). Może wydawać się, że niewiele. Pamiętaj jednak, że obliczenia mogą w praktyce dotyczyć tysięcy odcinków składających się z setek punktów. 

Okazuje się, że rozwiązanie wykorzystujące opisane wyżej równanie nie jest zbyt szybkie i w praktyce może być nieprzydatne (np. dla animacji i w grach komputerowych). W praktyce korzysta się ze znacznie bardziej efektywnej metody.

{panel type="teacher-note" summary="Rozwiązanie"}
Wyznaczenie każdego punktu wymaga wykonania mnożenia, dodwawania i także operacji zaokrąglania. Operacja mnożenia jest obliczeniowo dość kosztowną operacją (zwłaszcza gdy obraz składa się z tysięcy czy nawet milionów pikseli!). Co gorsza, metoda opisana wyżej wymaga wykonywania obliczeń w tzw. arytmetyce zmiennoprzecinkowej, co jest o wiele bardziej czasochłonne niż operacje wykonywane na liczbach całkowitych.
{panel end}

### Algorytm Bresenhama rysowania ocinka

Szybszym sposobem na wyznaczenie współrzędnych punktów tworzących odcinek na ekranie jest algorytm zaproponowany przez Jacka Bresenhama.  Składa się z kilku etapów. Najpierw wyznacza się trzy wartości:

{math-block}
A = 2 \times (y_2 - y_1)
\\
B = A - 2 \times (x_2 - x_1)
\\
P = A - (x_2 - x_1)
{math-block end}

Oto kolejne kroki algorytmu.
- Zapal piksel początkowy. 

Następnie dopóki nie napotkasz punktu końcowego, dla kolejnych wartości *x*, poruszając się wzdłuż osi *X* wykonuj:
- Jeśli {math}P < 0{math end}, to zapal piksel położony bezpośrednio po prawej stronie wcześniej zapalonego i dodaj {math}A{math end} do {math}P{math end}.
- W przeciwnym przypadku zapal piksel po prawej, położony wiersz wyżej niż wcześniej wybrany i dodaj {math}B{math end} do {math}P{math end}.

Sprawdź działanie algorytmu Bresenhama, rysując ponownie odcinek z *A* do *B*:

{image filename="grid-20x20-diagonal-question.png" alt="Siatka do narysowania odcinka AB"}

Sprawdź efekt przy pomocy linijki. Jak wyszło w porównaniu do wcześniejszych prób?

{panel type="teacher-note" summary="|Rozwiązanie"}
Poniżej zapisano obliczenia wykonane z użyciem algorytmu Bresenhama:

| Etap obliczeń | Wybór piksela |
|-------------|--------------------|
| {math}A = 10,  B = -16{math end} | Zapalenie piksela początkowego. |
| {math}P_0 = -3{math end} | Kolejny zapalony piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_1 = 7{math end} | Kolejny piksel to piksel po prawej w wierszu wyżej. |
| {math}P_2 = -9{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_3 = 1{math end} | Kolejny piksel to piksel po prawej w wierszu wyżej. |
| {math}P_4 = -15{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_5 = -5{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_6 = 5{math end} | Kolejny piksel to piksel po prawej w wierszu wyżej. |
| {math}P_7 = -11{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_8 = -1{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_9 = 9{math end} | Kolejny piksel to piksel po prawej w wierszu wyżej. |
| {math}P_{10} = -7{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |
| {math}P_{11} = 3{math end} | Kolejny piksel to piksel po prawej w wierszu wyżej. |
| {math}P_{12} = -13{math end} | Kolejny piksel jest bezpośrednio po prawej stronie poprzedniego. |

{panel end}

### Odcinki o innych kątach nachylenia

Przedstawiona powyżej wersja algorytmu Bresenhama była wersją niepełną, gdyż działała poprawnie tylko dla odcinków nachylonych do poziomu o kąt między 0 a 45 stopni (co odpowiada wartościom współczynnika nachylenia *m* od 0 do 1). Aby algorytm był uniwersalny, trzeba listę kroków algorytmu uzupełnić:

- W przypadku, gdy odcinek jest nachylony nie w górę, ale w dół, wówczas, gdy {math}P >= 0{math end}, jako kolejny piksel należy zapalić ten położony po prawej w wierszu niżej.
- Jeśli wartość {math}y{math end} rośnie szybciej niż wartość {math}x{math end} (co odpowiada kątowi nachylenia większemu niż 45 stopni), to podczas obliczania wartości *A*, *B* i początkowej wartości *P*, zamień w algorytmie rolę osi *X* i *X* rolami. Oznacza to, że zamiast poruszać się wzdłuż osi *X*, poruszasz się wzdłuż *X*, a zamiast zapalać po jednym pikselu w każdej kolumnie, zapalasz po jednym pikselu w każdym wierszu.

{image filename="grid-20x20-blank.png" alt="Siatka pikseli dla odcinka"}

Zaznacz na siatce kwadratowej dowolne dwa punkty. 
Wybierz je tak, aby nie łączył ich odcinek poziomy, pionowy, ani po przekątnej!

Użyj algorytmu Bresenhama do narysowania odcinka. Sprawdź, że w efekcie otrzymujesz te same piksele, które uzyskać można z użyciem linijki lub równania prostej {math}y = mx+b{math end}.
Ile operacji arytmetycznych (mnożenia i dodawania) było wykonanych przy wyznaczaniu zbioru pikseli metodą Bresenhama?
Ile byłoby ich w przypadku posługowania się równaniem {math}y = mx+b{math end}?
Który sposób jest szybszy? (Pamiętaj, że w większości przypadków koszt dodawania jest o wiele mniejszy niż koszt mnożenia.)

{panel type="teacher-note" summary="Szybkość metody Bresenhama"}
Ta metoda dla wskazania kolejnego piksela wymaga wyłącznie porównania jednej liczby całkowitej z zerem i jednego dodawania. Jest o wiele szybsza od metody z równaniem.
{panel end}

Możesz napisać program komputerowy lub użyć narzędzi arkusza kalkulacyjnego do wykonania obliczeń --- tego wymaga się od programistów zajmujących się grafiką komputerową.

### Okręgi

Oprócz odcinków prostej, często komputery muszą rysować okręgi.
Algorytm Bresenhama rysowania odcinków przystosowano do rysowania okręgów.

Dany okrąg jest jednoznacznie określony przez jego środek i promień. Przypomnijmy, że okrąg jest zbiorem punków oddalonych o promień od środka.

{image filename="grid-20x20-circle-question.png" alt="Siatka pikseli dla okręgu"}

Spróbuj narysować okrąg „na oko”, bez posługiwania się cyrklem. Dlaczego nie jest to takie proste?

Do określenia pikseli tworzących rysunek okręgu można by użyć twierdzenia Pitagorasa, ale to wymagałoby wielokrotnego obliczania pierwiastka kwadratowego, a tego nie da się zrobić zbyt szybko.
Poniżej opisany algorytm jest o wiele szybszy. Poza tym posługuje się wyłącznie prostymi operacjami arytmetycznymi.

### Algorytm Bresenhama dla okręgu
{comment}

.. xTCB could mention later that Bresenham didn't invent it, but idea comes from his line algorithm and is often named after him

{comment end}

Oto kolejne kroki algorytmu dla okręgu o środku ({math}c_{x}{math end}, {math}c_{y}{math end}) i promieniu {math}R{math end}:

{math-block}

E = -R\\
x = R\\
y = 0

{math-block end}

Powtarzaj kolejne kroki aż {math}y{math end} będzie mieć większą wartość niż {math}x{math end}:

- Zapal piksel o współrzędnych ({math}c_{x} + x{math end}, {math}c_{y} + y{math end}).
- Zwiększ {math}E{math end} o wartość wyrażenia {math}2 \times y + 1{math end}.
- Zwiększ {math}y{math end} o 1.
- Jeśli {math}E >=0{math end},  to odejmij wartość {math}2 \times x - 1{math end} od {math}E{math end}, a następnie odejmij 1 od {math}x{math end}.

Zastosuj algorytm, by stworzyć rysunek okręgu na siatce kwadratowej. Piksel opisany literą *C* ({math}c_{x}{math end}, {math}c_{y}{math end}) niech będzie środkiem okręgu, a piksel {math}R{math end} jednym z punktów na okręgu.
Zwróć uwagę na to, że zgodnie z algorytmem rysowanie należy przerwać, gdy {math}y{math end} będzie większe niż {math}x{math end}! 

{image filename="grid-20x20-circle-question.png" alt="Siatka pikseli dla okręgu"}

{panel type="teacher-note" summary="Rozwiązanie"}
Na rysunku poniżej zaczerniono piksele uzyskane po wykonaniu algorytmu (jest to ośma część okręgu). Ciemnym szarym kolorem zaznaczono piksele uzyskane kolejno jako efekt symetrii osiowej (odbicia lustrzane) względem prostych równoległych do osi *X* i osi *Y*. Jasnym szarym kolorem zaznaczono piksele, które są obrazem pikseli w symetrii względem przekątnej siatki. 
Warto, aby uczniowie samodzielnie poszukali odpowiednich przekształceń. (Dla symetrii względem przekątnych osiami symetrii są proste o współczynnikach kierunkowych 1 i -1.)

{image filename="grid-20x20-circle-answer.png" alt="Rozwiązanie dla okręgu"}

Oto etapy obliczeń:

| Etap obliczń | Wybrany piksel |
|-------------|--------------------|
| {math}E_0 = -7, X_0 = 7, Y_0 = 0{math end} | Zapalenie piksela (16, 9) |
| {math}E_1 = -6, Y_1 = 1{math end} | Zapalenie piksela (16, 10) |
| {math}E_2 = -3, Y_2 = 2{math end} | Zapalenie piksela (16, 11) |
| {math}E_3 = 2, Y_3 = 3{math end} | -  |
| {math}E_4 = -11, X_4 = 6{math end} | Zapalenie (15, 12) |
| {math}E_5 = -4, Y_5 = 4{math end} | Zapalenie (15, 13) |
| {math}E_6 = 5, Y_6 = 5{math end} | - |
| {math}E_7 = -6, X_7 = 5{math end} | Zapalenie (14, 14) |
| {math}E_8 = 5, Y_8 = 6{math end} | *y* > *x*, co oznacza, że mamy ośmą część okręgu narysowaną |

{panel end}

{panel type="jargon-buster" summary="Kwadranty i oktanty"}
*Kwadrant* to ćwiartka jakiegoś obszaru. *Oktant* to óśma część jakiegoś obszaru.
{panel end}

W istocie komputer nie wykonuje wielu dodatkowych obliczeń w celu narysowania 7/8 okręgu. Algorytm wyznacza w każdej iteracji dwie liczby {math}(x, y){math end}, które określają położenie piksela względem środka okręgu. Z łatwością wówczas wskazać 7 par liczb odpowiadających {math}(x, y){math end} w odpowiedniej symetrii:{math}(x, -y){math end}, {math}(-x, y){math end}, {math}(-x, -y){math end}, {math}(y, x){math end}, {math}(y, -x){math end}, {math}(-y, x){math end} i {math}(-y, -x){math end}. W sumie mamy 8 pikseli w każdej iteracji.

Warto dodać, że algorytm można dostosować do rysowania elips. Wówczas bazą dla rysunku jest 1/4 elipsy.

### Zastosowania praktyczne

Komputery rysują odcinki prostych, okręgi i elipsy na potrzeby różnych zastosowań praktycznych: grafiki w grach komputerowych, grafiki w programach dla architektów etc. Nawet kropka nad „i” w dokumencie tekstowym musi być narysowana jako okrąg, gdy jest wyświetlana na ekranie. Przez wzbogacenie metod rysowania odcinków i okręgów różnymi technikami wypełniania krzywych i wygładzania, można uzyskać efektowne gładkie krawędzie obiektów wyświetlanych na ekranie. W przypadku takich grafik nie ma ograniczenia rozdzielczości. 

Taką grafikę nazywa się grafiką wektorową. Ma tę własność, że podczas powiększania rysunku unikniemy efektu pikselizacji. Powiększanie oznacza zwiększenie szczęgółowości obrazu, więc element obrazu jest rysowany wówczas na nowo, liczba pikseli tworzących obraz jest dopasowywana do rozmiaru ekranu. Koszt to obliczenia, które trzeba wykonać. Dlatego używa się szybkich algorytmów.

Najbardziej powszechne rysunki wektorowe to rysunki konturów czcionek wyświetlanych na ekranie.

Informatycy zajmują się projektowaniem szybkich algorytmów dla grafiki komputerowej. Nie chodzi tu wyłącznie o szybkość wyświetlania. Dzięki postępowi w tej dziedzinie oszczędza się również na żywotności np. baterii smartfonów, gdyż nie obarcza się ich procesorów zbędnymi obliczeniami.

Jak zwykle, szczegóły są bardziej skomplikowane. Na przykład, wyobraźmy sobie odcinek łączący punkty (0,0) i (10,0), złożony z 11 pikseli. Następnie porównajmy go z odcinkiem pochylonym pod kątem 45 stopni, łączącym punkty (0,0) i (10,10). Jego rysunek składa się z 11 pikseli, ale odcinek jest dłuższy (o ok. 41%).

Jako skutek uboczny otrzymujemy więc różnej grubości odcinki na ekranie. Tak postrzega je nasze oko. Aby zredukować to wrażenie, stosuje się różne techniki, przede wszystkim wygładzanie (ang. anty-aliasing). 


## Podsumowanie

Powyżej ukazany jest tylko mały wycinek dziedziny, jaką jest grafika komputerowa.
Informatycy projektują algorytmy dla wielu obszarów grafiki komputerowej:
 - oświetlenia (np. w celu uzyskania efektu cienia w scenie 3D),
 - teksturowania (np. w celu uzyskania możliwie realistycznego obrazu trawy, skóry, wody, drewana itd.),
 - wygładzania (np. w celu zredukowania efektu ostrych krawędzi na obrazie),
 - rzutowania (np. w celu odwzorowania obiektów 3D na płaszczyźnie),
 - ukrywania obiektów (np. w celu określenia fragmentów obiektu niwidocznych dla obserwatora),
 - renderowania fotorealistycznego (przy tworzeniu obrazów, które wyglądają jak obrazy pochodzące z rzeczywistości), jak i renderowania nierealistycznego, taki jak „renderowanie malarskie” (np. w celu uzyskania obrazu na wzór obrazów malarskich, czyli efektu pociągnienia pędzlem), and
 - symulowania zajwisk takich jak ogień, fale morskie, ruch człowieka itd. 

System oparty na mnożeniu macierzy 3 x 3, przedstawiony w tym rozdziale to uproszczona wersja jednego z systemów, który oparty jest o [współrzedne jednorodne](https://en.wikipedia.org/wiki/Homogeneous_coordinates). Używa się w nim macierzy 4 x 4.
Jego zaletą jest to, że wszystkie operacje można realizować wyłącznie przez mnożenie (również przesunięcie). System pozwala też na uproszczenie innych operacji graficznych. Współczesne karty graficzne sprzętowo, a więc bardzo szybko, realizują operacje na współrzędnych jednorodnych.

{panel type="Curiosity" summary="Moebius i jego odkrycia"}
System współrzędnych jednorodnych wprowadził w 1827 roku niemiecki matematyk
[August Ferdinand Möbius](https://en.wikipedia.org/wiki/August_Ferdinand_M%C3%B6bius), ponad 100 lat przed erą komputerów.
Möbius jest prawodopoodbnie bardziej znany jako odkrywca pewnej matematycznej powierzchni jednostronnej, określanej jako [wstęga Möbiusa](https://en.wikipedia.org/wiki/M%C3%B6bius_strip)!



### Ciekawe linki

- [https://en.wikipedia.org/wiki/Computer_graphics](https://en.wikipedia.org/wiki/Computer_graphics)
- [https://en.wikipedia.org/wiki/Transformation_matrix](https://en.wikipedia.org/wiki/Transformation_matrix)
- [https://en.wikipedia.org/wiki/Bresenham’s_line_algorithm](https://en.wikipedia.org/wiki/Bresenham%27s_line_algorithm)
- [https://en.wikipedia.org/wiki/Ray_trace](https://en.wikipedia.org/wiki/Ray_trace)
- [http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html](http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html)
- [http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html](http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html)
- [http://www.povray.org/resources/links/3D_Tutorials/POV-Ray_Tutorials/](http://www.povray.org/resources/links/3D_Tutorials/POV-Ray_Tutorials/)



