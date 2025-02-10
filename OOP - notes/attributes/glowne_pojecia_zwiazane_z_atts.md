1️⃣ Lookup – mechanizm wyszukiwania atrybutów
	•	Python najpierw sprawdza, czy atrybut istnieje w __dict__ obiektu.
	•	Jeśli nie, przechodzi do klasy (type(self)) i klasy nadrzędnej (MRO – Method Resolution Order).
	•	W przypadku braku atrybutu sprawdzana jest metoda __getattr__, a jeśli jej nie ma – Python podnosi AttributeError.

2️⃣ Metody __getattribute__ i __getattr__
	•	__getattribute__ jest zawsze wywoływana jako pierwsza przy dostępie do atrybutu.
	•	__getattr__ działa tylko wtedy, gdy __getattribute__ nie znalazło atrybutu.
	•	Pozwalają na dynamiczne kontrolowanie dostępu do atrybutów.

3️⃣ Blokowanie modyfikacji atrybutów (__setattr__ i __delattr__)
	•	__setattr__ może uniemożliwiać nadpisywanie atrybutów, np. blokowanie zmian wartości.
	•	__delattr__ może zapobiegać usuwaniu atrybutów, co jest używane np. w atrybutach obliczanych dynamicznie.

4️⃣ Proxy – obiekt pośredniczący
	•	Klasy proxy przekierowują dostęp do atrybutów innego obiektu (LoggingProxy).
	•	Umożliwia to np. śledzenie dostępu do atrybutów bez zmieniania głównej klasy.

5️⃣ Descriptor – kontrolowanie atrybutów na poziomie klasy
	•	__get__, __set__, __delete__ pozwalają na modyfikację sposobu przechowywania i walidacji atrybutów (Positive).
	•	WeakKeyDictionary przechowuje wartości per instancja klasy, ale nie utrzymuje ich w pamięci na stałe.

6️⃣ __slots__ – optymalizacja przechowywania atrybutów
	•	Ogranicza atrybuty tylko do zdefiniowanych nazw, co zmniejsza zużycie pamięci.
	•	Blokuje dynamiczne dodawanie nowych atrybutów do instancji.

🚀 Wnioski:
✔ Lookup definiuje kolejność wyszukiwania atrybutów i może być modyfikowany.
✔ __getattribute__, __getattr__, __setattr__ dają pełną kontrolę nad dostępem do atrybutów.
✔ Proxy pozwala monitorować atrybuty i ich zmiany bez modyfikacji klasy źródłowej.
✔ __slots__ zwiększa wydajność i ogranicza pamięć, ale kosztem elastyczności.

![file:/Users/pfury/Documents/MY_PROJECTS/oop_projects/attributes_/wywoalnie_dekryptorow.png](file:///Users/pfury/Documents/MY_PROJECTS/oop_projects/attributes_/wywoalnie_dekryptorow.png)