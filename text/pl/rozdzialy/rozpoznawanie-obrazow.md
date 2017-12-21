# Rozpoznawanie obrazów (przez komputer)

{video url="https://www.youtube.com/embed/bE2u5trQAHM?rel=0"}

## Z perspektywy

W początkach ery komputerów komunikacja komputera ze światem zewnętrznym odbywała się poprzez bezpośrednie zestawianie połączeń kablowych lub poprzez klawiaturę. Współczesne urządzenia cyfrowe wyposażone są w aparaty fotograficzne, kamery, mikrofony i inne urządzenia wejściowe, używane przez oprogramowanie do automatycznego pobierania informacji ze świata, w którym żyjemy. Przetwarzanie obrazów z kamery w celu znalezenia poszukiwanych informacji (wzorców) nazywa się w informatyce * rozpoznawaniem obrazów * lub komputerowym widzeniem (ang. computer vision).

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

{panel type="teacher-note" summary="The importance of image segmentation"}

Ostatni znak trudniej było rozpoznać, gdyż rysunek postaci człowieka jest zbyt blisko znaku. Oprogramowanie smarfona nie potrafiło określić, gdzie kończy się znak pisma, a gdzie rozpoczyna się rysunek. Ten problem jest znany pod nazwą *segmentacji obrazu*. Wrócimy do niego później.

{panel end}

Celem tego rodziału jest zaznajomienie czytelnika nie tylko z tematem rozpoznawania obrazów. Proces automatycznego rozpoznawania informacji (przechwytywania danych) ze świata realnego może być użyteczny na różne sposoby. Na przykład znajduje zastosowanie w samochodach, pomagając w unikaniu kolizji na drodze, poprzez ostrzeganie o zbyt małej odległości między samochodami i o innych zagrożeniach. W połączeniu z systemami map (nawigacji) system rozpoznawania obrazów pozwala na budowę samochodów, które będą się poruszać bez kierowcy. Inny przykład zastosowania to komputerowe systemy ostrzegania wbudowane w wózki inwalidzkie. 

## Światła, kamera, akcja!

Kamery cyfrowe i ludzkie oczy pełnią podobne funkcje: promienie światła przechodzą odpowiednio przez obiektyw kamery lub przez soczewkę oka, tam ulegają załamaniu i w końcu padają na powierzchnię (w oku to siatkówka) pokrytą fotoreceptorami, gdzie są przetwarzane na sygnały elektryczne, które później są przetwarzane przez komputer czy mózg. Oczywiście to tylko uproszczony schemat.

{panel type="teacher-note" summary="Receptory cyfrowego aparatu fotograficznego"}

Jest kilka różnych typów sensorów cyfrowego aparatu fotogrficznego. W tym rozdziale ograniczymy się do sensorów [CMOS](https://en.wikipedia.org/wiki/CMOS_sensor”), najbardziej popularnych. Inny typ to [Charge-Coupled Device (CCD)](https://en.wikipedia.org/wiki/Charge-coupled_device), znany bardziej wśród fachowców zajmujących się astronomią.

{panel end}

W środku plamki żółtej, czyli części siatkówki **ludzkiego oka** o największym zagęszczeniu fotoreceptorów, zwanych czopkami, znajduje się zagłębienie dołeczkiem (łac. fovea). To miejsce o największej rozdzielczości widzenia, to znaczy, że odpowiada za postrzeganie szczegółów obiektu, na który patrzymy wprost. Mamy trzy zbiory czopków, wrażliwych na różne barwy (kolory), odpowiednio na światło czerwone, zielone i niebieskie. 
Inne receptory siatkówki oka to pręciki, które są bardzo wrażliwe na światło, odpowiadają za postrzeganie kształtów i postrzeganie czarno-białe widzenie nawet przy słabym oświetleniu. 
Obszar siatkówki oka, w którym nerw wzrokowy opuszcza gałkę oczną i biegnie w stronę mózgu to plamka ślepa. Jest on całkowicie pozbawiony fotoreceptorów. Jednak luki w polu widzenia obu oczu nie pokrywają się, z więc to, czego nie widzi jedno oko, widzi drugie i powstaje wrażenie, że pole widzenia jest pełne.

**Aparaty cyfrowe**, inaczej niż oczy, są jednakowej czułości na światło dla całego pola widzenia. Intensywność światła i kolor są rejestrowane przez elementy receptorów RGB wdrukowane na krzemowym układzie scalonym. Te receptory nie mają jednak takiej zdolności jak oczy jeśli chodzi o zakres poziomów światła podczas przechwytywania informacji. Zwykle, współczesne aparaty cyfrowe potrafią automatycznie dopasować ustawienia w zależności od jasności otoczenia, ale ma to swoją cenę: bardziej szczegółowe informacje o obiektach będą stracone (np. jasne objekty będą na zdjęciu widoczne jako białe plamy).

Jest ważne, by zrozumieć, że ani ludzkie oko, ani cyfrowy aparat fotograficzny --- nawet bardzo drogi --- nie są w stanie zapisać wszystkich informacji o obiektach znajdujących się w polu widzenia. Prowadzone są badania, wspólnie przez inżynierów elektorników i informatyków, których celem jest stworzenie urządzeń, które będą pozwalać na jeszcze bardziej dokładne rejestrowanie informacji oraz jej szybkie przetwarzanie.

{panel type="curiosity" summary="Further reading"}

Więcej na ten temat (w języku angielskim) można przeczytać tutaj: [Cambridge in Colour](http://www.cambridgeincolour.com/tutorials/cameras-vs-human-eye.htm), [Pixiq](https://web.archive.org/web/20130309170941/http://www.pixiq.com/article/eyes-vs-cameras).

{panel end}

## Szum

Użytkownicy aparatów cyfrowych muszą mieć świadomość istnienia problemu, jakim jest *szum*. Mówi o nim wówczas, gdy pojedyńcze piksele rejestrowane są jako jaśniejsze niż ciemniejsze niż być powinny. Zjawisko jest skutkiem interfrencji (nakładania się) w układach elektronicznych aparatu. Problem jest większy, gdy poziomy światła sąfotografujemy w ciemnym miejscu i aparat dopasować czas ekspozycji (naświetlania), aby zapisać więcej informacji. Używa się wtedy ustawień ASA/ISO celem przechwycenia takiej ilości promieni światła, ile to tylko możliwe. Receptory są wówczas bardzo wrażliwe na światło, co wiąże się z ryzykiem interferencji i obraz ma efekt ,,ziarnistości''. 

Efekt szumu jest widoczny głównie jako losowe (przypadkowe) zmiany pikseli. W przykładzie poniżej widzimy szum typu ,,sól i pieprz'.

{image filename="banana-with-salt-and-pepper-noise.jpg" alt="An image of a banana with salt-and-pepper noise"}

Rozpoznawanie obiektów na obrazach, które zawierają szum jest trudniejsze. Dlatego ważne jest, by szukać coraz lepszych metod redukowania szumu na obrazie. 
Przy projektowaniu takich metod należy zachować ostrożność. Efektem ubocznym usunięcia szumu nie może być bowiem utrata istotnych informacji o obrazie. Trzeba podkreślić, że stosowane metody są zawsze metodami przybliżonymi rozwiązania problemu, co oznacza, że decyzja o zachowaniu wartości liczbowej lub zmianie wartości dla konkretnego piksela jest efektem domysłu, uzasadnionego domniemania.

{panel type="teacher-note" summary="Image noise on Wikipedia"}

Warto zapoznać się z artykułem: [Image noise](https://en.wikipedia.org/wiki/Image_noise)

{panel end}

Ponieważ aparat fotograficzny zapisuje informacje o składowych (czerwona, zielona i niebieska) osobno dla każdego piksela, to czasami celem zaoszczędzenia na czasie przetwarzania obrazu, jest uzasadnione zapisanie obrazu w odcieniach szarości. Wtedy pomija się informacje o barwie, a zapisuje się tylko informacje o intensywności światła dla każdego piksela.

{comment}

.. todo [Demonstrate a noisy colour image and its combined greyscale]

{comment end}

Dzieki temu można zmieniejszyć poziom szumu na obrazie. Dlaczego? I w jakim stoponiu to pomaga? (Aby się przekonać, można zrobić ekesperyment: wykonać zdjęcie w miejscu słabo oświetlonym -- można wtedy dostrzec jakby małe łatki na obrazie. Następnie w programie graficznym można zapisać je jako czarno-białe -- czy to zmniejszy efekt szumu?)

{panel type="teacher-note" summary="Noisy channels"}

Każdy światłoczuły element fotoreceptora aparatu fotograficznego jest równie podatny na szum. To oznacza, że efekty szumu dla różnych składowych RGB są zjawiskami niezależnymi. Jeśli wartości RGB uśredni się (co oznacza jedną liczbę zamiast trzech), to wartość szumu zredukuje się do ok. 1/3. Dlaczego nie *dokładnie* 1/3? Może się zdarzyć, że efekt szumu dotyczy dwóch czy nawet trzech składowych tego samego piksela: wtedy wartość uśredniona pozostanie daleka od dokładnej.

{panel end}

Zamiast analizować oddzielnie każdą ze składowych RGB piksela, techniki redukujące szum najczęściej działają tak, że sprawdzają piksele sąsiadujące z danym pikselem i na podstawie zebranych informacji przypisują mu wartość przypuszczalną wartość.

W *filtrze uśredniającym* korzysta się z założenia, że piksele sąsiadujące z danym pikselem są podobne. Wartości przypisane pikselom tworzącym kwadrat, w którego centrum znajduje się dany piksel, są uśredniane i ta wartość średnia jest przypisana pikselowi.
Im kwadrat jest większych rozmiarów, tym większe niebezpieczeństwo pojawienia się w wyniku filtrowania efektu rozmycia obrazu, zwłaszcza w przypadku, gdy fragment obrazu przedstawia np. krawędzie obietków (wtedy jasne i ciemne piksele sąsiadują).

W *filtrze medianowym* stosuje się inne podejście. Odczytuje się wartości sąsiednich pikseli, podobnie jak dla filtru uśredniającego. Następnie szuka się mediany (wartości środkowej) ciągu uporządkowanego odczytanych wartości. Taki filtr daje dobre rezultaty w przypadku, gdy fragment obrazu przedstawia krawędź jakiegoś obiektu, gdyż wówczas wartość mediany będzie jedną z dwóch: albo odpowiadającą jasnemu pikselowi albo ciemnemu pikselowi. Filtr działa też dobrze, gdy analizowany obszar jest w dużej części jednolity, gdyż wówczas obecność mniej licznych pikseli o innej wartości nie ma żadnego wpływu na wartość mediany. Wadą tej metody jest czas działania, tj. koszt operacji porządkowania wartości przez wyznaczeniem mediany. 

Inną techniką jest metoda zwana *rozmyciem Gaussa*. Działa podobnie do metody uśredniania, ale zamiast wartości średniej korzysta się własności *rozkładu normalnego*: przyjmuje się, że pikseli sąsiadujące bezpośrednio z analizowanym pikselem mają przypisaną wartość najbardziej zbliżoną do poszukiwanej, a piksele polożone dalej wręcz przeciwnie.  

### Ćwiczenie: Usuwanie szumu z obrazu

Otwórz interaktywne narzędzie [noise reduction filtering interactive using this link](http://www.csfieldguide.org.nz/releases/1.9.9/_static/widgets/cv-noise-filters.html) i przeprowadź badania według opisu poniżej. Niebędna będzie kamera internetowa.

Mathematically, this process is applying a special kind of matrix called a *convolution kernel* to the value of each pixel in the source image, averaging it with the values of other pixels nearby and copying that average to each pixel in the new image. The average is weighted, so that the values of nearby pixels are given more importance than ones that are far away. The stronger the blur, the wider the convolution kernel has to be and the more calculations take place.

Bazą matematyczną przetwarzania obrazu jest w tym przypadku specjalny rodzaj macierzy zwany *jądrem splotu* (ang. convolution kernel). Każdy z pikseli tworzących obraz jest przetwarzany: wartość mu przypisana jest uśredniania na podstawie wartości sąsiednich pikseli. Zbiór pikseli uśrednionych wartości tworzy nowy obraz. W tym przypadku średnia jest średnią ważoną, tzn. wpływ na średnią wartości pikseli sąsiadujących bezpośrednio z analizowanym pikselem jest większy niż wartości pikseli bardziej oddalonych. Im większe ma być rozmycie, tym większa macierz jest używana, co oznacza większą liczbę obliczeń do wykonania podczas przetwarzania.


For this activity, investigate the different kinds of noise reduction filter and their settings (mask size, number of iterations) and determine:

- how well they cope with different kinds and levels of noise (you can set this in the interactive).
- how much time it takes to do the necessary processing (the interactive shows the number of frames per second that it can process)
- how they affect the quality of the underlying image (a variety of images + camera)

You can take screenshots of the image to show the effects in your writeup. You can discuss the tradeoffs that need to be made to reduce noise.

## Face recognition

Recognising faces has become a widely used computer vision application.
These days photo album systems like Picasa and Facebook can try to recognise who is in a photo using face recognition ---
for example, the following photos were recognised in Picasa as being the same person, so to label the photos with people's names you only need to click one button rather than type each one in.

{image filename="face-recognition-software-screenshot.jpg" alt="Google's Picasa recognises these photos as being the same person"}

There are lots of other applications.
Security systems such as customs at country borders use face recognition to identify people and match them with their passport.
It can also be useful for privacy --- Google Maps streetview identifies faces and blurs them.
Digital cameras can find faces in a scene and use them to adjust the focus and lighting.

There is some information about [How facial recognition works](http://electronics.howstuffworks.com/gadgets/high-tech-gadgets/facial-recognition.htm) that you can read up as background, and some more information at [i-programmer.info](http://www.i-programmer.info/babbages-bag/1091-face-recognition.html).

There are some relevant [articles on the cs4fn website](http://www.cs4fn.org/vision/) that also provide some general material on computer vision.

### Project: Recognising faces

{panel type="teacher-note" summary="NCEA"}

The following activity can be used as part of a project for the 3.44 standard. This project covers material for an example for the 3.44 standard through the following components:

- Key problem: face recognition in digital images
- Practical application: security, photo album tagging
- Algorithm/technique: Haar face detector
- Evaluation: ability to recognise faces, false positives and negatives, processing speed
- Personalised student examples: applying the processing to the student's own images

{panel end}

First let's manually try some methods for recognising whether two photographs show the same person.

- Get about 3 photos each of 3 people
- Measure features on the faces such as distance between eyes, width of mouth, height of head etc. Calculate the ratios of some of these.
- Do photos of the same person show the same ratios? Do photos of different people show different ratios? Would these features be a reliable way to recognise two images as being the same person?
- Are there other features you could measure that might improve the accuracy?

You can evaluate the effectiveness of facial recognition in free software such as Google’s Picasa or the Facebook photo tagging system, but uploading photos of a variety of people and seeing if it recognises photos of the same person. Are there any false negatives or positives? How much can you change your face when the photo is being taken to not have it match your face in the system? Does it recognise a person as being the same in photos taken several years apart? Does a baby photo match of a person get matched with them when they are five years old? When they are an adult? Why or why not does this work?

Try using [face recognition on this website](https://inspirit.github.com/jsfeat/sample_haar_face.html) to see how well the Haar face recognition system can track a face in the image. What prevents it from tracking a face? Is it affected if you cover one eye or wear a hat? How much can the image change before it isn't recognised as a face? Is it possible to get it to incorrectly recognise something that isn't a face?

## Edge detection

A useful technique in computer vision is *edge detection*, where the boundaries between objects are automatically identified.
Having these boundaries makes it easy to *segment* the image (break it up into separate objects or areas), which can then be recognised separately.

For example, here's a photo where you might want to recognise individual objects:

{image filename="fruit-bowl-photo.jpg" alt="Image of a fruit bowl"}

And here's a version that has been processed by an edge detection algorithm:

{image filename="fruit-bowl-photo-with-canny-edge-detection.png" alt="The image above with canny edge detection applied"}

Notice that the grain on the table above has affected the quality; some pre-processing to filter that would have helped!

You can experiment with edge-detection yourself with the [Canny edge detector on this website](https://inspirit.github.io/jsfeat/sample_canny_edge.html) (see the information about [Canny edge detection on Wikipedia](https://en.wikipedia.org/wiki/Canny_edge_detector)).
This is a widely used algorithm in computer vision, developed in 1986 by John F. Canny.

### Activity: Edge detection evaluation

{panel type="teacher-note" summary="NCEA"}

The following activity can be used as part of a project for the 3.44 standard. This project covers material for an example for the 3.44 standard through the following components:

- Key problem: edge detection in digital images
- Practical application: segmenting an image into component objects
- Algorithm/technique: Canny Edge detector
- Evaluation: ability to find all real edges (and not get false edges), and speed of the detector with various settings and types of images
- Personalised student examples: applying the processing to the student's own images

{panel end}

With the canny edge detection website above, try putting different images in front of the camera and determine how good the algorithm is at detecting boundaries in the image.
Capture images to put in your report as examples to illustrate your experiments with the detector.

- Can the Canny detector find all edges in the image? If there are some missing, why might this be?
- Are there any false edge detections? Why did they system think that they were edges?
- Does the lighting on the scene affect the quality of edge detection?
- Does the system find the boundary between two colours? How similar can the colours be and still have the edge detected?
- How fast can the system process the input? Does the nature of the image affect this?
- How well does the system deal with a page with text on it?

## The whole story!

The field of computer vision is changing rapidly at the moment because camera technology has been improving quickly over the last couple of decades.
Not only is the resolution of cameras increasing, but they are more sensitive for low light conditions, have less noise, can operate in infra-red (useful for detecting distances), and are getting very cheap so that it's reasonable to use multiple cameras, perhaps to give different angles or to get stereo vision.

Despite these recent changes, many of the fundamental ideas in computer vision have been around for a while; for example, the "k-means" segmentation algorithm was first described in 1967, and the first digital camera wasn't built until 1975 (it was a 100 by 100 pixel Kodak prototype).

(More material will be added to this chapter in the near future)

## Further reading

- [https://en.wikipedia.org/wiki/Computer_vision](https://en.wikipedia.org/wiki/Computer_vision)
- [https://en.wikipedia.org/wiki/Mri](https://en.wikipedia.org/wiki/Mri)
- [http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html](http://www.cosc.canterbury.ac.nz/mukundan/cogr/applcogr.html)
- [http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html](http://www.cosc.canterbury.ac.nz/mukundan/covn/applcovn.html)
