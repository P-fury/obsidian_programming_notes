Created: 2025-02-18 12:02

--- 
Note: 
Wzorzec projektowy: Template Method z metaklasą
## 📌 Opis

**Template Method** to wzorzec projektowy, który definiuje szkielet algorytmu w metodzie bazowej, pozostawiając implementację niektórych kroków w klasach pochodnych. W połączeniu z **metaklasą** można narzucić strukturę tworzenia obiektów na poziomie klasy, zapewniając konsekwentną organizację kodu.

## 🔹 Struktura

1. **Metaklasa** zarządza kolejnością wywołań metod inicjalizacyjnych (`_pre_init()`, `__init__()`, `_post_init()`).
    
2. **Klasa bazowa** zawiera szablon metody (`template_method()`), który definiuje etapy procesu.
    
3. **Klasy pochodne** implementują konkretne etapy bez zmiany struktury ogólnej.
    

## 🏗 Przykład kodu

```
class TemplateMeta(type):
    def __call__(cls, *args, **kwargs):
        obj = cls.__new__(cls, *args, **kwargs)
        obj._pre_init(*args, **kwargs)
        obj.__init__(*args, **kwargs)
        obj._post_init(*args, **kwargs)
        return obj

class TemplateBase(metaclass=TemplateMeta):
    def _pre_init(self):
        print("Pre-initialization step")

    def __init__(self):
        print("Main initialization")

    def _post_init(self):
        print("Post-initialization step")

class ConcreteClass(TemplateBase):
    def __init__(self):
        super().__init__()
        print("Concrete class specific init")

# Tworzenie obiektu
obj = ConcreteClass()
```

## 🔥 Zalety stosowania

- **Sztywna struktura procesu tworzenia obiektów** – metaklasa wymusza określone kroki.
    
- **Elastyczność w implementacji** – klasy pochodne mogą nadpisywać konkretne etapy.
    
- **Redukcja duplikacji kodu** – jednolity mechanizm inicjalizacji.
    

## 🚀 Zastosowanie

- Frameworki, w których wymagane są ustandaryzowane metody inicjalizacji.
    
- Systemy, w których proces tworzenia obiektów powinien być kontrolowany centralnie.
    
- Budowanie API, które wymusza określoną kolejność operacji dla klas pochodnych.
    

**Template Method** w połączeniu z metaklasą to potężne narzędzie do zarządzania strukturą kodu, umożliwiające zarówno kontrolę, jak i rozszerzalność w projektach opartych na dziedziczeniu. 🚀
--- 
Metadata: 

Status: #pending 
Tags: #python