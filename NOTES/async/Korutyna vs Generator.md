Created: 2025-03-26 10:53

--- 
## 1. `send()` w generatorze

Generatory mogą **otrzymywać dane z zewnątrz** za pomocą metody `send()`. Działa to tylko, jeśli generator zawiera `yield`, który odbierze wartość.

```python
def echo():
    received = yield "Start"
    while True:
        received = yield f"Got: {received}"

g = echo()
print(next(g))         # "Start"
print(g.send("hello")) # "Got: hello"
print(g.send("world")) # "Got: world"
```

## 2. `send()` w klasycznych korutynach (PEP 342)

Korutyny oparte na generatorach (`def` + `yield`) również używają `send()` do komunikacji dwustronnej – to stary styl korutyn **przed `async def`**.

```python
def classic_coroutine():
    total = 0
    while True:
        x = yield total
        if x is None:
            break
        total += x

c = classic_coroutine()
print(next(c))     # 0
print(c.send(5))   # 5
print(c.send(10))  # 15
c.close()
```

## 3. `async def` korutyny NIE używają `send()`

Nowoczesne korutyny (z `async def`) **nie używają `send()`**. Do przekazywania danych służy `await` + odpowiednie obiekty (`Future`, `Task`, itp.).

```python
import asyncio

async def example():
    await asyncio.sleep(1)
    return "Done"

# Brak send(), używamy asyncio.run lub await
asyncio.run(example())
```

## 4. Porównanie: Generator vs Coroutine (z `send()`)

| Cecha               | Generator (`yield`)     | Classic Coroutine (`yield`)     | Async Coroutine (`async def`) |
|--------------------|--------------------------|----------------------------------|-------------------------------|
| `send()` działa?   | ✅ tak                   | ✅ tak                           | ❌ nie                        |
| Obsługa danych      | jednostronna lub dwustronna | dwustronna                   | przez `await`                |
| Styl               | synchroniczny            | synchroniczny                   | asynchroniczny               |

## 5. Podsumowanie

- `send()` jest dostępne tylko w generatorach i klasycznych korutynach.
- `async def` nie obsługuje `send()` – nowoczesne korutyny korzystają z `await` i `asyncio`.
- Współczesne aplikacje używają `async`/`await`, ale warto znać `send()` dla zrozumienia niskopoziomowego działania generatorów.

--- 
Metadata: 

Status: #pending 
Tags: #python #generator #coroutine #send #async #await