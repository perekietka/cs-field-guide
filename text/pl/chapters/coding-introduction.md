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
