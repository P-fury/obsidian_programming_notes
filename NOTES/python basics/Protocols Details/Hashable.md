Created: 2025-02-22 21:24

--- 
**Note:**

  

**Hashowalność w Pythonie**

  

**Hashowalność** oznacza, że obiekt ma:

1. Wartość skrótu zwracaną przez metodę ___hash___.

2. Stałą wartość skrótu przez cały czas życia obiektu.

3. Możliwość porównania z innymi obiektami przez metodę ___eq___.

  

**Zasada spójności:** Jeśli dwa obiekty są równe (__eq__ zwraca True), muszą mieć ten sam hash.

  

**Typy wbudowane:**

• Hashowalne: int, float, str, tuple (jeśli wszystkie elementy są hashowalne), frozenset.

• Niehashowalne: list, dict, set (są mutowalne, więc ich hash mógłby się zmieniać).

  

**Praktyczne zastosowania:**

• Klucze w słownikach (dict).

• Elementy w zbiorach (set).

• Używane w funkcjach wymagających unikalnych identyfikatorów (lru_cache, set, dict).

  

**Przykład:**
```python
# Przykład hashowalności typu niezmiennego (tuple)
t = (1, 2, 3)
print(hash(t))  # Działa, bo tuple jest niemutowalne

# Przykład typu niehashowalnego (list)
try:
    l = [1, 2, 3]
    print(hash(l))
except TypeError:
    print("Listy nie są hashowalne, ponieważ są mutowalne.")
```
**Tworzenie własnych hashowalnych obiektów:**

Jeśli tworzysz klasę, która ma być hashowalna:
4. Zdefiniuj ___hash___.
5. Zdefiniuj ___eq___ dla poprawnego porównywania.

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def __eq__(self, other):
        return isinstance(other, Book) and self.title == other.title and self.author == other.author

    def __hash__(self):
        return hash((self.title, self.author))

# Przykład użycia
b1 = Book("1984", "George Orwell")
b2 = Book("1984", "George Orwell")

books = {b1}
print(b2 in books)  # True, bo b1 i b2 są równi i mają ten sam hash
```
--- 
Metadata: 

Status: #pending 
Tags: #empty