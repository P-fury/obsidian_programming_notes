Created: 2025-02-10 17:56

--- 
Note: 

📌 Podstawowe komendy uv

uv to nowoczesny, ultralekki i szybki menedżer pakietów dla Pythona, który jest alternatywą dla pip i virtualenv. Jest rozwijany przez twórców pipenv i pdm i wyróżnia się wysoką wydajnością dzięki implementacji w Rust.

Kluczowe cechy uv:

✅ Szybkość – działa znacznie szybciej niż pip, zwłaszcza przy instalacji wielu pakietów.
✅ Efektywność – lepiej zarządza zależnościami, minimalizując konflikty.
✅ Samodzielność – działa niezależnie od Pythona, nie wymaga środowisk wirtualnych.
✅ Kompatybilność – może współpracować z pip, requirements.txt i pyproject.toml.


🔹 Zarządzanie środowiskiem Python
```shell
# Tworzenie nowego środowiska
uv venv .venv
# Aktywowanie środowiska
source .venv/bin/activate   # Linux/macOS
# Dezaktywacja środowiska
deactivate
```

🔹 Zarządzanie pakietami
```shell
# Instalacja pakietu
uv pip install nazwa_pakietu
# Instalacja pakietu w konkretnej wersji
uv pip install nazwa_pakietu==1.2.3
# Instalacja pakietów z pliku requirements.txt
uv pip install -r requirements.txt
```
### 🔹 **Praca z** `**pyproject.toml**` **i środowiskiem w** `**uv**`

```shell
# Inicjalizacja nowego projektu
uv init
# Instalacja zależności z `pyproject.toml`
uv sync
# Dodanie nowego pakietu do `pyproject.toml`
uv add nazwa_pakietu
# To wyświetli szczegóły pakietu, w tym jego wersję.
uv pip show nazwa_pakietu
# Usunięcie pakietu z `pyproject.toml`
uv remove nazwa_pakietu
```

### 🔹 Tymczasowe środowisko UV

```shell
# uruchamia tymczasowe srodowisko z wybrana paczka
uv run --with nazwa_paczki nazwa_pliku_py
```

## Przy większej ilości zależności:

```python
# w pytonie wprowadzamy liste

# /// script
# python = ">=3.10,<3.12"
# dependencies = [
#   "requests<3",
#   "numpy>=1.21,<1.25",
#   "pandas"
# ]
# ///
```


--- 
Metadata: 

Status: #pending 
Tags: #pip #virtualenv #python_projects #uv