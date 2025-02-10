1️⃣ Programowanie obiektowe (OOP) – Klasy i obiekty
	•	Klasa to szablon definiujący wspólne cechy i zachowania obiektów.
	•	Obiekt to konkretna instancja klasy, posiadająca swoje dane i metody.
	•	Atrybuty instancji są przechowywane w __dict__, co pozwala na dynamiczne zarządzanie danymi.

2️⃣ Hermetyzacja i kontrola dostępu (@property)
	•	@property pozwala na kontrolę dostępu do atrybutów obiektu, działając jak getter.
	•	Setter (@property_name.setter) umożliwia ustawianie wartości z dodatkowymi warunkami walidacji.
	•	Deleter (@property_name.deleter) pozwala na usunięcie atrybutu w kontrolowany sposób.
	•	Zastosowanie @property pozwala na enkapsulację logiki biznesowej, np. walidację minimalnej wartości wynagrodzenia, przeliczanie wartości w różnych jednostkach lub ukrywanie wewnętrznych reprezentacji danych.

3️⃣ Specjalne metody (__str__, __repr__, __add__)
	•	__str__ zwraca czytelną, przyjazną użytkownikowi reprezentację obiektu.
	•	__repr__ zwraca techniczną reprezentację obiektu, przydatną do debugowania.
	•	__add__ umożliwia przeciążenie operatora +, co pozwala np. sumować obiekty.

4️⃣ Modyfikacja zachowania klas (__dict__, __slots__, mixiny)
	•	__dict__ umożliwia dynamiczne dodawanie i modyfikację atrybutów instancji.
	•	__slots__ ogranicza możliwość dodawania nowych atrybutów, co poprawia wydajność.
	•	Mixiny to małe klasy pomocnicze, dodające funkcjonalności bez zmiany głównej hierarchii dziedziczenia.

5️⃣ Atrybuty współdzielone przez instancje klasy
	•	Atrybuty zdefiniowane na poziomie klasy są współdzielone przez wszystkie instancje.
	•	Jeśli instancja nadpisze taki atrybut, otrzyma własną kopię, niezależną od wartości w klasie.
	•	Zmiana atrybutu w klasie wpływa na wszystkie instancje, które go nie nadpisały.

6️⃣ Obsługa wyjątków i solidność kodu
	•	try-except pozwala na bezpieczne wychwytywanie błędów i zapobieganie awariom.
	•	Hierarchia wyjątków pozwala na dokładniejsze kontrolowanie błędów, np. różnicowanie między błędami arytmetycznymi a dzieleniem przez zero.

7️⃣ Metaprogramowanie i dynamiczne zachowanie klas
	•	Dynamiczne atrybuty (__dict__) pozwalają na elastyczne rozszerzanie obiektów.
	•	Metody można definiować i modyfikować w trakcie działania programu (__str__ = __repr__).

8️⃣ Defensywne programowanie i bezpieczeństwo
	•	Ograniczanie atrybutów (__slots__).
	•	Kontrola dostępu do danych (property, getter, setter).
	•	Walidacja wartości, np. ograniczanie minimalnych lub maksymalnych wartości atrybutów w setterach.


🚀 Główne wnioski:
✔ Kod skupia się na programowaniu obiektowym, hermetyzacji i dziedziczeniu.
✔ Wykorzystuje nowoczesne techniki Pythonowe – @property, __slots__, dynamiczne atrybuty.
✔ Zapewnia odporność na błędy i elastyczność – walidacja danych, obsługa wyjątków, przeciążanie operatorów.
