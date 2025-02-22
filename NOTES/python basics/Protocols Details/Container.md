Created: 2025-02-22 17:53

--- 
Note: 
Metoda specjalna ___contains___ -> sprawdza obecność elementu w kolekcji przy użyciu operatora in.

Zwraca wartość boolowską (True/False).

```python
class CustomContainer:
    def __init__(self, items):
        self.items = items

    def __contains__(self, item) -> bool:
        return item in self.items

c = CustomContainer([1, 2, 3])
print(2 in c)  # True
```

--- 
Metadata: 

Status: #pending 
Tags: #empty