# Kodowanie - wprowadzenie

## What's the big picture?

Słowo “kod” ma wiele znaczeń w informatyce. Często używa się go mówiąc o programowaniu (jako o kodowaniu), a treść programu nazywa się “kodem źródłowym”. Nawet reprezentację binarną informacji określa się mianem kodu. Jednakże w tym rozdziale (oraz w kolejnych trzech rozdziałach) sens tego słowa będzie wyrażony jako sprytny sposób reprezentacji informacji, który przy okazji pozwala na rozwiązanie jednego z praktycznych problemów, takich jak szyfrowanie danych w celu zachowania ich w tajemnicy.

W poprzednim rozdziale zajmowaliśmy się binarną reprezentacją pozwalającą zapisywać różne rodzaje danych --- liczby, tekst, obrazy itp. Jednakże w wielu sytuacjach prosta reprezentacja binarna nie sprawdza się. Czasami zajmuje za dużo miejsca, innym razem mały błąd w zapisie może spowodować olbrzymi problem, a w innym przypadku naszym zmartwieniem może być fakt, że ktoś przeczyta naszą wiadomość. Bardzo często wszystkie trzy wspomniane problemy są istotne. Kody, którymi się zajmiemy radzą sobie właśnie z tymi problemami, i są powszechnie wykorzystywane w zapisywaniu i przesyłaniu informacji.

Trzy główne powody, dla których stosujemy skomplikowane reprezentacje danych to:
- **Kompresja:** pozwala zredukować przestrzeń jaką potrzebują dane (np. zakodowanie pliku audio do formatu MP3 pozwala zmniejszyć rozmiar do 10% rozmiaru początkowego).
- **Szyfrowanie:** zmienia reprezentację danych w ten sposób, iż potrzebny jest “klucz” aby odczytać wiadomość (np. jeżeli przeglądarka internetowa korzysta z “https” zamiast “http”, to cała komunikacja ze stroną internetową jest zaszyfrowana, tak aby nikt kto podsłuchuje nie mógł poznać przesyłanych informacji)
- **Korekcja błędów:** dodaje pewne informacje do danych, tak aby w przypadku małych błędów w zapisie lub transmisji można było ten fakt wyryć, a nawet odtworzyć poprawne dane (np. kody kreskowe na produktach posiadają dodatkową cyfrę, która pozwala określić czy kod został prawidłowo zeskanowany w kasie, w przypadku nieprawidłowego skanowania emitowany jest dźwięk ostrzegawczy)

Często wszystkie trzy techniki są używane na tych samych danych, np. jeżeli robimy zdjęcie smartfonem to jest ono zwykle kompresowane kodowaniem JPEG, zapisywane w pamięci telefonu z kodem korekcji błędów, a następnie wysyłane do sieci przez bezprzewodowe połączenie, które jest szyfrowane, tak aby nikt w pobliżu nie mógł sobie skopiować tego zdjęcia.

Bez tych form kodowania współczesne urządzenia elektroniczne byłyby bardzo wolne, posiadały mocno ograniczoną pojemność, byłyby zawodne oraz niezdolne do zachowania prywatności danych.

## Historia kodowania

{image filename="shannon-juggling.png" alt="Cartoon of Claude Shannon juggling and riding a unicycle."}
{comment image from http://csunplugged.org/information-theory/}

Idea kodowania danych w celu skrócenia zapisu, uodpownienia na błędy lub zabezpiecznia prywatności jest znana od wieków, jednakże twarda teoria potrzebna do stworzenia kodów dla ery informacyjnej została rozwinięta dopiero w latach 40-tych --- nie powinno to być zaskoczeniem biorąc pod uwagę rolę jaką odegrała technologia w II wojnie światowej, podczas której wydajność, niezawodność i tajność byłby bardzo ważne. Jednym z najbardziej uznanych naukowców w tej dziedzinie był Claude Shannon, który rozwinął dyscyplinę “teorii informacji” zajmującą się efektywną reprezentacją danych (Shannon był również żąglerem, unicyklistą oraz wynalazcą pomysłowych maszyn).


{panel type="curiosity" summary="Entropy"}

Kluczowym pojęciem w pracach Shannona jest miara informacji zwana “entropią”, która wyznacza matematyczne ograniczenia tego jak małe mogą być skompresowane pliki, oraz ile dodatkowych bitów trzeba poświęcić na kody korekcji błędów, aby osiągnąć zamierzony poziom niezawodności. Pomimo tego, iż szczegółowe wytłumaczenie entropii wykracza poza zakres tego podręcznika, zawarte są w nim pewne gry, które dostarczają intuicji jak można mierzyć zawartości informacji poprzez zgadywanie kolejnych liter. Dla przykładu, wymyśl zdanie i zapytaj kolegi czy potrafi odgadnąć pierwszą literę. W języku angielskim istnieje duże prawdopodobieństwo, że będą to litery “T”, “A” lub “I”, a nie “X” lub “Z”. ??If, after a while, you had guessed that the beginning letters in a sentence are "There is no revers", you'd probably guess that the next letter is an "e". ?? Entropia mówi nam jak łatwo jest odgadnąć następną literę; to z kolei przydaje się w kompresji (dajemy krótkie kody literom, które mają duże prawdopodobieństwo wystąpienia), oraz w korekcji błędów (jeśli pojawi się błąd to powinno być łatwo “odgadnąć” jaki był oryginalny tekst).

You can explore the idea of entropy further using an
Więcej o entropi można się dowiedzieć z 
[Zadnie Dwadzieścia odgadnięć](http://csunplugged.org/information-theory),
oraz [z gry polegającej na zgadywaniu zdań online](http://www.math.ucsd.edu/~crypto/java/ENTROPY).
{panel end}

## Further reading

Ksiażka James'a Gleick'a [The Information: A History, a Theory, a Flood](http://www.amazon.com/The-Information-History-Theory-Flood/dp/1400096235) pokazuje ciekawe spojrzenie na historię kilku dziedzin kodowania.

### Useful Links

- A good collection of resources related to all three kinds of coding is available in the [Bletchley Park Codes Resources](http://www.cimt.plymouth.ac.uk/resources/codes/)
- [Entropy and information theory](https://en.wikipedia.org/wiki/Entropy_(information_theory)
- [History of information theory and its relationship to entropy in thermodynamics](https://en.wikipedia.org/wiki/History_of_entropy#Information_theory)
- [Timeline of information theory](https://en.wikipedia.org/wiki/Timeline_of_information_theory)
- [Shannon's seminal work in information theory](https://en.wikipedia.org/wiki/A_Mathematical_Theory_of_Communication)
