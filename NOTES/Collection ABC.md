Created: 2025-02-11 20:01

--- 
Note: 

[ABC and Abstract methods](https://docs.python.org/3/library/collections.abc.html#collections-abstract-base-classes)

W Pythonie wirtualne dziedziczenie pozwala klasom rejestrować się jako implementacje interfejsów (ABC – Abstract Base Class) bez konieczności rzeczywistego dziedziczenia.

Dzięki temu klasa może być traktowana jako podklasa danej abstrakcyjnej klasy bazowej, ale nie musi bezpośrednio po niej dziedziczyć.

📌 **Ważne**: Wirtualne dziedziczenie **nie wymusza implementacji metod** – tylko deklaruje, że klasa powinna spełniać interfejs.# Kolekcje abstrakcyjne w `collections.abc`

```python
from collections.abc import Sequence

class MyList:
    def __getitem__(self, index): ...
    def __len__(self): ...
    
Sequence.register(MyList)  # Rejestracja jako "wirtualna" podklasa
print(issubclass(MyList, Sequence))  # ✅ True, mimo że MyList nie dziedziczy po Sequence
print(isinstance(MyList(), Sequence))  # ✅ True
```

## 📌 Kolekcje sekwencyjne:
- **`Iterable`** – `__iter__()`
- **`Iterator`** – `__iter__()`, `__next__()`
- **`Reversible`** – `__reversed__()`
- **`Sized`** – `__len__()`
- **`Container`** – `__contains__(item)`
- **`Collection`** – `__len__()`, `__iter__()`, `__contains__(item)`
- **`Sequence`** – `__getitem__(index)`, `__len__()`, `__contains__(item)`

## 📌 Kolekcje mutowalne:
- **`MutableSequence`** – `__setitem__(index, value)`, `__delitem__(index)`, `__iadd__(iterable)`

## 📌 Zbiory:
- **`Set`** – `__contains__(item)`, `__iter__()`, `__len__()`
- **`MutableSet`** – `__contains__(item)`, `__iter__()`, `__len__()`

## 📌 Mapowania (słowniki):
- **`Mapping`** – `__getitem__(key)`, `__iter__()`, `__len__()`, `__contains__(key)`
- **`MutableMapping`** – `__setitem__(key, value)`, `__delitem__(key)`

## 📌 Kolejki i stosy:
- **`MappingView`** – `__len__()`, `__iter__()`, `__contains__(item)`
- **`ItemsView`** – brak dodatkowych metod
- **`KeysView`** – brak dodatkowych metod
- **`ValuesView`** – brak dodatkowych metod

--- 
Metadata: 

Status: #pending 
Tags: #empty