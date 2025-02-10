1️⃣ Logowanie jako narzędzie monitorowania aplikacji
	•	Pozwala śledzić zdarzenia w kodzie bez konieczności używania print().
	•	Ułatwia diagnozowanie błędów i analizę działania programu.

2️⃣ Poziomy logowania
	•	DEBUG – szczegółowe informacje dla deweloperów.
	•	INFO – ogólne informacje o działaniu programu.
	•	WARNING – ostrzeżenia o potencjalnych problemach.
	•	ERROR – błędy, które nie przerywają działania programu.
	•	CRITICAL – poważne błędy, które mogą zakończyć działanie aplikacji.

3️⃣ Konfiguracja logowania (basicConfig)
	•	level=logging.DEBUG określa minimalny poziom logów do wyświetlenia.
	•	format pozwala dostosować wygląd logów (np. dodanie czasu, nazwy modułu).

4️⃣ Logowanie do różnych miejsc (Handlers)
	•	StreamHandler – logi wyświetlane w konsoli.
	•	FileHandler – zapisywanie logów do pliku.
	•	RotatingFileHandler – logi zapisywane do pliku z limitem rozmiaru.

5️⃣ Konfiguracja za pomocą plików (logging.toml)
	•	Logowanie można skonfigurować za pomocą plików .toml, .ini, .yaml.
	•	dictConfig(config) pozwala ładować ustawienia logowania z pliku.

🚀 Wnioski:
✔ Logowanie jest kluczowe w diagnostyce i debugowaniu aplikacji.
✔ Poziomy logowania pozwalają na filtrowanie istotnych komunikatów.
✔ Można logować do wielu źródeł, np. plików, konsoli, zewnętrznych systemów.