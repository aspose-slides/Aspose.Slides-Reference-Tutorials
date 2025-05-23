---
"date": "2025-04-22"
"description": "Dowiedz się, jak tworzyć i dostosowywać wykresy kołowe w prezentacjach PowerPoint za pomocą Aspose.Slides dla języka Python, rozwijając w ten sposób swoje umiejętności wizualizacji danych."
"title": "Jak utworzyć wykres kołowy w programie PowerPoint za pomocą Aspose.Slides dla języka Python"
"url": "/pl/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres kołowy w programie PowerPoint za pomocą Aspose.Slides dla języka Python

Tworzenie atrakcyjnych wizualnie wykresów, takich jak wykres kołowy, może znacznie ulepszyć prezentacje PowerPoint, czyniąc złożone informacje bardziej przyswajalnymi. Ten samouczek przeprowadzi Cię przez proces tworzenia wykresu kołowego przy użyciu Aspose.Slides dla Pythona.

## Czego się nauczysz

- Konfigurowanie Aspose.Slides dla Pythona
- Kroki tworzenia prezentacji programu PowerPoint z wykresem kołowym
- Konfigurowanie etykiet danych i opcji grup serii w celu zapewnienia lepszej czytelności
- Praktyczne zastosowania wykresu kołowego w prezentacjach

Przyjrzyjmy się bliżej konfigurowaniu środowiska i implementacji tych funkcji.

### Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- **Python zainstalowany**:Zalecany jest Python w wersji 3.6 lub nowszej.
- **Aspose.Slides dla Pythona**: Zainstaluj za pomocą pip:
  ```bash
  pip install aspose.slides
  ```
- **Licencja**:Uzyskaj bezpłatną licencję próbną od Aspose i poznaj wszystkie funkcje bez ograniczeń.

#### Wymagania wstępne dotyczące wiedzy

Podstawowa znajomość programowania Pythona i zrozumienie prezentacji PowerPoint będzie korzystne. Jeśli jesteś nowy w tych tematach, rozważ najpierw zapoznanie się z materiałami wprowadzającymi.

### Konfigurowanie Aspose.Slides dla Pythona

Aby rozpocząć korzystanie z Aspose.Slides dla języka Python, wykonaj następujące proste kroki:

1. **Instalacja**: Użyj pip, aby zainstalować bibliotekę:
   ```bash
   pip install aspose.slides
   ```

2. **Nabycie licencji**: 
   - Odwiedzać [Strona zakupów Aspose](https://purchase.aspose.com/buy) aby zakupić licencję lub uzyskać tymczasową bezpłatną wersję próbną.
   - Zastosuj licencję w swoim projekcie, korzystając z poniższego fragmentu kodu:
     ```python
     import aspose.slides as slides

     # Załaduj plik licencji
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Podstawowa inicjalizacja**:
   Zacznij od zaimportowania Aspose.Slides i zainicjowania obiektu prezentacji.

### Przewodnik wdrażania

#### Funkcja 1: Tworzenie prezentacji z wykresem

W tym artykule pokażemy, jak utworzyć prezentację programu PowerPoint i dodać wykres kołowy do pierwszego slajdu.

##### Dodawanie wykresu

Zacznij od utworzenia nowej prezentacji i dodania wykresu kołowego w pozycji (50, 50) na pierwszym slajdzie:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Dodaj wykres kołowy „Kołowy” o określonych wymiarach
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Konfigurowanie etykiet danych

Aby zwiększyć czytelność, skonfiguruj etykiety danych tak, aby wyświetlały wartości:

```python
# Włącz wyświetlanie wartości na etykietach danych, aby zapewnić większą przejrzystość
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Ustawianie opcji wykresu kołowego

Skonfiguruj określone właściwości wykresu kołowego, takie jak rozmiar drugiego koła i pozycję podziału:

```python
# Ustaw drugi rozmiar wykresu kołowego i właściwości podziału
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Zapisywanie prezentacji

Na koniec zapisz prezentację w wybranym katalogu:

```python
# Zapisz prezentację z wykresem
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Zastosowania praktyczne

Wykres kołowy jest uniwersalny i można go stosować w różnych scenariuszach:

1. **Raporty biznesowe**:Wizualizacja dystrybucji danych w różnych działach lub produktach.
2. **Projekty akademickie**:Przedstaw wyniki ankiety, pokazujące główne wątki obok mniej istotnych ustaleń.
3. **Analiza finansowa**:Porównaj wydatki podstawowe z kosztami wtórnymi w raporcie budżetowym.

### Rozważania dotyczące wydajności

Aby uzyskać optymalną wydajność podczas korzystania z Aspose.Slides:

- Jeśli to możliwe, zminimalizuj liczbę slajdów i wykresów, aby zmniejszyć zużycie pamięci.
- Regularnie usuwaj nieużywane zasoby i odwołania w kodzie.
- Użyj wbudowanego w Pythonie mechanizmu zbierania śmieci (`gc` moduł) umożliwiający efektywne zarządzanie pamięcią.

### Wniosek

Nauczyłeś się, jak tworzyć prezentację PowerPoint z wykresem kołowym za pomocą Aspose.Slides dla Pythona. Ta umiejętność może znacznie zwiększyć atrakcyjność wizualną i skuteczność prezentacji. Rozważ zapoznanie się z większą liczbą funkcji w Aspose.Slides, takich jak dodawanie animacji lub integrowanie elementów multimedialnych.

### Następne kroki

- Eksperymentuj z różnymi typami wykresów dostępnymi w Aspose.Slides.
- Zintegruj tę funkcję z większym procesem automatyzacji prezentacji.

### Sekcja FAQ

**P: Czy mogę dostosować kolory wykresu kołowego?**
A: Tak, możesz dostosować kolory wykresu za pomocą `fill_format` Nieruchomość dla każdego segmentu.

**P: Jak obsługiwać duże zbiory danych za pomocą Aspose.Slides?**
A: Zoptymalizuj wprowadzane dane i rozważ podzielenie ich na mniejsze fragmenty, aby utrzymać wydajność.

**P: Czy istnieje sposób na zautomatyzowanie dodawania wielu wykresów na raz?**
A: Tak, przejrzyj swoje zestawy danych i użyj `add_chart` metodę w ramach jednego kontekstu prezentacji.

### Zasoby

- **Dokumentacja**:Przeglądaj szczegółowe przewodniki na [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/python-net/).
- **Pobierać**:Pobierz najnowszą wersję z [Wydania](https://releases.aspose.com/slides/python-net/).
- **Zakup i bezpłatna wersja próbna**:Dostęp do opcji licencji na [Zakup Aspose](https://purchase.aspose.com/buy) lub spróbuj [Bezpłatna wersja próbna](https://releases.aspose.com/slides/python-net/).
- **Wsparcie**:Dołącz do dyskusji na temat [Forum Aspose](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}