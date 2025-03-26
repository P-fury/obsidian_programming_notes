Created: 2025-03-26 10:44

--- 
Note: 
# 🌀 Event Loop w Pythonie

  

Event Loop to centralny mechanizm asynchronicznego przetwarzania zadań w Pythonie (moduł `asyncio`).

  

## 🔧 Jak działa?

  

- **Rejestruje** zadania (np. funkcje `async def`, coroutine, future, task).

- **Czeka** na ich zakończenie bez blokowania innych zadań.

- **Zarządza** cyklicznym sprawdzaniem stanu zadań i ich wykonywaniem, gdy są gotowe.

  

## 📌 Przykład użycia:

  

```python

import asyncio

  

async def say_hello():

    print("Hello")

    await asyncio.sleep(1)

    print("World")

  

asyncio.run(say_hello())
```

--- 
Metadata: 

Status: #pending 
Tags: #empty