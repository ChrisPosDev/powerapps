---
layout: default
title: "TEST: Pełny przegląd możliwości motywu Hacker"
date: 2023-10-30
---

To jest post testowy, który sprawdza wszystkie style motywu Hacker.

---

## 3. Listy i Zadania

Struktura to podstawa. Testujemy listy zagnieżdżone i checklisty.

### Lista numerowana (Kroki procesu)
1. Utwórz nową aplikację typu Canvas.
2. Podłącz źródło danych (np. SharePoint).
    1. Wybierz witrynę.
    2. Wybierz listę.
3. Dodaj galerię i formularz.

### Lista nienumerowana (Cechy)
* Szybkie tworzenie interfejsu.
* Integracja z Power Automate.
    * Wyzwalacze.
    * Akcje.
* Wsparcie dla mobile.

### Checklista (Task List)
- [x] Przygotowanie środowiska deweloperskiego.
- [x] Stworzenie modelu danych.
- [ ] Testy UAT (To zadanie jest jeszcze do wykonania).
- [ ] Wdrożenie na produkcję.

---

## 4. Tabele Danych

Tabela porównująca funkcje delegowalne i niedelegowalne w SharePoint. Sprawdź czytelność na ciemnym tle.

| Funkcja Power Fx | Delegowalna (SP) | Typ zwracany | Uwagi |
| :--- | :---: | :--- | :--- |
| **Filter** | TAK | Tabela | Podstawowa funkcja filtracji. |
| **Search** | CZĘŚCIOWO | Tabela | Działa tylko na polach tekstowych. |
| **LookUp** | TAK | Rekord | Zwraca pierwszy wynik. |
| **AddColumns** | NIE | Tabela | Przetwarzana lokalnie. |
| **CountRows** | NIE | Liczba | Limit 500/2000 wierszy. |

---

## 5. Multimedia

Testowanie obrazów i osadzania wideo (HTML).

### Obraz statyczny
Poniżej powinien wyświetlić się schemat (z zewnętrznego źródła):

![Diagram Power Platform](https://learn.microsoft.com/en-us/power-platform/admin/media/security-roles.png)
*Podpis: Przykładowy diagram ról bezpieczeństwa (źródło: Microsoft Learn)*

### Obraz z linkiem (Kliknij w logo)
[![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png)](https://github.com)

### Wideo (YouTube Embed)
Motyw Hacker pozwala na wstrzykiwanie czystego HTML. Poniżej przykładowe wideo instruktażowe:

<div style="text-align: center; margin: 20px 0;">
<iframe width="100%" height="350" src="https://www.youtube.com/embed/l59s4C1iQO0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
