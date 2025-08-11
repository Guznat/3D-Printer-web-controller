# 3D-Printer-web-controller

🧩 WordPress ↔️ 3D Printer API Integration

Projekt open-source umożliwiający komunikację między drukarką 3D a wtyczką WordPressa przy wykorzystaniu REST API. Celem jest zdalne zarządzanie drukiem 3D bezpośrednio z panelu WordPress.

---

## 📦 Funkcjonalności

- 🔌 Integracja wtyczki WordPress z drukarką 3D
- 📤 Wysyłanie plików G-code do drukarki przez API
- 🖨️ Uruchamianie/zatrzymywanie/zapauzowanie druku
- 📡 Odbieranie statusu i postępu wydruku
- 🛠️ Podstawowe komendy sterujące (temperatura, kalibracja, restart)

---

## 🔧 Wymagania

### Po stronie drukarki 3D:
- Serwer OctoPrint lub inny serwer API wspierający druk 3D
- Dostęp do API (token/klucz autoryzacyjny)

### Po stronie WordPress:
- WordPress 5.8+
- PHP 7.4+
- Wtyczka (zawarta w tym repozytorium)

## ⚙️ Instalacja

1. **WordPress Plugin:**
   - Skopiuj zawartość folderu `plugin/` do katalogu `/wp-content/plugins/wp-3dprinter/`
   - W panelu WordPress przejdź do "Wtyczki" i aktywuj **3D Printer Connector**

2. **Konfiguracja:**
   - W ustawieniach wtyczki wpisz URL serwera drukarki oraz klucz API
   - Zapisz zmiany

---

## 📡 Przykładowe użycie

### Wysłanie pliku do druku:
```php
PrinterAPI::sendFile($filePath);
````

### Rozpoczęcie druku:

```php
PrinterAPI::startPrint($fileId);
```

### Sprawdzenie statusu:

```php
PrinterAPI::getStatus();
```

---

## 🛡️ Bezpieczeństwo

* Autoryzacja za pomocą klucza API
* Walidacja danych wejściowych
* Obsługa błędów i ograniczenie uprawnień do admina

