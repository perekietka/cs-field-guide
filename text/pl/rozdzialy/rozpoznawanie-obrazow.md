# Rozpoznawanie obrazów (przez komputer)

{video url="https://www.youtube.com/embed/bE2u5trQAHM?rel=0"}

## Z perspektywy

W początkach ery komputerów komunikacja komputera ze światem zewnętrznym odbywała się poprzez bezpośrednie zestawianie połączeń kablowych lub poprzez klawiaturę. Współczesne urządzenia cyfrowe wyposażone są w aparaty fotograficzne, kamery, mikrofony i inne urządzenia wejściowe, używane przez oprogramowanie do automatycznego pobierania informacji ze świata, w którym żyjemy. Przetwarzanie obrazów z kamery w celu znalezenia poszukiwanych informacji (wzorców) nazywa się w informatyce *rozpoznawaniem obrazów* lub widzeniem komputerowym (ang. computer vision).

Wraz ze wzrostem mocy obliczeniowej komputerów, ich miniaturyzacją oraz stopniowym rozwojem algorytmicznych metod przetwarzania danych, komputerowe rozpoznawanie obrazów znajdowało coraz więcej zastosowań. Najpierw w dziedzinach takich, jak medycyna, bezpieczeństwo i przemysł, a później coraz częściej w codziennym życiu ludzi.

Oto przykład napisu w języku chińskim.

{image filename="no-smoking-sign.jpg" alt="Rozpoznawanie obrazu: celem jest przetłumaczenie."}

Jeśli ktoś nie zna pisma chińskiego, to może wspomóc się programem zaintalowanym w smartfonie:

{image filename="no-smoking-sign-translated.png" alt="Rozpoznawanie obraz: celem jest przetłumaczenie."}

Dla podróżujących takie przenośne małe urządzenie, które ,,patrzy'' i wyświetla tłumaczenie (,,palić'') jest wielkim udogodnieniem. 
Zauważyć należy, że tłumaczenie nie obejmuje pierwszej części (,,prosimy nie''). Trzeba zachować ostrożność!

Rozpoznawanie pisma chińskiego może być czasem niedoskonałe. Oto drogowy znak ostrzegawczy:

{image filename="steep-sign-translated.jpg" alt="Rozpoznawanie obrazu: celem jest przetłumaczenie."}

Przedstawiony na zdjęciu smartfon znalazł tłumaczenie dla znaków o znaczeniu ,,stromy'' i ,,ostrożnie'', ale nie rozpoznał ostatniego znaku w linii. Dlaczego?

{panel type="teacher-note" summary="Znaczenie segmentacji obrazu"}

Ostatni znak trudniej było rozpoznać, gdyż rysunek postaci człowieka jest zbyt blisko znaku. Oprogramowanie smarfona nie potrafiło określić, gdzie kończy się znak pisma, a gdzie rozpoczyna się rysunek. Ten problem jest znany pod nazwą *segmentacji obrazu*. Wrócimy do niego później.

{panel end}

Celem tego rodziału jest zaznajomienie czytelnika nie tylko z tematem rozpoznawania obrazów. Proces automatycznego rozpoznawania informacji (przechwytywania danych) ze świata realnego może być użyteczny na różne sposoby. Na przykład znajduje zastosowanie w samochodach, pomagając w unikaniu kolizji na drodze, poprzez ostrzeganie o zbyt małej odległości między samochodami i o innych zagrożeniach. W połączeniu z systemami map (nawigacji) system rozpoznawania obrazów pozwala na budowę samochodów, które będą się poruszać bez kierowcy. Inny przykład zastosowania to komputerowe systemy ostrzegania wbudowane w wózki inwalidzkie. 

## Światła, kamera, akcja!

Kamery cyfrowe i ludzkie oczy pełnią podobne funkcje: promienie światła przechodzą odpowiednio przez obiektyw kamery lub przez soczewkę oka, tam ulegają załamaniu i w końcu padają na powierzchnię (w oku to siatkówka) pokrytą fotoreceptorami, gdzie są przetwarzane na sygnały elektryczne, które później są przetwarzane przez komputer czy mózg. Oczywiście to tylko uproszczony schemat.

{panel type="teacher-note" summary="Receptory cyfrowego aparatu fotograficznego"}

Jest kilka różnych typów sensorów cyfrowego aparatu fotogrficznego. W tym rozdziale ograniczymy się do sensorów [CMOS](https://pl.wikipedia.org/wiki/Matryca_CMOS), najbardziej popularnych. Inny typ to [Charge-Coupled Device (CCD)](https://pl.wikipedia.org/wiki/Matryca_CCD), znany bardziej wśród fachowców zajmujących się astronomią.

{panel end}

W środku plamki żółtej, czyli części siatkówki **ludzkiego oka** o największym zagęszczeniu fotoreceptorów, zwanych czopkami, znajduje się zagłębienie zwane dołeczkiem (łac. fovea). To miejsce o największej rozdzielczości widzenia, to znaczy, że odpowiada za postrzeganie szczegółów obiektu, na który patrzymy wprost. Mamy trzy zbiory czopków, wrażliwych na różne barwy (kolory), odpowiednio na światło czerwone, zielone i niebieskie. 
Inne receptory siatkówki oka to pręciki, które są bardzo wrażliwe na światło, odpowiadają za postrzeganie kształtów i postrzeganie czarno-białe widzenie nawet przy słabym oświetleniu. 
Obszar siatkówki oka, w którym nerw wzrokowy opuszcza gałkę oczną i biegnie w stronę mózgu to plamka ślepa. Jest on całkowicie pozbawiony fotoreceptorów. Jednak luki w polu widzenia obu oczu nie pokrywają się, z więc to, czego nie widzi jedno oko, widzi drugie i powstaje wrażenie, że pole widzenia jest pełne.

**Aparaty cyfrowe**, inaczej niż oczy, są jednakowej czułości na światło dla całego pola widzenia. Intensywność światła i kolor są rejestrowane przez elementy receptorów RGB wdrukowane na krzemowym układzie scalonym. Te receptory nie mają jednak takiej zdolności jak oczy jeśli chodzi o zakres poziomów światła podczas przechwytywania informacji. Zwykle, współczesne aparaty cyfrowe potrafią automatycznie dopasować ustawienia w zależności od jasności otoczenia, ale ma to swoją cenę: bardziej szczegółowe informacje o obiektach będą stracone (np. jasne objekty będą na zdjęciu widoczne jako białe plamy).

Jest ważne, by zrozumieć, że ani ludzkie oko, ani cyfrowy aparat fotograficzny --- nawet bardzo drogi --- nie są w stanie zapisać wszystkich informacji o obiektach znajdujących się w polu widzenia. Prowadzone są badania, wspólnie przez inżynierów elektorników i informatyków, których celem jest stworzenie urządzeń, które będą pozwalać na jeszcze bardziej dokładne rejestrowanie informacji oraz jej szybkie przetwarzanie.

{panel type="Ciekawostka" summary="Do dalszej lektury"}

Więcej na ten temat (w języku angielskim) można przeczytać tutaj: [Cambridge in Colour](http://www.cambridgeincolour.com/tutorials/cameras-vs-human-eye.htm), [Pixiq](https://web.archive.org/web/20130309170941/http://www.pixiq.com/article/eyes-vs-cameras).

{panel end}

## Szum

Użytkownicy aparatów cyfrowych muszą mieć świadomość istnienia problemu, jakim jest *szum*. Mówi się o nim wówczas, gdy pojedyncze piksele rejestrowane są jako jaśniejsze lub ciemniejsze niż być powinny. Zjawisko jest skutkiem interfrencji (nakładania się) w układach elektronicznych aparatu. Jest to większy problem, gdy poziomy światła są niskie, a aparat próbuje zwiększyć czas ekspozycji obrazu (naświetlania), aby można było zobaczyć więcej. Używa się wtedy ustawień ASA/ISO celem przechwycenia takiej ilości promieni światła, ile to tylko możliwe. Receptory są wówczas bardzo wrażliwe na światło, co wiąże się z ryzykiem interferencji i obraz ma efekt „ziarnistości”. 

Efekt szumu jest widoczny głównie jako losowe (przypadkowe) zmiany pikseli. W przykładzie poniżej widzimy szum typu „sól i pieprz”.

{image filename="banana-with-salt-and-pepper-noise.jpg" alt="Obrazek banana z szumem typu sól i pieprz"}

Rozpoznawanie obiektów na obrazach, które zawierają szum jest trudniejsze. Dlatego ważne jest, by szukać coraz lepszych metod redukowania szumu na obrazie. 
Przy projektowaniu takich metod należy zachować ostrożność. Efektem ubocznym usunięcia szumu nie może być bowiem utrata istotnych informacji o obrazie. Trzeba podkreślić, że stosowane metody są zawsze metodami przybliżonymi rozwiązania problemu, co oznacza, że decyzja o zachowaniu wartości liczbowej lub zmianie wartości dla konkretnego piksela jest efektem domysłu, uzasadnionego domniemania.

{panel type="teacher-note" summary="Szumy w fotografii na Wikipedii"}

Warto zapoznać się z artykułem: [Image noise](https://en.wikipedia.org/wiki/Image_noise) lub po polsku [Szumy] (https://pl.wikipedia.org/wiki/Szumy_(fotografia_cyfrowa))

{panel end}

Ponieważ aparat fotograficzny zapisuje informacje o składowych (czerwona, zielona i niebieska) osobno dla każdego piksela, to czasami celem zaoszczędzenia na czasie przetwarzania obrazu, jest uzasadnione zapisanie obrazu w odcieniach szarości. Wtedy pomija się informacje o barwie, a zapisuje się tylko informacje o intensywności światła dla każdego piksela.

Dzieki temu można zmieniejszyć poziom szumu na obrazie. Dlaczego? I w jakim stoponiu to pomaga? (Aby się przekonać, można zrobić eksperyment: wykonać zdjęcie w miejscu słabo oświetlonym -- można wtedy dostrzec jakby małe łatki na obrazie. Następnie w programie graficznym można zapisać je jako czarno-białe -- czy to zmniejszy efekt szumu?)

{panel type="teacher-note" summary="Zaszumione kanały"}

Każdy światłoczuły element fotoreceptora aparatu fotograficznego jest równie podatny na szum. To oznacza, że efekty szumu dla różnych składowych RGB są zjawiskami niezależnymi. Jeśli wartości RGB uśredni się (co oznacza jedną liczbę zamiast trzech), to wartość szumu zredukuje się do ok. 1/3. Dlaczego nie *dokładnie* 1/3? Może się zdarzyć, że efekt szumu dotyczy dwóch czy nawet trzech składowych tego samego piksela: wtedy wartość uśredniona pozostanie daleka od dokładnej.

{panel end}

Zamiast analizować oddzielnie każdą ze składowych RGB piksela, techniki redukujące szum najczęściej działają tak, że sprawdzają piksele sąsiadujące z danym pikselem i na podstawie zebranych informacji przypisują mu przypuszczalną wartość.

W *filtrze uśredniającym* korzysta się z założenia, że piksele sąsiadujące z danym pikselem są podobne. Wartości przypisane pikselom tworzącym kwadrat, w którego centrum znajduje się dany piksel, są uśredniane i ta wartość średnia jest przypisana pikselowi.
Im kwadrat jest większych rozmiarów, tym większe niebezpieczeństwo pojawienia się w wyniku filtrowania efektu rozmycia obrazu, zwłaszcza w przypadku, gdy fragment obrazu przedstawia np. krawędzie obietków (wtedy jasne i ciemne piksele sąsiadują).

W *filtrze medianowym* stosuje się inne podejście. Odczytuje się wartości sąsiednich pikseli, podobnie jak dla filtru uśredniającego. Następnie szuka się mediany (wartości środkowej) ciągu uporządkowanego odczytanych wartości. Taki filtr daje dobre rezultaty w przypadku, gdy fragment obrazu przedstawia krawędź jakiegoś obiektu, gdyż wówczas wartość mediany będzie jedną z dwóch: albo odpowiadającą jasnemu pikselowi albo ciemnemu pikselowi. Filtr działa też dobrze, gdy analizowany obszar jest w dużej części jednolity, gdyż wówczas obecność mniej licznych pikseli o innej wartości nie ma żadnego wpływu na wartość mediany. Wadą tej metody jest czas działania, tj. koszt operacji porządkowania wartości przed wyznaczeniem mediany. 

Inną techniką jest metoda zwana *rozmyciem Gaussa*. Działa podobnie do metody uśredniania, ale zamiast wartości średniej korzysta się własności *rozkładu normalnego*: przyjmuje się, że piksele sąsiadujące bezpośrednio z analizowanym pikselem mają przypisaną wartość najbardziej zbliżoną do poszukiwanej, a piksele położone dalej wręcz przeciwnie.  

### Ćwiczenie: Usuwanie szumu z obrazu

Otwórz interaktywne narzędzie [noise reduction filtering interactive using this link](http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/cv-noise-filters.html) i przeprowadź badania według opisu poniżej. Niebędna będzie kamera internetowa.

Bazą matematyczną przetwarzania obrazu jest w tym przypadku specjalny rodzaj macierzy zwany *jądrem splotu* (ang. convolution kernel). Każdy z pikseli tworzących obraz jest przetwarzany: wartość mu przypisana jest uśredniania na podstawie wartości sąsiednich pikseli. Zbiór pikseli uśrednionych wartości tworzy nowy obraz. W tym przypadku średnia jest średnią ważoną, tzn. wpływ na średnią wartości pikseli sąsiadujących bezpośrednio z analizowanym pikselem jest większy niż wartości pikseli bardziej oddalonych. Im większe ma być rozmycie, tym większa macierz jest używana, co oznacza większą liczbę obliczeń do wykonania podczas przetwarzania.

Ćwiczenie polega na zbadaniu wpływu różnych ustawień dla filtrów usuwania szumu i określeniu:
- jak radzą sobie z różnymi rodzajami i poziomami szumu
- jak dużo czasu trwa przetwarzanie (narzędzie wyświetla informację o liczbie ramek przewarzanych w ciągu sekundy)
- jaki mają wpływ na jakość obrazu.


## Rozpoznawanie twarzy

Zdolność komputerów do rozpoznawania twarzy na zdjęciu znajduje wiele zastosowań. 
Na przykład na portalach społecznościowych coraz częściej pojawiają się narzędzia określania osób na zdjęciu bazujące na algorytmach rozpoznawania twarzy (i dopasowaniu ich do tych zapisanych już w bazie danych).

{image filename="face-recognition-software-screenshot.jpg" alt="Picasa do Google rozpoznaje te zdjęcia, jako te, na których jest tam sama osoba"}

Jest wiele innych zastosowań.
Systemy bezpieczeństwa, np. używane przez służby celne podczas przekraczania granicy między krajami, porównują twarz podróżującego z zdjęciem twarzy na paszporcie czy innym dowodzie tożsamości.
Celem przetwarzania obrazu i rozpoznawania twarzy może być dbałość o anonimowość (zachowanie prawa do prywatności) osób, które zostały zarejestrowane przez kamery systemów map ulicznych (np. Google Maps). Wówczas odpowiednie fragmenty zdjęć poddaje się rozmyciu.
Współczesne aparaty cyfrowe automatycznie dopasowują swoje ustawienia przez wykoaniem zdjęcia na podstawie lokalizacji twarzy wewnątrz kadru.

Więcej informacji na ten temat można znaleźć (w języku angielskim) tutaj:  [Jak działa rozpoznawanie twarzy?](http://electronics.howstuffworks.com/gadgets/high-tech-gadgets/facial-recognition.htm), [i-programmer.info](http://www.i-programmer.info/babbages-bag/1091-face-recognition.html).

Artykuły edukacyjne dotyczące tego zagadnienia znajdują się również [na stronie cs4fn](http://www.cs4fn.org/vision/)

### Projekt: Rozpoznawanie twarzy

{panel type="teacher-note" summary="NCEA"}

Poniższe zadanie może być ciekawą propozycją na projekt szkolny.
Dotyczy zagadnień:
- Temat: Rozpoznwanie twarzy na zdjęciu cyfrowym
- zastosowania praktyczne: bezpieczeństwo, znakowanie treści albumów zdjęć
- algorytm: detektor twarzy Haar'a
- kryteria oceny: dokładność rozpoznawania twarzy, fałszywe alarmy, szybkość działania
- autorskie przykłady: zastosowanie metody do własnych zdjęć

{panel end}

Zacznijmy od ręcznych prób zastosowania kilku metod dla rozpoznania, czy dwa zdjęcia ukazują tę samą osobę.

- Zgromadź co najmniej trzy zdjęcia przedstawijące trzy osoby.
- Zmierz cechy twarzy takie, jak odległość między oczami, szerokość ust, wysokość głowy itp. Porównaj wyniki uzyskane na różnych zdjęciach, wyznaczając odpowiednie ilorazy (proporcje).
- Sprawdź, czy na każdym ze zdjęć odpowiednie ilorazy dla konkretnej osoby są takie same. Czy te wartości różnią się w istotny sposób dla różnych osób? Czy te informacje pozwolą na bezbłędne rozpoznanie danej osoby na dwóch zdjęciach?
- Jakie inne cechy osób można by zmierzyć, aby zwiększyć skuteczność rozpoznawania twarzy na zdjęciu?

Wypróbuj interaktywne narzędzie [do rozpoznawania twarzy](https://inspirit.github.com/jsfeat/sample_haar_face.html), używające obrazu z kamery (np. wbudowanej w laptop). Sprawdź, jak dobrze działa śledzenie ruchu twarzy w tym systemie. Kiedy system zaczyna źle działać? Wystarczy zasłonić jedno oko? Wystarczy założyć kapelusz? Jaką część twarzy trzeba zakryć, aby rozpoznawanie twrzy przestało dobrze działzć? Co zrobić, aby system opacznie rozpoznał twarz w miejscu, gdzie jej nie ma?

## Wykrywanie krawędzi

Użyteczną techniką rozpoznawania obrazów przez komputer jest *wykrywanie krawędzi*, co oznacza automatyczną lokalizację granicznych częśći obiektów. To w praktyce oznacza możliwość podziału obrazu na rozłączne obiekty i obszary (segmentyzację).

Oto przykład. Na zdjęciu łatwo dostrzec wzrokiem różne obiekty.

{image filename="fruit-bowl-photo.jpg" alt="Zdjęcie miski z owocami"}

Oto efekt przetwarzania obrazu przez algorytm wykrywania krawędzi:

{image filename="fruit-bowl-photo-with-canny-edge-detection.png" alt="Zdjęcie powyżej z zastosowanym wykrywaniem krawędzi Canny'ego"}

Można zauważyć, że algorytm przetwarzał również fragment obrazu ukazujący stół; lepiej, aby właściwy proces wykrywania krawędzi poprzedzić innym wstępnym filtrowaniem!

Warto poeksperymentować z wykrywaczem krawędzi na stronie  [Canny detektor](https://inspirit.github.io/jsfeat/sample_canny_edge.html) (więcej informacji o [detektorze Canny'ego](https://pl.wikipedia.org/wiki/Canny)).
Algorytm został zaprojektowany w 1986 roku przez Johna F. Canny'ego.

### Projekt: Wykrywanie krawędzi

{panel type="teacher-note" summary="NCEA"}

Poniższe zadanie może być ciekawą propozycją na projekt szkolny.
Dotyczy zagadnień:
- Temat: Wykrywanie krawędzi na zdjęciu cyfrowym
- zastosowania praktyczne: segmentacja obrazu (podział obrazu na części)
- algorytm: detektor krawędzi Canny'ego
- kryteria oceny: dokładność rozpoznawania krawędzi, fałszywe alarmy, szybkość działania
- autorskie przykłady: zastosowanie metody do własnych zdjęć

{panel end}

Korzystając z narzędzia ze wskazanej wyżej strony internetowej, sprawdź efekt działania detektora dla różnych obiektów czy obrazów, jakie umieścisz w polu widzenia kamery.
Zachowaj wybrane obrazy (zrzuty ekranu), jako przykład eksperymentowania z detektorem.

- Czy system wykrył wszystkie krawędzie? Dlaczego niektórych nie wykrył? Czy niektórze krawędzie zostały błędnie zlokalizowane? Dlaczego? Jak sądzisz?
- Czy na efektywność działania wykrywacza ma wpływ oświetlenie (jasność) pomieszczenia?
- Czy system pozwala wykryć granicę między obszarami o dwóch różnych kolorach? Czy kolory muszą się bardzo różnić, aby system działał poprawnie?
- Czy działanie systemu zależy od rodzaju obiektu umieszczonego przed kamerą?
- Jak system radzi sobie z wykrywaniem krawędzi na kartce tekstu?

## Podsumowanie
Dziedzina grafiki komputerowej określana jako rozpoznawanie obrazów szybko się rozwija.

Not only is the resolution of cameras increasing, but they are more sensitive for low light conditions, have less noise, can operate in infra-red (useful for detecting distances), and are getting very cheap so that it's reasonable to use multiple cameras, perhaps to give different angles or to get stereo vision.

Zwiększają się możliwości teczniczne aparatów cyfrowych: rozdzielczość, czułość (światłoczułość), mniej szumu, działanie w podczerwieni (użyteczne dla wykrywania odległości między obiektami), a jednocześnie spadają ceny. W konsekwencji powszechne staje się np. użytkowanie wielu kamer jednocześnie, umieszczonych pod różnymi kątami aby otrzymać widzenie stereoskopowe.

Trzeba podkreślić, że fundamentalne koncepcje tej dziedziny wymyślone zostały już jakiś czas temu; na przykład pierwszy algorytm segmentacji (podziału na części) były zaproponowane w roku 1967, a pierwszy cyfrowy aparat fotograficzny zbudowano w 1975 roku (o rozmiarach obrazu 100 x 100 pikseli).

(W przyszłość rozdział zostanie uzupełniony.)

## Do dalszej lektury

- [https://en.wikipedia.org/wiki/Computer_vision](https://en.wikipedia.org/wiki/Computer_vision)
- [https://en.wikipedia.org/wiki/Mri](https://en.wikipedia.org/wiki/Mri)
- [http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html](http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html)
- [http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html](http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html)
