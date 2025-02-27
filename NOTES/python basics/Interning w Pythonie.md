Created: 2025-02-27 12:29

--- 
Note:
**📝 Interning w Pythonie**

  

**Interning** to technika optymalizacji pamięci w Pythonie, która polega na **ponownym użyciu tych samych obiektów**, zamiast tworzenia nowych. Dzięki temu możemy **oszczędzać pamięć** i **przyspieszać porównania obiektów**.

**📌 1. Jak działa interning?**

  
Python automatycznie internuje:

✅ **Małe liczby całkowite (-5 do 256)** – te same wartości są współdzielone w pamięci.

✅ **Niektóre krótkie stringi** – np. "hello" czy "python", jeśli składają się tylko z liter i cyfr.
  

Przykład:

```
a = 100
b = 100
print(a is b)  # True

x = "hello"
y = "hello"
print(x is y)  # True
```

📌 **Python współdzieli obiekty, aby oszczędzać pamięć.**

**🔥 2. Interning w obiektach – przykład cache’owania w __new__**

  

Interning można także **zaimplementować ręcznie** dla własnych klas poprzez **cache w __new__**, jak w kodzie ze zdjęcia:

```
class A:
    _cache = {}  # Przechowywanie istniejących instancji

    def __new__(cls, x, y):
        key = f"{x}-{y}"  # Tworzymy unikalny klucz dla obiektu

        if key not in cls._cache:
            cls._cache[key] = super().__new__(cls)  # Tworzymy instancję tylko raz

        return cls._cache[key]  # Zwracamy istniejącą instancję

# Test
a1 = A(1, 2)
a2 = A(1, 2)
a3 = A(3, 4)

print(a1 is a2)  # True, bo obiekty są internowane
print(a1 is a3)  # False, bo klucz (3,4) jest nowy
```

📌 **Obiekty o tych samych wartościach ((1,2)) są współdzielone, dzięki czemu oszczędzamy pamięć.**

**⚡ 3. sys.intern() dla stringów**

  

Dla stringów możemy wymusić interning ręcznie za pomocą sys.intern():

```
import sys

s1 = sys.intern("very_long_string_example")
s2 = sys.intern("very_long_string_example")

print(s1 is s2)  # True
```

📌 **Dzięki temu Python przechowuje tylko jedną kopię stringa w pamięci.**

**🚀 4. Podsumowanie**

  

✅ **Interning** pozwala na **oszczędzanie pamięci** i **przyspieszanie porównań**.

✅ Python **automatycznie internuje małe liczby i niektóre stringi**.

✅ **Możemy ręcznie wdrożyć interning** dla własnych obiektów poprzez **cache w __new__**.

✅ **sys.intern()** pozwala wymusić interning dla stringów.

  

📌 **Warto stosować interning, gdy często używamy tych samych danych i chcemy oszczędzać zasoby.**
--- 
Metadata: 

Status: #pending 
Tags: #python