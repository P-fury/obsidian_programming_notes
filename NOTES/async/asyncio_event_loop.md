Created: 2025-04-10 20:45

---
Note:

Pętla zdarzeń (event loop) to centralny mechanizm w asyncio, który zarządza i uruchamia wszystkie asynchroniczne zadania w aplikacji. Właśnie dzięki niej kod współbieżny może być wykonywany efektywnie i nienblokująco.

---

## 🔄 Jak działa pętla zdarzeń?

✅ Pętla zdarzeń monitoruje wszystkie korutyny i zadania.  
✅ Rejestruje operacje I/O i wznowi je, gdy będą gotowe.  
✅ Zapewnia współbieżność bez używania wątków.

---

## ▶️ Tworzenie i uruchamianie pętli

Najczęściej używa się wysokopoziomowego API:

```python
async def main():
    ...

asyncio.run(main())  # automatycznie tworzy i uruchamia pętlę
```

Ale można to zrobić też ręcznie (niższy poziom kontroli):

```python
loop = asyncio.get_event_loop()
loop.run_until_complete(main())
loop.close()
```

---

## ➕ Dodawanie zadań do pętli

Można dodać zadania w trakcie działania programu:

```python
task = loop.create_task(korutyna())
loop.run_until_complete(task)
```

lub z poziomu korutyny:

```python
async def example():
    task = asyncio.create_task(inna_korutyna())
    await task
```

---

## ⏹️ Zamykanie pętli

Automatycznie przy `asyncio.run()`.  
Jeśli tworzysz pętlę ręcznie, **zamknij ją** po zakończeniu:

```python
loop.close()
```

---

## ⚠️ Uwaga na wyjątki

- `RuntimeError: This event loop is already running` → nie próbuj uruchamiać pętli wewnątrz innej działającej pętli (np. w Jupyter Notebook).
- `loop.run_forever()` – jeśli używasz serwera socketowego lub chcesz utrzymać aplikację cały czas aktywną.

---

## 📌 Przydatne metody pętli zdarzeń

| Metoda                    | Opis |
|--------------------------|------|
| `run_until_complete()`   | Uruchamia korutynę i czeka na zakończenie |
| `create_task()`          | Tworzy nowe zadanie |
| `run_forever()`          | Uruchamia pętlę nieskończenie długo |
| `stop()`                 | Zatrzymuje pętlę (wewnętrznie) |
| `close()`                | Zamyka pętlę – ważne przy ręcznym użyciu |

---

Metadata:

Status: #ready  
Tags: #python #asyncio #event_loop #beginner #programming
