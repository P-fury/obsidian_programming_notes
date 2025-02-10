# Podstawowe typy danych w Pythonie

## 1. Typy Prymitywne (Primitive Types)

Typy prymitywne to skalarne wartości, które przechowują pojedynczą wartość.

| Typ       | Opis                           | Właściwości                                         |
| --------- | ------------------------------ | --------------------------------------------------- |
| `int`     | Liczby całkowite               | Scalar, Immutable, Ordered                          |
| `float`   | Liczby zmiennoprzecinkowe      | Scalar, Immutable, Ordered                          |
| `complex` | Liczby zespolone               | Scalar, Immutable, Ordered, posiada `real` i `imag` |
| `bool`    | Wartości logiczne `True/False` | Scalar, Immutable, Ordered                          |
| `str`     | Ciąg znaków                    | Scalar, Immutable, Ordered                          |

## 2. Typy Złożone (Complex Types)

Typy złożone przechowują wiele wartości jednocześnie.

|   |   |   |
|---|---|---|
|Typ|Opis|Właściwości|
|`list`|Dynamiczna kolekcja elementów|Collection, Mutable, Ordered, Heterogenic|
|`tuple`|Niemutowalna lista|Collection, Immutable, Ordered, Heterogenic|
|`range`|Generuje sekwencję liczb|Collection, Immutable, Ordered|
|`set`|Kolekcja unikalnych wartości|Collection, Mutable, Unordered, Heterogenic|
|`frozenset`|Niemutowalna wersja `set`|Collection, Immutable, Unordered, Heterogenic|
|`dict`|Mapa klucz-wartość|Collection, Mutable, Ordered (od Python 3.7+), Heterogenic|
|`bytearray`|Mutowalna sekwencja bajtów|Collection, Mutable, Ordered|
|`memoryview`|Widok na bufor pamięci|Collection, Immutable, Ordered|

## 3. Typ Specjalny (Special Type)

|   |   |   |
|---|---|---|
|Typ|Opis|Właściwości|
|`NoneType`|Brak wartości|Scalar, Immutable, Brak wartości|

## 4. Podział według właściwości

|   |   |   |   |   |
|---|---|---|---|---|
|Typ|Kategoria|Mutable?|Ordered?|Heterogenic?|
|`int`|Scalar|❌ Nie|✅ Tak|❌ Nie|
|`float`|Scalar|❌ Nie|✅ Tak|❌ Nie|
|`complex`|Scalar|❌ Nie|✅ Tak|❌ Nie|
|`bool`|Scalar|❌ Nie|✅ Tak|❌ Nie|
|`str`|Scalar|❌ Nie|✅ Tak|❌ Nie|
|`list`|Collection|✅ Tak|✅ Tak|✅ Tak|
|`tuple`|Collection|❌ Nie|✅ Tak|✅ Tak|
|`range`|Collection|❌ Nie|✅ Tak|❌ Nie|
|`set`|Collection|✅ Tak|❌ Nie|✅ Tak|
|`frozenset`|Collection|❌ Nie|❌ Nie|✅ Tak|
|`dict`|Collection|✅ Tak|✅ Tak (od 3.7)|✅ Tak|
|`bytearray`|Collection|✅ Tak|✅ Tak|❌ Nie|
|`memoryview`|Collection|❌ Nie|✅ Tak|❌ Nie|
|`NoneType`|Special|❌ Nie|❌ Nie|❌ Nie|

**Scalar** – pojedyncza wartość, np. int, float, bool, None.
>• **Nie przechowuje wielu elementów.**
• **Immutable** (niezmienny po przypisaniu nowej wartości).
• **Ordered** (ma określoną wartość w porządku liczbowym). 


• **Collection** – struktura przechowująca wiele elementów, np. list, tuple, set, dict.
>• **Może zawierać wiele wartości** (jednorodnych lub różnorodnych).
• **Może być mutable (**list**) lub immutable (**tuple**,** frozenset**)**.
• **Może być ordered (**list**,** tuple**) lub unordered (**set**,** dict**)**.!

![[- visual selection.png]]![[- visual selection(1).png]]