Created: 2025-03-04 12:38

--- 
Note: 
## 1. Czym są descriptory?

Descriptory w Pythonie to mechanizm pozwalający na dostosowanie sposobu uzyskiwania i ustawiania wartości atrybutów w obiektach. Wykorzystuje on metody `__get__`, `__set__` i `__delete__`, które pozwalają na przechowywanie danych poza standardowym słownikiem `__dict__` instancji klasy.

## 2. Przykład użycia descriptorów

W podanym kodzie tworzony jest descriptor `BitFieldDescriptor`, który kontroluje dostęp do wartości atrybutu `value_1` w klasie `Magic`.

### **BitFieldDescriptor – klasa descriptorów**

```python
from weakref import WeakKeyDictionary

class BitFieldDescriptor(property):
    def __init__(self, *args, **kwargs):
        self._instance_data = WeakKeyDictionary()

    def __get__(self, instance, owner):
        print('getter')
        return self._instance_data[instance]

    def __set__(self, instance, value):
        print('setter')
        self._instance_data[instance] = value
```

- `**__init__**` – tworzy słownik `WeakKeyDictionary()`, który przechowuje wartości przypisane do różnych instancji klasy.
    
- `**__get__**` – zwraca wartość przechowywaną w `_instance_data` dla danej instancji.
    
- `**__set__**` – zapisuje wartość w `_instance_data`, jednocześnie wyświetlając komunikat „setter”.
    

### **Klasa Magic – wykorzystanie descriptorów**

```python
class Magic:
    def __init__(self):
        self.value_1 = 42
        self.value_2 = 2137

    @BitFieldDescriptor
    def value_1(self):
        return self.value_1

    @value_1.setter
    def value_1(self, value):
        self.value_1 = value
```

- **Atrybut** `**value_1**` w `Magic` używa `BitFieldDescriptor`, co oznacza, że jego dostęp i modyfikacja są kontrolowane przez ten descriptor.
    
- `**@BitFieldDescriptor**` przypisuje metodę `value_1` jako getter, a `@value_1.setter` definiuje setter, ale kod zawiera błąd (o tym poniżej).
    

## 3. Problemy w kodzie

Kod zawiera błąd: `value_1` jest jednocześnie zwykłym atrybutem w `__init__` oraz metodą z dekoratorem `@BitFieldDescriptor`. To prowadzi do konfliktu – Python nie pozwala na nadpisanie metody jako atrybutu.

**Poprawiona wersja kodu:**

```python
class Magic:
    value_1 = BitFieldDescriptor()
    
    def __init__(self):
        self.value_2 = 2137
```

Teraz `value_1` działa poprawnie jako descriptor.

## 4. Zalety descriptorów

- **Kontrola dostępu do atrybutów** – umożliwia walidację i modyfikację wartości przed ich zapisaniem.
    
- **Hermetyzacja danych** – dane mogą być przechowywane oddzielnie od `__dict__` instancji.
    
- **Optymalizacja pamięci** – `WeakKeyDictionary` zapobiega wyciekom pamięci poprzez automatyczne usuwanie danych dla nieistniejących instancji.
    

## 5. Podsumowanie

Descriptory w Pythonie to potężne narzędzie umożliwiające pełną kontrolę nad atrybutami klasy. W poprawnej wersji kodu `BitFieldDescriptor` działa jako pełnoprawny descriptor, który zarządza dostępem do wartości atrybutów bez konfliktów w `__init__`.--- 
Metadata: 

Status: #pending 
Tags: #python 