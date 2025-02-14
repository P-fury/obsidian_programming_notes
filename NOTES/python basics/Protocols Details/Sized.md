Created: 2025-02-11 21:27

--- 
Note: 
Zwraca liczbę elementów *len(sized)*
Nie może zużywać ani modyfikować kolekcji.

```python
class X:
	def __len__(self) -> int:
	return 42

x = X()
len(x) #42
```
--- 
Metadata: 

Status: #pending 
Tags: #empty