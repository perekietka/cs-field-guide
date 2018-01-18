# Algorytmy

{comment explain different views of algorithm (programming context) and Algorithm (that have interesting complexity); use https://www.youtube.com/watch?v=6hfOvs8pY1k for the former?}

{video url="https://www.youtube.com/embed/FOwCCvHEfY0"}

## Z perspektywy

Działanie każdego z urządzeń komputerowych, jakie znasz, nawet prosty kalkulator szkolny, bazuje na algorytmach. To pojęcie jest bardzo ważnym pojęciem w informatyce. Trudno wyobrazić sobie tworzenie sprawnego, efektywnego i bezbłędnie działającego oprogramowania bez korzystania z algorytmów. Już na początku trzeba podkreślić, że może być wiele algorytmów rozwiązujących dany problem, ale niektóre są o wiele lepsze od pozostałych!

{interactive name="sorting-algorithm-comparison" type="in-page"}

Komputery z niesamowitą szybkością przetwarzają informacje. Okazuje się, że ich moc może okazać się jednak niewystarczająca, jeśli chcielibyśmy ogromne zbiory danych przetwarzać (choćby przeszukiwać) w sposób mało przemyślany. Czas reakcji komputera na zadanie czy pytanie użytkownika nie może być zbyt długi. To byłoby frustrujące, niezależnie od tego, jak atrakcyjna jest szata graficzna programu. Z pewnością firmy takie jak Google, Facebook czy Twitter nie mogłyby sobie na to pozwolić! 
Tutaj jest miejsce na pomysłowe efektywne algorytmy, które w rozsądnym czasie poradzą sobie w przetwarzaniem nawet ogromnych zbiorów danych.

### Algorytmy, programy komputerowe i inne sposoby zapisu algorytmów

Być może ktoś myśli, że algorytmy i programy komputerowe to jedno i to samo. Takie twierdzenie jest nieuprawnione. 
Istnieją różne sposoby opisu instrukcji do wykonania, o bardzo różnych poziomach szczegółowości:

Człowiek zrozumie instrukcję wypowiedzianą w języku naturalnym, np. ,,Proszę podać mi szklankę wody''. Komputery prawdopodobnie nie!

{interactive name="high-score-boxes" type="whole-page" text="High Score Boxes"}

Oto prosty przykład: Chcesz znaleźć najlepszy wynik w tablicy wyników liczbowych, która nie jest uporządkowana. Rozwiązaniem jest sprawdzenie liczb jedna po drugiej i pamiętywanie w każdym kroku największej znalezionej do tej pory. Co to jednak miałoby znaczyć konkretnie dla komputera? Taki zwięzły opis metody będzie być może zrozumiały dla człowieka, ale bezużyteczny dla maszyny.

{glossary-definition term="Algorithm" definition="A step by step process that describes how to solve a problem and/or complete a task, which will always give a result."}

Algorytm to opis kolejnych kroków potrzebnych do poprawnego rozwiązania problemu (zadania).

Algorytm dostarczenia szklanki wody można by zapisać jako listę kroków:
1) Idź do kuchni. 2) Weź szklankę. 3) Odkręć kran. 4) Podstaw szklankę i nalej wodę. 5) Zakręć kran. 6) Zanieś szklankę osobie, którą prosiła o wodę.  
Choć opis jest szczegółowy, to jednak ciągle jest to język naturalny. Informatycy posługują się bardziej sformalizowanymi opisami.

Algorytmy komputerowe w podręcznikach często zapisuje się w postaci [pseudokodu](https://en.wikipedia.org/wiki/Pseudocode),
który przypomina kod języka programowania, ale pozbawiony jest szczegółów technicznych, które są istotne wyłącznie dla programisty.

Algorytm znajdowania wartości największej w tablicy, zapisany w pseudokodzie może wyglądać tak:

```
Jeżeli tablica jest pusta,
  to zakończ.
W przeciwnym przypadku, zapamiętaj pierwszą wartość w tablicy.
Dla każdej z pozostałych wartości w tablicy wykonaj:
  Jeżeli ta wartość jest większa od zapamiętanej, 
    to zastąp wartość pamiętaną na tę wartość.
Wyświetl zapmiętaną wartość.
```

Algorytmy zapisane w pseudokodzie lub jako lista kroków to ciąg jednoznacznych instrukcji, zrozumiałych dla informatyka;
mimo to nie jest to jeszcze ten poziom precyzji sfmormułowań, jaki wymagany jest od instrukcji przeznaczonych do wykonania przez komputer.

Algorytm powinien być tak zapisany, na takim poziomie szczegółowości, żeby można było oszacować jego efektywność.
Osoba, która przeanalizuje przedstawiony wyżej algorytm znajdowania największej wartości w tablicy, nie powinna mieć wątpliwości, że że podwojenie rozmiaru tablicy skutkowałoby podwojeniem czasu wykonania.
Taka wiedza ma ogromne znaczenie: algorytm jest wystarczająco szybki dla małych tablic wyników, ale niepraktyczny dla wielodostepnych (obługujących wielu użytkowników) systemów internetowych przetwarzających ogromne zbiory danych, które wymagałyby istnienia tablicy o milonach wyników.

Najbardziej precyzjnym sposobem zapisu listy instrukcji algorytmu jest kod źródłowy programu komputerowego, zapisany w konkretnym języku programowania. Taka forma zapisu algorytmu stanowi kod zrozumiały dla komputera.

Algorytm dostarczenia szklanki wody można by zapisać w formie programu komputerowego, który wykonałby robot. Oczywiście programista musiałby użyć języka programowania, który rozumie komputer wbudowany w robota.

Poniżej zapisano algorytm znajdowania największej wartości w tablicy. Użyto języka Python.
Trzeba podkreślić, że nawet w tym jednym konkretnym języku programowania można by na wiele sposobów zapisać ten sam algorytm. Różni programiści mogliby zapisać pewne szczegóły techniczne w trochę inny sposób.

```python3
def znajdz_najwiekszy(wyniki):
    if len(wyniki) == 0:
        print("Tabela wyników jest pusta.")
        return -1
    else:
        najwiekszy = wyniki[0]
        for wynik in wyniki[1:]:
            if wynik > najwiekszy:
                najwiekszy = wynik
        return najwiekszy
```

Poniżej ten sam algorytm przedstawiono w języku Scratch.
{image filename="highscore-in-scratch.png" alt="High score program in Scratch"}

Oba programy realizują ten sam algorytm. 

W tym rozdziale, w dalszej części, zajmiemy się tematem algorytmów bardziej szczegółowo. Koncepcja algorytmu jest fundamentalną koncepcją informatyki. Interesować będą nas algorymy same w sobie, a nie ich konkretne komputerowe realizacje.

{glossary-link term="Algorithm" reference-text="algorithm cost"}{glossary-link end}

### Koszt algorytmu

Kiedy informatycy porównują dwa algorytmy rozwiązujące ten sam problem, to często używają określenia ,,koszt algorytmu''. Mówi się o zależności sprawności lub pracochłonności algorytmu od rozmiaru danych wejściowych (oznaczmy ten rozmiar jako *n*).
W tym rozdziale koszt działania algorytmu będziemy mierzyć albo badając czas wykonania programu (realizującego algorytm), albo zliczając liczbę kroków, operacji podstawowych algorytmu.

Jednym ze sposobów określenia kosztu algorytmu znajdowania największej wartości w tablicy może być zliczenie operacji odczytu wartości z tablicy. Okazuje się, że jeśli tablica składa się z 10 elementów, to operacji jest 10. Podwojenie liczby elementów tablicy prowadzi do podwojenia liczby operacji.
Można więc powiedzieć, że liczba operacji jest proporcjonalna do *n*.
Nie wszystkie algorytmy mają tę własność; niektóre algorytmy są o wiele bardziej kosztowne, a niektóre mniej kosztowne;
Warto, aby programista potrafił określić pracochłonność algorytmu, zanim zdecyduje się nim posłużyć. Program komputerowy musi być skalowalny. Gra komputerowa, którą programista stworzył, może okazać się bardzo popularna, więc algorytm znajdowania najlepszego wyniku musi być wystarczająco szybka.

{panel type="extra-for-experts" "Złożoność obliczeniowa algorytmów"}
Szacowanie kosztów algorytmu znane jest w informatyce pod nazwa [analiza algorytmu](https://en.wikipedia.org/wiki/Analysis_of_algorithms). Taka analiza powinna prowadzić do wyznaczenia *złożoności obliczeniowej* algorytmu (dotyczącej czasu wykonania), ale częśto i zlożności pamięciowej (dotyczącej ilości pamięci, potrzebnej podczas uruchomienia programu).

Więcej informacji na temat określania kosztu algorytmu, m.in. o notacji "duże-O", znajduje się w podrozdziale ["Podsumowanie"](chapters/algorithms.html#the-whole-story) .
{panel end}

Trzeba podkreślić, że czas potrzebny różnym komputerom do realizacji tego samego algorytmu i tych samych danych może być różny. Zależy to od parametrów komputerów, ilości zasobów przydzielonych do wykonania zadania, ale i od języka programowania, w którym algorytm został zakodowany. Dlatego trzeba być ostrożnym w wyciąganiu pochopnych wniosków o koszcie algorytmu tylko na podstawie czasu wykonania programu. 

Znacznie lepszą miarą jest zliczanie operacji (takich jak porównywanie dwóch wartości), które są właściwe danemu algorytmowi. 


### Przeszukiwanie i porządkowanie

In this chapter we will look at two of the most common and important types of algorithms, Searching and Sorting. You probably come across these kinds of algorithms every time you use a computer without even realising!
They also happen to be great for illustrating some of the key concepts that arise with algorithms.
W tym rozdziale przyjrzymy się dokładniej dwu najważniejszym typom algorytmów: przeszukiwania i porządkowania danych. Prawdopodobnie każdy z nas z jednym z tych typów problemów już się musiał zmierzyć, być może nie do końca świadomie!

Na przykładach tych typów algorytmów można w ciekawy sposób przedstawić kluczowe koncepcje projektowania i analizy algorytmów.

{glossary-link term="Algorithm" reference-text="searching algorithms"}{glossary-link end}

## Przeszukiwanie

{panel type="teacher-note" summary="Prezentacja tematu w klasie"}

Gry zaproponowane w tym podrozdziale są wzorowane na scenariuszu [Gra w statki](http://csunplugged.com/searching-algorithms). Pierwsza dotyczy algorytmu przeszukiawnia liniowego (zwanego też sekwencyjnym), a druga algorytmu przeszukiwania binarnego.

Wszyscy uczniowie w klasie powinny w tym samym czasie zagrać w każdą z gier. Po zakończeniu pierwszej gry (obu części) nauczyciel powinien poprowadzić krótką dyskusję. Może zacząć od pytań: "Komu udało się zakończyć grę z sukcesem już w pierwszej próbie?", "Kto potrzebował sprawdzić wszyskie pudełka?". Warto wyznaczyć wartość średnią liczby prób.

Po zakończeniu przez wszystkich uczniów drugiej gry nauczyciel może zapytać: "Czy pięć pytań to nie za mało, aby zakończyć grę z sukcesem?", "Jaką strategią można się posłużyć?". Może się okazać, że wielu uczniów nieświadomie posługiwało się metodą dwudzielną (binarnym przeszukiwaniem). 

Gier nie powinno się pomijać. Te aktywności powinny poprzedzić prezentację tematu przez nauczyciela.
{panel end}

Przeszukiwanie różnych zbiorów danych zajmuje znaczącą część pracy wielu komputerów. Gdy używasz wyszukiwarki Google'a, to w istocie prowadzisz dialog z programem przeszukującym indeksy baz danych na serwerach wyszukiwarki. Komputery często muszą przetwarzać ogromne ilości danych, a to oznacza, że potrzebują szybkich algorytmów.

Zdobywanie wiedzy na ten temat zacznij od poniższej gry...

{interactive name="searching-algorithms" type="whole-page" text="Searching Boxes - Part 1" parameters="max=2"}

Cechą charakterystyczną tej gry było losowae rozmieszczenie liczb. Skutek był taki, że sukces zależał najpierw od szczęścia! 
Wyobraź sobie, że pudełek jest 1000, czy nawet 1 000 000! Przeszukiwanie takich zbiorów trwałoby długo.

Kolejna gra różni się od poprzedniej. Liczba dopuszczalnych prób będzie mniejsza, ale tym razem liczby będą rozmieszczone od najmniejszej (po lewej) do największej (po prawej). Wyzwaniem będzie zakończyć grę z sukcesem. To jest jednak możliwe! 

{interactive name="searching-algorithms" type="whole-page" text="Searching Boxes - Part 2" parameters="level=3" thumbnail="thumbnail2.png"}

Dlaczego w drugiej grze wygrana była zawsze możliwa? Na czym opiera się zwycięska strategia?


### Przeszukiwanie liniowe

Since the boxes in the first game were in a random order there really wasn't any strategy you could have used to find the pet, except simply keep opening presents one by one until you found the pet. This is essentially the *Linear Search* algorithm (sometimes called a sequential search). In plain English, Linear Search algorithm is as follows:
W pierwszej z gier pudełka były w przypadkowej kolejności. Trudno więc mówić o stosowaniu jakiejkolwiek strategii przeszukiwania. Konieczne było sprawdzanie pudełek jedno po drugim, aż do skutku. W informatyce mówi się w takim przypadku o *przeszukiwaniu liniowym* (czasami o przeszukiwaniu sekwencyjnym). Taki algorytm można by opisać listą kroków:
- Sprawdź, czy pierwszy element listy jest tym, który jest poszukiwany. Jeśli tak, to zakończ przeszukiwanie.
- W przeciwnym przypadku, sprawdź kolejny element listy.
- Kontynuuj przeszukiwanie, aż znajdziesz element, który jest poszukiwany.

W przypadku przeszukiwania listy 10 elementów, średnia liczba prób prowadzących do sukcesu to 5. Dla listy 10 000 elementów tych prób będzie średnio 5000. Oczywiście w konkretnym przypadku liczba prób może być mniejsza od średniej, nawet znacznie mniejsza, albo i większa.

{panel type="curiosity" summary="Przeszukiwanie metodą Bozo-Search?"}
W filmie na początku rozdziału pojawił się zabawny przykład przeszukiwania, zwany po angielsku Bozo-Search. Od przeszukiwania liniowego różni się tym, że wielokrotnie może być sprawdzany ten sam element zbioru (np. zawartość pudełka), gdyż element raz sprawdzony nie jest odrzucany (po prostu wraca do zbioru elementów).
{panel end}

### Przeszukiwanie binarne

{glossary-definition term="Binary Search" definition="Searching a sorted list by looking at the middle item, and then searching the appropriate half recursively (used for phone books, dictionaries and computer algorithms)."}

W drugiej z gier pudełka były uporządkowane, co umożliwiło podejmowanie kolejnych prób w sposób przemyślany. Być może nieświadomie ktoś stosował algorytm zwany w informatyce przeszukiwaniem binarnym (dwudzielnym).

{panel type="teacher-note" summary="O przeszukiwaniu binarnym z książką telefoniczną"}
Temat algorytmu przeszukiwania binarnego można zilustrować za pomocą książki telefonicznej lub słownika: wybierz nazwisko (lub jakieś słowo), otwórz książkę lub słownik mniej więcej w połowie i sprawdź pierwszy wyraz na stronie, najlepiej tej o numerze nieparzystym. (Jeśli książka jest przeznaczona na makulaturę, to warto dosłownie przedrzeć ją mniej więcej w połowie objętości.) Następnie uczniowie powinni wskazać tę część książki, którą należy przeszukiwać. 
Odrzucenie połowy stron książki, czyli prawdopodobnie setek stron, było możliwe na podstawie tylko jednej decyzji.

Tę strategię połowienia należy stosować dalej. Powtórzyć dla połowy, połowy tej połowy itd. 

Warto przeanalizować z uczniami ciąg liczb, który odpowiada liczbie kartek pozostałych po wykonaniu kolejnych decyzji. 
Na przykład dla 512 kartek będzie to: 256, potem 128, potem 64, 32, 16, 8, 4, 2 i w końcu jedna kartka. To oznacza, że do znalezienia odpowiedniej kartki wystarczy co najwyżej 9 prób.
(Można się posłużyć przykładem z liczbami, które nie są potęgami liczby 2, ale wówczas trzeba by doprecyzować znaczenie ,,połowienia''.)

Siłę przeszukiwania binarnego niektórym być może będzie łatwiej pojąć, gdy zapytamy ich o liczbę prób wystarczających do przeszukania książki o podwojonej liczbie stron. 
Warto podkreślić w czasie zajęć, że na gdyby stworzyć uporządkowaną (np. według nazwisk i imion) listę wszystich ludzi obecnie żyjących na świecie, to potrzeba nie więcej niż 30 prób do znalezienia dowolnej osoby. 
{panel end}

Algorytm przeszukiwania binarnego można by opisać listą kroków:
- Sprawdź, czy element znajdujący się w środku listy jest tym, który jest poszukiwany. Jeśli tak, to zakończ przeszukiwanie.
- W przeciwnym przypadku: Jeśli ten środkowy element ma wartość większą od poszukiwanego, to w dalszych przeszukiwaniach pomiń elementy listy po prawej stronie środkowego. (Jeśli lista jest uporządkowana od nawiększego do najmniejszego, to pomiń elementy po lewej.)
Jeśli ten środkowy element ma wartość mniejszą od poszukiwanego, to w dalszych poszukiwaniach pomiń elementy mniejsze od środkowego.
- Kontynuuj przeszukiwanie, aż znajdziesz element, który jest poszukiwany.

{panel type="spoiler" summary="Jak podwojenie liczby pudełek wpływa na liczbę prób podczas przeszukiwania?"}
W przypadku przeszukiwania liniowego niezbędna liczba prób wzrośnie dwa razy. W przypadku przeszukiwania binarnego wzrośnie tylko o jedno! 
{panel end}

Jest ważne, by pamiętać, że przeszukiwanie binarne można stosować tylko dla zbiorów uporządkowanych. To oznacza, że algorytmy porządkowania należy uznać za jeszcze ważniejsze!


{panel type="project" summary="Zakodowane algorytmy przeszukiwania"}
Poniżej znajdują się odnośniki do komputerowych realizacji algorytmów przeszukiwania zapisanych w różnych językach; możesz się nimi posłużyć do przygotowania list losowych wartości i porównania kosztów wykonania programów.
Twoje zadanie polega na wykonaniu pomiarów czasu działania programów dla coraz większych wartości (*n*); wyniki spróbuj przedstawić na wykresie.
- [Scratch](files/linear-binary-search-scratch.zip) - [Download Scratch here](https://scratch.mit.edu/scratch2download/)
- [Python (Version 2)](files/linear-binary-search-python2.py) - [Download Python 2 here](https://www.python.org/downloads/)
- [Python (Version 3)](files/linear-binary-search-python3.py) - [Download Python 3 here](https://www.python.org/downloads/)
{panel end}

{glossary-link term="Algorithm" reference-text="sorting algorithms"}{glossary-link end}

## Porządkowanie

{panel type="teacher-note" summary="Dlaczego o sortowaniu?"}
Powyżej przedstawione zostały główne zagadnienia: pojęcie algorytmu, pracochłonność (koszt) algorytmu, przykłady algorytmów o różnych kosztach (proporcjonalne do liczby danych wejściowych, ale i inne).
Warto przywołać jeszcze kilka innych przykładów algorytmów komputerowych. I opisać ich własności. 
Algorytmy porządkowania mają duże walory dydaktyczne, gdyż na ich przykładzie można ukazać kluczowe zagadnienia z dziedziny algorytmów. 
{panel end}

Porządkowanie danych to innych bardzo ważny temat z dziedziny algorytmów. Komputery często muszą porządkować duże zbiory danych. Kryteria porządkowania mogą być różne, mogą się zmieniać. Użytkownik komputera czasami chce zobaczyć listę plików uporządkowaną według nazw, a czasem według rozmiaru itp. Lista klientów zwykle jest porządkowana według nazwisk. 
Uporządkowanie danych ułatwia ich przeszukiwanie. 
Jak zwykle uporządkowane są informacje w książce telefonicznej telefonu? Według nazwiska, czy według numerów telefonów? Dlaczego?

Wymyślono wiele algorytmów porządkowania. W tym podrozdziale przedstawione będą trzy: dwa mniej efektywne i jeden bardzo szybki.

### Waga szalkowa (online)

Udostępniamy interaktywne narzędzie z wirtualną wagą szalkową do testowania algorytmów opisanych poniżej. U dołu ekranu pojawia się informacja o liczbie porównań (ważeń): każde ważenie to jedno porównanie. Koszt algorytmu będzie określony liczbą porównań użytych do uporządkowania 8 pudełek. Zakładamy, że na każdej szalce wagi kładzie się jedno pudełko.

Pudełka należy uporządkować od najlżejszego po lewej do najcięższego po prawej. Do sprawdzenia użyj przycisku ,,Sprawdź porządek''.

Możesz posłużyć się prawdziwą wagą szalkową. Odważniki trzeba tak przygotować, żeby dla każdej pary odważników można było określić, który z odważników jest cięższy.

{interactive name="sorting-algorithms" type="whole-page" text="Scales interactive"}


### Porządkowanie przez wybór

Jednym z najbardziej intuicyjnych sposobów porządkowania jest: zacząć od znalezienia najlżejszego (lub najcięższego) pudełka i odłożyć je na bok. Spróbuj to zrobić z użyciem wagi szalkowej. Zapisz liczbę wykonanych porównań.

Po znalezieniu najlżejszego pudełka znajdź drugie najlżejsze pudełko w ten sam sposób i ustaw je obok najlżejszego. Zapisz liczbę porównań.
Powtarzaj poszukiwanie kolejnych najlżejszych, na danym etapie, pudełek, aż wszystkie pudełka będą uporządkowane. Zapisuj liczbę porównań.
Ile porównań (ważeń) zostało wykonanych?

Wskazówka: Zacznij od przeniesienia wszystkich pudełek na prawą stronę ekranu. (Jeśli szukasz najcięższego, to przenieś pudełka na lewą stronę ekranu.)

Przeanalizuj notatki dotyczące liczby porównań. Dostrzegasz jakąś prawidłowość? Ile porównań było wykonywanych w kolejnych etapach wybierania najlżeszych pudełek? Ile porównań łącznie byłoby wykonanych, gdybyśmy porządkowali zbiór 9 pudełek? Ile dla 20 pudełek? Załóżmy, że wiesz, ile porównań potrzeba do uporządkowania 1000 pudełek tym algorytmem. O ile więcej byłoby potrzebnych, gdyby pudełek było 1001?

{panel type="teacher-note" summary="Odpowiedzi"}
Dla pudełek mamy kolejno: 7 porównań do znalezienia najlżejszego, 6 do znalezienia drugiego najlżejszego, 5 do znalezienia następnego, potem 4, potem 3, 2 i w końcu 1 porównanie (gdy zostaną dwa pudełka do porównania). W sumie mamy:  7+6+5+4+3+2+1 = 28 porównań. 
Gdyby pudełek było 9, to porównań byłoby: 8+7+6+5+4+3+2+1 = 36. Dla 20 pudełek byłoby 190 porównań. Liczba porównań w algorytmie dla przypadku 1001 pudełek będzie o 1000 większa niż w przypadku 1000 pudełek. 
Algorytm porządkowania przez wybór wymaga wykonania {math}(n\times(n-1))/2{math end} porównań do uporządkowania *n* elementów.

Dla przykładu wyznaczmy liczbę porównań dla 20 pudełek (*n* = 20):

(20*(20-1))/2

= (20*19)/2

= 380/2

= 190 porównań

Niektórzy uczniowie mogą znać anegdotę o Gaussie (zobacz [Wikipedia](https://en.wikipedia.org/wiki/Carl_Friedrich_Gauss#Anecdotes). 
W wersji dla 20 obliczenia przypisywane młodemu matematykowi wyglądałyby tak: 
Sumę 1+2+3+...+17+18+19 zapisujemy wspak (19+18+17+...3+2+1) w taki sposób, aby 19 znalazło się pod 1, 18 pod 2, 17 pod 3 itd. Otrzymuejmy 19 par: (1+19)+(2+18)+(3+17)+...+(17+3)+(18+2)+(19+1). Ta suma jest równa: 20x19. Liczba porównań jest więc równa 20x19/2 = 190 (każdy składnik sumy występuje dwa razy).  
Warto obejrzeć [to video](http://www.numberphile.com/videos/one_to_million.html) i zapoznać się z innymi przykładami [na tej stronie](http://nzmaths.co.nz/gauss-trick-staff-seminar).
{panel end}

Przedstawiony wyżej algorytm nazywa się porządkowaniem przez wybór (selekcję).
Taki algorytm można by opisać listą kroków:
- Znajdź najmniejszy element na liście. Umieść go na początku nowej listy.
- Znajdź najmniejszy element wśród pozostałych na liście. Umieść go na drugiej liście obok elementu ustawionego tam po poprzednim przeszukiwaniu.
- Kontynuuj przeszukiwanie listy, aż wszystkie elementy znajdą się na drugiej liście. Ta lista będzie uporządkowana.

W powyższym opisie można zastąpić słowo ,,najmniejszy'' słowem ,,największy'' i algorytm będzie nadal poprawny. Oczywiście w tym przypadku porządek elementów na liście będzie odwrócony (od największego do najmniejszego).

### Porządkowanie przez wstawianie

{panel type="teacher-note" summary="This section could be skipped"}
This algorithm is useful and commonly taught, although for the purpose of teaching the principles of algorithms, it's doesn't add a lot to what we've just covered with selection sort, so could be skipped.
However, if you have time, it's worth looking at for extra examples.
{panel end}
This algorithm works by removing each box from the original group of boxes and inserting it into its correct position in a new sorted list. Like Selection Sort, it is very intuitive and people often perform it when they are sorting objects themselves, like cards in their hands.

Try this with the scales interactive. Start by moving all the boxes to one side of the screen, this is your original, and unsorted, group. Now choose a box at random and place that on the other side of the screen, this is the start of your sorted group.

To insert another box into the sorted group, compare it to the box that is already in the sorted group and then arrange these two boxes in the correct order. Then to add the next box compare it to these boxes (depending on the weight of the box you might only have to compare it to one!) and then arrange these three boxes in the correct order. Continue inserting boxes until the sorted list is complete. Don't forget to count how many comparisons you had to make!

This algorithm is called Insertion Sort. If you're not quite sure if you've got the idea of the algorithm yet then have a look at [this animation](https://upload.wikimedia.org/wikipedia/commons/0/0f/Insertion-sort-example-300px.gif) from [Wikipedia](https://en.wikipedia.org/wiki/Insertion_sort).

Insertion sort can be described with informal instructions as follows:
- Take an item from your unsorted list and place it to the side, this will be your sorted list.
- One by one, take each item from the unsorted list and insert it into the correct position in the sorted list.
- Do this until all items have been sorted.

People often perform this when they physically sort items. It can also be a very useful algorithm to use if you already have a sorted set of data and want to add a new piece of data into the set. For example if you owned a library and purchased a new book you wouldn't do a Selection Sort on the entire library just to place this new book, you would simply insert the new book in its correct place.


{glossary-definition term="Quicksort" definition="A process for achieving an outcome, normally for a general problem such as searching, sorting, finding an optimal path through a map and so on."}

### Porządkowanie szybkie (Quicksort)

Insertion and Selection Sort may seem like logical ways to sort things into order, but they both take far too many comparisons when they are used for large amounts of data. Remember computers often have to search through HUGE amounts of data, so even if they use a good searching algorithm like Binary Search to look through their data, if they use a bad sorting algorithm to first sort that data into order then finding anything will take far too long!

O wiele lepszym algorytmem porządkowania jest metoda {glossary-link term="quicksort"}Quicksort!{glossary-link end} 

{interactive name="sorting-algorithms" type="whole-page" text="Quicksort interactive" parameters="method=quick" thumbnail="thumbnail-quick.png"}

This algorithm is a little more complicated, but is very powerful. To do this algorithm with the sorting interactive, start by randomly choosing a box and placing it on the scales. Now compare every other box to the one you selected; heavier boxes should be put on the right of the second row and lighter boxes are put on the left. When you are done, place the box you were comparing everything else to between these two groups, but to help you keep track of things, put it in the row below. The following example shows how it might look after this step. Note that the selected block is in the right place for the final sorted order, and everything on either side will remain on the side that it is on.

{image filename="quicksort-interactive-step-1.png" alt="Quicksort interactive in progress"}

Now apply this process to each of the two groups of boxes (the lighter ones, then the heavier ones). Keep on doing this until they are all sorted. The boxes should then be in sorted order!

It might be worth trying this algorithm out a few times and counting the number of comparisons you perform each time. This is because sometimes you might be unlucky and happen to pick the heaviest, or the lightest box first. On the other hand you might be very lucky and choose the middle box to compare everything to first. Depending on this the number of comparisons you perform will change.

Quicksort can be described in the following way:
- Choose an item from the list and compare every other item in the list to this (this item is often called the pivot).
- Place all the items that are greater than it into one subgroup and all the items that are smaller into another subgroup. Place the pivot item in between these two subgroups.
- Choose a subgroup and repeat this process. Eventually each subgroup will contain only one item and at this stage the items will be in sorted order.

{panel type="project" summary="Code to run selection sort and quicksort for yourself"}
The following files will run selection sort and quicksort in various languages; you can use them to generate random lists of values and measure how long they take to be sorted.
Note how long these take for various amounts of input (*n*), and show it in a table or graph.
You should notice that the time taken by Quicksort is quite different to that taken by selection sort.
- [Scratch](files/selection-quicksort-scratch.zip) - [Download Scratch here](https://scratch.mit.edu/scratch2download/)
- [Python (Version 2)](files/selection-quicksort-python2.py) - [Download Python 2 here](https://www.python.org/downloads/)
- [Python (Version 3)](files/selection-quicksort-python3.py) - [Download Python 3 here](https://www.python.org/downloads/)
{panel end}

There are dozens of sorting algorithms that have been invented; most of the ones that are used in practice are based on quicksort and/or mergesort. These, and many others, can be seen in this intriguing animated video.

{video url="https://www.youtube.com/watch?v=kPRA0W1kECg"}

## Podsumowanie

We've only really scratched the surface of algorithms in this chapter, as there are millions of different algorithms for millions of different problems! Algorithms are used in maths, route planning, network planning and operation, problem solving, artificial intelligence, genetic programming, computer vision, the list goes on and on! But by going through this chapter you should have gained an understanding of the key concepts of algorithms and will be well prepared to tackle more complicated ones in the future.

The algorithms introduced in this chapter aren't even necessarily the best for any situation; there are several other common ways of searching (e.g. hashing and search trees) and sorting (e.g. mergesort), and a computer scientist needs to know them, and be able to apply and fine tune the right one to a given situation.

In this chapter we have only talked about the number of comparisons an algorithm makes, and the amount of time a program takes to complete as 'costs' of algorithms. There are actually many other ways of measuring the cost of an algorithm. These include the amount of memory the algorithm uses and its computational complexity. Computer Scientists use 'Big O notation' to more accurately describe the performance or complexity of an algorithm, and you are likely to come across this notation very quickly when investigating the performance of algorithms. It characterises the resources needed by an algorithm and is usually applied to the execution time required, or sometimes the space used by the algorithm.

{panel type="extra-for-experts" summary="Examples of Big O notation"}
Here are some Big O examples:
- {math}O(1){math end} - An algorithm with {math}O(1){math end} complexity will always execute in the same amount of time regardless of how much data you give it to process. For example, finding the smallest value in a sorted list is always easy.
- {math}O(n){math end} - The amount of time an algorithm with {math}O(n){math end} complexity will take to execute will increase roughly linearly with (i.e. in direct proportion to) the amount of data you give it to process. The high-score algorithm was {math}O(n){math end}, and so was the linear search.
- {math}O(n^{2}){math end} - The performance of an algorithm with this complexity is roughly proportional to the square of the size of the input data set. Selection sort and insertion sort take {math}O(n^{2}){math end} time. That's not very good value - 10 times the amount of input will take 100 times as long!
- {math}O(2^{n}){math end} - The amount of time an algorithm with this complexity will take to complete will double with each additional element added to the data set! We haven't seen these kinds of situations in this chapter, but they are common, and are a theme of the Complexity and Tractability chapter. Algorithms that are this slow can be almost impossible to use!
{panel end}

Big O Notation however requires some advanced mathematics to explore thoroughly so has been intentionally left out of this main chapter, but if you want to learn more check out the Useful Links section. These topics are looked at in more depth in the Complexity and Tractability chapter.

To make things even more complicated, in practice algorithms are running on computers that have cached memory and virtual memory, where the time to access a particular value can be particularly short, or particularly long. There is a whole range of algorithms that are used for this situation to make sure that the algorithm still runs efficiently in such environments. Such algorithms are still based on the ideas we've looked at in this chapter, but require some clever adjustments to ensure that they work well.

## Do dalszej lektury

### Inne zagadnienia algorytmiczne

- Istnieje metoda przeszukiwania zbiorów danych, lepsza od przeszukiwania binarnego. Nazywa się haszowaniem (ang. "to hash" oznacza "posiekać"). Łagodne wprowadzenie do tematu znajdziesz w materiałach pt. [Gra w statki](http://csunplugged.org/searching-algorithms).
- Istnieją problemy, dla których nie znaleziono dobrych algorytmów, a nawet takie, których prawdopoodbnie nigdy nie da się rozwiązać w efektywny sposób. Więcej na ten temat piszemy w rozdziale o złożoności obliczenionej algorytmów i pojęciu praktycznej wykonalności algorymów.

### Ciekawe linki

- [CS Unplugged i algorytmy przeszukiwania](http://csunplugged.org/searching-algorithms)
- CS Unplugged [i algorymy sortowania](http://csunplugged.org/sorting-algorithms)
- [Gra na temat przeszukiwania (http://csunplugged.org/divideAndConquer)
- Wikipedia has more details on [Przeszukiwanie liniowe](https://en.wikipedia.org/wiki/Linear_search), [Przeszukiwanie binarne](https://en.wikipedia.org/wiki/Binary_search), [Sortowanie przez wybór](https://en.wikipedia.org/wiki/Selection_sort), [Sortowanie przez wstawianie](https://en.wikipedia.org/wiki/Insertion_sort) and  [Quicksort](https://en.wikipedia.org/wiki/Quicksort).
- [Sortowanie cegieł (gra)](http://mathsite.math.berkeley.edu/sorting/brick.html) do nauki algorytmów sortowania (wymaga obługi Javy przez przeglądarkę).
- [Wizualizacja algorytmów sortowania](http://www.sorting-algorithms.com/) przestawia różne algorytmy sortowania, są zapisane w pseudokodzie.
- [Wprowadzenie do notacji dużego O](http://rob-bell.net/2009/06/a-beginners-guide-to-big-o-notation/)
