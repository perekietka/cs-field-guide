# Kodowanie -- wprowadzenie

## Z lotu ptaka

Słowo „kod” ma wiele znaczeń w informatyce. Często używa się go mówiąc o programowaniu (jako o kodowaniu), a treść programu nazywa się „kodem źródłowym”. Nawet reprezentację binarną informacji określa się mianem kodu. Jednakże w tym rozdziale (oraz w kolejnych trzech rozdziałach) sens tego słowa będzie wyrażony jako sprytny sposób reprezentacji informacji, który przy okazji pozwala na rozwiązanie jednego z praktycznych problemów, jakim jest szyfrowanie danych w celu zachowania ich w tajemnicy.

W poprzednim rozdziale zajmowaliśmy się binarną reprezentacją pozwalającą zapisywać różne rodzaje danych -- liczby, tekst, obrazy itp. Jednakże w wielu sytuacjach prosta reprezentacja binarna nie sprawdza się. Czasami zajmuje za dużo miejsca, innym razem mały błąd w zapisie może spowodować olbrzymi problem, a w innym przypadku naszym zmartwieniem może być fakt, że ktoś przeczyta naszą wiadomość. Bardzo często wszystkie trzy wspomniane problemy są istotne. Kody, którymi się zajmiemy radzą sobie właśnie z tymi problemami, i są powszechnie wykorzystywane w zapisywaniu i przesyłaniu informacji.

Trzy główne powody, dla których stosujemy skomplikowane reprezentacje danych to:
- **Kompresja:** pozwala zredukować przestrzeń jaką potrzebują dane (np. zakodowanie pliku audio do formatu MP3 pozwala zmniejszyć rozmiar do 10% rozmiaru początkowego).
- **Szyfrowanie:** zmienia reprezentację danych w ten sposób, iż potrzebny jest “klucz” aby odczytać wiadomość (np. jeżeli przeglądarka internetowa korzysta z “https” zamiast “http”, to cała komunikacja ze stroną internetową jest zaszyfrowana, tak aby nikt kto podsłuchuje nie mógł poznać przesyłanych informacji).
- **Korekcja błędów:** dodaje pewne informacje do danych, tak aby w przypadku małych błędów w zapisie lub transmisji można było ten fakt wykryć, a nawet odtworzyć poprawne dane (np. kody kreskowe na produktach posiadają dodatkową cyfrę, która pozwala określić czy kod został prawidłowo zeskanowany w kasie, a w przypadku nieprawidłowego skanowania emitowany jest dźwięk ostrzegawczy).

Często wszystkie trzy techniki są używane na tych samych danych, np. jeżeli robimy zdjęcie smartfonem to jest ono zwykle kompresowane kodowaniem JPEG, zapisywane w pamięci telefonu z kodem korekcji błędów, a następnie wysyłane do sieci przez bezprzewodowe połączenie, które jest szyfrowane, tak aby nikt w pobliżu nie mógł sobie skopiować tego zdjęcia.

Bez tych form kodowania współczesne urządzenia elektroniczne byłyby bardzo wolne, posiadały mocno ograniczoną pojemność, byłyby zawodne oraz niezdolne do zachowania prywatności danych.

## Historia kodowania

{image filename="shannon-juggling.png" alt="Cartoon of Claude Shannon juggling and riding a unicycle."}
{comment image from http://csunplugged.org/information-theory/}

Idea kodowania danych w celu skrócenia zapisu, uodpornienia na błędy lub zabezpiecznia prywatności jest znana od wieków, jednakże twarda teoria potrzebna do stworzenia kodów dla ery informacyjnej została rozwinięta dopiero w latach czterdziestych -- nie powinno to być zaskoczeniem biorąc pod uwagę rolę jaką odegrała technologia w II wojnie światowej, podczas której wydajność, niezawodność i tajność były bardzo ważne. Jednym z najbardziej uznanych naukowców w tej dziedzinie był Claude Shannon, który rozwinął dyscyplinę *teorii informacji* zajmującą się efektywną reprezentacją danych (Shannon był również żonglerem, cyklistą oraz wynalazcą pomysłowych maszyn).


{panel type="curiosity" title="Ciekawostka" summary="Entropia"}

Kluczowym pojęciem w pracach Shannona jest miara informacji zwana *entropią*, która wyznacza matematyczne ograniczenia tego jak małe mogą być skompresowane pliki, oraz ile dodatkowych bitów trzeba poświęcić na kody korekcji błędów, aby osiągnąć zamierzony poziom niezawodności. Pomimo tego, iż szczegółowe wytłumaczenie entropii wykracza poza zakres tego podręcznika, zawarte są w nim pewne gry, które dostarczają intuicji jak można mierzyć zawartości informacji poprzez zgadywanie kolejnych liter. Dla przykładu, wymyśl zdanie i zapytaj kolegi czy potrafi odgadnąć pierwszą literę. W języku angielskim istnieje duże prawdopodobieństwo, że będą to litery „T”, „A” lub „I”, a nie „X” lub „Z”. Jeśli po jakimś czasie zgadniesz, że początkiem zdania jest „Wlazł kote”, to prawdopodobnie domyślisz się, że następną literą jest „k”. Entropia mówi nam jak łatwo jest odgadnąć następną literę; to z kolei przydaje się w kompresji (dajemy krótkie kody literom, które mają duże prawdopodobieństwo wystąpienia), oraz w korekcji błędów (jeśli pojawi się błąd to powinno być łatwo „odgadnąć” jaki był oryginalny tekst).

Ideę entropii pomoże Ci zrozumieć
[ćwiczenie interaktywne Dwadzieścia pytań (w języku angielskim)](http://csunplugged.org/information-theory),
oraz [gra w zgadywanie zdań online (również w języku angielskim).](http://www.math.ucsd.edu/~crypto/java/ENTROPY).
{panel end}

## Dalsza lektura

Ksiażka Jamesa Gleicka [*Informacja. Bit, wszechświat, rewolucja*](https://www.znak.com.pl/kartoteka,ksiazka,3364,Informacja) ciekawie opowiada o kilku dziedzinach związanych z kodowaniem.

### Ciekawe odnośniki
Wszystkie materiały są po angielsku.
- Materiały dotyczące wszystkich trzech rodzajów kodowania znajdziesz w [zasobach Bletchley Park](http://www.cimt.org.uk/resources/codes/index.htm)
- [Entropia i teoria informacji](https://en.wikipedia.org/wiki/Entropy_(information_theory))
- [Historia teorii informacji oraz z jej związki z entropią w termodynamice](https://en.wikipedia.org/wiki/History_of_entropy#Information_theory)
- [Chronologia rozwoju teorii informacji](https://en.wikipedia.org/wiki/Timeline_of_information_theory)
- [Pionierska praca Shannona w dziedzinie teorii informacji](https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication)
