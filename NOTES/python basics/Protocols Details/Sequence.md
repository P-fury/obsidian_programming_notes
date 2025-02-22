Created: 2025-02-22 18:29

--- 
**Note:**

Protokół _Sequence_ -> obsługuje uporządkowaną kolekcję elementów.

Wymaga implementacji metod:

• ___getitem___ -> dostęp do elementów przez indeks lub slicing

• ___len___ -> zwraca długość sekwencji

```python 
class CustomSequence:

    def __init__(self, items):

        self.items = items

  

    def __getitem__(self, index):

        return self.items[index]

  

    def __len__(self):

        return len(self.items)

  

seq = CustomSequence([10, 20, 30, 40, 50])

print(seq[2])    # 30

print(len(seq))  # 5
```
--- 
Metadata: 

Status: #pending 
Tags: #empty