Created: 2025-02-26 13:15

--- 
Note: 
📝 Name Mangling w Pythonie

Name mangling (zaciemnianie nazw) to mechanizm w Pythonie, który zmienia nazwy atrybutów zaczynających się od podwójnego podkreślnika (__) w celu uniknięcia konfliktów nazw w klasach dziedziczących.

🏷 1. Jak działa name mangling?

Jeśli atrybut klasy zaczyna się od __ (np. __private_var), Python automatycznie przekształca jego nazwę, dodając do niej _ClassName, np.:
```python
class Example:
    def __init__(self):
        self.__secret = "Ukryte"

obj = Example()
print(dir(obj))  # ['_Example__secret']
```


📌 Nazwa __secret została zamieniona na _Example__secret, co chroni ją przed przypadkowym nadpisaniem w podklasach.

🏷 2. Dlaczego Python stosuje name mangling?
	•	Unikanie kolizji nazw w dziedziczeniu klas.
	•	Ukrycie atrybutu, ale nie jako “prawdziwa” prywatność (w Pythonie nie ma private, jak w Javie/C++).
	•	Zachowanie czytelności kodu, unikając przypadkowych konfliktów.

🔥 3. Przykład działania w dziedziczeniu

```python
class Base:
    def __init__(self):
        self.__value = 42

class Derived(Base):
    def __init__(self):
        super().__init__()
        self.__value = 99  # Tworzy _Derived__value, a nie nadpisuje _Base__value

obj = Derived()
print(dir(obj))  # ['_Base__value', '_Derived__value']
```

📌 Base.__value stało się _Base__value, a Derived.__value to _Derived__value, więc wartości się nie nadpisują.

🏷 4. Jak uzyskać dostęp do zmienionych nazw?

Mimo że Python stosuje name mangling, nadal można uzyskać dostęp do takich zmiennych:

```python
obj = Example()
print(obj._Example__secret)  # Ukryte
```

📌 To nie jest pełna prywatność, a jedynie konwencja ukrywania nazw.

❌ 5. Czego nie robi name mangling?
	•	Nie działa dla pojedynczego podkreślnika _var (to tylko konwencja “prywatności”).
	•	Nie ukrywa atrybutów przed użytkownikiem – można je nadal odczytać.
	•	Nie zabezpiecza kodu przed świadomym dostępem do atrybutów.

✅ 6. Kiedy stosować name mangling?
	•	Gdy tworzysz bazową klasę, którą ktoś może rozszerzać, i chcesz uniknąć kolizji nazw.
	•	Gdy chcesz ukryć atrybuty i zasygnalizować, że nie powinny być bezpośrednio używane.
	•	Gdy pracujesz z frameworkami i bibliotekami, gdzie może dojść do nadpisania nazw.

🚀 Podsumowanie
	•	Name mangling automatycznie zamienia __var na _ClassName__var.
	•	Chroni przed przypadkowym nadpisaniem atrybutów w podklasach.
	•	Nie jest to prawdziwa prywatność – można uzyskać dostęp do zmienionych nazw.
	•	Najlepiej stosować do wewnętrznych mechanizmów klas bazowych.

Chcesz przykład wykorzystania name mangling w praktycznym kodzie? 🚀 
Metadata: 

Status: #pending 
Tags: #python #namemangling