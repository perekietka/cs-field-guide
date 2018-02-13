# Języki programowania

## Z lotu ptaka

Programowanie, czasami nazywane kodowowaniem, jest praktycznym zastosowaniem informatyki. Celem tej książki nie jest oczywiście nauka programowania (dodaliśmy jednakże kilka linków do stron, które mogą służyć jako znakomity wstęp do tego zagadnienia), zobaczymy natomiast, czym jest język programowania i jak informatycy z niego korzystają. Z punktu widzenia programisty kodowanie polega na wpisywaniu instrukcji, które są wykonywane przez komputer. Ale w jaki sposób komputer wie, co robić? Pamiętaj, że możesz używać jednego z wielu języków, takich jak Python, Java, Scratch, Basic lub C#, lecz komputery wyposażone są w sprzęt, który rozumie tylko jeden język, tzw. „kod maszynowy”. Składa się on z bardzo prosty podstawowych instrukcji, które jest trudno czytać i pisać ludziom. Co zrobić, gdy wymyślisz nowy język programowania, jak sprawić by komputer mógł z niego korzystać?

W tym rozdziale przyjrzymy się temu, co dzieje się podczas pisania i uruchamiania programu oraz w jaki sposób wpływa to na sposób, w jaki sposób rozpowszechniany jest program.

Zaczniemy od opcjonalnego podrozdziału o tym, na czym polega programowanie, dla tych, którzy wcześniej nigdy nie programowali. Wprowadzenie do programowania zawiera przykłady bardzo prostych programów w języku Python, które można uruchamiać i modyfikować. Poznanie tego podrozdziału pozwoli zrozumieć dalsze części rozdziału; nie nauczymy cię programowania, ale będziesz mógł prześledzić proces myślenia programisty podczas kodowania. Jeśli masz już pewną wiedzę o programowaniu, to możesz przeskoczyć ten podrozdział.

Poniższa część rozdziału zawiera przegląd zagadnień opisanych w rozdziale, z tego względu zalecana jest jego lektura.

{comment}

.. consider introductory video which mentions role of languages: https://www.youtube.com/watch?v=AkFi90lZmXA

{comment end}

### Czym jest programowanie?

{panel type="teacher-note" summary="Zadanie na rozgrzewkę"}

Spójrz na [zadanie rozgrzewkowe z CSUnplugged](http://csunplugged.org/programming-languages), lub na [rozszerzoną wersję tutaj](http://csunplugged.org/wp-content/uploads/2014/12/tellAndDraw1.5.pdf).

Uczniowie, którzy nigdy wcześniej nie programowali, powinni również przejrzeć materiał w tym podrozdziale. Zawiera on przegląd tego, czym jest programowanie, pozwoli to zrozumieć dalszą część rozdziału.

{panel end}

Uwaga: Ten podrozdział przeznaczony jest dla osób, które nie są zaznajomione z programowaniem. Jeśli masz już pewną wiedzę o programowaniu, możesz pominąć tą część rozdziału.

Oto przykład bardzo prostego programu: ma pięć instrukcji (po jednej w każdym wierszu), które są zapisane w określonej kolejności.

```
print("**********************************************")
print("**********************************************")
print("**** Witaj w nauce programowania, Uczniu *****")
print("**********************************************")
print("**********************************************")
```

Powyższy program został napisany w języku o nazwie Python, a po uruchomieniu wyświetli na ekranie następujący tekst

```
**********************************************
**********************************************
**** Witaj w nauce programowania, Uczniu *****
**********************************************
**********************************************
```

Aby uruchomić program napisany w Pythonie, potrzebujemy tak zwanego interpretera Pythona. Interpreter Pythona jest w stanie odczytać program i przetworzyć go. Poniżej znajduje się interpreter języka Python, którego można używać do uruchamiania własnych programów. Jeśli masz zainstalowany interpreter Pythona na swoim komputerze (poradź się nauczyciela jeżeli czujesz się zdezorientowany) i wiesz, jak z niego korzystać, możesz go użyć.

{interactive name="python-interpreter" type="in-page"}

Spróbuj tak zmienić program, aby zawierał Twoje imię zamiast *uczeń*. Kiedy stwierdzisz, że program jest gotowy, spróbuj go ponownie uruchomić. Upewnij się, czy przez pomyłkę nie usunąłeś podwójnych cudzysłowów lub nawiasów okrągłych. Co się stanie, jeśli napiszesz słowo „programming” z błędem? Czy komputer to koryguje? Jeśli całkowicie utkniesz, poproś swojego nauczyciela o pomoc, zanim przejdziesz dalej.

Mamy nadzieję, że wymyśliłeś, jak sprawić, by program wypisał twoje imię. Możesz także zamienić gwiazdki (\*) na inne symbole. Co się stanie, jeśli usuniesz jeden z cudzysłowów lub jeden z nawiasów? Spróbuj!

Jeśli zmienisz istotny symbol składni programu, prawdopodobnie zobaczysz, że interpreter Pythona wyświetla komunikat o błędzie. W interpreterze online Pythona, którego link znajduje się powyżej, komunikat mówi „ParseError: bad input on line 1 (złe dane wejściowe na linii 1)”. Komunikat może być inny w innym interpreterze. Jeśli masz problem z naprawieniem błędu, skopiuj kod programu jeszcze raz.

{comment}

.. xtcb jargon statement (vs. command)

{comment end}

Języki programowania mogą jednak znacznie więcej niż wypisywanie tekstu. Poniższy program zwraca iloraz liczb. Spróbuj uruchomić program.

{panel type="teacher-note" summary="Wersje języka Python"}

Poniższy kod Pythona jest napisany dla wersji 3 języka Python, ale będzie również działać z wersją 2.

{panel end}

```python3
print("Wypiszę 5 pierwszych wielokrotności 3")
for i in range(5):
  print(i*3)
```

Pierwsza linia to instrukcja wypisywania *print* (ang. drukuj), podobna do tych, które widziałeś wcześniej. Powoduje ona wyświetlenie podanego tekstu na ekranie. Druga linia to instrukcja *pętli*, która pozwala powtórzyć linie występujące po niej pięć razy. Za każdym razem zmienia się wartość *i*, tzn. po przy pierwszym wykonaniu wynosi 0, potem 1, potem 2, potem 3, i na końcu 4. Może wydawać się dziwne, że wartości zaczynają się od 0 i kończą na 4, a nie od 1 do 5, ale programiści mają skłonność do liczenia od 0, ponieważ dzięki temu niektóre rzeczy działają nieco prościej. Trzecia linia wypisuje bieżącą wartość i pomnożoną przez 3 (chcemy wypisać wielokrotności 3). Zwróć uwagę, że instrukcja print wewnątrz pętli *nie* zawiera cudzysłowów. Są one potrzebne jedynie, gdy chcemy wypisać coś dosłownie jako tekst. Gdybyśmy je umieścili, ten program wydrukowałby tekst „i * 3” pięć razy zamiast odpowiedniej wartości!

Spróbuj dokonać następujących zmian w programie.

- Spraw, aby program wypisał wielokrotności 5 zamiast 3. *Wskazówka:* Musisz zmienić zarówno linię pierwszą jak i trzecią.
- Spraw, aby program wypisał pierwsze 10 wielokrotności zamiast pierwszych 5. Upewnij się, że wydrukowano 10 wielokrotności, a nie 9 lub 11!

Pętla może „przechodzić” po elementach listy. Spróbuj uruchomić poniższy program. Wygeneruje serię komunikatów „spamowych”, po jednym adresowanym do każdej osoby na liście odbiorców!

Zauważ, że symbol # mówi komputerowi, że powinien ignorować daną linię programu. Pozwala to programiście komentować, opisywać kod.

```python3
# List of recipients to generate messages for
spam_recipients = ["Heidi", "Tim", "Pondy", "Jack", "Caitlin", "Sam", "David"]
# Go through each recipient
for recipient in spam_recipients:
# Write out the letter for the current recipient
  print("Dear " + recipient + ", \n")
  print("You have been successful in the random draw for all  people ")
  print("who have walked over a specific piece of ground located 2 meters ")
  print("from the engineering road entrance to Canterbury University.\n")
  print("For being successful in this draw you, " + recipient + ", win ")
  print("a prize of 10 million kilograms of chocolate!!!\n")
  print("And " + recipient + " if you phone us within the next 10 minutes ")
  print("you will get a bonus 5 million kilograms of chocolate!!! \n")
  print("\n\n\n") # Put some new lines between the messages
```

Spróbuj zmienić odbiorców lub treść listu. Przyjrzyj się uważnie wszystkim symbolom, których użyto do umieszczenia nazwiska adresata w treści listu.

{panel type="jargon-buster" summary="Składnia języka programowania"}
Szczegółowa specyfikacja wymagań języka programowania odnośnie tego, które znaki mogą być używane oraz w jakim miejscu, jest nazywana jego *składnią*. W powyższym przykładzie składnia listy nazw wymaga kwadratowych nawiasów na liście, cudzysłowów wokół nazw i przecinków między nimi. Jeśli popełnisz błąd, np. pominiesz jeden z nawiasów kwadratowych, system zakomunikuje *błąd składni* i nie będzie mógł uruchomić programu. Każdy znak jest istotny, a jeden mały błąd w programie może go zatrzymać lub sprawić, że będzie działał nieprawidłowo.
{panel end}

Programy mogą również używać *zmiennych* do przechowywania wyników obliczeń, odbierania danych wejściowych pochodzących od użytkownika i podejmowania decyzji (zwanych *instrukcjami warunkowymi*, takimi jak instrukcja *if*). Spróbuj uruchomić ten program. Podaj liczbę mil, gdy program o nią zapyta. Nie umieszczaj jednostek przy wpisanym numerze; na przykład wprowadź po prostu "12".

```
print("This program will convert miles to kilometers")
number_of_miles = int(input("Number of miles: "))
if number_of_miles < 0:
  print("Error: Can only convert a positive number of miles!")
else:
  number_of_kilometers = number_of_miles / 0.6214
  print("Calculated number of kilometers...")
  print(number_of_kilometers)
```

Pierwsza linia zawiera instrukcję *print* (o której powinieneś już wiedzieć!) Drugi wiersz pyta użytkownika o liczbę mil, która jest konwertowana z tekstu wejściowego (zwanego łańcuchem znaków) na liczbę całkowitą. Trzecia linia używa instrukcji warunkowej *if* w celu sprawdzenia, czy wprowadzony numer był mniejszy niż 0. W tym przypadku wyświetlany jest komunikat błędu. Jeśli numer jest większy od 0, to program wykona sekcję *else* (komunikat błędu nie został wyświetlony, ponieważ warunek *if* nie został spełniony), oblicza liczbę kilometrów (jest 0,6214 mili w 1 kilometrze). Wartość wynikową przechowuje *zmienna* o nazwie number_of_kilometers. W ostatniej linii programu wartość zmiennej jest wyświetlona na ekranie. Podobnie jak poprzednio, nie mamy cudzysłowów wokół number_of_kilometers w ostatnim wierszu, gdyż chcemy wypisać wartość zmiennej a nie jest nazwę. Jeśli nadal czujesz się zagubiony, nie martw się. Celem tego rozdziału nie jest nauka programowania, a jedynie zaznajomienie z tym czym jest program i co może zrobić.

Jeśli masz ochotę, możesz zmodyfikować program, aby przeliczał coś innego, np. funty na kilogramy lub stopnie Fahrenheita na stopnie Celsjusza. Korzystanie z zainstalowanego interpretera Pythona zamiast jego wersji online może okazać się korzystniejsze, szczególnie w przypadku, gdy ten drugi będzie wyświetlał niezrozumiałe komunikaty o błędach dla nieprawidłowego programu (wszystkie interpretery miewają problemy z wyświetlaniem czytelnych komunikatów o błędach!)

Programy mogą robić o wiele więcej, np. mogą posiadać graficzny interfejs użytkownika (podobnie jak większość programów komputerowych, z którymi miałeś do czynienia), mogą wyświetlać pliki graficzne lub zapisywać i odczytywać pliki z dysku umożliwiając zapis i odczyt danych po ponownym uruchomieniu programu.


### Dokąd zmierzamy?

Może wydawać się nieco magiczne, że uruchomiony program daje natychmiastowe wyniki. Jednak za kulisami komputer uruchamia nasz program przy pomocy innego programu (interpretera), który tłumaczy kod programu na instrukcje zrozumiałe dla procesora komputera.

Możesz się zastanawiać, dlaczego w ogóle potrzebujemy języków takich jak Python i dlaczego nie możemy udzielać instrukcji komputerowych w języku angielskim. Gdybyśmy wpisali na komputerze „W porządku komputerze, wypisz mi pierwszych pięć wielokrotności 3”, nie jest oczywiste czemu komputer miałby to rozumieć. Komputer po prostu nie zna takich pojęć jak „wielokrotność”, a przez to nie potrafiłby wykonać tego zdania. Komputerów nie można nauczyć znaczenia wszystkich słów, a przez to nie mogą wykonać każdego zadania. Zrozumienie ludzkiego języka jest bardzo trudnym zadaniem dla komputera, o czym dowiesz się w rozdziale „Sztuczna inteligencja”. W przeciwieństwie do ludzi, którzy rozumieją świat i widzą sens pojęć, komputery mogą jedynie postępować zgodnie z precyzyjnymi instrukcjami. Dlatego potrzebujemy języków, które są ograniczone i jednoznaczne, gdyż tylko takie instrukcje „rozumie” komputer. Przykłady takich instrukcji zamieszone są w zaprezentowanych wcześniej programach.

Nie jest to jednak tak proste jak się może wydawać ponieważ komputer nie może uruchamiać instrukcji podawanych bezpośrednio w tych językach. Na najniższym poziomie komputer musi używać fizycznego sprzętu do uruchamiania instrukcji. Działania arytmetyczne, takie jak dodawanie, odejmowanie, mnożenie i dzielenie, lub proste porównania, takie jak mniejszy, większy lub równy, są wykonywane na liczbach reprezentowanych w systemie binarnym przez przepływ prądu przez fizyczne układy komputerowe składające się z tranzystorów. Wynik działania jest także liczbą reprezentowaną w postaci binarnej. Budowa szybkiego i taniego obwodu do wykonywania prostych działań arytmetycznych nie jest trudna, ale instrukcje, które ludzie chcą wydawać komputerom (np. "wypisz następujące zdanie" lub "powtórz coś 100 razy") wymagają bardziej skomplikowanych obwodów elektrycznych.

{panel type="jargon-buster" summary="System binarny"}

Elektronika w komputerach wykorzystuje obwody, które działają głównie z dwiema wartościami (reprezentowanymi jako wysokie i niskie napięcie), aby zapewnić szybkość i niezawodność. Ten system reprezentacji liczb nazywa się *binarnym* i jest często zapisywany na papierze za pomocą zer i jedynek. Więcej informacji na temat reprezentacji binarnej zamieszczone jest w rozdziale [reprezentacja danych](chapters/data-representation.html). Warto tam zajrzeć wcześniej, szczególnie, jeśli nie miałeś do czynienia z systemem binarnym.

{panel end}

{comment}

.. xtcb put in jargon buster on transistors somewhere (or in representations chapter)
.. xjrm insert picture of transistor - Will do once Tim has written jargon buster.
.. not urgent... need to think about whether to put it here or in data representation. It's mainly something to break up the text, but the topic might be distracting here

{comment end}

Zamiast budować komputery, które mogą zrozumieć instrukcje języków wysokiego poziomu takich jak Python (lub Java, Basic, JavaScript, C i tak dalej), budujemy komputery, które mogą wykonywać bardzo ograniczony zestaw instrukcji, a następnie piszemy programy konwertujące instrukcje w języku programowania na proste instrukcje, które mogą być uruchomione przez sprzęt. Językiem tych prostych instrukcji jest język programowania niskiego poziomu, często nazywany kodem maszynowym.

Konwersja z języka wysokiego poziomu do języka niskiego poziomu może obejmować proces *kompilacji*, który zastępuje instrukcje wysokiego poziomu instrukcjami maszynowymi. Te z kolei mogą być uruchomione bezpośrednio przez sprzęt. Alternatywnie kod programu może zostać uruchomiony w procesie *interpretacji*. Proces ten polega na konwersji i śledzeniu każdej instrukcji podczas uruchamiania programu. W rzeczywistości wiele języków używa kombinacji tych dwóch procesów, kompilując program do języka pośredniego, a następnie interpretując go (Java to robi). Język, o którym mówiliśmy wcześniej, Python, jest językiem interpretowanym. Inne języki, takie jak C ++, są kompilowane. W dalszej części rozdziału wrócimy do kompilacji i interpretacji.

Zaczniemy od zapoznania się z niskopoziomowymi językami i sposobem, w jaki komputery wykonują instrukcje języków maszynowych. Następnie przyjrzymy się innym językom programowania używanym przez programistów do udzielania instrukcji komputerom, a na końcu omówimy, w jaki sposób programy napisane przez ludzi w języku wysokiego poziomu są konwertowane na język maszynowy zrozumiały dla komputera.

## Kod maszynowy (języki niskiego poziomu)

{panel type="teacher-note" summary="Pisanie kodu maszynowego przez uczniów nie jest wymagane!"}

Nie jest wymagane od uczniów (a nawet nie jest zalecane), aby pisali własny kod programu w języku maszynowym. Celem przykładów jest zachęcenie uczniów do ich modyfikacji w celu lepszego zrozumienia, dlaczego należy unikać programowania bezpośrednio w tych językach, a tym samym dlaczego należy stosować języki wysokiego poziomu.

Jeśli uczniowie będą mieli problem z modyfikacjami, nie należy się tym przejmować. Przypomnij uczniom, że najważniejsze jest zrozumienie programów w językach wysokiego poziomu, natomiast zmaganie się z tymi przykładami ma tylko uświadomić zalety języków wysokiego poziomu.

Zalecane jest wykorzystanie starego procesora (który nie nadaje się do użycia), aby udostępnić go uczniom do bliższego przyjrzenia się

{panel end}

{comment}

.. xtcb consider putting in alternative assembler examples e.g. 8080, http://www.cs.hmc.edu/~cs5grad/cs5/hmmm/documentation/documentation.html

{comment end}

Komputer wykonuje instrukcje na fizycznych obwodach elektrycznych. Obwody te zawierają tranzystory ułożone w odpowiedni sposób, taki który daje właściwe wartości wyjściowe dla podanych wartości wejściowych.

{comment}

.. xtcb xhtml [Todo: Put an example here of a simple adder, or in meantime link to something on web]

{comment end}

Aby dane wejściowe reprezentowane przez liczby (binarne) mogły być przetworzone przez obwód muszą być umieszczone w specjalnych miejscach pamięci zwanych rejestrami. Rejestry mogą przechowywać bezpośrednio dane lub adres miejsca w pamięci, gdzie owe dane się znajdują. Dane w rejestrach można dodawać, odejmować, mnożyć, dzielić lub sprawdzać równość, warunki  „większy” lub  „mniejszy”. Wyniki tych operacji umieszczane są również w rejestrze, z którego można je odczytać lub użyć do dalszych obliczeń.

Wszystkie komputery mają swój język maszynowy (zwykle nazywany zbiorem instrukcji), który jest używany do instruowania komputera, aby umieścił wartości w rejestrach, wykonał obliczenia i umieścił wynik w innym rejestrze. Kod maszynowy zawiera również instrukcje dotyczące ładowania i zapisywania wartości z i do pamięci (z lub do rejestrów), przeskakiwania do określonej linii w programie (przed lub za bieżącą linią), lub do przejścia do linii tylko wtedy, gdy pewien warunek jest spełniony (wykonywane jest pewne porównanie wartości w rejestrach). Istnieją również instrukcje dotyczące obsługi prostych operacji wejścia/wyjścia oraz interakcji z innymi komponentami komputera.

Instrukcje maszynowe znacząco różnią się od tych, które występują w językach wysokiego poziomu. Na przykład poniższy program napisany jest w języku maszynowym o nazwie MIPS, który jest używany w niektórych wbudowanych systemach komputerowych. Język MIPS będzie używany  w przykładach w tym rozdziale.

Program zaczyna się od zsumowania dwóch liczb (które zostały umieszczone w rejestrach $t0 i $t1) i wypisaniu wyniku. Następnie wypisywane jest  „Hello World!”. Nie martw się, nie chcemy, abyś nauczył się programować w tym języku! A jeśli rzeczywiście nie rozumiesz programu, to tylko potwierdza, iż języki wysokiego poziomu nie zostały stworzone na darmo.

```
.data          	 
str:  .asciiz "\nHello World!\n"
# You can change what is between the  quotes if you like

.text          	 
.globl main       	 

main:
# Do the addition
# For this, we first need to put the values to add into registers ($t0 and $t1)
li $t0, 10 #You can change the 10
li $t1, 20 #You can change the 20
# Now we can add the values together, putting the result in register $a0
add $a0, $t0, $t1
# Set up for printing the value in $a0.
# A '1' in $v0 means we want to print an int
li $v0, 1
# The system call looks at what is in $v0 and $a0,
# and knows to print what is in $a0
syscall    	 

# Now we want to print 'Hello World!'
# So we load the (address of the) string into $a0
la $a0, str
# A '4' in $v0 means we want to print an string
li $v0, 4
# And just like before syscall looks at $v0 and $a0
# and knows to print the string
syscall

# Nicely end the program
li $v0, 0
jr $ra
```

Przykład możesz uruchomić przy pomocy emulatora MIPS za pomocą tego narzędzia:

{interactive name="mips-assembler" type="whole-page" text="Asembler MIPS" file-type="php"}

Skopiuj i wklej dane wyjściowe z pola „Assembler Output” do symulatora MIPS:

{interactive name="mips-simulator" type="whole-page" text="Symulator MIPS" file-type="php"}

Po udanym uruchomieniu programu spróbuj zmienić sumowane wartości. Komentarze w kodzie wskazują, gdzie można zmienić te liczby. Powinieneś również być w stanie, bez większego kłopotu, zmienić komunikat, który jest wyświetlany. Opcjonalnie możesz przerobić program aby odejmował zamiast dodawać liczby. Wskazówka: nazwy instrukcji są zawsze bardzo krótkie. Niestety nie będzie można pomnożyć ani podzielić za pomocą tego symulatora, ponieważ nasz symulator tego nie potrafi. Pamiętaj, że aby ponownie uruchomić program po jego zmianie, musisz ponownie wykonać kroki 1 i 2.

Możesz się zastanawiać, dlaczego musisz wykonać oba te kroki. Wynika to z faktu, że komputery działają na zerach i jedynkach, stąd konieczność konwersji na system szesnastkowy (heksadecymalny). Szesnastkowy jest skróconym zapisem liczb binarnych. *Nie myl tego procesu z kompilacją lub interpretacją!* Jest to znacznie prostsza operacja polegająca na prostej zamianie każdej linii kodu na linię w reprezentacji heksadecymalnej.

Jedną z rzeczy, które być może zauważyłeś podczas przeglądania listy instrukcji języka MIPS, jest brak instrukcji pętli. Jednakże przy użyciu kilku instrukcji możliwe jest napisanie pętli za pomocą tego prostego języka. Jeszcze raz przeczytaj paragraf opisujący różne instrukcje w MIPS. Czy masz jakiś pomysł, jak rozwiązać ten problem? To wymaga kreatywności!

{comment}

.. xjrm: here would be a good place for a box or image, in order to seperate my question from answer
.. ajb took me a while to find the paragraph on instructions referred to. This box could be a table of possible instructions in MIPS?
.. hrn will look at this.
.. xtcb I do not understand what is required here. An image or box of what?

{comment end}

Instrukcja skoku oraz skoku warunkowego mogą być użyte do stworzenia pętli! Przykładem prostego programu z pętlą jest program, który odlicza w dół od pięciu, a następnie wypisuje „Go!!!!”, gdy liczniki dojdzie do zera. W Pythonie możemy z łatwością napisać ten program w trzech linijkach.

```
# Start at 5, count down by 1 each time, and stop when we get to 0
for number in range(5, 0, -1):
   print(number)
print("GO!!!!!")
```

Ale w MIPS to nie jest takie proste. Musimy umieścić wartości w rejestrach i musimy zbudować pętlę z instrukcją skoku. Jak możemy właściwie zaprojektować pętlę?

{comment}

.. xhrn TODO: Flow chart (I will do this tomorrow)

{comment end}

Pełny program MIPS dla naszego problemu jest następujący. Możesz go przerobić.

```
# Define the data strings
.data
go_str:   .asciiz "GO!!!!!\n"
new_line: .asciiz "\n"

.text
# Where should we start?
.globl main

main:
  # Put our starting value 5 into register $t0. We will update it as we go
  li $t0, 5
  # Put our stopping value 0 into register $t1
  li $t1, 0

# This label is just used for the jumps to refer to
start_loop:
  # This says that if the values in $t0 and $t1 are the same,
  # it should jump down to the end_loop label. This is the
  # main loop condition.
  beq $t0, $t1, end_loop
  # These three lines prepare for and print the current int
  # It must be moved into $a0 for the printing
  move $a0, $t0
  li $v0, 1
  syscall
  # These three lines print a new line character so that
  # each number is on a new line
  li $v0, 4
  la $a0, new_line
  syscall
  # Add -1 to the value in $t0, i.e decrement it by 1
  addi $t0, $t0, -1
  # Jump back up to the start_loop label
  j start_loop

# This is the end loop label that we jumped to when the loop is false
end_loop:
  # These three lines print the “GO!!!!” string
  li $v0, 4
  la $a0, go_str
  syscall
  # And these 2 lines make the program exit nicely
  li $v0, 0
  jr $ra
```

Czy możesz zmienić program Python tak, aby odliczał od 10? Czy potrafisz sprawić, aby się zatrzymał na wartości 5? (Być może będziesz musiał spróbować kilka razy, ponieważ jest to trochę nieintuicyjne. Pamiętaj, że jeśli *i* jest numerem zatrzymania, to program uruchamia pętlę dla tej wartości!). Czy potrafisz zmniejszać licznik o 2 zamiast 1? I zmienić komunikat wyświetlany na końcu?

Prawdopodobnie program w języku Python nie był zbyt trudny do modyfikacji. Sprawdź, czy możesz wprowadzić te same zmiany w programie MIPS.

Jeśli to było dla ciebie zbyt proste, może sprawisz, aby oba programy wypisywały „GO!!!!” dwa razy zamiast raz? (nie musisz do tego używać pętli). A jeśli i to było zbyt łatwe, to jakbyś go zmodyfikował, aby wypisał „GO!!!!” 10 razy? Ponieważ powtarzanie linii w programie 10 razy bez pętli byłoby okropną praktyką programistyczną, do tego zadania musiałbyś użyć pętli.

Najprawdopodobniej będziesz raczej zdezorientowany w tym momencie i nie będziesz w stanie zmodyfikować programu MIPS z wszystkimi naszymi życzeniami. Natomiast jeśli stworzyłeś jeszcze jedną pętlę w swoim programie MIPS poprawnie drukującą "GO!!!" 10 razy, to jesteś na najlepszej drodze do bycia dobrym programistą!

Jaki jest zatem sens tego wszystkiego? Te instrukcje niskiego poziomu wydają się żmudne i nieco głupie, lecz dzięki ich prostocie komputer może je uruchomić bezpośrednio na sprzęcie. Programista może napisać program w tym języku, jeśli go dobrze zna, a komputer będzie mógł go uruchomić bezpośrednio, bez dalszego przetwarzania. Jak już zapewne wiesz, nie jest to najszybszy sposób programowania komputerów. Trzeba załadować dane i wyjąć je z rejestrów, implementacja pętli za pomocą instrukcji skoku oraz wypisywanie ciągów znaków i liczb całkowitych przy pomocy trzyliniowego schematu instrukcji, którego znaczenia pewnie być nie odgadł bez naszych wyjaśnień. Wypisywanie w ten sposób, jak się okazuje w praktyce, stwarza wiele okazji do popełnienia błędu, nie wspominając o tym, że powstałe programy są niezwykle trudne do odczytania i zrozumienia.

Ponieważ komputery nie mogą bezpośrednio uruchamiać instrukcji w językach, które lubią programiści, same języki programowania wysokiego poziomu nie wystarczą. Rozwiązaniem tego problemu różnych potrzeb jest użycie kompilatora lub interpretera, który jest w stanie przekonwertować program w języku programowania wysokiego poziomu, który napisał programista, na zrozumiały dla komputera kod maszynowy.

Obecnie niewielu programistów programuje bezpośrednio w językach niskiego poziomu. Na początku rozwoju komputerów programy były pisane bezpośrednio w języku maszynowym, gdyż działały wyraźnie szybciej niż te skompilowane z języków wysokiego poziomu. Wynika to z faktu, że kompilatory nie były zbyt dobre w minimalizowaniu liczby instrukcji języka maszynowego, czyli w tak zwanej *optymalizacji*. Osoby przeszkolone do pisania w kodzie maszynowym były w tym lepsze. Obecnie jednak kompilatory są o wiele inteligentniejsze i mogą zoptymalizować kod znacznie lepiej niż większość ludzi. Napisanie programu bezpośrednio w kodzie maszynowym może spowodować, że program będzie *mniej* zoptymalizowany niż program skompilowany. Z tego względu trzeba uważać, gdy się mówi, że się języki niskiego poziomu są szybsze!

{comment}

.. xtcb point out that compiling for large software can be slow https://xkcd.com/303/

{comment end}

To nie jest koniec opowieści. Opisany tutaj kod maszynowy MIPS jest przykładem architektury ograniczonego zestawu instrukcji RISC (ang. Reduced Instruction Set Architecture). Obecnie wiele komputerów korzysta ze architektury złożonego zestawu instrukcji CISC (ang. Complex Instruction Set Architecture). Oznacza to, że czipy komputerowe mogą być trochę bardziej inteligentne i mogą zrobić więcej w jednym kroku. Jest to jednak zagadnienie znacznie wykraczające poza zakres tej książki. Dla zrozumienia różnic między kodem maszynowym a wysokopoziomowymi językami wystarczy MIPS, dotyczy to również większości informatyków i inżynierów oprogramowania.

Podsumowując, potrzebujemy języków programowania niskiego poziomu, ponieważ komputery je rozumieją. Potrzebujemy również języków programowania wysokiego poziomu, bo rozumieją je ludzie. Dalsza część rozdziału poświęcona jest kompilatorom i interpreterom; będziemy korzystać z programów do konwersji programu napisanego w języku wysokiego poziomu (dla ludzi) na język niskiego poziomu (dla komputerów).

{comment}

.. xtcb trivia: Grace Hopper credited with creating first compiler: http://computingportal.org/node/4684

.. xtcb put in activity on interpreter vs. compiler, based perhaps on http://community.computingatschool.org.uk/resources/2521 (Python program that interprets/compiles to turtle language) http://community.computingatschool.org.uk/forums/1/topics/3090

{comment end}

## Wieża Babel języków programowania

Istnieje wiele różnych języków programowania. Tutaj prezentujemy jedynie mały podzbiór języków, aby zademonstrować zakres ich zastosowań. Należy zdawać sobie sprawę, że poza tymi językami istnieje wiele innych, które mają wielu zwolenników.

Bardziej kompletną listę języków programowania  [znajdziesz na Wikipedii](https://en.wikipedia.org/wiki/List_of_programming_languages).

### Python


Python jest powszechnie używanym językiem, który stał się bardzo popularny w edukacji. Wiele osób uczy się Pythona jako swojego pierwszego języka programowania. We wstępie przyjrzeliśmy się kilku przykładom programów w Pythonie, przeznaczonych dla początkujących programistów.

Pierwotnie jednak Python miał być językiem skryptowym. Języki skryptowe mają uproszczoną składnię, która umożliwia szybkie pisanie programów do przetwarzania plików i wykonywania powtarzalnych zadań na komputerze.

Za przykład przykład sytuacji, w której Python jest bardzo przydatny, może posłużyć sytuacja, w której twój nauczyciel przeprowadził 5 sprawdzianów przez cały rok. Następnie zapisał wyniki dla każdego ucznia w pliku podobnym do poniższego (może to być więcej niż 6 uczniów), w którym po imieniu każdego ucznia następują jego wyniki. Niektórzy uczniowie nie byli obecni podczas wszystkich sprawdzianów, więc zanotowano mniej niż 5 wyników.

```
Karen 12 12 14 18 17
James 9 7 1
Ben 19 17 19 13
Lisa 9 1 3 0
Amalia 20 20 19 15 18
Cameron 19 15 12 9 3
```

W pewnym momencie nauczyciel zdaje sobie sprawę, że musi ustalić średnią (z 5 sprawdzianów), którą zdobył każdy uczeń. Nie chce jednak, mając wiele innych spraw na głowie, poświęcać zbyt wiele czasu na to zadanie. Korzystając z Pythona, może bardzo szybko wygenerować potrzebne dane za pomocą mniej niż 10 linijek kodu.

Zrozumienie szczegółów poniższego kodu jest nieistotne dla tego rozdziału, szczególnie jeśli nie jesteś jeszcze programistą. Jeśli kod nie jest dla ciebie jasny, prostu przeczytaj komentarze (zaczynające się od "#"), dzięki czemu zrozumiesz z grubsza, jak problem został rozwiązany.

```python3
# Open the raw score file for reading
raw_scores_file = open("scores.txt", "r")
# Create and open a file for writing the processed scores into
processed_scores_file = open("processed_scores.txt", "w")

# For each line in the file
for line in raw_scores_file.readlines():
    # Get the name, which is in the first part of the line
    name = line.split()[0]
    # Get a list of the scores, which are on the remainder of the lines
    scores_on_line = [int(score) for score in line.split()[1:]]
    # Calculate the average, which is the sum of the scores divided by 5
    average = sum(scores_on_line) / 5
    # Write the average to the processed scores output file
    processed_scores_file.write(name + " " + str(average) + "\n")

# Close both files
raw_scores_file.close()
processed_scores_file.close()
```

Wynikiem działania programu będzie plik zawierający imię każdego ucznia, po którym wypisana będzie suma wyników po dzieleniu przez 5. Jeśli masz zainstalowany Python na swoim komputerze, możesz uruchomić program na próbę (nie zadziała on na internetowym interpreterze, ponieważ potrzebuje dostępu do systemu plików). Po prostu zapisz dane do pliku o nazwie "scores.txt" w tym samym formacie, w jakim był wyświetlany powyżej. Program zadziała pod warunkiem, że plik znajduje się w tym samym katalogu co plik kodu źródłowego.

Ten problem można oczywiście rozwiązać w dowolnym języku, ale w niektórych językach jest to znacznie prostsze. Standardowe języki programowania, takie jak Java, o których wkrótce wspomnimy, nie oferują tak prostego przetwarzania plików. Java wymaga od programisty określenia, co zrobić, jeśli otwarcie pliku się nie powiedzie. Pomaga to zapobieganiu awariom programu. Python nie wymaga tego od programisty, chociaż opcjonalnie jest to możliwe, jeśli programista sobie tego życzy. Oba te podejścia mają zalety w różnych sytuacjach. Dla nauczyciela piszącego szybki skrypt do przetworzenia wyników quizu, nie ma to większego znaczenia, czy program się czasem zawiesza. Nie musi więc tracić czasu na pisanie kodu obsługującego sytuacje wyjątkowe. W przypadku dużego oprogramowania, z którego korzysta wiele osób, awarie mogą stanowić zagrożenie dla bezpieczeństwa. Zmuszenie wszystkich programistów pracujących nad takim systemem do właściwego radzenia sobie z sytuacjami wyjątkowymi może zapobiec wielu problemom. W tym przypadku podejście języka Java jest korzystniejsze.

Oprócz prostej obsługi plików Python nie wymagał od nauczyciela z naszego przykładu umieszczania kodu wewnątrz klasy ani funkcji, a ponadto dostarcza bardzo przydatne wbudowane funkcje do rozwiązania problemu, na przykład funkcja, która wyznacza sumę listy, lub linia konwertująca tekst na listę liczb (przy użyciu bardzo często używanej, wygodnej konstrukcji).

Ten sam kod napisany w Javie byłby co najmniej dwukrotnie dłuższy.

Poza Pythonem jest wiele innych języków skryptowych, takich jak Perl, Bash i Ruby.

### Scratch

Scratch jest językiem programowania przeznaczonym do nauczania młodszych adeptów programowania. Interfejs typu „przeciągnij i upuść” jest używany zamiast edytora kodu, aby nowi programiści nie musieli się martwić o składnię. Programy napisane w Scratch koncentrują się wokół kontrolowania postaci z kreskówek lub innych elementów animowanych na ekranie.

Scratch nie jest przeznaczony do programowania dla przemysłu, tylko do celów edukacyjnych. Jeśli jesteś zainteresowany wypróbowaniem Scratch, [możesz go wypróbować online tutaj] (http://scratch.mit.edu/projects/editor/?tip_bar=getStarted), nie musisz niczego pobierać ani instalować.

{button link="http://scratch.mit.edu/projects/19711355/#editor" text="Przykładowy projekt Scratch"}

Poniżej zamieszczony został przykład prostego programu w Scratch. Jest podobny do programów, które zamieściliśmy dla Pythona i Javy. Program pyta użytkowników o liczby, dopóki nie wpiszą "stop", a następnie wyznacza średnią z podanych liczb.

{image filename="scratch-example-program.png"}

Po kliknięciu zielonej flagi wyświetli się następujący rezultat:

{image filename="scratch-example-program-output.png"}

Scratch może posłużyć do prostych obliczeń, tworzenia gier i animacji. Jednak nie ma wszystkich możliwości pozostałych języków.

Przykładami innych języków edukacyjnych są Alice i Logo. Alice używa również techniki „przeciągnij i upuść”, lecz odbywa się to w środowisku 3D. Logo to bardzo stary język ogólnego przeznaczenia oparty na Lispie. Nie jest już używany, ale zasłynął z żółwia z długopisem, który rysuje na ekranie, podobnie do Scratch. Scratch powstał dzięki inspiracji językiem Logo. Języki te nie są używane poza zastosowaniami edukacyjnymi. Wynika to z faktu, iż są wolne i nieefektywne.

### Java

Java jest popularnym językiem programowania ogólnego przeznaczenia. Służy do budowania dużych systemów informatycznych. Jest używana przez bardzo wielu programistów na całym świecie. W przeciwieństwie do Pythona, zmusza programistów do określania, w jaki sposób program ma sobie radzić z sytuacjami wyjątkowymi i wymaga określenia jaki typ danych przechowują zmienne, np. *int* (liczba całkowita) lub *String* (ciąg znaków). Python nie wymaga podawania typów danych. Wszystkie te cechy pomagają zmniejszyć liczbę błędów w kodzie. Dodatkowo, mogą ułatwić innym programistom odczytanie kodu, ponieważ łatwo zobaczyć typ każdej zmiennej (ustalenie tego w programie Pythona napisanym przez innych może być czasem trudne, a to bardzo utrudnia modyfikowanie cudzego kodu bez psucia go!)

Poniżej zamieszczony został kod w Javie do rozwiązania problemu średnich, który wcześniej rozwiązaliśmy w Pythonie.

```java
import java.io.*;
import java.util.*;

public class Averager {
    public static void main() {
        String inputFile = "scores.txt";
        String outputFile = "processed_scores.txt";
       	try {
           	Scanner scanner = new Scanner(new File(inputFile));
           	PrintStream outputFile = new PrintStream(new File(outputFile));
           	while (scanner.hasNextLine()) {
               	String name = scanner.next();
               	Scanner numbersToRead = new Scanner(scanner.nextLine());
               	int totalForLine = 0;
               	while (numbersToRead.hasNextInt()) {
                    totalForLine += numbersToRead.nextInt();
               	}
               	outputFile.println(name + " " + totalForLine/5.0 + "\n");
           	}
           	outputFile.close();
       	} catch (IOException e) {
            System.out.println("The file could not be opened!" + e);
       	}
    System.out.println("I am finished!");
    }
}
```

Kod jest dłuższy, lecz gwarantuje większą niezawodność. Mówi, aby *spróbować* (ang. try) otworzyć i czytać plik, a jeśli wystąpi błąd, to powinien *złapać* (ang. catch) ten błąd i wypisać komunikat dla użytkownika o błędzie. Niezależnie od tego, czy wystąpi błąd, to i tak linia „I am finished!” zostanie wypisana, gdyż błąd został bezpiecznie "złapany". W języky Python możemy również wyrazić podobne zachowanie, ale nie jest to obowiązkowe i zależy od programisty. Java nawet nie skompiluje kodu, jeśli nie zostało to zrobione! Dzięki temu programist nie zapomni o sytuacjach wyjątkowych, ani nie pominie ich z lenistwa.

{comment}

.. ajb Probably known but formatting needs to be fixed here

{comment end}

Istnieje wiele innych języków programowania ogólnego przeznaczenia, takich jak C# i C++. Python jest czasem używany do tworzenia dużych systemów oprogramowania, chociaż generalnie nie jest uważany za idealny język w tym kontekście.

### JavaScript

- Interpretowany w przeglądarce internetowej
- Podobny język: Actionscript (Flash)

Uwaga: podrozdział ten zostanie uzupełniony w przyszłej wersji podręcznika. Na razie po więcej informacji odsyłamy do stron Wikipedii.

### C

- Język niskiego poziomu ze składnią języka wysokiego poziomu.
- Używany powszechnie do programowania systemów operacyjnych i systemów wbudowanych.
- Programy napisane w C są przeważnie bardzo szybkie (język został zaprojektowany w sposób, który ułatwia optymalne skompilowanie do kodu maszynowego).
- Podatny na błędy ze względu na swoją niskopoziomowość. Najlepiej nie używać go w sytuacjach, w których nie jest to konieczne.
- Powiązane języki: C++ (w pewnym sensie).

Uwaga: podrozdział ten zostanie uzupełniony w przyszłej wersji podręcznika. Na razie po więcej informacji odsyłamy do stron Wikipedii.

### Matlab

- Używany do pisania programów wymagających zaawansowanej matematyki (rachunku różniczkowego, algebry liniowej itp.).
- Nie jest darmowy.
- Powiązane języki: Mathematica, Maple.

Uwaga: podrozdział ten zostanie uzupełniony w przyszłej wersji podręcznika. Na razie po więcej informacji odsyłamy do stron Wikipedii.

### Ezoteryczne Języki Programowania

Każdy może stworzyć własny język programowania. Wymaga to wymyślenia składni języka, napisania analizatora składni (tzw. parsera) i kompilatora lub interpretera. Elementy te pozwolą uruchomić program w nowym języku. Większość języków programowania stworzonych przez ludzi nigdy nie była powszechnie używana.

Oprócz języków programowania, które mają praktyczne zastosowanie, ludzie stworzyli wiele języków programowania, które miały być jedynie dowcipami lub testami na granice tego, jak niejasny może być język programowania. Niektóre z nich sprawiają, że języki maszynowe niskiego poziomu, które wcześniej widzieliście, wydają się logiczne! Wikipedia zawiera [wykaz takich języków] (https://en.wikipedia.org/wiki/Esoteric_programming_language).

Jeśli tylko masz ochotę, możesz stworzyć własny język programowania!

## Jak komputer uruchamia program?

Język programowania, taki jak Python lub Java jest uruchamiany przez program, który został przez kogoś napisany!

Ponieważ sprzęt komputerowy może uruchamiać tylko programy w języku niskiego poziomu (kod maszynowy), system programowania musi umożliwiać wykonywanie instrukcji w języku Python przy użyciu języka maszynowego. Można to zrobić na dwa sposoby: interpretując i kompilując.

[Ten film z 1983 r.](Https://www.youtube.com/watch?v=_C5AHaS1mOA) przedstawia trafną analogię między interpreterem a kompilatorem.

Główna różnica sprowadza się do faktu, że kompilator to program, który konwertuje kod programu na język maszynowy, który następnie jest uruchamiany na komputerze. Interpreter to program, który czyta twój program wiersz po wierszu, analizuje instrukcje i wykonuje je natychmiast.

Oba podejścia mają swoje zalety, a każde z nich do jednych języków pasuje bardziej, a do innych mniej. W rzeczywistości większość współczesnych języków używa kombinacji kompilacji i interpretacji. Na przykład większość programów Java jest *kompilowana* do "języka pośredniego" o nazwie ByteCode, który jest bliższy kodowi maszynowemu niż Java. ByteCode jest następnie wykonywany przez interpreter.

Jeśli twój program ma być udostępniany większemu gronu odbiorców, zwykle będziesz chciał, aby był w postaci kodu maszynowego. Dzięki temu będzie działał szybciej, użytkownik nie będzie musiał mieć zainstalowanego interpretera i kiedy ktoś pobierze kod maszynowy, nie będzie miał dostępu do kodu źródłowego programu wysokiego poziomu. Języki, w których mamy do czynienia z taką sytuacją to C#, Objective C (używane do programowania urządzeń iOS), Java i C.

Programy interpretowane mają tę zaletę, że mogą być łatwiejsze do napisania, gdyż można je szybko przetestować, łatwiej śledzić, co się w nich dzieje, a nawet czasami dodać pojedynczą instrukcję, aby zobaczyć, co się stanie. Można to zrobić bez konieczności przechodzenia przez cały proces kompilacji. Z tego powodu są one szeroko używanie w celach edukacyjnych (na przykład Scratch i Alice są interpretowane), a także w przypadku prostych zadań, ponieważ programy je wykonujące można szybko napisać i przetestować (również języki takie jak PHP, Ruby i Python są używane w takich sytuacjach).

Poniższy diagram pokazuje różnicę pomiędzy procesem interpretacji i kompilacji na przykładzie programu sortującego liczby. Rezultatem działania kompilatora jest program w kodzie maszynowym, który dokonuje sortowania. Dane wejściowe są podawane bezpośrednio do tego drugiego programu, w celu uzyskania posortowanego wyniku. Interpreter z kolei wykonuje sortowanie na danych wejściowych, interpretując instrukcje programu. Kompilator tworzy program w kodzie maszynowym, który można rozpowszechniać.

{image filename="comparing-sorting-programs-across-scratch-and-c.png" alt="Porównanie sortowania przez program w Scratch i C"}

{comment}

.. xtcb mention cross compilers, especially for mobile apps

{comment end}

## Podsumowanie

Pomimo tego, że istnieje wiele różnych języków programowania, to nowe są ciągle wymyślane. Każdy nowy język będzie wymagał opracowania nowego kompilatora i/lub interpretera. Na szczęście istnieją sprawdzone narzędzia, które pozwalają na szybkie stworzenie nowego języka. Niektóre pomysły na nowy język pojawią się w rozdziale *Języki formalne*, gdzie pojawiają się takie pojącie opisujące język jak wyrażenia regularne i gramatyki.

Języki, które omawialiśmy w tym rozdziale, są często używane na początku nauki programowania. Istnieją zupełnie inne typy języków, które mają bardzo ważne zastosowania. Przykładem tego może być podejścia do programowania o nazwie [programowanie funkcyjne](https://en.wikipedia.org/wiki/Functional_programming), gdzie wszystkie operacje są sformułowane jako funkcje matematyczne. Popularne języki, które używają technik funkcyjnych to: Lisp, Scheme, Haskell, Clojure i F#; nawet niektóre języki konwencjonalne (takie jak Python) zawierają elementy programowania funkcyjnego. Czysty funkcyjny styl programowania eliminuje problem zwany *efektami ubocznymi*, co z kolei pozwala zapewnić większą niezawodność programu. Innym ważnym typem programowania jest [programowanie logiczne](https://en.wikipedia.org/wiki/Logic_programming), gdzie program może być traktowany jako zbiór reguł stwierdzających, co powinien robić, a nie ciąg instrukcji typu „zrób to”. Najbardziej znanym językiem programowania logicznego jest Prolog.



## Dalsza lektura

### Ciekawe odnośniki

- [Lekcje poświęcone językom programowania -- TeachICT](http://www.teach-ict.com/gcse_computing/ocr/216_programming/programming_languages/miniweb/index.htm) obejmujące wiele zagadnień z tego rozdziału
- CS Online zawiera [przegląd zagadnień poruszonych w rozdziale](http://courses.cs.vt.edu/~csonline/ProgrammingLanguages/Lessons/Introduction/index.html)
- Artykuły Wikipedii o [Językach programowania](https://en.wikipedia.org/wiki/Programming_language), [Język wysokiego poziomu](https://en.wikipedia.org/wiki/High-level_programming_language), oraz [Język niskiego poziomu](https://en.wikipedia.org/wiki/Low-level_programming_language)

- [Strona z plakatami porównującymi języki progrmowania](http://programming.dojo.net.nz/) stworzona przez Samuela Williamsa
- [Samouczek porównujący języki programowania](http://holowczak.com/programming-concepts-tutorial-programmers/)
- [Plakat opisujący szczegóły zawartości plików wykonywalnych](http://code.google.com/p/corkami/wiki/PE101?show=content) (format exe)
- David Bolton tłumaczy czym jest [język programowania](http://cplus.about.com/od/introductiontoprogramming/p/programming.htm), [Kompilator](http://cplus.about.com/od/introductiontoprogramming/p/compiler.htm), oraz [różnica między kompilatorem i interpreterem](http://cplus.about.com/od/introductiontoprogramming/a/compinterp.htm).
- [Artykuł z Computerworld: od A do Z języków programowania](http://www.computerworld.com.au/article/344826/z_programming_languages/)
- [Czym jest Python?](http://python.about.com/od/gettingstarted/ss/whatispython_4.htm) (porównianie z innymi językami)
- [Duży plakat pokazujący chronologię rozwoju języków programowania](http://www.levenez.com/lang/)
- [Program typu Hello World w wielu językach programowania](http://www.roesler-ac.de/wolfram/hello.htm)
- [Pisenka „99 butelek piwa” w wielu językach programowania](http://99-bottles-of-beer.net/)


{panel type="teacher-note" summary="Ciekawe linki"}

Poniższe strony internetowe będą przydatne dla nauczycieli

- [który przegląd pojęć zawartych w rozdziale](http://userpages.wittenberg.edu/bshelburne/Comp150/ProgrammingLanguages.html)
- [historia języków programowania z przymrużeniem oka](http://james-iry.blogspot.co.nz/2009/05/brief-incomplete-and-mostly-wrong.html)

{panel end}
