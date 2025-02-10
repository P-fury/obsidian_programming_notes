Podczas dostępu do instance.attribute, interpreter Python wykonuje następujące kroki w poszukiwaniu wartości:

1️⃣ Data descriptor (__get__, __set__, __delete__)
	•	Jeśli atrybut w klasie jest data descriptor, zostaje wywołany jego __get__.
	•	Data descriptor ma pierwszeństwo przed wszystkim innym.

2️⃣ Slots (__slots__)
	•	Jeśli klasa definiuje __slots__, interpreter sprawdza, czy atrybut jest tam zapisany.
	•	__slots__ ogranicza użycie __dict__ instancji, zmniejszając zużycie pamięci.

3️⃣ Atrybut instancji (instance.__dict__)
	•	Jeśli atrybut istnieje w instance.__dict__, interpreter zwraca jego wartość.
	•	Wykorzystywane, gdy atrybut został ustawiony bezpośrednio na instancji.

4️⃣ Non-data descriptor (__get__ bez __set__)
	•	Jeśli atrybut w klasie ma __get__, ale nie ma __set__, Python traktuje go jako non-data descriptor.
	•	Jeśli nie znaleziono atrybutu w instancji, wywoływana jest jego metoda __get__.

5️⃣ Atrybut klasy (class.__dict__)
	•	Jeśli atrybut nie został znaleziony wcześniej, Python sprawdza class.__dict__.
	•	Jeśli tam go znajdzie, zwraca jego wartość.

6️⃣ __getattr__ i __getattribute__
	•	Jeśli atrybut nadal nie został znaleziony, Python wywołuje __getattr__ (jeśli jest zdefiniowane w klasie).
	•	__getattribute__ jest zawsze wywoływane jako pierwsze, ale może zostać nadpisane w celu kontrolowania dostępu do wszystkich atrybutów.

📌 Podsumowanie:
	•	Data descriptor ma pierwszeństwo nad wszystkim.
	•	Atrybuty instancji są sprawdzane po slots.
	•	Non-data descriptor ma niższy priorytet niż instance.__dict__.
	•	Jeśli nic nie zostanie znalezione, Python sprawdza __getattr__.
	•	Jeśli nadal nic, podnosi AttributeError.