🛠️ 1. Klasy Abstrakcyjne (ABC, ABCMeta)
	•	Klasy abstrakcyjne definiują interfejsy, które muszą być zaimplementowane przez klasy dziedziczące.
	•	W Pythonie są tworzone za pomocą ABC (Abstract Base Class) lub ABCMeta.
	•	Nie można tworzyć instancji klasy abstrakcyjnej – wymusza ona implementację metod oznaczonych jako abstrakcyjne.

🔹 2. Metody Abstrakcyjne (@abstractmethod)
	•	Metoda abstrakcyjna to metoda zadeklarowana w klasie abstrakcyjnej, która nie ma implementacji.
	•	Klasa dziedzicząca musi ją zaimplementować, inaczej nie można utworzyć jej instancji.

♻️ 3. Idempotentność (Idempotency)
	•	Idempotentna operacja daje ten sam wynik niezależnie od liczby jej wywołań.
	•	W programowaniu odnosi się do metod, które nie zmieniają stanu obiektu przy wielokrotnym wywołaniu.
	•	Przykłady idempotentnych operacji to np. pobieranie wartości (getter), podczas gdy operacje modyfikujące (setter) mogą nie być idempotentne.

🔄 4. Dekoratory i Transparentność
	•	Dekorator to funkcja, która modyfikuje inną funkcję lub metodę.
	•	Transparentność dekoratora oznacza, że dekorowana funkcja zachowuje swoje metadane (__name__, __doc__).
	•	Python dostarcza functools.wraps, aby zachować nazwę i docstring funkcji.

🚀 5. Kluczowe wnioski
	•	🛠️ Klasy abstrakcyjne: Definiują interfejsy, nie mogą być instancjonowane.
	•	🔹 Metody abstrakcyjne: Muszą być zaimplementowane w podklasach.
	•	♻️ Idempotentność: Metoda daje ten sam wynik niezależnie od liczby wywołań.
	•	🔄 Dekoratory i wraps: Dekoratory powinny być transparentne, aby zachować metadane.