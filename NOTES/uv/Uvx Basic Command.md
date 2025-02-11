Created: 2025-02-10 18:54

--- 
Note: 
## **✅ Główne założenia** `**uvx**`

- **Automatyczna obsługa zależności** – `uvx` pobiera brakujące pakiety na bieżąco.
    
- **Bez instalowania w systemie** – działa w izolacji, nie wpływa na globalne środowisko Pythona.
    
- **Idealne do jednorazowych uruchomień** – użyteczne do testowania narzędzi lub skryptów.

```python
# uruchamia pytest o zadanej wersji
uvx pytest==7.4.0
# wymusza uzycie konkretnej wersji Python
uvx --python=3.11 python script.py
```

--- 
Metadata: 

Status: #pending 
Tags: #uvx #python #virtualenv #scripts