Created: 2025-02-14 11:06

--- 
Note: `inspect` i adnotacje w Pythonie

#### 1. **Adnotacje w Pythonie**

Adnotacje pomagają określić typy argumentów i zwracanej wartości w funkcjach. Są jedynie informacją dla programisty i narzędzi, Python ich nie egzekwuje.

```python
def add(a: int, b: int) -> int:
    return a + b

print(add.__annotations__)
# {'a': <class 'int'>, 'b': <class 'int'>, 'return': <class 'int'>}
```

**Parametry adnotacji:**

- `__annotations__`: słownik z adnotacjami parametrów i zwracanej wartości.
- Mogą zawierać typy wbudowane, klasy użytkownika lub `typing` (np. `List[int]`).

#### 2. **Paczka `inspect`**

Moduł `inspect` pozwala analizować obiekty (funkcje, klasy, metody) w czasie działania programu.

- `inspect.signature(func)`: zwraca obiekt podpisu funkcji.
- `inspect.getmembers(obj)`: zwraca listę `(nazwa, obiekt)` dla wszystkich atrybutów obiektu.

Przykład:

```python
import inspect

def greet(name: str) -> str:
    return f"Hello, {name}!"

# Pobranie adnotacji
print(inspect.signature(greet))
# (name: str) -> str

# Pobranie członków obiektu
print(inspect.getmembers(greet))
# Przykładowy wynik:
# [('__annotations__', {'name': <class 'str'>, 'return': <class 'str'>}),
#  ('__call__', <method-wrapper '__call__' of function object at 0x...>),
#  ('__class__', <class 'function'>),
#  ...]
```

#### 3. **Obiektowość w Pythonie**

Python jest językiem obiektowym – wszystko jest obiektem (liczby, łańcuchy, funkcje, klasy).

**Cechy obiektowości:**

- **Hermetyzacja:** ukrywanie wewnętrznych szczegółów implementacji.
- **Dziedziczenie:** możliwość tworzenia klas potomnych.
- **Polimorfizm:** różne implementacje tej samej metody.
- **Abstrakcja:** ukrycie szczegółów implementacyjnych i eksponowanie jedynie istotnych funkcji.

Przykład klasy z adnotacjami i użyciem `inspect`:

```python
class Person:
    def __init__(self, name: str, age: int):
        self.name = name
        self.age = age

person = Person("Anna", 30)

# Sprawdzenie adnotacji klasy
print(Person.__annotations__)

# Sprawdzenie członków obiektu
print(inspect.getmembers(person))
```

### Podsumowanie

- Adnotacje ułatwiają zrozumienie kodu i są wspierane przez narzędzia typu lintery.
- `inspect` umożliwia dynamiczną analizę kodu.
- Obiektowość to fundament Pythona, który opiera się na klasach, dziedziczeniu, polimorfizmie i abstrakcji.

--- 
Metadata: 

Status: #pending 
Tags: #python #annotation #commands