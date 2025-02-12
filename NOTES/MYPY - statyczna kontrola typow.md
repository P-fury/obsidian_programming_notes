Created: 2025-02-11 20:31

--- 
Note: 

MyPy to narzędzie do **statycznej analizy typów**, które pozwala wykrywać błędy związane z niezgodnością typów już na etapie pisania kodu, zanim program zostanie uruchomiony.

  

**Główne cechy MyPy:**

✅ **Weryfikacja typów w Pythonie** – sprawdza zgodność z adnotacjami typu

✅ **Pomaga unikać błędów runtime** – wykrywa potencjalne problemy wcześniej

✅ **Kompatybilność z dynamicznym Pythonem** – działa na opcjonalnych adnotacjach

✅ **Obsługuje popularne frameworki** – dobrze współpracuje z FastAPI, Django, itp.

**📌 Użycie**

```python
# Sprawdzenie typu w pliku script.py
mypy script.py
# Ignorowanie plików w sprawdzaniu (np. biblioteki zewnętrzne)
mypy --ignore-missing-imports script.py
# Sprawdzenie całego projektu
mypy .
```

--- 
Metadata: 

Status: #pending 
Tags: #python #python_projects #commands 