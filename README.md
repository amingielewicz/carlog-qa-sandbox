# CarLog - QA Sandbox & Test Automation

Domowy dziennik serwisowy i kosztów auta, w którym użytkownicy mogą prowadzić prywatny rejestr wydatków: tankowania, serwis, polisy i inne opłaty. Pod maską serwis jest bezwzględnym poligonem testerskim najeżonym wyzwaniami pod automatyzację (Wait Traps, Shadow DOM, asynchroniczność, znikające toasty i błędy danych).

## Funkcjonalności biznesowe
- Moduł tankowań:
  - rejestracja litrów
  - rejestracja kwot
  - przebiegi
  - automatyczne wyliczanie spalania (l/100 km)
  - koszt 1 km
- Książka serwisowa:
  - rejestr wymian (olej, filtry, klocki hamulcowe itp.)
  - historia napraw
- Terminarz opłat:
  - pilnowanie terminów ważności polisy OC/AC oraz badania technicznego

## Architektura poligonu QA (Feature Toggles)
Aplikacja wykorzystuje flagi konfiguracyjne (Feature Toggles), które na produkcji są wyłączone, a w trybie testowym aktywują celowe utrudnienia:
- znikające powiadomienia (toasty po 3 sek.)
- 4-sekundowy loader raportu (Wait Traps)
- zaokrąglenia ułamków i testowanie wartości brzegowych
- izolowany komponent w Shadow DOM
- niestandardowe listy wyboru

## Stack technologiczny
### Frontend
- HTML5
- CSS3
- Vanilla JavaScript

### Backend & Baza danych
- Node.js (Express)
- PostgreSQL (REST API)

### Testy API
- Postman / Bruno
- SoapUI
- Java + REST Assured

### Testy E2E
- UI: Java + Selenium WebDriver + TestNG
- JavaScript / TypeScript + Playwright

### CI/CD
- GitHub Actions