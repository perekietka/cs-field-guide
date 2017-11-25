# Kdowanie - Kompresja

## What's the big picture?

Kompresja danych pozwala zredukować ilość miejsc potrzebną do zapisu plików. Jeżeli możesz zmniejszyć o połowę rozmiar pliku, to oznacza, że możesz przechowywać dwa razy więcej plików przy tych samych kosztach, lub możesz ściągać pliki dwa razy szybciej (płacąc dwa razy mniej za transfer).
Pomimo tego, iż dyski twarde zwiększają objętość oraz wysoka przepustowość łącz staje się powszechna, to nadal dobrze jest osiągnąć tą samą wartość pracując na mniejszym, skompresowanym pliku.
Dla dużych magazynów danych, takich jakie posiadają Google lub Facebook, zmniejszenie o połowę przestrzeni potrzebnej do zapisu oznacza olbrzymie oszczędności w przestrzeni dyskowej, mocy obliczeniowej, a w konsekwencji  oszczędności w zużyciu energii, chłodzeniu oraz niepożądanym wpływie na środowisko.

Częste formy kompresji będące aktualnie w użyciu to JPEG (dla zdjęć), MP3 (dla plików audio), MPEG (dla wideo w tym DVD), oraz ZIP (dla dowolnych typów danych).
Przykładowo, metoda kompresji JPEG redukuje rozmiar zdjęcia do jednej dziesiątej lub mniejszej części początkowego rozmiaru, co oznacza, iż aparat może przechowywać 10 razy więcej zdjęć, a obrazki w sieci mogą być ściągane 10 razy szybciej.

Na czym polega haczyk? Okazuje się, że może być problem z jakością danych - np. mocno skompresowany JPEG może nie być tak ostry jak nieskompresowany oryginał. Poza tym, kompresowanie i dekompresowanie wymaga mocy obliczeniowej procesora. W większości przypadków ten narzut się jednak opłaca.

{interactive name="compression-comparer" type="in-page"}

W tym rozdziale przyjrzymy się temu jak można uzyskać kompresje, jakie są korzyści i jakie koszty związane z używaniem skompresowanych danych. Będzie to przydatne podczas podejmowania decyzji, o tym czy opłaca się kompresować dane.

Zaczniemy od prostego przykłady – kodowania długości serii (RLE od ang. Run Length Encoding) – które daje pewien wgląd w zalety i wady kompresji.

{panel type="teacher-note" summary="Locked in activity"}
Przykładem intrygującego zadania związanego z kompresją jest ["locked-in" activity](http://www.cs4fn.org/lockedin.html) z CS4FN.
W tym zadaniu uczniowie symulują pisanie tekstu metodą używaną przez Jean’a-Dominique’a Bauby, który był całkowicie sparaliżowany i mógł poruszać jedynie powieką. Przy pomocy prostego binarnego interfejsu (miga lub nie miga) był w stanie podyktować całą książkę. Warto dobrać uczniów w pary i kazać im spróbować porozumiewać się jedynie mrugając. Zadanie to spowoduje wiele pytań o to jak robić to w najkrótszym czasie i przy najmniejszym wysiłku. Oczywiście, w pierwszym kroku będą musieli ustalić jak przekazać jakąkolwiek treść w ten sposób.
{panel end}


## Kodowanie Długości Serii

{video url="https://www.youtube.com/embed/uaV2RuAJTjQ?rel=0"}

Kodowanie długości serii (RLE od ang. Run Length Encoding) nie jest techniką często używaną współcześnie, ale jest nadaje się świetnie jako wprowadzenie do problemów związanych z kompresją.

{panel type="teacher-note" summary="Who uses run length encoding?"}
[Kodowanie długości serii](https://en.wikipedia.org/wiki/Run-length_encoding) było w powszechnym użyciu kiedy normą były czarno-białe obrazy.
To właśnie ten typ kompresji umożliwił realizację urządzenia jakim był Fax, również dzięki unstandardowieniu 1980 roku.
Piksele w przesyłanym faksem obrazie był jedynie czarne lub białe, charakteryzowały się przeważnie długimi ciągami białych pikseli na marginesach, co sprawiało, że RLE było wyjątkowo skuteczne.
Poza tym metoda ta była bardzo prosta, co było ważne w roku 1980, gdyż pozwoliło znacznie obniżyć koszt elektroniki w urządzeniu.

Kodowanie długości serii jest nadal używane jako część kompresji JPEG, jednakże nie do kodowanie ciągu pikseli (w fotografii rzadko występują ciągi pikseli o dokładnie takim samym kolorze).

Wprowadziliśmy RLE gdyż jest praktycznym podejściem do kompresji, i co ważniejsze pokazuje kluczowe zalety i problemy związane z kompresją.
{panel end}


Imagine we have the following simple black and white image.

{image filename="pixel-diamond.png" alt="A diamond shape made out of pixels"}

One very simple way a computer can store this image in binary is by using a format where '0' means white and '1' means black (this is a "bit map", because we've mapped the pixels onto the values of bits). Using this method, the above image would be represented in the following way:

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

Zatem mamy następującą reprezentacją dla pierwszych trzech wierszy pikseli obrazu.

```
1, 2, 4, 1, 4, 2, 1
0, 1, 5, 3, 5, 1
5, 5, 5
```

Łatwo mona się domyśleć jak będą wyglądać kolejne wiersze w tym systemie reprezentacji.

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

Aby upewnić się, że możemy odwrócić proces kompresji, spróbuj znaleźć oryginalną reprezentację (zera i jedynki) skompresowanego obrazu.

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

For example, the following image shows a zoomed in view of the pixels that are part of the detail around an eye from the above (high quality) image.

{image filename="zoomed-eye.png"}

Notice that the colours in adjacent pixels are often very similar, even in this part of the picture that has a lot of detail. For example, the pixels shown in the red box below just change gradually from very dark to very light.

{image filename="zoomed-eye-highlighted.png"}

Run-length encoding wouldn't work in this situation. You could use a variation that specifies a pixel's colour, and then says how many of the following pixels are the same colour, but although most adjacent pixels are nearly the same, the chances of them being identical are very low, and there would be almost no runs of identical colours.

But there is a way to take advantage of the gradually changing colours. For the pixels in the red box above, you could generate an approximate version of those colours by specifying just the first and last one, and getting the computer to calculate the ones in between assuming that the colour changes gradually between them. Instead of storing 5 pixel values, only 2 are needed, yet someone viewing it probably might not notice any difference. This would be *lossy* because you can't reproduce the original exactly, but it would be good enough for a lot of purposes, and save a lot of space.

{panel type="jargon-buster" summary="Interpolation"}
{glossary-definition term="Interpolation" definition="Working out values between some given values;
for example, if a sequence of 5 numbers starts with 3 and finishes with 11, we might interpolate the values 5, 7, 9 in between."}

The process of guessing the colours of pixels between two that are known is an example of
{glossary-link term="interpolation" reference-text="compressing images"}interpolation{glossary-link end}.
A *linear* interpolation assumes that the values increase at a constant rate between the two given values; for example, for the five pixels above, suppose the first pixel has a blue colour value of 124, and the last one has a blue value of 136,
then a linear interpolation would guess that the blue values for the ones in between are 127, 130 and 133, and this would save storing them.
In practice, a more complex approach is used to guess what the pixels are, but linear interpolation gives the idea of what's going on.
{panel end}

The JPEG system, which is widely used for photos, uses a more sophisticated version of this idea. Instead of taking a 5 by 1 run of pixels as we did above, it works with 8 by 8 blocks of pixels. And instead of estimating the values with a linear function, it uses combinations of cosine waves.

{comment}
It would be good have a figure that shows a line of pixels, and the corresponding waveform.
{comment end}

{panel type="curiosity" summary="What are cosine waves"}
A cosine wave form is from the trig function that is often used for calculating the sides of a triangle. If you plot the cosine value from 0 to 180 degrees, you get a smooth curve going from 1 to -1. Variations of this plot can be used to approximate the value of pixels, going from one colour to another. If you add in a higher frequency cosine wave, you can produce interesting shapes. In theory, any pattern of pixels can be created by adding together different cosine waves!

The following graph shows the values of {math}\sin(x){math end} and {math}\cos(x){math end} for {math}x{math end} ranging from 0 to 180 degrees.

{image filename="cosine-graph.png" alt="A graph showing cos(x) and sin(x) curves"}
{panel end}

{panel type="curiosity" summary="Adding sine or cosine waves to create any waveform"}
JPEGs (and MP3) are based on the idea that you can add together lots of sine or cosine waves to create any waveform that you want.
Converting a waveform for a block of pixels or sample of music into a sum of simple waves can be done using a technique called a [Fourier transform](https://en.wikipedia.org/wiki/Fourier_transform), and is a widely used idea in signal processing.

You can experiment with adding sine waves together to generate other shapes using the
[spreadsheet provided](files/Adding-Sine-Waves.xls).
In this spreadsheet, the yellow region on the first sheet allows you to choose which sine waves to add.
Try setting the 4 sine waves to frequencies that are 3, 9, 15, and 21 times the fundamental frequency respectively (the "fundamental" is the lowest frequency.)
Now set the "amplitude" (equivalent to volume level) of the four to 0.5, 0.25, 0.125 and 0.0625 respectively (each is half of the previous one).
This should produce the following four sine waves:

{image filename="sine-waves.png" alt="Four sine waves"}

When the above four waves are added together, they interfere with each other, and produce a shape that has sharper transitions:

{image filename="sine-waves-sum.png" alt="The four sine waves added together"}

In fact, if you were to continue the pattern with more than four sine waves, this shape would become a "square wave", which is one that suddenly goes to the maximum value, and then suddenly to the minimum.
The one shown above is bumpy because we've only used 4 sine waves to describe it.

This is exactly what is going on in JPEG if you compress a black and white image.
The "colour" of pixels as you go across the image will either be 0 (black) or full intensity (white), but JPEG will approximate it with a small number of cosine waves (which have basically the same properties as sine waves.)
This gives the "overshoot" that you see in the image above; in a JPEG image, this comes out as bright and dark patches surrounding the sudden change of colour, like here:

{image filename="jpeg-word-zoomed.jpg"}

You can experiment with different combinations of sine waves to get different shapes.
You may need to have more than four to get good approximations to a shape that you want; that's exactly the tradeoff that JPEG is making.
There are some suggestions for parameters on the second sheet of the spreadsheet.

You can also learn about Fourier transforms using the Wolfram Alpha software; this will require you to install a browser plugin.
The Wolfram demonstrations include:
[an interactive demonstration of JPEG](http://demonstrations.wolfram.com/JPEGCompressionAlgorithm/),
[showing the relationship between sine saves and creating other waveforms](http://demonstrations.wolfram.com/RecoveringTheFourierCoefficients/), and
[showing how sine waves can be summed to produce other shapes](http://demonstrations.wolfram.com/SumsOfSineWavesWithSeveralStepSizesSawtoothOrSquareApproxima/).

{panel end}

{comment}
.. html5 low priority interactive to add cosine waves to try to match a given waveform e.g. square wave, triangle, random. Select amplitude for various frequencies. I have a spreadsheet that basically does this, could put it in for the meantime - tim
{comment end}

You can see the 8 by 8 blocks of pixels if you zoom in on a heavily compressed JPEG image. For example, the following image has been very heavily compressed using JPEG (it is just 1.5% of its original size).

{image filename="compressed-jpeg.png"}

If we zoom in on the eye area, you can see the 8 x 8 blocks of pixels:

{image filename="compressed-jpeg-zoomed.png"}

Notice that there is very little variation across each block. In the following image the block in the red box only changes from top to bottom, and could probably be specified by giving just two values, and having the ones in between calculated by the decoder as for the line example before. The green square only varies from left to right, and again might only need 2 values stored instead of 64. The blue block has only one colour in it! The yellow block is more complicated because there is more activity in that part of the image, which is where the cosine waves come in. A "wave" value varies up and down, so this one can be represented by a left-to-right variation from dark to light to dark, and a top-to-bottom variation mainly from dark to light. Thus still only a few values need to be stored instead of the full 64.

{image filename="compressed-jpeg-zoomed-highlighted.png"}

The quality is quite low, but the saving in space is huge – it's more than 60 times smaller (for example, it would download 60 times faster). Higher quality JPEG images store more detail for each 8 by 8 block, which makes it closer to the original image, but makes bigger files because more details are being stored. You can experiment with these tradeoffs by saving JPEGs with differing choices of the quality, and see how the file size changes. Most image processing software offers this option when you save an image as a JPEG.

{comment}
low priority : interactive that could load a photo, zoom in on pixels, and change it to different qualities of jpg coding
{comment end}

{panel type="jargon-buster" summary="Where does the term JPEG come from?"}
The name "JPEG" is short for "Joint Photographic Experts Group", a committee that was formed in the 1980s to create standards so that digital photographs could be captured and displayed on different brands of devices. Because some file extensions are limited to three characters, it is often seen as the ".jpg" extension.
{panel end}

{panel type="curiosity" summary="More about cosine waves"}
The cosine waves used for JPEG images are based on a "Discrete Cosine Transform". The "Discrete" means that the waveform is digital – it is the opposite of continuous, where any value can occur. In a JPEG wave, there are only 8 x 8 values (for the block being coded), and each of those values can have a limited range of numbers (binary integers), rather than any value at all.
{panel end}

An important issue arises because JPEG represents images as smoothly varying colours: what happens if the colours change suddenly?
In that case, lots of values need to be stored so that lots of cosine waves can be added together to make the sudden change in colour, or else the edge of the image become fuzzy.
You can think of it as the cosine waves overshooting on the sudden changes, producing artifacts like the ones in the following image where the edges are messy.

{image filename="jpeg-word.jpg"}

The original had sharp edges, but this zoomed in view of the JPEG version of it show that not only are the edges gradual, but some darker pixels occur further into the white space, looking a bit like shadows or echoes.

{image filename="jpeg-word-zoomed.jpg"}

For this reason, JPEG is used for photos and natural images, but other techniques (such as GIF and PNG, which we will look at in another section) work better for artificial images like this one.

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


## General purpose compression

General purpose compression methods need to be lossless because you can't assume that the user won't mind if the data is changed. The most widely used general purpose compression algorithms (such as ZIP, gzip, and rar) are based on a method called "Ziv-Lempel coding", invented by Jacob Ziv and Abraham Lempel in the 1970s.

We'll look at this with a text file as an example.
The main idea of Ziv-Lempel coding is that sequences of characters are often repeated in files (for example, the sequence of characters "image " appears often in this chapter), and so instead of storing the repeated occurrence, you just replace it with a reference to where it last occurred. As long as the reference is smaller than the phrase being replaced, you'll save space. Typically this systems based on this approach can be used to reduce text files to as little as a quarter of their original size, which is almost as good as any method known for compressing text.

The following interactive allows you to explore this idea.
The empty boxes have been replaced with a reference to the text occurring earlier.
You can click on a box to see where the reference is, and you can type the referenced characters in to decode the text.
What happens if a reference is pointing to another reference?
As long as you decode them from first to last, the information will be available before you need it.

{comment}
.. xhtml5 Eventually this could use a parameter so there's one version with no tabs, and a later one with them.
{comment end}

{button link="http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/COMPRESSION/LWZ/public_html/index.html" text="View compression interactive"}

{comment}
.. xjrm (or Rhem): pasting text in that is too big causes it to be rejected. It would be nicer if the pasted text is truncated to the maximum length.
{comment end}

You can also enter your own text by clicking on the "Text" tab.
You could paste in some text of your own to see how many characters can be replaced with references.

The references are actually two numbers: the first says how many characters to count back to where the previous phrase starts, and the second says how long the referenced phrase is.
Each reference typically takes about the space of one or two characters, so the system makes a saving as long as two characters are replaced.
The options in the interactive above allow you to require the replaced length to be at least two, to avoid replacing a single character with a reference.
Of course, all characters count, not just letters of the alphabet, so the system can also refer back to the white spaces between words.
In fact, some of the most common sequences are things like a full stop followed by a space.

This approach also works very well for black and white images, since sequences like "10 white pixels" are likely to have occurred before.
Here are some of the bits from the example earlier in this chapter; you can paste them into the interactive above to see how many pointers are needed to represent it.

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

In fact, this is essentially what happens with GIF and PNG images; the pixel values are compressed using the Ziv-Lempel algorithm, which works well if you have lots of consecutive pixels the same colour. But it works very poorly with photographs, where pixel patterns are very unlikely to be repeated.

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

{panel type="curiosity" summary="ZL or LZ compression?"}
The method we have described here is named “Ziv-Lempel” compression after Jacob Ziv and Abraham Lempel, the two computer scientists who invented it in the 1970s. Unfortunately someone mixed up the order of their names when they wrote an article about it, and called it “LZ” compression instead of “ZL” compression. So many people copied the mistake that Ziv and Lempel’s method is now usually called “LZ compression”!
{panel end}

## Audio compression

One of the most widely used methods for compressing music is MP3, which is actually from a video compression standard called MPEG (Moving Picture Experts Group).


{panel type="curiosity" summary="The naming of mp3"}
The name "mp3" isn't very self explanatory because the "mp" stands for "moving picture", and the 3 is from version 1, but mp3 files are used for music!

The full name of the standard that it comes from is MPEG, and the missing "EG" stands for "experts group", which was a consortium of companies and researchers that got together to agree on a standard so that people could easily play the same videos on different brands of equipment (so, for example, you could play the same DVD on any brand of DVD player).
The very first version of their standards (called MPEG-1) had three methods of storing the sound track (layer 1, 2 and 3).
One of those methods (MPEG-1 layer 3) became very popular for compressing music, and was abbreviated to MP3.

The MPEG-1 standard isn't used much for video now (for example, DVDs and TV mainly use MPEG-2), but it remains very important for audio coding.

The next MPEG version is MPEG-4 (MPEG-3 was redundant before it became a standard).
MPEG-4 offers higher quality video, and is commonly used for digital video files, streaming media, Blu-Ray discs and some broadcast TV.
The AAC audio compression method, used by Apple among others, is also from the MPEG-4 standard.
On computers, MPEG-4 Part 14 is commonly used for video, and it's often abbreviated as "MP4."

So there you have it: MP3 stands for "MPEG-1 layer 3", and MP4 stands for "MPEG-4 part 14".
{panel end}

Most other audio compression methods use a similar approach to the MP3 method, although some offer better quality for the same amount of storage (or less storage for the same quality).
We won't go into exactly how this works, but the general idea is to break the sound down into bands of different frequencies, and then represent each of those bands by adding together the values of a simple formula (the sum of cosine waves, to be precise).

{comment}
.. xtcb sometime could put in an expert section on this, perhaps with recordings or a filter showing the waveforms and adding them. Here are some links in the meantime:
{comment end}

There is some [more detail about how MP3 coding works on the cs4fn site](http://www.cs4fn.org/mathemagic/sonic.html), and also in [an article on the I Programmer site](http://www.i-programmer.info/babbages-bag/1222-mp3.html).

Other audio compression systems that you might come across include AAC, ALAC, Ogg Vorbis, and WMA. Each of these has various advantages over others, and some are more compatible or open than others.

The main questions with compressed audio are how small the file can be made, and how good the quality is of the human ear. (There is also the question of how long it takes to encode the file, which might affect how useful the system is.)
The tradeoff between quality and size of audio files can depend on the situation you're in: if you are jogging and listening to music then the quality may not matter so much, but it's good to reduce the space available to store it.
On the other hand, someone listening to a recording at home on a good sound system might not mind about having a large device to store the music, as long as the quality is high.

To evaluate an audio compression you should choose a variety of recordings that you have high quality originals for, typically on CD (or using uncompressed WAV or AIFF files). Choose different styles of music, and other kinds of audio such as speech, and perhaps even create a recording that is totally silent. Now convert these recordings to different audio formats. One system for doing this that is free to download is Apple's iTunes, which can be used to rip CDs to a variety of formats, and gives a choice of settings for the quality and size.
A lot of other audio systems are able to convert files, or have plugins that can do the conversion.

Compress each of your recordings using a variety of methods, making sure that each compressed file is created from a high quality original. Make a table showing how long it took to process each recording, the size of the compressed file, and some evaluation of the quality of the sound compared with the original. Discuss the tradeoffs involved – do you need much bigger files to store good quality sound? Is there a limit to how small you can make a file and still have it sounding ok? Do some methods work better for speech than others? Does a 2 minute recording of silence take more space than a 1 minute recording of silence? Does a 1 minute recording of music use more space than a minute of silence?

{comment}
.. xtcb could have a section on Huffman coding sometime (remove from "the whole story")
{comment end}

## The whole story!

The details of how compression systems work have been glossed over in this chapter, as we have been more concerned about the file sizes and speed of the methods than how they work.
Most compression systems are variations of the ideas that have been covered here, although one fundamental method that we haven't mentioned is Huffman coding, which turns out to be useful as the final stage of *all* of the above methods, and is often one of the first topics mentioned in textbooks discussing compression (there's a brief [explanation of it here](http://www.cimt.plymouth.ac.uk/resources/codes/codes_u17_text.pdf)).
A closely related system is Arithmetic coding (there's an [explanation of it here](http://www.cimt.plymouth.ac.uk/resources/codes/codes_u18_text.pdf)).
Also, video compression has been omitted, even though compressing videos saves more space than most kinds of compression.
Most video compression is based on the "MPEG" standard (Moving Pictures Experts Group). There is some information about how this works in the [CS4FN article on "Movie Magic"](http://www.cs4fn.org/films/mpegit.php).

{panel type="teacher-note" summary="Teacher guides for Plymouth resources"}
Access to teacher guides for the Plymouth resources (linked in the previous paragraph) above are [available here](http://www.cimt.plymouth.ac.uk/resources/codes/).
{panel end}

The Ziv-Lempel method shown is a variation of the so-called "LZ77" method. Many of the more popular lossless compression methods are based on this, although there are many variations, and one called "LZW" has also been used a lot. Another high-compression general-purpose compression method is bzip, based on a very clever method called the Burrows-Wheeler Transform.

Questions like "what is the most compression that can be achieved" are addressed by the field of [information theory](https://en.wikipedia.org/wiki/Information_theory). There is an [activity on information theory on the CS Unplugged site](http://csunplugged.org/information-theory), and there is a [fun activity that illustrates information theory](http://www.math.ucsd.edu/~crypto/java/ENTROPY/). Based on this theory, it seems that English text can't be compressed to less than about 12% of its original size at the very best. Images, sound and video can get much better compression because they can use lossy compression, and don't have to reproduce the original data exactly.

{comment}
.. xtcb jargon uncompressed are typically BMP or RAW. TIFF files Tagged Image File Format can contain many formats, including uncompressed, runlength and JPEG.
{comment end}

## Further reading

- "The Data Compression Book" by Mark Nelson and Jean-Loup Gailly is a good overview of this topic
- A list of books on this topic (and lots of other information about compression) is available from [The Data Compression Site](http://www.data-compression.info/Books/).
- Gleick's book "The Information" has some background to compression, and coding in general.


### Useful Links

- Images, run-length-coding [http://csunplugged.org/image-representation](http://csunplugged.org/image-representation) This is also relevant to binary representations in general, although is probably best used in the compression section.
- There is a detailed section on [JPEG encoding on Wikipedia](https://en.wikipedia.org/wiki/Jpeg).
- Text compression [http://csunplugged.org/text-compression](http://csunplugged.org/text-compression)
