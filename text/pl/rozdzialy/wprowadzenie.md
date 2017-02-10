# Wprowadzenie

{panel type="teacher-note" summary="Wprowadzenie dla nauczycieli"}

Celem tego przewodnika (interaktywnego podręcznika) jest wsparcie procesu nauczania informatyki w szkołach średnich.
Pierwotnie podręcznik został tworzony w związku z wprowadzeniem zajęć informatyki do szkół średnich w Nowej Zelandii w latach 2011-2013.

W wersji dla nauczyciela w specjalnych ramkach dodano informacje dla nauczyciela oraz odpowiedzi i wskazówki do zadań.

{panel end}

{video url="https://wwww.youtube.com/embed/v5yeq5u2RMI?rel=0"}

## Z lotu ptaka

Dlaczego jest tak, że ludzie albo kochają komputery albo ich nienawidzą? Dlaczego niektórzy nie wyobrażają sobie życia bez różnego rodzaju urządzeń komputerowych, a  inni na samą myśl o takich urządzeniach są poirytowani i są nawet gotowi zniszczyć sprzęt komputerowy? I co to ma wspólnego z informatyką? I co to jest w ogóle informatyka?

Dobrze, że zadajesz takie pytania!

Wielu ludzi myli informatykę z programowaniem. Ktoś kiedyś powiedział „Informatyka ma tyle samo wspólnego z programowaniem, co astronomia z teleskopami” ([Mike Fellows](http://en.wikiquote.org/wiki/Computer_science)). 
Programowanie to narzędzie, którym informatycy posługują się, aby urzeczywistnić różne wspaniałe pomysły, które mogą zmienić życie ludzi na lepsze. Jednak wyłącznie znajomość składni języka programowania nie wystarczy, by tworzyć oprogramowanie szybkie, przyjazne w użyciu, niezawodne, bezpieczne, użyteczne i do tego zabawne! 

Oto przykład: Komputery potrafią wykonywać miliardy operacji w ciągu sekundy, a ciągle możemy usłyszeć narzekania, że są zbyt powolne. Człowiek jest w stanie dostrzec ułamek czasu rzędu 1/10 sekundy. Jeśli na odpowiedź programu komputerowego ktoś czeka dłużej, to może uznać program za powolny, działający mało płynnie i frustrujący. Aby zadowolić użytkownika, reakcja programu na polecenie użytkownika powinna pojawić się o wiele szybciej niż w ciągu sekundy! Jeśli stworzony przez Ciebie program przeszukuje miliony pozycji w danych lub wyświetla miliony pikseli (megapiksele), to nie możesz pozwolić sobie na to, aby działał w sposób nieefektywny. Nie możesz po prostu powiedzieć użytkownikowi, by kupił szybszy komputer ...skończy się prawdopodobnie tym, że użytkownik podziękuje Ci za współpracę i pójdzie kupić u konkursencji szybsze oprogramowanie!

Oto rada pochodząca od Freda Wilsona, który zainwestował wiele w firmy z branży komputerowej:

> Po pierwsze i najważniejsze, wierzymy, że szybkość to coś więcej niż cecha (właściwość). Szybkość jest najważniejszą cechą. Jeśli twoje oprogramowanie działa powoli, ludzie nie będą go używać. Dotyczy to zwłaszcza zwykłych użytkowników. Myślę, że użytkownicy, którzy korzystają z zaawansowanych funkcji danego oprogramowania, są czasami bardziej wyrozumiali, ale kiedy patrzę na moją żonę i moje dzieci, to oni są dla mnie jak zwykli, typowi używkownicy. Jeśli coś działa powoli, to oni po prostu odchodzą. ...Szybkość to coś więcej niż cecha. To jest niezbędne wymaganie.

> -- [Fred Wilson](https://en.wikipedia.org/wiki/Fred_Wilson_(financier\)) ([Source](http://triple-networks.com/2011/12/06/10-golden-principles-of-successful-web-apps/))

Kluczowym wyzwaniem w informatyce jest stworzyć oprogramowanie działające szybko! Zwłaszcza jeśli ma działać na urządzeniach (np. smarfonach) starszej generacji lub ma być uruchamiane je w jakimś centrum obliczeniowym (superkomputerowym), gdzie użytkownik ma płacić za każdą minutę czasu dostępu do komputerów. 
Nie można powiedzieć klientom, by kupili szybsze urządzenia --- trzeba dostarczyć efektywne oprogramowanie.

## Szybkość to nie wszystko

W informatyce nie chodzi jedynie o szybkość.
Spróbuj wykonać jakieś proste obliczenia, posługując się dwoma kalkulatorami, udostępnionymi poniżej. Oba mają tę samą funkcjonalność (można na nich wykonać te same obliczenia), ale jeden z nich jest bardziej przyjazny w obsłudze. Dlaczego?

(W podręczniku jest wiele podobnych interaktywnych narzędzi. Aby ich używać, będziesz potrzebować aktualnych wersji przeglądarek internetowych.)

{interactive name="awful-calculator" type="in-page"}

Drugi kalkulator działa wolniej i to może być frustrujące. Ale ma bardziej ekstrawagancki interfejs – klawisze są wyświetlane w powiększeniu po wskazaniu ich myszką. Czy to ułatwia posługiwanie się kalkulatorem? Czy umieszczenie bardzo blisko siebie klawiszy "C" i "=" nie było źródłem dodatkowych problemów

Projektowanie przyjaznych w użyciu interfejsów jest istotne w informatyce. Estetyka (wygląd i grafika) interfejsu jest ważna, ale bardziej istotne jest uwzględnienie w nim zasad psychologii  zachowań użytkownika.  Oto przykład: Wyobraź sobie, że przyciski "OK" i "Anuluj" od czasu do czasu w oknach dialogowych będą zamienione miejscami. W konsekwencji użytkownik musi zachować szczególną ostrożność, zamiast działać instynktownie nauczony wcześniej w niezliczonej liczbie podobnych przypadków. 

Problem skalowalności oprogramowania to inny ważny temat. Wyobraź sobie, że jesteś twórcą witryny internetowej, którą odwiedzają tysiące użytkowników. Wszystko idzie dobrze, aż do chwili, gdy gwałtownie zwiększa się liczba użytkowników i są ich miliony. Jeśli twój serwis okaże się przeciążony, ludzie będą się irytować czekaniem na odpowiedź serwera, i kolejnego dnia możesz stracić wszystkich użytkowników – przeniosą się do serwisu,  stworzonego przez kogoś innego. Ale jeśli twoje programy są tak zaprojektowane, że nigdy nie dojdzie do przeciążenia, to  możesz się spodziewać, że  pojawią się zainteresowani kupnem twojej firmy!

Niektóre z problemów można rozwiązań przez zakup większej ilości sprzętu komputerowego (serwerów), ale to może być kosztowna i rozrzutna opcja. Do tego takie rozwiązanie ma niekorzystny wpływ na środowisko, gdyż wiąże się ze zwiększeniem zapotrzebowania na energię elektryczną (potrzebną m.in. do chłodzenia urządzeń). W przypadku urządzeń przenośnych wymagania, aby oprogramowanie działało szybko i wykorzystywało zasoby w sposób ekonomiczny (energooszczędny) mają jeszcze większe znaczenie. Nieefektywne przetwarzanie oznacza nie tylko większe zużycie baterii, ale i większe zapotrzebowanie oprogramowania na pamięć, czyli w konsekwencji zwiększenie rozmiaru i wagi urządzenia, a więc i kosztów związanych np. z chłodzeniem. 

Załóżmy optymistycznie, że Twój serwis internetowy nigdy nie jest przeciążony i znakomicie sobie radzi z obsługą milionów użytkowników. Pojawia się kolejne pytanie: czy Twoja witryna jest bezpieczna? Czy zostały zastosowane odpowiednie zabezpieczenia, aby nikt nie mógł się włamać do serwisu i wykraść dane użytkowników? W jaki sposób należy projektować systemy, aby zapewnić poufność informacji o klientach i ich transakcjach?

All these questions and more are addressed by the field of computer science. The purpose of this guide is to introduce you to those ideas so that you have a better idea of whether this field is for you. It is aimed at high-school level, and is intended to bring you to the point where you have a good overview of the field, and are well prepared for further in-depth study to become an expert.
Informatyka zajmuje się szukaniem odpowiedzi na te wszystkie pytania. I nie tylko te!
Celem tego przewodnika jest przedstawienie w sposób przystępny różnych pojęć i koncepcji informatycznych, aby poszerzyć twoją wiedzę na temat informatyki i dać ci lepsze wyobrażenie temat różnych zagadnień informatycznych.  Ten podręcznik ma pomóc ci w rozeznaniu, czy informatyka to jest dziedzina dla ciebie na tyle interesująca, by wiązać z nią swoją przyszłość zawodową.
Przewodnik jest skierowany do uczniów szkół ponadpodstawowych. 

Podzieliliśmy całość na wiele zagadnień, które razem tworzą całość curriculum z informatyki. Są to m.in. algorytmy, interakcja człowiek — komputer, kompresja danych, kryptografia, grafika komputerowa i sztuczna inteligencja. Trzeba podkreślić, że te tematy są ze sobą powiązane i należy o tym pamiętać w czasie zaznajamiani się z nimi. 

Przewodnik ma taki poziom szczegółowości, że pozwoli ci uzyskać niezłe pojęcie o tym, czym jest informatyka. Przewodnik ma  dobrze przygotowywać do późniejszych pogłębionych studiów na lekcjach w szkole średniej, czy szkole wyższej. W tekście znajduje się wiele odnośników do stron internetowych i podane są informacje o książkach, w których możesz znaleźć bardziej szczegółowe informacje.

## Programming

And what about programming? You can get through this whole guide without doing any programming, although we'll suggest exercises. Ultimately, however, all the concepts here are reflected in programs that people write. If you want to learn programming there are many excellent courses available. It takes time and practice, and is well worth doing in parallel with working through the topics in this guide. There are a number of free online systems and books that you can use to teach yourself programming.
A list of options for learning to program is being compiled by [code.org](http://www.code.org/), where there is also a popular video of some well-known high-fliers in computing that is good to show classes. Here are some other sources that might suit you:

-  [The NCEA year 12 workbook](http://www.cs.otago.ac.nz/year12dt/) is a book (two actually) on programming in Java and Python, written for the NZ achievement standards. The authors are developing a second book for the year 13 programming standard.
- [CodeAvengers](http://www.codeavengers.com)  is an online system where you can work through challenges that will introduce you to programming in Javascript. This system matches the NZ programming achievement standards from level 1 to 3.
- [Interactive Python](http://interactivepython.org/) has a free online "book" called "How to Think Like a Computer Scientist: Interactive Edition" (also referred to as "Think Python") which teaches the Python language, and enables students to edit and run Python examples within the web browser. The original book is open source and is also available in various non-interactive versions.
- [Codecademy](http://www.codecademy.com) is an online system where you can learn languages including Python and Javascript
- [Coder Dojo](http://coderdojo.com) is a "movement orientated around running free not-for-profit coding clubs and regular sessions for young people".
- [Python tutor](http://pythontutor.com/) allows you to run Python in your web browser --- no installation needed.
- [CodingBat](http://codingbat.com) has hundreds of programming challenges that you can try to check on how you are progressing with learning to program.
- [Greenfoot](http://greenfoot.org/) is a visual, interactive system that teaches object orientation with Java. You create 'actors' that live in 'worlds' to build games, simulations, and other graphical programs.
- [Khan Academy](http://www.khanacademy.org/cs/) has a "Computer Science" section; most of the material here is about programming rather than computer science in general.
- [Grok Learning](https://groklearning.com/) is a new site for learning to code
- [Learn Python the Hard Way](http://learnpythonthehardway.org/) is a rigorous (but fun) introduction to Python for beginners who are prepared to work hard. It's available for free online, or you can buy a book. It comes with the warning that it may cause students to think!

The following programming teaching systems are aimed more at younger students, or are based around a "drag and drop" language which is only intended as a teaching tool:

- [ScratchEd](http://scratched.media.mit.edu) provides extensive educational material for Scratch, which is a drag-and-drop programming language centred around creating 2D animations. Scratch has many of the features of more conventional languages. The [Snap! (BYOB)](http://byob.berkeley.edu/) system is based on Scratch, and has some more advanced features.
- [Computer Science Concepts in Scratch](http://stwww.weizmann.ac.il/g-cs/scratch/scratch_en.html) is a book on programming in Scratch.
- [Alice](http://alice.org/) is an educational programming language based around creating 3D animations.
- [Kodu](http://www.kodugamelab.com/) is a visual programming tool that is also available of Xbox.
- [Snake wrangling for kids](http://briggs.net.nz/snake-wrangling-for-kids.html) is a free downloadable book that introduces younger students to Python programming.

And there are [dozens of other websites and systems](https://en.wikipedia.org/wiki/List_of_educational_programming_languages) for learning about programming.

Programming is just one of the skills you'll need to be a computer scientist. In this book you'll be exercising many other skills --- maths, psychology, and communication are important ones.

## How to use this guide

This guide is intended to support a variety of curricula, and teacher guides will become available for using it in different contexts. For students, we've designed most chapters so that they can stand alone; the few that build on previous chapters explain at the outset what preparation you need (the most useful general preparation is the chapter on data representation, because everything on a computer is stored using binary numbers and so they have an important role in many areas of computer science.)

Each chapter begins with a section about the "big picture" --- why the topic is useful for understanding and designing computer systems, and what can be achieved using the main ideas in the chapter. You'll then be introduced to key ideas and applications of the topic through examples, and wherever possible we'll have interactive activities that enable you to work with the ideas first hand. Sometimes these will be simplified versions of the full sized problems that computer scientists need to deal with -- our intention is for you to actually interact with the ideas, not just read about them. Make sure you give them a go!

We finish each chapter by talking about the "whole story," giving hints about parts of the topic that we omitted because we didn't want to make the chapter too overwhelming. There will be pointers for further reading, but be warned that some of it might be quite deep, and require advanced math or programming skills.

If you are doing this for formal study, you'll end up having to do some sort of assessment. The chapters provide ideas for projects and activities that could be used for this, and the appendix has more detailed guidance for assessment (currently designed for the New Zealand NCEA requirements).

## About this guide

This guide is free for you to copy, share and even modify. It is currently available online, and we plan to have versions available for ebooks, and as a downloadable PDF file (although it's much better viewed in the other formats because you can watch the videos and use the interactive activities).
The source material (all raw text, images, videos and interactive programs) is available through the "Contribute on GitHub" link.

This guide is licenced under a [Creative Commons Attribution-NonCommercial-ShareAlike licence](http://creativecommons.org/licenses/by-nc-sa/4.0/), which means that you are welcome to take copies and modify them. If you do make improvements, we ask that you share those, and acknowledge this guide by linking back to our web site. You can give away the guide (or any derivatives), and you can use it for teaching, but you’re not allowed to sell it directly for profit.

Production of the guide was partially funded by a generous grant from Google Inc., and supported by the University of Canterbury. Of course, we welcome donations to support further work on the guide.

## Further reading
Each chapter gives suggestions for further reading for that particular topic. There are also plenty of general books and websites about computer science that you might want to read to keep your view of the topic broad.

Books that we particularly recommend include:

- Algorithmics, by David Harel
- [Computational fairy tales](http://computationaltales.blogspot.co.nz), by Jeremy Kubica
- Algorithmic adventures: from knowledge to magic, by Jurag Hromkovic
- The Turing Omnibus, by A.K. Dewdney

Wikipedia has a fairly extensive [entry on computer science](https://en.wikipedia.org/wiki/Computer_science).

The  AQA Computing A2 book(s), by Sylvia Langfield and Kevin Bond, give a more detailed account of many of these topics.

The ["Nested" Youtube channel](https://www.youtube.com/channel/UCp-hlYynzR5VW18ITtrcMtQ) has some videos that introduce different computer science topics (for example: binary search) and closely match the topics in this Field Guide.

There are also some excellent general web sites about Computer Science, many of which we've referenced in other chapters:

- [Computer Science For Fun](http://www.cs4fn.org) --- a very readable collection of short articles about practical applications of topics in computer science
- [Babbage's bag](http://www.i-programmer.info/babbages-bag/) is an excellent collection of technical articles on many topics in computing.
- [CS Bytes](http://www.nsf.gov/cise/csbytes/) has up-to-date articles about applications of computer science.
- [Thriving in our digital world](http://www.cs.utexas.edu/~engage/) has some excellent information and  interactive material on topics from computer science.
- [The Virginia tech online interactive modules for teaching computer science](http://courses.cs.vt.edu/csonline/) cover a range of relevant topics.
- [CS animated](http://www.csanimated.com/) has interactive activities on computer science.
- [CS for All](http://www.cs.hmc.edu/csforall/)

