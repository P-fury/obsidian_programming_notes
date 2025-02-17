Created: 2025-02-17 19:45

--- 
Note: 
# Tworzenie obiektu w Pythonie – Metody `__prepare__`, `__new__`, `__init__` 🚀

## 1. `__prepare__(mcs, name, bases, **kwargs)` 🛠️

- Metoda klasy w metaklasie (`type`).
    
- Tworzy przestrzeń nazw dla nowej klasy **przed** jej definicją.
    
- Może zwrócić niestandardowy słownik do kontrolowania kolejności atrybutów.
    
- Wywoływana **zanim** Python przetworzy definicję klasy.
    

## 2. `__new__(mcs, name, bases, namespace, **kwargs)` 🏗️

- Metoda instancji metaklasy, wywoływana **przed** utworzeniem nowej klasy.
    
- Odpowiada za **alokację pamięci** dla nowego obiektu klasy.
    
- Może modyfikować przestrzeń nazw klasy przed jej utworzeniem.
    

## 3. `__init__(cls, name, bases, namespace, **kwargs)` 🔧

- Wywoływana **po utworzeniu** klasy.
    
- Pozwala na finalne dostosowanie obiektu klasy, np. dodanie atrybutów.
    
- Operuje na już utworzonej klasie, w przeciwieństwie do `__new__`.
    

Te metody pozwalają na zaawansowaną kontrolę nad procesem tworzenia obiektów w Pythonie, co jest szczególnie przydatne w dynamicznym programowaniu i metaprogramowaniu. 💡

Metadata: 

Status: #pending 
Tags: #python #python_projects 