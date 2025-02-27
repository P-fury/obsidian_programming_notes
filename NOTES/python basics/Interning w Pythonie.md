Created: 2025-02-27 12:29

--- 
Note:

**📝 Interning w Pythonie**

**Interning** to technika optymalizacji pamięci w Pythonie, polegająca na **ponownym użyciu tych samych obiektów** zamiast tworzenia nowych. Jest szczególnie stosowana dla **łańcuchów znaków (stringów)** oraz **liczb całkowitych (integers)**.

**🏷 1. Jak działa interning?**

Python automatycznie stosuje interning dla:

✅ **Małych liczb całkowitych (-5 do 256)** → są współdzielone w pamięci.

✅ **Niektórych krótkich stringów** → zwłaszcza tych składających się tylko z liter i cyfr.

✅ **Identycznych, niemutowalnych obiektów** → mogą być używane wielokrotnie zamiast tworzenia nowych.

  
**Przykład:**

```
a = 100
b = 100
print(a is b)  # True, bo Python używa tej samej referencji w pamięci

x = "hello"
y = "hello"
print(x is y)  # True, bo krótkie stringi są internowane
```

📌 **Ale dłuższe stringi mogą nie być internowane automatycznie:**

```
s1 = "very_long_string_example"
s2 = "very_long_string_example"
print(s1 is s2)  # Może być False, bo Python nie musi ich internować
```

**🔥 2. Interning ręczny – sys.intern()**

  

Jeśli chcesz wymusić interning stringów, użyj **sys.intern()**:

```
import sys

s1 = sys.intern("very_long_string_example")
s2 = sys.intern("very_long_string_example")

print(s1 is s2)  # True, bo wymusiliśmy współdzielenie
```

✅ **Kiedy używać sys.intern()?**

• Gdy masz **dużo powtarzających się stringów** (np. parsowanie plików XML, JSON).

• Gdy chcesz **oszczędzać pamięć** i **przyspieszyć porównania** stringów.

**🏷 3. Interning vs Memoization**

  

**Interning** przechowuje **identyczne obiekty**, które są **niemutowalne**.

**Memoization** zapamiętuje **wyniki funkcji**, by uniknąć ponownych obliczeń.

  

📌 **Interning:**

```
a = "python"
b = "python"
print(a is b)  # True (jeśli string jest internowany)
```

📌 **Memoization (np. w cache funkcji):**

```
from functools import lru_cache

@lru_cache(maxsize=None)
def fib(n):
    if n < 2:
        return n
    return fib(n - 1) + fib(n - 2)

print(fib(10))  # Zapamiętuje wyniki dla przyszłych wywołań
```

**🚀 Podsumowanie**

  

✅ **Interning oszczędza pamięć** poprzez ponowne użycie tych samych obiektów.

✅ **Działa automatycznie** dla małych liczb i prostych stringów.

✅ **sys.intern()** pozwala wymusić interning dla dłuższych stringów.

✅ **Nie działa dla mutowalnych obiektów (np. list, słowników).**

--- 
Metadata: 

Status: #pending 
Tags: #python