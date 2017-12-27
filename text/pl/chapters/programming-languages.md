# Języki programowania

## ??What's the big picture?

Programowanie, czasami nazywane kodowowaniem, jest praktycznym zastosowaniem informatyki. Celem tej książki nie jest oczywiście nauka programowania (dodaliśmy jednakże kilka linków do stron, które mogą służyć jako znakomity wstęp do tego zagadnienia), zobaczymy natomiast, czym jest język programowania i jak informatycy z niego korzystają. Z punktu widzenia programisty kodowanie polega na wpisywaniu instrukcji, które są wykonywane przez komputer. Ale w jaki sposób komputer wie, co robić? Pamiętaj, że możesz używać jednego z wielu języków, takich jak Python, Java, Scratch, Basic lub C #, lecz komputery wyposażone są w sprzęt, który rozumie tylko jeden język, tzw. "kod maszynowy". Składa się on z bardzo prosty podstawowych instrukcji, które jest trudno czytać i pisać ludziom. Co zrobić, gdy wymyślisz nowy język programowania, jak sprawić by komputer mógł z niego korzystać?

W tym rozdziale przyjrzymy się temu, co dzieje się podczas pisania i uruchamiania programu oraz w jaki sposób wpływa to na sposób, w jaki sposób rozpowszechniany jest program.

Zaczniemy od opcjonalnego podrozdziału o tym, na czym polega programowanie, dla tych, którzy wcześniej nigdy nie programowali. Wprowadzenie do programowania zawiera przykłady bardzo prostych programów w języku Python, które można uruchamiać i modyfikować. Poznanie tego podrozdziału pozwoli zrozumieć dalsze części rozdziału; nie nauczymy cię programowania, ale będziesz mógł prześledzić proces myślenia programisty podczas kodowania. Jeśli masz już pewną wiedzę o programowaniu, to możesz przeskoczyć ten podrozdział.

Poniższa część rozdziału zawiera przegląd zagadnień opisanych w rozdziale, z tego względu zalecana jest jego lektura.

{comment}

.. consider introductory video which mentions role of languages: https://www.youtube.com/watch?v=AkFi90lZmXA

{comment end}

### Czym jest programowanie?

{panel type="teacher-note" summary="Warm-up activity"}

Spójrz na [warm-up activity from CSUnplugged](http://csunplugged.org/programming-languages), lub na [rozszerzoną wersję tutaj](http://csunplugged.org/wp-content/uploads/2014/12/tellAndDraw1.5.pdf).

Uczniowie, którzy nigdy wcześniej nie programowali, powinni również przejrzeć materiał w tym podrozdziale. Zawiera on przegląd tego, czym jest programowanie, pozwoli to zrozumieć dalszą część rozdziału.

{panel end}

Uwaga: Ten podrozdział przeznaczony jest dla osób, które nie są zaznajomione z programowaniem. Jeśli masz już pewną wiedzę o programowaniu, możesz pominąć tą część rozdziału.

Przykład najprostszego rodzaju programu jest następujący: ma pięć instrukcji (po jednej w każdym wierszu), które są zapisane w określonej kolejności.Przykład najprostszego rodzaju programu jest następujący: ma pięć instrukcji (po jednej w każdym wierszu), które są zapisane w określonej kolejności.

```
print("**********************************************")
print("**********************************************")
print("** Welcome to computer programming, Student **")
print("**********************************************")
print("**********************************************")
```

Powyższy program został napisany w języku o nazwie Python, a po uruchomieniu wyświetli na ekranie następujący tekst

```
************************************************
************************************************
*** Welcome to computer programming, Student ***
************************************************
************************************************
```

Aby uruchomić program napisany w Pythonie, potrzebujemy tak zwanego interpretera Pythona. Interpreter Pythona jest w stanie odczytać program i przetworzyć go. Poniżej znajduje się interpreter języka Python, którego można używać do uruchamiania własnych programów. Jeśli masz zainstalowany interpreter Pythona na swoim komputerze (poradź się nauczyciela jeżeli czujesz się zdezorientowany) i wiesz, jak z niego korzystać możesz się ograniczyć do dostępnych narzędzi.

{interactive name="python-interpreter" type="in-page"}

Spróbuj tak zmienić program, aby zawierał Twoje imię zamiast *Uczeń*. Kiedy stwierdzisz, że program jest gotowy, spróbuj go ponownie uruchomić. Upewnij się, czy przez pomyłkę nie usunąłeś podwójnych cudzysłowów lub nawiasów okrągłych. Co się stanie, jeśli napiszesz słowo "programming" z błędem? Czy komputer to koryguje? Jeśli całkowicie utkniesz, poproś swojego nauczyciela o pomoc, zanim przejdziesz dalej.

Mamy nadzieję, że wymyśliłeś, jak sprawić, by program wypisał twoje imię. Możesz także zamienić gwiazdki (\*) na inne symbole. Co się stanie, jeśli usuniesz jeden z cudzysłowów lub jeden z nawiasów? Spróbuj!

Jeśli zmienisz istotny symbol składni programu, prawdopodobnie zobaczysz, że interpreter Pythona wyświetla komunikat o błędzie. W interpreterze online Pythona, którego link znajduje się powyżej, komunikat mówi "ParseError: bad input on line 1 (złe dane wejściowe na linii 1)". Komunikat może być inny w innym interpreterze. Jeśli masz problem z naprawieniem błędu, skopiuj kod programu jeszcze raz.

{comment}

.. xtcb jargon statement (vs. command)

{comment end}

PJęzyki programowania mogą jednak znacznie więcej niż wypisywanie tekstu. Poniższy program jest zwraca iloraz liczb. Spróbuj uruchomić program.

{panel type="teacher-note" summary="Wersje języka Python"}

Poniższy kod Pythona jest napisany dla wersji 3 języka Python, ale będzie również działać z wersją 2.

{panel end}

```python3
print("I am going to print the first 5 multiples of 3")
for i in range(5):
  print(i*3)
```

Pierwsza linia to instrukcja wypisywania print (ang. drukuj), podobna do tych, które widziałeś wcześniej. Powoduje ona wyświetlenie podanego tekstu na ekranie. Druga linia to instrukcja *pętli*, która pozwala powtórzyć linie występujące po niej 5 razy. Za każdym razem zmienia się wartość i, tzn. po przy pierwszym wykonaniu wynosi 0, potem 1, potem 2, potem 3, i na końcu 4. Może wydawać się dziwne, że wartości zaczynają się od 0 i kończą na 4, a nie od 1 do 5, ale programiści mają skłonność do liczenia od 0, ponieważ dzięki temu niektóre rzeczy działają nieco prościej. Trzecia linia wypisuje bieżącą wartość i pomnożoną przez 3 (chcemy wypisać wielokrotności 3). Zwróć uwagę, że instrukcja print wewnątrz pętli *nie* zawiera cudzysłowów. Są one potrzebne jedynie, gdy chcemy wypisać coś dosłownie jako tekst. Gdybyśmy je umieścili, ten program wydrukowałby tekst "i * 3" 5 razy zamiast odpowiedniej wartości!

Spróbuj dokonać następujących zmian w programie.

- Spraw, aby program wypisał wielokrotności 5 zamiast 3. *Wskazówka:* Musisz zmienić zarówno linię pierwszą jak i trzecią.
- Spraw, aby program wypisał pierwsze 10 wielokrotności zamiast pierwszych 5. Upewnij się, że wydrukowano 10 wielokrotności, a nie 9 lub 11!

Pętla może “przechodzić” po elementach listy. Spróbuj uruchomić poniższy program. Wygeneruje serię komunikatów "spamowych", po jednym adresowanym do każdej osoby na liście odbiorców!

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

Pierwsza linia zawiera instrukcję *print* (o której powinieneś już wiedzieć!) Drugi wiersz pyta użytkownika o liczbę mil, która jest konwertowana z tekstu wejściowego (zwanego łańcuchem znaków) na liczbę całkowitą. Trzecia linia używa instrukcji warunkowej *if* w celu sprawdzenia, czy wprowadzony numer był mniejszy niż 0. W tym przypadku wyświetlany jest komunikat błędu. Jeśli numer jest większy od 0, to program wykona sekcję *else* (komunikat błędu nie został wyświetlony, ponieważ warunek *if* nie został spełniony), oblicza liczbę kilometrów (jest 0,6214 mili w 1 kilometrze ??tu jest błąd w oryginale??). Wartość wynikową przechowuje *zmienna* o nazwie number_of_kilometers. W ostatniej linii programu wartość zmiennej jest wyświetlona na ekranie. Podobnie jak poprzednio, nie mamy cudzysłowów wokół number_of_kilometers w ostatnim wierszu, gdyż chcemy wypisać wartość zmiennej a nie jest nazwę. Jeśli nadal czujesz się zagubiony, nie martw się. Celem tego rozdziału nie jest nauka programowania, a jedynie zaznajomienie z tym czym jest program i co może zrobić.

Jeśli masz ochotę, możesz zmodyfikować program, aby przeliczał coś innego, np. funty na kilogramy lub stopnie Fahrenheita na stopnie Celsjusza. Korzystanie z zainstalowanego interpretera Pythona zamiast jego wersji online może okazać się korzystniejsze, szczególnie w przypadku, gdy ten drugi będzie wyświetlał niezrozumiałe komunikaty o błędach dla nieprawidłowego programu (wszystkie interpretery miewają problemy z wyświetlaniem czytelnych komunikatów o błędach!)

Programy mogą robić o wiele więcej, np. mogą posiadać graficzny interfejs użytkownika (podobnie jak większość programów komputerowych, z którymi miałeś do czynienia), mogą wyświetlać pliki graficzne lub zapisywać i odczytywać pliki z dysku umożliwiając zapis i odczyt danych po ponownym uruchomieniu programu.


### Dokąd zmierzamy?

Może wydawać się nieco “magiczne”, że uruchomiony program może dawać natychmiastowe wyniki. Jednak za kulisami komputer uruchamia nasz program przy pomocy innego programu (interpretera), który tłumaczy kod programu na instrukcje zrozumiałe dla procesora komputera.

Możesz się zastanawiać, dlaczego w ogóle potrzebujemy języków takich jak Python i dlaczego nie możemy udzielać instrukcji komputerowych w języku angielskim. Gdybyśmy wpisali na komputerze "W porządku komputerze, wypisz mi pierwszych 5 wielokrotności 3", nie jest oczywiste czemu komputer nie miałby tego wykonać. Komputer po prostu nie zna takich pojęć jak "wielokrotność", a przez to nie potrafiłby wykonać tego zdania. Komputerów nie można nauczyć znaczenia wszystkich słów, a przez to nie mogą potrafić wykonać każdego możliwego zdania. Zrozumienie ludzkiego języka jest bardzo trudnym zadaniem dla komputera, o czym dowiesz się w rozdziale "Sztuczna inteligencja". W przeciwieństwie do ludzi, którzy rozumieją świat i widzą sens, komputery mogą jedynie postępować zgodnie z precyzyjnymi instrukcjami. Dlatego potrzebujemy języków, które są ograniczone i jednoznaczne, gdyż tylko takie instrukcje "rozumie" komputer. Przykłady takich instrukcji zamieszone są w zaprezentowanych wcześniej programach.

It isn’t this simple though, a computer cannot run instructions given directly in these languages. At the lowest level, a computer has to use physical hardware to run the instructions. Arithmetic such as addition, subtraction, multiplication, and division, or simple comparisons such as less than, greater than, or equal to are done on numbers represented in binary by putting electricity through physical computer chips containing transistors. The output is also a number represented in binary. Building a fast and cheap circuit to do simple arithmetic such as this isn't that hard, but the kind of instructions that people want to give computers (like "print the following sentence", or "repeat the following 100 times") are much harder to build circuitry for.

{panel type="jargon-buster" summary="Binary"}

The electronics in computers uses circuitry that mainly just works with two values (represented as high and low voltages) to make it reliable and fast. This system is called *binary*, and is often written on paper using zeroes and ones. There's a lot more about binary in the [data representation](chapters/data-representation.html) chapter, and it's worth having a quick look at the first section of that now if you haven't come across binary before.

{panel end}

{comment}

.. xtcb put in jargon buster on transistors somewhere (or in representations chapter)
.. xjrm insert picture of transistor - Will do once Tim has written jargon buster.
.. not urgent... need to think about whether to put it here or in data representation. It's mainly something to break up the text, but the topic might be distracting here

{comment end}

So instead of building computers that can understand these high level instructions that you find in languages like Python (or Java, Basic, JavaScript, C and so on), we build computers that can follow a very limited set of instructions, and then we write programs that convert the instructions in the standard languages people write programs in into the simple instructions that the circuitry can directly carry out. The language of these simple instructions is a low level programming language often referred to as machine code.

The conversion from a high level to a low level language can involve *compiling*, which replaces the high level instructions with machine code instructions that can then be run, or it can be done by *interpreting*, where each instruction is converted and followed one by one, as the program is run. In reality, a lot of languages use a mixture of these, sometimes compiling a program to an intermediate language, then interpreting it (Java does this). The language we looked at earlier, Python, is an interpreted language. Other languages such as C++ are compiled. We will talk more about compiling and interpreting later.

We will start with looking at low level languages and how computers actually carry out the instructions in them, then we will look at some other programming languages that programmers use to give instructions to computers, and then finally we will talk about how we convert programs that were written by humans in a high level language into a low level language that the computer can carry out.

## Machine Code (Low level languages)

{panel type="teacher-note" summary="Not expecting students to write machine code!"}

Students are NOT expected (or even encouraged) to be able to write their own program in these languages. The purpose of the examples and getting the students to modify them is to help them understand why programming directly in these languages is best avoided, and thus the reason for high level languages.

If they have trouble with a lot of the modifications that are suggested, this is fine. They should not be concerned about it. Remind students that if they were able to modify the high level language programs, but really struggle with these ones, that this is the point of the exercise and that they should explain why it was so difficult in their report.

Having an old CPU (that you will never want to use again) that the students can pass around and look at could be a good thing to do if you can find one.

{panel end}

{comment}

.. xtcb consider putting in alternative assembler examples e.g. 8080, http://www.cs.hmc.edu/~cs5grad/cs5/hmmm/documentation/documentation.html

{comment end}

A computer has to carry out instructions on physical circuits. These circuits contain transistors laid out in a special way that will give a correct output based on the inputs.

{comment}

.. xtcb xhtml [Todo: Put an example here of a simple adder, or in meantime link to something on web]

{comment end}

Data such as numbers (represented using binary) have to be put into storage places called registers while the circuit is processing them. Registers can be set to values, or data from memory can be put into registers. Once in registers, they can be added, subtracted, multiplied, divided, or be checked for equality, greater than, or less than. The output is put into a register, where it can either be retrieved or used in further arithmetic.

All computers have a machine code language (commonly referred to as an instruction set) that is used to tell the computer to put values into registers, to carry out arithmetic with the values in certain registers and put the result into another specified register like what we talked about above. Machine code also contains instructions for loading and saving values from memory (into or out of registers),  jumping to a certain line in the program (that is either before or after the current line), or to jump to the line only if a certain condition is met (by doing a specified comparisons on values in registers). There are also instructions for handling simple input/ output, and interacting with other hardware on the computer.

The instructions are quite different to the ones you will have seen before in high level languages. For example, the following program is written in a machine language called MIPS; which is used on some embedded computer systems. We will use MIPS in examples throughout this chapter.

It starts by adding 2 numbers (that have been put in registers $t0 and $t1) and printing out the result. It then prints “Hello World!” Don’t worry, we aren’t about to make you learn how to actually program in this language! And if you don’t really understand the program, that’s also fine because many software engineers wouldn’t either! (We are showing it to you to help you to appreciate high level languages!)

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

You can run this program using a MIPS emulator using this interactive:

{interactive name="mips-assembler" type="whole-page" text="MIPS Assembler" file-type="php"}

Copy and paste the output in the “Assembler Output” box into the box in this simulator interactive:

{interactive name="mips-simulator" type="whole-page" text="MIPS Simulator" file-type="php"}

Once you have got the program working, try changing the values that are added. The comments tell you where these numbers that can be changed are. You should also be able to change the string (text) that is printed without too much trouble also. As a challenge, can you make it so that it subtracts rather than adds the numbers? Clue: instruction names are always very short. Unfortunately you won’t be able to make it multiply or divide using this simulator as this is not currently supported. Remember that to rerun the program after changing it, you will have to follow both steps 1 and 2 again.

You may be wondering why you have to carry out both these steps. Because computers work in 1’s and 0’s, the instructions need to simply be converted into hexadecimal. Hexadecimal is a shorthand notation for binary numbers. *Don’t muddle this process with compiling or interpreting!* Unlike these, it is much simpler as in general each instruction from the source code ends up being one line in the hexadecimal.

One thing you might have noticed while reading over the possible instructions is that there is no loop instruction in MIPS. Using several instructions though, it actually is possible to write a loop using this simple language. Have another read of the paragraph that describes the various instructions in MIPS. Do you have any ideas on how to solve this problem? It requires being quite creative!

{comment}

.. xjrm: here would be a good place for a box or image, in order to seperate my question from answer
.. ajb took me a while to find the paragraph on instructions referred to. This box could be a table of possible instructions in MIPS?
.. hrn will look at this.
.. xtcb I do not understand what is required here. An image or box of what?

{comment end}

The jumping to a line, and jumping to a line if a condition is met can be used to make loops! A very simple program we could write that requires a loop is one that counts down from five and then says “Go!!!!” once it gets down to one. In Python we can easily write this program in three lines.

```
# Start at 5, count down by 1 each time, and stop when we get to 0
for number in range(5, 0, -1):
   print(number)
print("GO!!!!!")
```

But in MIPS, it isn’t that straightforward. We need to put values into registers, and we need to build the loop out of jump statements. Firstly, how can we design the loop?

{comment}

.. xhrn TODO: Flow chart (I will do this tomorrow)

{comment end}

And the full MIPS program for this is as follows. You can go away and change it.

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

Can you change the Python program so that it counts down from 10? What about so it stops at 5? (You might have to try a couple of times, as it is somewhat counter intuitive. Remember that when i is the stopping number, it stops there and does not run the loop for that value!). And what about decrementing by 2 instead of 1? And changing the string (text) that is printed at the end?

You probably found the Python program not too difficult to modify. See if you can make these same changes to the MIPS program.

If that was too easy for you, can you make both programs print out “GO!!!!” twice instead of once? (you don’t have to use a loop for that). And if THAT was too easy, what about making each program print out “GO!!!!” 10 times? Because repeating a line in a program 10 times without a loop would be terrible programming practice, you’d need to use a loop for this task.

More than likely, you’re rather confused at this point and unable to modify the MIPS program with all these suggested changes. And if you do have an additional loop in your MIPS program correctly printing “GO!!!” 10 times, then you are well on your way to being a good programmer!

So, what was the point of all this? These low level instructions may seem tedious and a bit silly, but the computer is able to directly run them on hardware due to their simplicity. A programmer can write a program in this language if they know the language, and the computer would be able to run it directly without doing any further processing. As you have probably realised though, it is extremely time consuming to have to program in this way. Moving stuff in and out of registers, implementing loops using jump and branch statements, and printing strings and integers using a three line pattern that you’d probably never have guessed was for printing had we not told you leaves even more opportunities for bugs in the program. Not to mention, the resulting programs are extremely difficult to read and understand.

Because computers cannot directly run the instructions in the languages that programmers like, high level programming languages by themselves are not enough. The solution to this problem of different needs is to use a compiler or interpreter that is able to convert a program in the high level programming language that the programmer used into the machine code that the computer is able to understand.

These days, few programmers program directly in these languages. In the early days of computers, programs written directly in machine language tended to be faster than those compiled from high level languages. This was because compilers weren’t very good at minimising the number of machine language instructions, referred to as *optimizing*, and people trained to write in machine code were better at it. These days however, compilers have been made a lot smarter, and can optimize code far better than most people can. Writing a program directly in machine code may result in a program that is *less* optimized than one that was compiled from a high level language. Don’t put in your report that low level languages are faster!

{comment}

.. xtcb point out that compiling for large software can be slow https://xkcd.com/303/

{comment end}

This isn’t the full story; the MIPS machine code described here is something called a Reduced Instruction Set Architecture (RISC). Many computers these days use a Complex Instruction Set Architecture (CISC). This means that the computer chips can be a little more clever and can do more in a single step. This is well beyond the scope of this book though, and understanding the kinds of things RISC machine code can do, and the differences between MIPS and high level languages is fine at this level, and fine for most computer scientists and software engineers.

In summary, we require low level programming languages because the computer can understand them, and we require high level programming languages because humans can understand them. A later section talks more about compilers and interpreters; programs that are used to convert a program that is written in a high level language (for humans) into a low level language (for computers).

{comment}

.. xtcb trivia: Grace Hopper credited with creating first compiler: http://computingportal.org/node/4684

.. xtcb put in activity on interpreter vs. compiler, based perhaps on http://community.computingatschool.org.uk/resources/2521 (Python program that interprets/compiles to turtle language) http://community.computingatschool.org.uk/forums/1/topics/3090

{comment end}

## A Babel of programming languages

There are many different programming languages. Here we have included a small subset of languages, to illustrate the range of purposes that languages are used for. There are many, many more languages that are used for various purposes, and have a strong following of people who find them particularly useful for their applications.

For a much larger list you can [check Wikipedia here](https://en.wikipedia.org/wiki/List_of_programming_languages).

### Python


Python is a widely used language, that has also become very popular as a teaching language. Many people learn Python as their first programming language. In the introduction, we looked at some examples of Python programs, for those who have never programmed before.

Originally though, Python was intended to be a scripting language. Scripting languages have syntax that makes them quick to write programs for file processing in, and for doing repetitive tasks on a computer.

As an example of a situation where Python is very useful, imagine your teacher has given 5 quizzes throughout the year, and recorded the results for each student in a file such as this (It could include more than 6 students), where each student’s name is followed by their scores. Some students didn’t bother going to class for all the quizzes, so have less than 5 results recorded.

```
Karen 12 12 14 18 17
James 9 7 1
Ben 19 17 19 13
Lisa 9 1 3 0
Amalia 20 20 19 15 18
Cameron 19 15 12 9 3
```

She realises she needs to know the average (assuming 5 quizzes) that each student scored, and with many other things to do does not want to spend much time on this task. Using python, she can very quickly generate the data she needs in less than 10 lines of code.

Note that understanding the details of this code is irrelevant to this chapter, particularly if you aren’t yet a programmer. Just read the comments (the things that start with a “#”) if you don’t understand, so that you can get a vague idea of how the problem was approached.

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

This will generate a file that contains each student’s name followed by the result of adding their scores and dividing the sum by 5. You can try the code if you have python installed on your computer (it won’t work on the online interpreter, because it needs access to a file system). Just put the raw data into a file called “scores.txt” in the same format it was displayed above. As long as it is in the same directory as the source code file you make for the code, it will work.

This problem could of course be solved in any language, but some languages make it far simpler than others. Standard software engineering languages such as Java, which we talk about shortly, do not offer such straight forward file processing. Java requires the programmer to specify what to do if opening the file fails in order to prevent the program from crashing. Python does not require the programmer to do this, although does have the option to handle file opening failing should the programmer wish to. Both these approaches have advantages in different situations. For the teacher writing a quick script to process the quiz results, it does not matter if the program crashes so it is ideal to not waste time writing code to deal with it. For a large software system that many people use, crashes are inconvenient and a security risk. Forcing all programmers working on that system to handle this potential crash correctly could prevent a lot of trouble later on, which is where Java’s approach helps.

In addition to straight forward file handling, Python did not require the code to be put inside a class or function, and it provided some very useful built in functions for solving the problem. For example, the function that found the sum of the list, and the line of code that was able to convert the raw line of text into a list of numbers (using a very commonly used pattern).

This same program written in Java would require at least twice as many lines of code.

There are many other scripting languages in addition to Python, such as Perl, Bash, and Ruby.

### Scratch

Scratch is a programming language used to teach people how to program. A drag and drop interface is used so that new programmers don’t have to worry so much about syntax, and programs written in Scratch are centered around controlling cartoon characters or other sprites on the screen.

Scratch is never used in programming in industry, only in teaching. If you are interested in trying Scratch, [you can try it out online here](http://scratch.mit.edu/projects/editor/?tip_bar=getStarted), no need to download or install anything.

{button link="http://scratch.mit.edu/projects/19711355/#editor" text="Example Scratch project"}

This is an example of a simple program in Scratch that is similar to the programs we have above for Python and Java. It asks the user for numbers until they say "stop" and then finds the average of the numbers given.

{image filename="scratch-example-program.png"}

And this is the output that will be displayed when the green flag is clicked:

{image filename="scratch-example-program-output.png"}

Scratch can be used for simple calculations, creating games and animations. However it doesn't have all the capabilities of other languages.

Other educational languages include Alice and Logo. Alice also uses drag and drop, but in a 3D environment. Logo is a very old general purpose language based on Lisp. It is not used much anymore, but it was famous for having a turtle with a pen that could draw on the screen, much like Scratch. The design of Scratch was partially influenced by Logo. These languages are not used beyond educational purposes, as they are slow and inefficient.

### Java

Java is a popular general purpose software engineering language. It is used to build large software systems involving possibly hundreds or even thousands of software engineers. Unlike Python, it forces programmers to say how certain errors should be handled, and it forces them to state what type of data their variables are intended to hold, e.g. *int* (i.e. a number with no decimal places), or *String* (some text data). Python does not require types to be stated like this. All these features help to reduce the number of bugs in the code. Additionally, they can make it easier for other programmers to read the code, as they can easily see what type each variable is intended to hold (figuring this out in a python program written by somebody else can be challenging at times, making it very difficult to modify their code without breaking it!)

This is the Java code for solving the same problem that we looked at in Python; generating a file of averages.

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

While the code is longer, it ensures that the program doesn’t crash if something goes wrong. It says to *try* opening and reading the file, and if an error occurs, then it should *catch* that error and print out an error message to tell the user. The alternative (such as in Python) would be to just crash the program, preventing anything else from being able to run it. Regardless of whether or not an error occurs, the "I am finished!" line will be printed, because the error was safely “caught”. Python is able to do error handling like this, but it is up to the programmer to do it. Java will not even compile the code if this wasn’t done! This prevents programmers from forgetting or just being lazy.

{comment}

.. ajb Probably known but formatting needs to be fixed here

{comment end}

There are many other general software engineering languages, such as C# and C++. Python is sometimes used for making large software systems, although is generally not considered an ideal language for this role.

### JavaScript

- Interpreted in a web browser
- Similar language: Actionscript (Flash)

Note that this section will be completed in a future version of the field guide. For now, you should refer to wikipedia page for more information.

### C

- Low level language with the syntax of a high level language
- Used commonly for programming operating systems, and embedded systems
- Programs written in C tend to be very fast (because it is designed in a way that makes it easy to compile it optimally into machine code)
- Bug prone due to the low level details. Best not used in situations where it is unnecessary
- Related languages: C++ (somewhat)

Note that this section will be completed in a future version of the field guide. For now, you should refer to wikipedia page for more information.

### Matlab

- Used for writing programs that involve advanced math (calculus, linear algebra, etc.)
- Not freely available
- Related languages: Mathematica, Maple

Note that this section will be completed in a future version of the field guide. For now, you should refer to wikipedia page for more information.

### Esoteric Programming Languages

Anybody can make their own programming language. Doing so involves coming up with a syntax for your language, and writing a parser and compiler or interpreter so that programs in your language can be run. Most programming languages that people have made never become widely used.

In addition to programming languages that have practical uses, people have made many programming languages that were intended to be nothing more than jokes, or to test the limits of how obscure a programming language can be. Some of them make the low level machine languages you saw earlier seem rather logical! Wikipedia has a [list of such languages](https://en.wikipedia.org/wiki/Esoteric_programming_language).

You could even make your own programming language if you wanted to!

## How does the computer process your program?

A programming language such as Python or Java is implemented using a program itself --- the thing that takes your Python program and runs it is a program that someone has written!

Since the computer hardware can only run programs in a low level language (machine code), the programming system has to make it possible for your Python instructions to be executed using only machine language. There are two broad ways to do this: interpreting and compiling.

[This 1983 video](https://www.youtube.com/watch?v=_C5AHaS1mOA) provides a good analogy of the difference between an interpreter and a compiler.

The main difference is that a compiler is a program that converts your program to machine language, which is then run on the computer. An interpreter is a program that reads your program line by line, works out what those instructions are, and does them immediately.

There are advantages to both approaches, and each one suits some languages better than others. In reality, most modern languages use a mixture of compiling and interpreting. For example, most Java programs are *compiled* to an "intermediate language" called ByteCode, which is closer to machine code than Java. The ByteCode is then executed by an interpreter.

If your program is to be distributed for widespread use, you will usually want it to be in machine code because it will run faster, the user doesn't have to have an interpreter for your particular language installed, and when someone downloads the machine code, they aren't getting a copy of your original high-level program. Languages where this happens include C#, Objective C (used for programming iOS devices), Java, and C.

Interpreted programs have the advantage that they can be easier to program because you can test them quickly, trace what is happening in them more easily, and even sometimes type in single instructions to see what they do, without having to go through the whole compilation process. For this reason they are widely used for introductory languages (for example, Scratch and Alice are interpreted), and also for simple programs such as scripts that perform simple tasks, as they can be written and tested quickly (for example, languages like PHP, Ruby and Python are used in these situations).

The diagram below shows the difference between what happens in an interpreter and compiler if you write and run a program that sorts some numbers. The compiler produces a machine code program that will do the sorting, and the data is fed into that second program to get the sorted result. The interpreter simply does the sorting on the input by immediately following the instructions in the program. The compiler produces a machine code program that you can distribute, but it involves an extra phase in the process.

{image filename="comparing-sorting-programs-across-scratch-and-c.png" alt="Comparing sorting programs across Scratch and C"}

{comment}

.. xtcb mention cross compilers, especially for mobile apps

{comment end}

## The whole story!

There are many different programming languages, and new ones are always being invented. Each new language will need a new compiler and/or interpreter to be developed to support it. Fortunately there are good tools to help do this quickly, and some of these ideas will come up in the *Formal Languages* chapter, where things like regular expressions and grammars can be used to describe a language, and a compiler can be built automatically from the description.

The languages we have discussed in this chapter are ones that you are likely to come across in introductory programming, but there are some completely different styles of languages that have very important applications. There is an approach to programming called [Functional programming](https://en.wikipedia.org/wiki/Functional_programming) where all operations are formulated as mathematical functions. Common languages that use functional techniques include Lisp, Scheme, Haskell, Clojure and F#; even some conventional languages (such as Python) include ideas from functional programming. A pure functional programming style eliminates a problem called *side effects*, and without this problem it can be easier to make sure a program does exactly what it is intended to do. Another important type of programming is [logic programming](https://en.wikipedia.org/wiki/Logic_programming), where a program can be thought of as a set of rules stating what it should do, rather than instructions on how to do it. The most well-known logic programming language is Prolog.



## Further reading

### Useful Links

- The [TeachICT lesson on programming languages](http://www.teach-ict.com/gcse_computing/ocr/216_programming/programming_languages/miniweb/index.htm) covers many of the topics in this chapter
- CS Online has a [quick overview of this topic](http://courses.cs.vt.edu/~csonline/ProgrammingLanguages/Lessons/Introduction/index.html)
- Wikipedia entries on [Programming language](https://en.wikipedia.org/wiki/Programming_language), [High level language](https://en.wikipedia.org/wiki/High-level_programming_language), and [Low level language](https://en.wikipedia.org/wiki/Low-level_programming_language)

- [website including posters comparing programming languages](http://programming.dojo.net.nz/) by Samuel Williams
- [tutorial comparing programming languages](http://holowczak.com/programming-concepts-tutorial-programmers/)
- a [poster with full details of the file content in an executable file](http://code.google.com/p/corkami/wiki/PE101?show=content) (the exe format)
- David Bolton explains a [Programming Language](http://cplus.about.com/od/introductiontoprogramming/p/programming.htm), [Compiler](http://cplus.about.com/od/introductiontoprogramming/p/compiler.htm), and [the difference between Compilers and Interpreters](http://cplus.about.com/od/introductiontoprogramming/a/compinterp.htm).
- [Computerworld article on the A to Z of programming languages](http://www.computerworld.com.au/article/344826/z_programming_languages/)
- [What is Python?](http://python.about.com/od/gettingstarted/ss/whatispython_4.htm) (compared with other languages)
- A [very large poster showing a timeline of the development of programming languages](http://www.levenez.com/lang/)
- [Hello World program in hundreds of programming languages](http://www.roesler-ac.de/wolfram/hello.htm)
- [99 bottles of beer song in hundreds of programming languages](http://99-bottles-of-beer.net/)


{panel type="teacher-note" summary="Links of interest"}

The following links will be of more interest to teachers

- [a brief overview of many of the key concepts in this chapter](http://userpages.wittenberg.edu/bshelburne/Comp150/ProgrammingLanguages.html)
- [a humorous but not directly relevant history of programming language](http://james-iry.blogspot.co.nz/2009/05/brief-incomplete-and-mostly-wrong.html)

{panel end}
