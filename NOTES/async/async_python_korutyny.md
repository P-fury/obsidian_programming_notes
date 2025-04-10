Created: 2025-04-10 20:40

---
Note:

Asyncio to biblioteka wbudowana w Pythona, która pozwala na wykonywanie wielu zadań współbieżnie — idealna do operacji I/O, jak pobieranie danych, czekanie na odpowiedź z serwera, czy praca z plikami.

---

## ✨ Co to jest async/await?

✅ `async def` tworzy funkcję asynchroniczną (korutynę)  
✅ `await` zatrzymuje działanie funkcji do momentu zakończenia operacji  
✅ `asyncio.run()` uruchamia główną korutynę

```python
import asyncio

async def say_hello():
    print("Cześć")
    await asyncio.sleep(1)
    print("Minęła sekunda!")

asyncio.run(say_hello())
```

---

## 🔧 Jak pisać funkcje współbieżne (korutyny)?

Funkcja współbieżna:
- jest oznaczona jako `async def`
- może wykorzystywać `await` do wstrzymywania działania i oddania kontroli innym zadaniom

```python
async def countdown(n):
    while n > 0:
        print(f"Odliczanie: {n}")
        await asyncio.sleep(1)
        n -= 1
```

---

## 🌀 Tworzenie i uruchamianie wielu zadań

Użyj `asyncio.create_task()` do uruchomienia wielu zadań jednocześnie.  
Zadania są wykonywane współbieżnie — program nie czeka na zakończenie jednego, by rozpocząć kolejne.

```python
async def task(name, seconds):
    print(f"{name} startuje")
    await asyncio.sleep(seconds)
    print(f"{name} kończy się")

async def main():
    t1 = asyncio.create_task(task("A", 2))
    t2 = asyncio.create_task(task("B", 1))
    await t1
    await t2

asyncio.run(main())
```

---

## 🔄 asyncio.gather()

`asyncio.gather()` uruchamia wiele korutyn jednocześnie i czeka, aż wszystkie się zakończą. Jest to wygodny sposób na równoległe operacje.

```python
async def main():
    await asyncio.gather(
        task("Zadanie 1", 1),
        task("Zadanie 2", 2),
        task("Zadanie 3", 3)
    )
```

---

## 🔁 asyncio.Queue – współdzielenie danych

`asyncio.Queue` pozwala tworzyć system producent–konsument, gdzie jedno zadanie dodaje dane, a inne je odbiera.

```python
queue = asyncio.Queue()

await queue.put("wiadomość")
msg = await queue.get()
print("Odebrano:", msg)
```

---

## 🛠️ Debugowanie async

✅ Dodawaj `print()` z nazwą funkcji i `await`  
✅ Używaj `asyncio.current_task()` do śledzenia aktualnego zadania  
✅ Unikaj funkcji blokujących jak `time.sleep()`

---

## 🧭 Dobre praktyki

- Używaj `asyncio.run()` tylko raz – jako "entrypoint"
- Nie mieszaj kodu async z funkcjami blokującymi
- Testuj async kod przy pomocy `pytest-asyncio`

---

Metadata:

Status: #ready  
Tags: #python #async #asyncio #beginner #programming #konkurencja
