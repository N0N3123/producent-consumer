# producent-consumer
# Projekt: System Producent-Konsument z Programowaniem Równoległym

## Opis

Zaawansowany system producent-konsument implementujący programowanie równoległe w Pythonie z wykorzystaniem `multiprocessing`.

### Działanie programu
1. **Producenci** (3 procesy) - Generują losowe liczby (1-100) i wstawiają je do wspólnej kolejki
2. **Kolejka** - Bezpiecznie przechowuje elementy między procesami (max 5 elementów)
3. **Konsumenci** (2 procesy) - Pobierają elementy z kolejki i je przetwarzają
4. **Lock** - Chroni liczniki aby tylko jeden proces na raz je aktualizował
5. **Monitor** - Co sekundę zbiera statystyki (ile wyprodukowano, ile skonsumowano, lag)
6. **Logger** - Loguje każde zdarzenie z czasem do konsoli i pliku
## Architektura

📁 Producent-konsument/
├── config.py           # Konfiguracja centralna
├── logger.py           # Zaawansowany system loggowania
├── producer.py         # Klasa Producenta
├── consumer.py         # Klasa Konsumenta
├── monitor.py          # Monitor wydajności
├── main.py             # Orkestracja systemu
└── README.md           # Dokumentacja


## Mechanizmy programowania równoległego

| Mechanizm                 | Zastosowanie                                 |
| ------------------------- | -------------------------------------------- |
| `Process`                 | Każdy producent/konsument w osobnym procesie |
| `Queue` / `PriorityQueue` | Bezpieczna komunikacja między procesami      |
| `Value`                   | Liczniki współdzielone między procesami      |
| `Lock`                    | Synchronizacja dostępu do liczników          |
| `Manager`                 | Współdzielone słowniki i listy               |

### Uruchomienie

python main.py

### Konfiguracja

Edytuj `config.py`, aby zmienić:

- Liczbę producentów/konsumentów
- Wielkość kolejki
- Timeouty i interwały
- Prioritety

### Statystyki
stats.json - Eksportowane statystyki w formacie JSON
**Autor:** [Twoje imię]  
**Data:** 2026-01-15  
**Język:** Python 3.7+
