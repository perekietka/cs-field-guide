# Kodowanie - Kompresja

## Z lotu ptaka

Kompresja danych pozwala zredukować ilość miejsca potrzebną do zapisu plików. Jeżeli możesz zmniejszyć o połowę rozmiar pliku, to oznacza, że możesz przechowywać dwa razy więcej plików przy tych samych kosztach, lub możesz ściągać pliki dwa razy szybciej (płacąc dwa razy mniej za transfer).
Pomimo tego, iż dyski twarde zwiększają objętość oraz wysoka przepustowość łączy staje się powszechna, to nadal dobrze jest osiągnąć tą samą wartość pracując na mniejszym, skompresowanym pliku.
Dla dużych magazynów danych, takich jakie posiadają Google lub Facebook, zmniejszenie o połowę przestrzeni potrzebnej do zapisu oznacza olbrzymie oszczędności w przestrzeni dyskowej, mocy obliczeniowej, a w konsekwencji  oszczędności w zużyciu energii, chłodzeniu oraz niepożądanym wpływie na środowisko.

Częste formy kompresji będące aktualnie w użyciu to JPEG (dla zdjęć), MP3 (dla plików audio), MPEG (dla wideo w tym DVD), oraz ZIP (dla dowolnych typów danych).
Przykładowo, metoda kompresji JPEG redukuje rozmiar zdjęcia do jednej dziesiątej lub mniejszej części początkowego rozmiaru, co oznacza, iż aparat może przechowywać 10 razy więcej zdjęć, a obrazki w sieci mogą być ściągane 10 razy szybciej.

Na czym polega haczyk? Okazuje się, że może być problem z jakością danych - np. mocno skompresowany JPEG może nie być tak ostry jak nieskompresowany oryginał. Poza tym, kompresowanie i dekompresowanie wymaga mocy obliczeniowej procesora. W większości przypadków ten narzut się jednak opłaca.

{interactive name="compression-comparer" type="in-page"}

W tym rozdziale przyjrzymy się temu jak można uzyskać kompresje, jakie są korzyści i jakie koszty związane z używaniem skompresowanych danych. Będzie to przydatne podczas podejmowania decyzji, o tym czy opłaca się kompresować dane.

Zaczniemy od prostego przykłady – kodowania długości serii (RLE od ang. Run Length Encoding) – które daje pewien wgląd w zalety i wady kompresji.

{panel type="teacher-note" summary="??Locked in activity"}
Przykładem intrygującego zadania związanego z kompresją jest ["locked-in" activity](http://www.cs4fn.org/lockedin.html) z CS4FN.
W tym zadaniu uczniowie symulują pisanie tekstu metodą używaną przez Jean’a-Dominique’a Bauby, który był całkowicie sparaliżowany i mógł poruszać jedynie powieką. Przy pomocy prostego binarnego interfejsu (miga lub nie miga) był w stanie podyktować całą książkę. Warto dobrać uczniów w pary i kazać im spróbować porozumiewać się jedynie mrugając. Zadanie to spowoduje wiele pytań o to jak robić to w najkrótszym czasie i przy najmniejszym wysiłku. Oczywiście, w pierwszym kroku będą musieli ustalić jak przekazać jakąkolwiek treść w ten sposób.
{panel end}


## Kodowanie Długości Serii

{video url="https://www.youtube.com/embed/uaV2RuAJTjQ?rel=0"}

Kodowanie długości serii (RLE od ang. Run Length Encoding) nie jest techniką często używaną współcześnie, ale jest nadaje się świetnie jako wprowadzenie do problemów związanych z kompresją.

{panel type="teacher-note" summary="Kto korzysta z kodowania długości serii?"}
[Kodowanie długości serii](https://en.wikipedia.org/wiki/Run-length_encoding) było w powszechnym użyciu kiedy normą były czarno-białe obrazy.
To właśnie ten typ kompresji umożliwił realizację urządzenia jakim był Fax, również dzięki unstandardowieniu 1980 roku.
Piksele w przesyłanym faksem obrazie był jedynie czarne lub białe, charakteryzowały się przeważnie długimi ciągami białych pikseli na marginesach, co sprawiało, że RLE było wyjątkowo skuteczne.
Poza tym metoda ta była bardzo prosta, co było ważne w roku 1980, gdyż pozwoliło znacznie obniżyć koszt elektroniki w urządzeniu.

Kodowanie długości serii jest nadal używane jako część kompresji JPEG, jednakże nie do kodowanie ciągu pikseli (w fotografii rzadko występują ciągi pikseli o dokładnie takim samym kolorze).

Wprowadziliśmy RLE gdyż jest praktycznym podejściem do kompresji, i co ważniejsze pokazuje kluczowe zalety i problemy związane z kompresją.
{panel end}


Wyobraźmy sobie, że mamy do czynienia z zamieszczonym poniżej prostym obrazkiem.

{image filename="pixel-diamond.png" alt="Kształt diamentu (rombu) stworzony z pikseli"}

Komputer może w prosty sposób zapisać taki obrazek stosując format, w którym ‘0’ oznacza piksel w kolorze białym, a ‘1’ piksel w kolorze czarnym (jest to “mapa bitowa”, gdyż przypisaliśmy piksele wartościom bitów). Używając tej metody powyższy obrazek będzie reprezentowany w następujący sposób:

```
011000010000110
100000111000001
000001111100000
000011111110000
000111111111000
001111101111100
011111000111110
111110000011111
011111000111110
001111101111100
000111111111000
000011111110000
000001111100000
100000111000001
011000010000110
```

{comment}
Interactive to make
low priority; interactive for images. If we were going to put in the interactive that takes the 1’s and 0’s and converts it into an image for the students, I’d want to put that in here. This would mostly be a convenience thing that allows students to easily see what an image looks like. We would also provide an interactive that can take a number representation and show the image for that. We do NOT want to provide a tool that converts between the 2; we want students to do the converting by hand. The tool will allow them to see if the images they got are the same though.
{comment end}

{panel type="curiosity" summary="Format pliku PBM"}
Istnieje format obrazu, który wykorzystuje prostą jeden-symbol-na-piksel reprezentację opisaną powyżej. Ten format nazywa się “przenośny format mapy bitowej” PBM (ang. portable bitmap format).
Pliki PBM są zapisywane z rozszerzeniem “.pbm”, i zawierają prosty nagłówek, za którym zapisane są dane obrazu.
Dane w tym pliku można obejrzeć otwierając go w edytorze tekstowym, podobnie jak plik .txt., a sam obrazek możemy zobaczyć otwierając w programie graficznym, który wspiera format PBM
(format ten nie jest szeroko wspierany, ale istnieje kilka programów go obsługujących)
Plik pbm dla obrazu zawierającego wcześniej przywołany kształt diamentu wygląda następująco:

```
P1
15 15
011000010000110
100000111000001
000001111100000
000011111110000
000111111111000
001111101111100
011111000111110
111110000011111
011111000111110
001111101111100
000111111111000
000011111110000
000001111100000
100000111000001
011000010000110
```

Pierwsze dwie linie stanowią nagłówek. Pierwsza linia określa format danych w pliku (P1 oznacza, że plik zawiera znaki zer i jedynek w formacie ASCII). Druga linia wyznacza szerokość i wysokość obrazu w pikselach. Dzięki temu komputer zna wymiary obrazu nawet wtedy gdyby brakowało znaków nowej linii.
Resztę danych stanowi po prostu obraz (patrz powyżej).
Można po prostu skopiować i wkleić tą reprezentację (wraz z nagłówkiem) do pliku tekstowego, a następnie zapisać z rozszerzeniem .pbm.
Jeśli posiadasz program, który obsługuje pliki PBM, może zobaczyć obraz. Mógłbyś również napisać program, który będzie pozwalał tworzyć tego typu pliki oraz wyświetlać je jako obrazy.

Z tego względu, iż cyfry są reprezentowane przez znaki ASCII, nie jest to najbardziej efektywny sposób zapisu. Jednakże pozwala nam przeczytać zawartość pliku.
Istnieją inne warianty tego formatu, które zapisują kolory w pojedynczych bitach zamiast w znakach ASCII, oraz takie, które pozwalają zapisywać odcienie szarości lub prawdziwe kolory. Więcej [informacji na temat tego formatu dostępnych jest na Wikipedii](https://en.wikipedia.org/wiki/Netpbm_format).
{panel end}

Kluczowym pytaniem w przypadku kompresji jest czy możemy zapisać ten sam obraz przy pomocy mniejszej ilości bitów i nadal być w stanie odtworzyć oryginalny obraz.

Okazuje się, że możemy, Jest wiele sposobów na osiągnięcie tego celu w tym podrozdziale ?? skupimy się na metodzie zwanej *kodowaniem długości serii*.

Wyobraź sobie, że masz za zadanie przeczytać powyższe bity komuś, kto z kolei ma jest zapisać… po pewnej chwili będziesz mówił “pięć zer” zamiast “zero zero zero zero zero”. To usprawnienie jest podstawą kodowania długości serii (RLE), które pozwala zaoszczędzić przestrzeń potrzebną do przechowywania cyfrowych obrazów. W kodowaniu długości serii zastępujemy każdy wiersz liczbą kolejnych pikseli tego samego koloru, *zawsze zaczynając od liczby pikseli białych*. Na przykład, pierwszy wiersz zawiera jeden biały, dwa czarne, cztery białe, jedne czarny, cztery białe, dwa czarne i jeden biały.

```
011000010000110
```

Może być przedstawione w następujący sposób.

```
1, 2, 4, 1, 4, 2, 1
```

Dla drugiego wiersza, który zaczyna się pikselem czarnym, musimy otwarcie powiedzieć, że jest zero białych na początku.

```
100000111000001
```

```
0, 1, 5, 3, 5, 1
```

Może to wydawać się dziwne, że musimy podać zawsze ilość białych na początku, która w tym wypadku wynosi zero. Powodem tego jest fakt, iż komputer potrzebuje ścisłych reguł odnośnie tego, od którego koloru pikseli zaczynać.

Trzeci wiersz zawiera pięć białych, pięć czarnych, oraz pięć białych.

```
000001111100000
```

To jest kodowane jako:

```
5, 5, 5
```

Zatem mamy następującą reprezentacją dla pierwszych trzech wierszy pikseli obrazu.

```
1, 2, 4, 1, 4, 2, 1
0, 1, 5, 3, 5, 1
5, 5, 5
```

Łatwo mona się domyśleć jak będą wyglądać kolejne wiersze w tym systemie reprezentacji.

{panel type="spoiler" summary="Reprezentacja pozostałych wierszy"}
Pozostałe wiersze to

```
4, 7, 4
3, 9, 3
2, 5, 1, 5, 2
1, 5, 3, 5, 1
0, 5, 5, 5
1, 5, 3, 5, 1
2, 5, 1, 5, 2
3, 9, 3
4, 7, 4
5, 5, 5
0, 1, 5, 3, 5, 1
1, 2, 4, 1, 4, 2, 1
```
{panel end}

{panel type="curiosity" summary="Run Length Encoding in the CS Unplugged show"}
W poniższym materiale wideo z ??Computer Science Unplugged show?? zakodowany przy pomocy długości serii obraz jest odkodowany i zaprezentowany przez bardzo duże piksele (drukarką jest farba w sprayu!).

{video url="https://www.youtube.com/watch?v=VsjpPs146d8"}
{panel end}

### Konwertowanie Kodu Długości Serii do oryginalnej reprezentacji

Aby upewnić się, że możemy odwrócić proces kompresji, spróbuj znaleźć oryginalną reprezentację (zera i jedynki) skompresowanego obrazu.

```
4, 11, 3
4, 9, 2, 1, 2
4, 9, 2, 1, 2
4, 11, 3
4, 9, 5
4, 9, 5
5, 7, 6
0, 17, 1
1, 15, 2
```

Co zawiera obraz? Z jak wielu pikseli się składa? Ile liczb użyto do reprezentacji tego obrazu?

{panel type="spoiler" summary="Odpowiedź dla powyższego obrazu"}
Przykładowy obrazek pochodzi z [??CS Unplugged image representation activity??](http://csunplugged.org/image-representation), a rozwiązanie jest dostępne w treści zadanie (jest nim filiżanka i tależyk).
{panel end}

Poniższy ??interactive?? pozwala na dalsze eksperymentowanie z Kodowaniem Długości Serii.

{interactive name="run-length-encoding" type="whole-page" text="??Run Length Encoding interactive??s"}

### Analiza Kodowanie długości serii

Ile przestrzeni zaoszczędziliśmy wykorzystując alternatywną reprezentację, i jak możemy to zmierzyć? Możemy w prosty sposób policzyć ile razy musieliśmy nacisnąć przycisk na klawiaturze zapisując każdą z reprezentacji, możemy więc sobie wyobrazić, że każdy bit jest reprezentowany przez literę oraz, że każda cyfra kodu RLE oraz każdy przecinek wymaga również znaku przy zapisie (jest oszacowanie “z grubsza” przestrzeni, ale wystarczy na początek).

Aby opisać obraz w postaci nieskompresowanej potrzebnych jest 225 cyfr (zer i jedynek). Policz ile potrzeba przecinków i cyfr (pomiń spacje i znaki nowej linii) w nowej reprezentacji. Sumą jest liczba znaków potrzebnych do zapisania skompresowanej reprezentacji (dla ułatwienia liczba znaków w trzech pierwszych wierszach wynosi 29).

Przy założeniu, że nowa reprezentacja jest prawidłowa oraz, że obliczenia odbyły się prawidłowo, powinieneś otrzymać wynik 119 znaków (sprawdź, czy wszystko się zgadza). Oznacza to, że skompresowana postać wymaga jedynie 53% znaków reprezentacji oryginalnej (wynika to z proporcji 119/225). To znacząca redukcja w ilości przestrzeni potrzebnej do zapisania obrazu --- to prawie połowa rozmiaru. Nowa reprezentacja jest skompresowaną postacią poprzedniej.

{panel type="curiosity" summary="Kodowanie długości serii w praktyce"}
W praktyce metoda ta (z pewnymi modyfikacjami) może być użyta do osiągnięcia kompresji na poziomie 15% oryginalnego rozmiaru. W prawdziwych systemach tylko jeden bit jest wykorzystywany do przechowywania wartości czarne-białe (w przeciwieństwie do jednego znaku z naszych obliczeń).
Jednakże, długości kodowanych serii są również przechowywane bardziej efektywnie, również przy pomocy bitów, których stosunkowo krótkie ciągi mogą reprezentować liczby.
Wykorzystywane ciągi bitów są tworzone przy pomocy techniki zwanej kodowaniem Huffmana, lecz zagadnienie to wykracza poza zakres tego materiału.
{panel end}


### Jakie jest praktyczne zastosowanie Kodowania Długości Serii

Współcześnie głównym zastosowaniem dla skanowanych czarno-białych obrazów są faksy, które wykorzystują to podejście do kompresji. Jednym z powodów, dla których działa to tak skutecznie dla skanowanych stron dokumentów jest fakt, iż w tym przypadku liczba kolejnych białych pikseli jest olbrzymia. Typowa strona przesyłana faksem ma 200 pikseli szerokości, więc zastąpienie tych 200 bitów liczbą jest znaczącą oszczędnością. Liczbę możemy wyrazić przy pomocy zaledwie kilku bitów. Choć może się zdarzyć na stronie, że liczą zastępujemy niewiele kolejnych pikseli, to i tak w ostatecznym rozrachunku oszczędności są znaczące. W praktyce faksy które nie korzystają z kompresji przesyłają dokumenty 7 razy wolniej.

{panel type="project" summary="Zastosuj Kodowanie Długości Serii"}
Teraz, gdy już znasz kodowanie długości serii możesz sam stworzyć obraz czarno-biały, a następnie go skompresować, oraz zdekompresować obraz otrzymany od kogoś innego.

Zacznij od narysowania obrazku przy pomocy zer i jedynek. (Upewnij się, że jest prostokątny, tzn. wszystkie wiersze mają tą samą długość.) Możesz go narysować na papierze lub przygotować go na komputerze (korzystaj z czcionki o stałej szerokości, w przeciwnym wypadku może to okazać się frustrujące i kłopotliwe!) Ułatwieniem może być skorzystanie z kartki w kratkę (takiej jak w zeszycie do matematyki) i zakreślenie kratek mających być czarnymi pikselami, i pozostawienie pustych kratek jako pikseli białych. Po zakończeniu tej czynności możesz spisać zera i jedynki reprezentujące obraz.

Stwórz skompresowaną reprezentację twojego obrazu stosując metodę kodowania długości serii, tzn. długości serii oddzielone przecinkami jak zostało przestawione powyżej.

Przekaż kopię *skompresowanej reprezentacji* (długości serii, nie oryginalną reprezentację zerojedynkową) koledze oraz wytłumacz na czym polegała kompresja. Poproś ich o narysowanie obrazu na kartce w kratkę. Następnie porównaj otrzymany obrazek z twoim oryginałem.

Wyobraź sobie, że ty i twój kolega oboje jesteście komputerami. Wykonując powyższe zadanie pokazałeś, że obrazy przy wykorzystaniu tej kompresji mogą zostać skompresowane na jednym komputerze i zdekompresowane na innym, tak długo jak istnieje uzgodniony standard (np. to, że każda linia zaczyna się od liczby białych pikseli).
W przypadku algorytmów kompresji bardzo istotne jest trzymanie się standardów tak, aby po skompresowaniu na jednym komputerze możliwa była dekompresja na innym;
przykładowo, utwory muzyczne zapisywane są w formacie “mp3”, aby po pobraniu z sieci mogły być odtworzone przez szeroką gamę urządzeń.
{panel end}


### Stratna vs bezstratna kompresja

O *kompresji bezstratnej* mówimy jeżeli skompresowana reprezentacja może zostać przekonwertowana podczas dekompresji do dokładnie takiej samej postaci jak reprezentacja oryginalna, innymi słowy żadna informacja nie została stracona podczas kompresji, i proces ten może być w pełni odwrócony.

Nie wszystkie algorytmy kompresji są jednak bezstratne. Dla niektórych typów plików takich jak zdjęcia, utwory muzyczne i materiały wideo, możemy poświęcić nieco jakości (ilości informacji o zdjęciu) jeśli pozwoli to zmniejszyć znacząco rozmiar pliku. Zmniejszenie rozmiaru plików może mieć olbrzymie znaczenie przy pobieraniu plików tak dużych jak pliki wideo, które mogą zbyt duże, aby dało się je ściągnąć! Te metody kompresji nazywa się *stratnymi*. Jeśli tracimy informacje w procesie kompresji, to niemożliwe jest odtworzenie dokładnie takiej samej postaci, jaką miał plik przed kompresją. Jednocześnie osoba, która ogląda plik wideo lub słucha muzyki może zaakceptować nieco pogorszoną jakość jeśli pliki są względnie małe. W dalszej części tego rozdziału zbadamy jakie efekty na obraz i dźwięk może mieć stratna kompresja.

Co ciekawe może się wyjątkowo zdarzyć, że skompresowany *stratnie* plik będzie miał większy rozmiar niż nieskompresowany! Co więcej naukowcy zajmujący się kompresją udowodnili, iż niemożliwe jest stworzenie kompresji stratnej, która zmniejsza każdy plik. W zdecydowanej większości przypadków nie jest problemem, gdyż stratne metody kompresji dostosowane są do pewnych rodzajów danych, posiadających pewną charakterystykę, dla których nieskuteczne kompresja jest wysoce nieprawdopodobna.

{panel type="challenge" summary="Najlepsze i najgorsze przypadki kodowanie długości serii"}
Jaki obraz będzie miał największy stopień kompresji przy kodowaniu długości serii (chodzi o obraz, którego rozmiar po skompresowaniu będzie najmniejszy w stosunku do rozmiaru początkowego)? Jest to przypadek, w którym wydajność algorytmu jest najwyższa.

Kiedy kompresja jest najgorsza? Czy potrafisz znaleźć obraz, który ma *większą* reprezentację skompresowaną? (Pamiętaj o przecinkach, którymi oddzielamy długości serii!) Jest to przypadek, w którym wydajność algorytmu jest najgorsza.
{panel end}

{panel type="spoiler" summary="Rozwiązanie zadania”}
Najlepszy przypadek jest wtedy, gdy obraz jest całkowicie biały (wystarczy jedna liczba na wiersz).
Najgorszy przypadek ma miejsce gdy na zmianę występują piksele białe i czarne, i potrzebujemy jednej liczby dla każdego piksela.
?? Tu jest chyba błąd bo plik będzie 2x większy dzięki przecinkom. In fact, in this case the size of the compressed file is likely to be a little larger than the original one because the numbers are likely to take more than one bit to store.??
W rzeczywistości dane są reprezentowane nieco inaczej, lecz problemy są bardzo podobne.
{panel end}

{panel type="curiosity" summary="Kompresja może powiększać pliki"}
W najgorszym przypadku (na zmianę piksele białe i czarne) kodowanie długości serii da nam plik skompresowany o rozmiarze większym niż plik oryginalny!
Jak został wspomniane wcześniej, *każdy* bezstratny algorytm kompresji, który przynajmniej jeden plik zmniejsza musi mieć kilka plików, które powiększ --- nie jest
matematycznie możliwe, aby stworzyć algorytm kompresji, który zmniejsza każdy plik. Stwierdzenie to nie dotyczy metod stratnych.
Jako trywialny przykład posłuży nam pewna kompresja plików z 3-bitowych do 2-bitowych.
Ile jest plików 3-bitowych? (Jest 8.) Ile jest plików 2-bitowych (Jest 4.) Czy widzisz problem? Mamy 8 plików, które możemy chcieć skompresować, ale jednocześnie tylko 4 sposoby na ich reprezentację. Zatem, niektóre z nich będą miały taką samą reprezentacji, a przez to nie mogą zostać odkodowane dokładnie.

Na przestrzeni lat było kilka oszustw opartych na twierdzeniach o bezstratnej metodzie kompresji, która kompresuje każdy plik.
Może to być prawdą tylko wtedy, gdy metoda jest stratna (traci informacje); wszystkie metody bezstratne muszą powiększać niektóre pliki.
Dobrze byłoby mieć metodę, która kompresuje wszystkie pliki bez strat; można by wtedy skompresować duży plik, a następnie zastosować kompresję do skompresowanego pliku i zmniejszyć go ponownie, powtarzając aż do uzyskanie jednego bajtu --- lub jednego bitu!
Niestety nie jest to możliwe.
{panel end}

## Kompresja obrazu metodą JPEG

Obrazy mogą zajmować dużo miejsca, i najczęściej obrazy są  przechowywane na komputerze w postaci skompresowanej. Pozwala to zaoszczędzić miejsce na dysku.
Z tego względu, iż przechowujemy dużo obrazków (zwłaszcza zdjęć), nie ma potrzeby przechowywania obrazu dokładnie tak, jak wyglądał on pierwotnie. Wynika to z faktu, iż zawiera on więcej szczegółów niż ktokolwiek może zobaczyć.
W rezultacie możemy zaoszczędzić na wykorzystanej przestrzeni dyskowej, zwłaszcza jeśli utracone szczegółu są trudno dostrzegalne dla ludzkiego oka.
Ten rodzaj kompresji nazywa się kompresją stratną.
Istnieją inne sytuacje, w których obrazy muszą być przechowywane dokładnie takiej samej postaci jak oryginał, na przykład w przypadku skanów medycznych lub przetwarzania zdjęć o bardzo wysokiej jakości. W takich przypadkach stosuje się metody bezstratne lub obrazy nie są w ogóle kompresowane (np. w formacie RAW na aparatach).

W podrozdziale o reprezentacji danych sprawdziliśmy, jak można zmniejszyć rozmiar pliku obrazu, używając mniejszej liczby bitów do opisania koloru każdego piksela.
Jednak metody kompresji obrazu, takie jak JPEG, wykorzystują wzorce w obrazie, aby zmniejszyć przestrzeń potrzebną do jego przedstawienia, bez niekorzystnego wpływu na obraz.

Poniższe trzy obrazy pokazują różnicę między zmniejszeniem głębi bitowej a użyciem wyspecjalizowanego systemu kompresji obrazu. Obraz po lewej stronie jest oryginałem, który używa 24 bity na piksel. Środkowy obraz został skompresowany do jednej trzeciej oryginalnego rozmiaru za pomocą JPEG; pomimo, iż jest to "stratna" wersja oryginału, różnica jest widoczna. Obraz po prawej stronie ma liczbę kolorów zmniejszoną do 256, a więc jest używa 8 bitów na piksel zamiast 24, co oznacza, że ​​zajmuje jedną trzecią pierwotnego rozmiaru. Mimo że stracił tyle samo bitów, usunięte informacje miały znacznie większy wpływ na to, jak wygląda. Na tym polega zaleta formatu JPEG: usuwa informacje z obrazu, które nie mają dużego wpływu na postrzeganą jakość. Ponadto w przypadku formatu JPEG można ustalić kompromis między jakością a rozmiarem pliku.

Zmniejszenie liczby bitów (głębia kolorów) jest na tyle istotną zmiana, że nie uważamy tego za metodę kompresji, lecz po prostu za reprezentację niskiej jakości. Metody kompresji obrazu, takie jak JPEG, GIF i PNG, zostały zaprojektowane tak, aby wykorzystać wzorce w obrazie, w celu uzyskania znacznej redukcji rozmiaru pliku bez znaczącej utraty jakości.

{image filename="compression-comparison.png"}

{comment}
.. xtcb low priority: these are all jpgs of the originals; consider replacing them with actual originals (as long as the browser can render them all).
.. ajb these images seem to appear in the wrong order to what is described for me… The middle one and left one should be swapped around?
{comment end}

Na przykład poniższy obraz pokazuje powiększone pikseli, które są fragmentem oka z powyższego obrazu (wysokiej jakości).

{image filename="zoomed-eye.png"}

Zauważmy, że kolory sąsiednich pikseli są często bardzo podobne, nawet w tej części obrazu, która ma dużo szczegółów. Na przykład piksele pokazane w czerwonym polu poniżej zmieniają się stopniowo z bardzo ciemnego na bardzo jasny.

{image filename="zoomed-eye-highlighted.png"}

Kodowanie długości serii nie działa w tym przypadku. Można by skorzystać z wariantu, który określa kolor piksela, a następnie mówi, ile kolejnych pikseli ma ten sam kolor. Chociaż większość sąsiednich pikseli jest prawie taka sama, to szanse na to, że są identyczne są bardzo niskie, a serie identycznych kolorów prawie nie występują.

Istnieje jednak sposób, aby wykorzystać stopniowo zmieniające się kolory. W przypadku pikseli w czerwonym polu powyżej, możesz wygenerować przybliżoną wersję tych kolorów, określając tylko pierwszy i ostatni w serii. Na tej podstawie komputer będzie obliczać pośrednie, zakładając, że kolor zmienia się stopniowo. Zamiast zapisywania 5-pikselowych wartości potrzebne są tylko 2, aby oglądający nie zauważył żadnej różnicy. Byłoby to *stratne*, ponieważ nie można dokładnie odtworzyć oryginału, ale wystarczająco dobre dla wielu zastosowań i pozwalające zaoszczędzić dużo miejsca.

{panel type="jargon-buster" summary="Interpolacja"}
{glossary-definition term="Interpolacja" definition="Wyliczenie wartości pośrednich pomiędzy pewnymi wartościami brzegowymi;
na przykład, jeśli sekwencja 5 liczb zaczyna się 3 i kończy 11, możemy wyznaczyć interpolację trzech pośrednich wartości jako: 5, 7, 9."}

Proces zgadywania kolorów pikseli między dwoma, które są znane, jest przykładem
{glossary-link term="interpolation" reference-text="kompresowanie obrazów"}interpolacja{glossary-link end}.
Interpolacja *liniowa* zakłada, że wartości rosną o stałą wielkość pomiędzy dwiema podanymi wartościami. Na przykład, dla pięciu powyższych pikseli załóżmy, że pierwszy piksel ma wartość koloru niebieskiego równą 124, a ostatni ma niebieską wartość 136. W takim przypadku  interpolacja liniowa domyślałaby się, że niebieskie wartości dla tych pośrednich wynoszą 127, 130 i 133, a dzięki temu nie trzeba ich zapisywać i można zaoszczędzić miejsce.
W praktyce stosuje się bardziej złożone podejście do odgadywania pikseli, ale interpolacja liniowa daje dobre wyobrażenie o tym, jak to działa.
{panel end}

System JPEG, który jest szeroko stosowany do zdjęć, wykorzystuje bardziej wyrafinowaną wersję tego pomysłu. Zamiast działać na pięci kolejnych pikselach, tak jak to zrobiliśmy powyżej, działa na bloku o rozmiarze 8 na 8 pikseli. Zamiast szacować wartości za pomocą funkcji liniowej, wykorzystuje kombinacje funkcji cosinus.

{comment}
It would be good have a figure that shows a line of pixels, and the corresponding waveform.
{comment end}

{panel type="curiosity" summary="Czym jest funkcja consinus"}
Funkcja cosinus jest jedną z funkcji trygonometrycznych , która jest często używana do obliczania długości boków trójkąta. Wykres wartość cosinusa od 0 do 180 stopni jest gładką krzywą w przedziale 1 do -1 przypominającą falę. Wariacje tego wykresu można wykorzystać do przybliżenia wartości pikseli przechodzących z jednego koloru do drugiego. Jeśli dodasz falę cosinusową o wyższej częstotliwości z inną, to możesz uzyskać interesujące kształty. Teoretycznie każdy piksel może zostać utworzony przez dodanie różnych fal cosinusowych!

Poniższy wykres pokazuje wartości funkcji {math}\sin(x){math end} oraz {math}\cos(x){math end} dla {math}x{math end} zakresu od 0 do 180 stopni.

{image filename="cosine-graph.png" alt="Wykres krzywych cos(x) i sin(x)"}
{panel end}

{panel type="curiosity" summary="Dodawanie sinusa i cosinusa w celu uzyskania dowolnego kształtu fali"}
Metody JPEGs (i MP3) bazują się na technice, pozwalającej falę dowolnego kształtu przedstawić jako sumę wielu fal sinusoidalnych lub cosinusowych. ??nie wiem jak fachowo nazywać te fale??
Przekształcenie kształtu fali dla bloku pikseli lub próbki muzyki w sumę prostych fal można wykonać za pomocą techniki zwanej [??Fourier transform??](https://en.wikipedia.org/wiki/Fourier_transform), która jest powszechnie wykorzystywana przy przetwarzaniu obrazu.

Możesz poeksperymentować z dodawaniem sinusoid, aby uzyskać inne kształty za pomocą
[udostępniony arkusz kalkulacyjny](files/Adding-Sine-Waves.xls).
W tym arkuszu kalkulacyjnym żółty obszar na pierwszym arkuszu pozwala wybrać, które fale sinusoidalne dodać.
Spróbuj ustawić 4 fale sinusoidalne na częstotliwości, które wynoszą odpowiednio 3, 9, 15 i 21 razy częstotliwości podstawowej ("podstawowa" to najniższa częstotliwość.)
Następnie ustaw "amplitudę" (odpowiednik poziomu głośności) tej czwórki na 0,5, 0,25, 0,125 i 0,0625 (każdy z nich jest równy połowie poprzedniego).
W rezultacie powinieneś uzyskać poniższe cztery sinusoidy:

{image filename="sine-waves.png" alt="Cztery sinusoidy"}

Kiedy powyższe cztery fale są ze sobą dodane, interferują i tworzą kształt, który ma ostrzejsze przejścia:

{image filename="sine-waves-sum.png" alt="Suma czterech sinusoid"}

Okazuje się, że gdyby kontynuować ten wzorzec z większą ilością sinusoid, kształt wynikowy stałby się "falą prostokątną", która nagle przechodzi od wartości maksymalnej do minimum.
Ta pokazana powyżej jest wyboista, gdyż wykorzystaliśmy tylko 4 fale sinusoidalne, aby ją opisać.

To właśnie dzieje się w algorytmie JPEG, jeśli kompresujesz czarno-biały obraz.
"Kolor" pikseli w miarę przesuwania się po obrazie będzie wynosił 0 (czarny) lub pełny poziom intensywności (biały), lecz JPEG będzie przybliżał go za pomocą sumy niewielkiej liczby fal cosinusów (które mają zasadniczo takie same własności jak fale sinusoidalne)
Daje to "przedobrzenia" widoczne na powyższym obrazku; w obrazie JPEG pojawia się jako jasne i ciemne plamy otaczające nagłą zmianę koloru:

{image filename="jpeg-word-zoomed.jpg"}

Możesz eksperymentować z różnymi kombinacjami fal sinusoidalnych uzyskując różne kształty.
Być może trzeba mieć więcej niż cztery, aby uzyskać dobre przybliżenia kształtu, który chcesz osiągnąć; to jest właśnie kompromis, z którym stara sobie radzić algorytm JPEG.
Na drugim arkuszu arkusza kalkulacyjnego zamieszczone zostały pewne sugestie dotyczące parametrów.

Więcej na temat przekształceniach Fouriera możesz się dowiedzieć za pomocą oprogramowania Wolfram Alpha; będzie to wymagało instalacji wtyczki w przeglądarce.
Demonstracje Wolfram obejmują:
[interaktywna demonstracja JPEG](http://demonstrations.wolfram.com/JPEGCompressionAlgorithm/),
[prezentacja związków między sinusoidami a innymi formami falowymi](http://demonstrations.wolfram.com/RecoveringTheFourierCoefficients/), and
[prezentacja tego jak sinusoidy można zsumować, aby otrzymać inne kształty](http://demonstrations.wolfram.com/SumsOfSineWavesWithSeveralStepSizesSawtoothOrSquareApproxima/).

{panel end}

{comment}
.. html5 low priority interactive to add cosine waves to try to match a given waveform e.g. square wave, triangle, random. Select amplitude for various frequencies. I have a spreadsheet that basically does this, could put it in for the meantime - tim
{comment end}

Warto przyjrzeć się z bliska mocno skompresowanemu obrazowi JPEG. Na przykład następujący obraz został bardzo mocno skompresowany przy użyciu JPEG (zajmuje jedynie 1,5% pierwotnego rozmiaru).

{image filename="compressed-jpeg.png"}

Jeśli powiększymy obszar oka, wyraźnie widać bloki 8 x 8 pikseli:

{image filename="compressed-jpeg-zoomed.png"}

Zauważ, iż w każdym bloku występuje bardzo niewielka różnorodność. Na poniższym obrazie blok w czerwonej ramce zmienia się tylko w kierunku pionowym. Prawdopodobnie można go określić podając tylko dwie wartości brzegowe, pozostałe mogę być wyliczone przez dekoder podobnie jak w przykładzie interpolacyjnym. Zielony kwadrat zmienia się tylko w poziomie i podobnie można go wyrazić przy pomocy dwóch wartości brzegowych zamiast 64 wartości. Niebieski blok ma tylko jeden kolor! Żółty blok jest bardziej skomplikowany, ponieważ w tej części obrazu więcej się dzieje. Pojawiają się tu fale cosinusowe. Wartość "fali" zmienia się pionowo, więc można ją przedstawić od lewej do prawej wariacją od ciemnej do jasnej do ciemnej oraz od góry do dołu, głównie od ciemności do jasności. (??tu coś jest zamotane w opisie??) Dzięki temu możemy nadal przechowywać tylko kilka wartości zamiast pełnych 64.

{image filename="compressed-jpeg-zoomed-highlighted.png"}

Pomimo tego, że jakość jest dość niska, to oszczędność w przestrzeni dyskowej jest ogromna - plik JPEG jest 60 razy mniejszy (mógłby zostać pobrany 60 razy szybciej). Obrazy JPEG o wyższej jakości przechowują więcej szczegółów dla każdego bloku 8 na 8, co sprawia, że odwzorowują wierniej oryginalny obraz. Zajmują też więcej miejsca, ponieważ zawierają informację o większej liczbie szczegółów. Możesz samemu przetestować jego działanie i kompromis pomiędzy jakością a stopniem kompresji. Większość edytorów graficznych pozwala wybrać jakość (stopień kompresji) podczas zapisuwania obrazu jako JPEG.

{comment}
low priority : interactive that could load a photo, zoom in on pixels, and change it to different qualities of jpg coding
{comment end}

{panel type="jargon-buster" summary="Skąd pochodzi nazwa JPEG?"}
Nazwa "JPEG" jest skrótem od "Joint Photographic Experts Group", komitetu utworzonego w latach 80. w celu wypracowania standardów umożliwiających przechwytywanie fotografii cyfrowych i wyświetlanie ich na różnych urządzeniach. Ponieważ niektóre systemy operacyjne ograniczają rozszerzenia plików do trzech znaków, pliki skompresowane JPEG mają rozszerzenie ".jpg".
{panel end}

{panel type="curiosity" summary="Więcej na temat fal cosinusowych"}
Fale cosinusowe wykorzystywane w metodzie JPEG oparte są na "Dyskretnej Transformacji Cosinusowej". "Dyskretna" oznacza, że wartości są ze skończonego zbioru - nie jest ciągłą, dla którym może wystąpić dowolna wartość. Fale w JPEG są reprezentowane jako wartości dla 8 x 8  punktów (dla kodowanego bloku), a każda z tych wartości pochodzi z ograniczonego przedziału (binarne liczby całkowite), nie mogą przyjąć dowolnej wartości.
{panel end}

Ważna kwestią jest to jak metoda JPEG, zaprojektowana do przedstawiania obrazów o płynnie zmieniających się kolorach, radzą sobie, gdy kolory zmieniają się nagle?
W takim przypadku należy zapisać wiele wartości, aby można było dodać wiele fal i uzyskać nagłą zmianę koloru, a tym samym ostrą krawędź.
Można to sobie wyobrazić jako fale cosinusowe powodujące przesadzone zmiany, wytwarzające artefakty, takie jak te na obrazie poniżej, gdzie krawędzie są zabrudzone.

{image filename="jpeg-word.jpg"}

Oryginał posiadał ostre krawędzie, ale na powiększeniu obrazu JPEG widać, że nie tylko krawędzie są stopniowe, ale niektóre ciemniejsze piksele pojawiają się dalej również na białym tle, wyglądając trochę jak cienie lub echa.

{image filename="jpeg-word-zoomed.jpg"}

Z tego względu JPEG jest używany do zdjęć i naturalnych obrazów, natomiast inne metody kompresji  (takie jak
GIF i PNG, które poznamy w dalszej części) będą działać lepiej w przypadku sztucznych obrazów, takich jak
ten.

{comment}
.. xjrm low priority create an image like the one in this link, with one, two three waveforms added http://mathworld.wolfram.com/images/eps-gif/FourierSeriesSquareWave_800.gif (then Tim to add some text)

.. xhtml5 interactive (medium priority): allow user to switch on and off the 64 basis vectors (https://en.wikipedia.org/wiki/File:Dctjpeg.png) and see the combined result

.. http://www.cs4fn.org/films/jpegit.php
{comment end}

{comment}
## Image compression using GIF and PNG

appearing soon!

.. http://www.cs4fn.org/films/jpegit.php CS4FN on Jpeg and

.. Students should discuss the basics of how one of them works (Not entirely sure how to approach this without it becoming a paraphrase, need to think about it). I’m thinking that an explanation of what it means for a compression algorithm to be lossy is important here.

.. images from compression lectures chapter 10

.. GIF and PNG use a palette; GIF strictly 256 bits - lossless, except GIF reduces colour depth; use LZ - see general purpose
.. best for images that don't have a big variety of colour e.g. cartoons, icons . These sorts of images don't work so well with JPEG compression because it isn't so good at sharp edges.
.. choosing right compression method is important

{comment end}


## Kompresja ogólnego przeznaczenia

Metody kompresji ogólnego przeznaczenia muszą być bezstratne, ponieważ nie można założyć, że użytkownik nie będzie akceptował zmiany danych. Najbardziej popularne algorytmy tego typu (takie jak ZIP, gzip i rar) oparte są na metodzie zwanej "kodowaniem Ziv-Lempel", wymyślonej przez Jacoba Ziva i Abrahama Lempela w latach siedemdziesiątych.

Przyjrzymy się temu zagadnieniu na przykładzie pliku tekstowego.
Główną ideą kodowania Ziv-Lempel zastępowanie sekwencji znaków często występujących w plikach (na przykład sekwencja znaków "obraz" pojawia się często w tym rozdziale) odnośnikami do miejsca, w którym ostatnio się pojawił. Pod warunkiem, że odniesienie jest mniejsze niż zastępowana fraza, oszczędzamy miejsce. Zwykle systemy oparte na tym podejściu można wykorzystać do zredukowania plików tekstowych do zaledwie jednej czwartej ich oryginalnego rozmiaru, co jest prawie tak dobre, jak każda znana metoda kompresowania tekstu.

Poniższy ??interactive?? pozwala się zapoznać z tą ideą.
Możesz kliknąć pole, aby zobaczyć dokąd prowadzi odnośnik, a następnie wpisać odpowiednie znaki i w rezultacie odkodować tekst.
Co się stanie, jeśli odniesienie wskazuje na inne odniesienie?
Dopóki dekodujesz je od początku, informacje będą dostępne, zanim będziesz ich potrzebować.

{comment}
.. xhtml5 Eventually this could use a parameter so there's one version with no tabs, and a later one with them.
{comment end}

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/COMPRESSION/LWZ/public_html/index.html" text="View compression interactive"}

{comment}
.. xjrm (or Rhem): pasting text in that is too big causes it to be rejected. It would be nicer if the pasted text is truncated to the maximum length.
{comment end}

Możesz wprowadzić własny tekst, klikając zakładkę "Tekst".
Możesz również wkleić jakiś własny tekst, aby sprawdzić ile znaków można zastąpić odniesieniami.

Odnośniki są w rzeczywistości dwiema liczbami: pierwsza określa, ile znaków wcześniej zaczyna się sekwencja, a druga jaka jest jej długość.
Każde takie odwołanie zwykle zajmuje około jednego lub dwóch znaków, więc oszczędzamy miejsce jeżeli zastępowane są co najmniej dwa znaki.
Opcje w powyższej ??interactive?? pozwalają wymusić, aby zastępowane sekwencje miały długość większą lub równą 2.
Oczywiście bierzemy pod uwagę wszystkie znaki, a nie tylko litery alfabetu, więc system kompresji może również odnosić się do spacji między wyrazami.
W praktyce jedną z najczęściej występujących sekwencji jest kropka, po której następuje spacja.

To podejście sprawdzi się również w przypadku obrazów czarno-białych, ponieważ sekwencje takie jak "10 białych pikseli" prawdopodobnie pojawiły się wcześniej.
Oto niektóre fragmenty z wcześniejszego przykładu; możesz wkleić je do powyższego ??interactive??, aby zobaczyć, jak działa kompresja.

```
011000010000110
100000111000001
000001111100000
000011111110000
000111111111000
001111101111100
011111000111110
111110000011111
```

Powyższy przykład jest dobrą deomnstracją tego, co dzieje się z obrazami podczas zapisu do formatu GIF lub PNG; wartości pikseli są kompresowane za pomocą algorytmu Ziv-Lempel, który działa dobrze, jeśli wiele kolejnych pikseli ma ten sam kolor. Ale działa bardzo słabo w przypadku zdjęć, w których mało prawdopodobne jest powtórzenie wzorców pikseli.

{comment}
.. xtcb extra for experts: compress "aaaaaaaaaa". how can it decode?

.. xtcb  Project
.. Students should try an algorithm [zip, gzip etc.] on several different text files, image files, sound files, and video files.
.. What would happen if text compression was lossy? (I think this should be a part of their merit discussion)
{comment end}

{panel type="teacher-note" summary="Unplugged activity on Ziv-Lempel approach"}
The [CS Unplugged site has activities and information about the Ziv-Lempel approach](http://csunplugged.org/text-compression),
and the ["Computing Science Inside" site also has an activity based on this method](https://web.archive.org/web/20150311225517/http://csi.dcs.gla.ac.uk/workshop-view.php?workshopID=1).
The CS4FN site discusses [a related approach which is a little simpler, but not so useful in practice](http://www.cs4fn.org/internet/crushed.php).
{panel end}

{panel type="curiosity" summary="Kompresja ZL lub LZ?"}
Opisany powyżej algorytm został nazwany kompresją "Ziv-Lempel" od nazwisk dwóch informatyków Jacoba Ziva i Abrahama Lempela, którzy wymyślili go w latach 70-tych. Niestety, ktoś pomieszał kolejność ich nazwisk, kiedy opisywał ten pomysł i nazwał go kompresją "LZ" zamiast kompresji "ZL". Wielu naukowców skopiowało błąd, przez co metoda Ziva i Lempela jest obecnie zwana "kompresją LZ"!
{panel end}

## Kompresja audio

Jedną z najczęściej stosowanych metod kompresji muzyki jest MP3, który jest częścią standardu kompresji wideo o nazwie MPEG (Moving Picture Experts Group).


{panel type="curiosity" summary="Nazwa mp3"}
Nazwa "mp3" nie jest zbyt oczywista. Pomimo tego, że "mp" oznacza "ruchomy obraz" (ang. "moving picture"), a 3 numer wersji standardu, to pliki mp3 są używane do zapisu muzyki!

Pełna nazwa standardu, z którego pochodzi MP3, to MPEG, a brakujące "EG" oznacza "grupę ekspertów" (and. "expert group"). Grupę tą stanowiło konsorcjum firm i naukowców, którego celem było ustalenie standardu pozwalającego odtwarzanie materiałów wideo na urządzeniach różnych marek (na przykład to samo DVD działało na dowolnym odtwarzaczu DVD).
Pierwsza wersja wypracowanych przez konsorcjum standardów (zwana MPEG-1) miała trzy metody przechowywania ścieżki dźwiękowej (warstwy 1, 2 i 3).
Jedna z tych metod (warstwa 3 MPEG-1) stała się bardzo popularna w kompresowaniu muzyki i jej nazwa została skrócona do formatu MP3.

Standard MPEG-1 nie jest już obecnie używany w przypadku wideo (płyty DVD i telewizja używają głównie MPEG-2), ale jest bardzo ważny w przypadku kodowania audio.

Współczesną wersją MPEG jest MPEG-4 (MPEG-3 przedawnił się zanim został uznany za standard).
MPEG-4 oferuje wideo wyższej jakości i jest powszechnie stosowany do kodowania plików wideo, transmisji strumieniowych, dysków Blu-Ray i w przypadku niektórych programów telewizyjnych.
Metoda kompresji audio AAC, używana między innymi przez Apple, również pochodzi ze standardu MPEG-4.
Na komputerach, MPEG-4 część 14 jest powszechnie używany do wideo, a jego skrócona nazwa to "MP4".

Podsumowując: MP3 oznacza "MPEG-1 layer 3", natomiast MP4 jest skrótem od "MPEG-4 część 14".
{panel end}

Pozostałe metody kompresji dźwięku wykorzystują podobne rozwiązania co algorytm MP3, i niektóre z nich oferują lepszą jakość przy podobnym rozmiarze pliku (lub mniejszy rozmiar przy tej samej jakości).
Nie będziemy dokładnie prezentować zasad działania tych algorytmów, ale ogólna idea sprowadza się do rozłożenia dźwięku na pasma o różnych częstotliwościach, a następnie przedstawienie każdego z tych pasm poprzez dodanie wartości prostego wzoru (jako suma fal cosinusowych).

{comment}
.. xtcb sometime could put in an expert section on this, perhaps with recordings or a filter showing the waveforms and adding them. Here are some links in the meantime:
{comment end}

Na stronie [cs4fn znajdziesz więcej informacji na temat mp3](http://www.cs4fn.org/mathemagic/sonic.html), oraz [w artykule na stronie I Programmer](http://www.i-programmer.info/babbages-bag/1222-mp3.html).

Inne dostępne systemy kompresji dźwięku to AAC, ALAC, Ogg Vorbis i WMA. Każda z tych metod ma pewne zalety w stosunku do innych, niektóre są bardziej kompatybilne lub otwarte niż inne.

Głównym pytaniem dotyczącym skompresowanego dźwięku jest jak mały może być plik i jak czułe jest ludzkie uchao. (Dodatkowo pojawia się pytanie, ile czasu zajmuje kodowanie pliku, co może być istotne dla praktyczności systemu).
Kompromis między jakością a wielkością plików audio może zależeć od sytuacji, w której muzyka jest odtwarzana. Jeśli biegasz i słuchasz muzyki, jakość może nie mieć większego znaczenia, dzięki czemu można ograniczyć przestrzeń potrzebną do jej przechowywania.
Z drugiej strony, jeśli słuchamy nagrań w domu na dobrym sprzęcie jakość może odgrywać o wiele większą rolę niż rozmiaru plików.

Aby ocenić stopień kompresji pliku audio, należy przyjrzeć oryginalnym nagraniom wysokiej jakości, takim jak płyta CD (lub nieskompresowane pliki WAV lub AIFF). Następnie przygotuj pliki audio z różnymi stylami muzycznymi oraz innymi rodzajami dźwięku, takimi jak mowa lub nawet cisza. W dalszej kolejności przekowertuj te nagrania do różnych formatów audio. Jednym narzędzi, które to umożliwia jest iTunes firmy Apple. Można go użyć do zgrywania płyt CD i zapisu w różnych formatach, po uprzednim ustaleniu jakości i wielkości.
Wiele innych programów audio oferuje podobne możliwości.

Skompresuj każde z przygotowanych nagrań przy użyciu różnych metod, po upewnieniu się, że każdy skompresowany plik jest tworzony z oryginału wysokiej jakości. Stwórz tabelę pokazującą, ile czasu zajęło przetwarzanie każdego nagrania, rozmiar skompresowanego pliku oraz ocenę jakości dźwięku w porównaniu z oryginałem. Prześledź związki pomiędzy jakością a rozmiarem - czy potrzebujesz dużo większych plików do przechowywania dobrej jakości dźwięku? Czy istnieje minimum dla rozmiaru pliku, który zachowuje akceptowalną jakość? Czy niektóre metody działają lepiej dla mowę niż inne? Czy 2-minutowe nagranie ciszy zajmuje więcej miejsca niż 1 minuta nagrania ciszy? Czy 1 minuta nagrywania muzyki zajmuje więcej miejsca niż minuta ciszy?

{comment}
.. xtcb could have a section on Huffman coding sometime (remove from "the whole story")
{comment end}

## Cała opowieść!

W rozdziale tym przedstawione zostały podstawowe informacje dotyczące kompresji, wiele szczegółów zostało tego zagadnienia zostało jedynie wspomnianych. Sporo miejsca zostało poświęcone rozmiarom plików i szybkości algorytmów kompresji.
Większość systemów kompresji to warianty pomysłów, które zostały tutaj omówione. Poza jednym wyjątkiem, o którym nie wspomnieliśmy, chociaż jest jednym z najważniejszych algorytmów. Chodzi o kodowanie Huffmana, które okazuje się przydatne jako ostatni etap *wszystkich* powyższych metod i często jest jednym z pierwszych tematów wymienionych w podręcznikach omawiających kompresję (krótkie [wyjaśnienie tutaj](http://www.cimt.plymouth.ac.uk/resources/codes/codes_u17_text.pdf)).
Blisko związanie kodowanie artymetyczne (krótkie [wyjaśnienie tutaj](http://www.cimt.plymouth.ac.uk/resources/codes/codes_u18_text.pdf)).
Kompresja wideo została również pominięta, mimo iż to właśnie ten typ kompresji daje największe oszczędności przestrzeni dyskowej.
Większość metod kompresji wideo jest oparta na standardzie "MPEG" (ang. Moving Pictures Experts Group). Nieco więcej informacji na ten tamat zawiera [artykuł CS4FN o "Movie Magic"](http://www.cs4fn.org/films/mpegit.php).

{panel type="teacher-note" summary="Teacher guides for Plymouth resources"}
Access to teacher guides for the Plymouth resources (linked in the previous paragraph) above are [available here](http://www.cimt.plymouth.ac.uk/resources/codes/).
{panel end}

Zaprezentowana metoda Ziv-Lempel jest odmianą metody zwanej "LZ77". Wiele algorytmów kompresji bezstratnej bazuje na tych metodach. Innym popularnym algorytmem o podobnym działaniu jest "LZW". Inną efektywną metodą kompresji ogólnego przeznaczenia jest bzip, oparty na bardzo sprytnej metodzie zwanej transformacją Burrows-Wheeler.

Pytania typu "jaki jest najwyższy możliwy stopień kompresji" są przedmiotem działu zwanego [teorią informacji](https://en.wikipedia.org/wiki/Information_theory). ??There is an [activity on information theory on the CS Unplugged site](http://csunplugged.org/information-theory), and there is a [fun activity that illustrates information theory](http://www.math.ucsd.edu/~crypto/java/ENTROPY/)??. Z tej teorii wynika, że tekst w języku angielskim nie może być skompresowany do mniej niż 12% oryginalnego rozmiaru. Zdjęcia, dźwięki i materiały wideo mogę być kompresowane z większą skutecznością, gdyż możemy stosować kompresję stratną.

{comment}
.. xtcb jargon uncompressed are typically BMP or RAW. TIFF files Tagged Image File Format can contain many formats, including uncompressed, runlength and JPEG.
{comment end}

## Dalsza lektura

- „The Data Compression Book” by Mark Nelson and Jean-Loup Gailly is a good overview of this topic
- A list of books on this topic (and lots of other information about compression) is available from [The Data Compression Site](http://www.data-compression.info/Books/).
- Gleick's book "The Information" has some background to compression, and coding in general.


### Ciekawe linki

- Images, run-length-coding [http://csunplugged.org/image-representation](http://csunplugged.org/image-representation) This is also relevant to binary representations in general, although is probably best used in the compression section.
- There is a detailed section on [JPEG encoding on Wikipedia](https://en.wikipedia.org/wiki/Jpeg).
- Text compression [http://csunplugged.org/text-compression](http://csunplugged.org/text-compression)
