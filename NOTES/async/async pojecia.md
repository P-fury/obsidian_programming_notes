Created: 2025-03-28 10:44

--- 
Note:

## 1. Co to jest korutyna (`coroutine`)?

Korutyna to funkcja asynchroniczna tworzona za pomocą `async def`. Umożliwia wstrzymywanie i wznawianie wykonywania kodu w sposób nieblokujący w ramach pętli zdarzeń (`event loop`).

```python
async def example():
    await asyncio.sleep(1)
    print("Done")
```

- Uruchamiana przez `await` lub przez `asyncio.run()`.
- Może czekać na inne korutyny, zadania (`Task`) i obiekty typu `Future`.

## 2. Co to jest `Future`?

`Future` to obiekt reprezentujący **rezultat operacji, która jeszcze się nie zakończyła**.

- Jest awaitable.
- Może zostać uzupełniony (`set_result()`) lub anulowany (`cancel()`).
- Jest niskopoziomowym mechanizmem budowania asynchronicznych operacji.

```python
future = asyncio.Future()
future.set_result(42)
print(future.result())  # 42
```

## 3. Co to jest `Task`?

`Task` to specjalizacja `Future` — automatycznie zarządza wykonaniem korutyny w tle.

- Tworzy się go przez `asyncio.create_task()` lub `asyncio.ensure_future()`.
- Task pozwala korutynie wystartować w tle i zwrócić `Future`, który można `awaitować`.

```python
async def work():
    await asyncio.sleep(1)
    return "done"

task = asyncio.create_task(work())
result = await task
```

## 4. Co to jest `awaitable`?

Obiekt `awaitable` to każdy obiekt, który można użyć w `await`. Może to być:

- **Korutyna** (`async def`)
- **Task** (`asyncio.Task`)
- **Future** (`asyncio.Future`)

Jeśli coś można `awaitować`, oznacza to, że w pewnym momencie zwróci wynik bez blokowania wątku.

## 5. Co to jest `event loop` (pętla zdarzeń)?

- Zarządza wszystkimi korutynami, taskami i future'ami.
- Przechwytuje i planuje wykonanie kodu asynchronicznego.
- Jest sercem modułu `asyncio`.

```python
loop = asyncio.get_event_loop()
loop.run_until_complete(example())
```

## 6. Kolejki asynchroniczne (`asyncio.Queue`)

- Działa jak klasyczna kolejka FIFO, ale bez blokowania wątku.
- `put()` i `get()` są **awaitable**.
- Używana do komunikacji między korutynami.

```python
queue = asyncio.Queue()

await queue.put(1)
item = await queue.get()
```

## 7. Asynchroniczny generator (nie będący korutyną)

Asynchroniczny generator to funkcja `async def` z `yield` + `await`, ale to **nie jest korutyna**, tylko **asynchroniczny iterator**.

```python
async def async_gen():
    for i in range(3):
        await asyncio.sleep(1)
        yield i

async for item in async_gen():
    print(item)
```

- Musi być iterowany za pomocą `async for`.
- Używany do tworzenia asynchronicznych strumieni danych.

## 8. Asynchroniczny context manager

Pozwala używać `async with` dla obiektów, które wymagają asynchronicznej inicjalizacji lub czyszczenia (np. otwieranie plików, sesje HTTP).

```python
class AsyncContext:
    async def __aenter__(self):
        print("Enter")
        return self

    async def __aexit__(self, exc_type, exc, tb):
        print("Exit")

async def main():
    async with AsyncContext():
        print("Inside")

asyncio.run(main())
```

## 9. Podsumowanie

| Pojęcie | Opis |
|---------|------|
| Coroutine | Asynchroniczna funkcja (`async def`) |
| Future | Obiekt-wynik operacji asynchronicznej |
| Task | Uruchomiona korutyna w tle, będąca Future |
| Awaitable | Obiekt, na który można `await` |
| Event Loop | Mechanizm zarządzania asynchronicznym kodem |
| Async Queue | Asynchroniczna kolejka do komunikacji |
| Async Generator | Generator zwracający wartości w `async for` |
| Async Context Manager | `async with` do zarządzania zasobami |

---

Metadata:

Status: #pending  
Tags: #python #async #coroutine #future #task #eventloop #queue #async_generator #async_context
