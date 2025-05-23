---
"date": "2025-04-22"
"description": "Dowiedz się, jak tworzyć i dostosowywać wykresy kołowe w programie PowerPoint za pomocą Aspose.Slides dla języka Python. Ulepsz swoje prezentacje dzięki wnioskom opartym na danych."
"title": "Twórz angażujące wykresy kołowe w programie PowerPoint za pomocą Aspose.Slides dla języka Python | Samouczek dotyczący wykresów i grafów"
"url": "/pl/python-net/charts-graphs/aspose-slides-python-powerpoint-pie-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów kołowych programu PowerPoint za pomocą Aspose.Slides dla języka Python

**Kategoria:** Wykresy i grafy

Tworzenie angażujących i informacyjnych prezentacji jest kluczem do skutecznego przekazywania spostrzeżeń opartych na danych. Jeśli chcesz ulepszyć swoje slajdy programu PowerPoint, włączając wizualnie atrakcyjne wykresy kołowe, **Aspose.Slides dla Pythona** library to doskonałe narzędzie, które upraszcza ten proces. W tym samouczku przeprowadzimy Cię przez tworzenie wykresu kołowego w programie PowerPoint przy użyciu Aspose.Slides dla Pythona.

## Czego się nauczysz:
- Zainstaluj i skonfiguruj Aspose.Slides dla języka Python
- Utwórz podstawowy wykres kołowy na slajdach programu PowerPoint
- Dostosuj swój wykres kołowy za pomocą punktów danych, kolorów, obramowań, etykiet, linii odniesienia i obrotu
- Optymalizacja wydajności podczas pracy z wykresami

Przyjrzyjmy się bliżej krokom niezbędnym do rozpoczęcia pracy.

## Wymagania wstępne

Przed wdrożeniem kodu upewnij się, że masz następujące elementy:
- Python zainstalowany w Twoim systemie (zalecana jest wersja 3.6 lub nowsza)
- `pip` menedżer pakietów do instalowania bibliotek
- Podstawowa znajomość programowania w Pythonie i prezentacji PowerPoint

## Konfigurowanie Aspose.Slides dla Pythona

Aby rozpocząć pracę z Aspose.Slides dla języka Python, należy zainstalować bibliotekę za pomocą pip:

```bash
pip install aspose.slides
```

**Nabycie licencji:**
Możesz zacząć od pobrania bezpłatnej licencji próbnej ze strony [Strona pobierania Aspose](https://releases.aspose.com/slides/python-net/). W celu szerszego wykorzystania należy rozważyć zakup pełnej licencji lub uzyskanie licencji tymczasowej w celach ewaluacyjnych.

### Podstawowa inicjalizacja i konfiguracja

Po zainstalowaniu Aspose.Slides zaimportuj niezbędne moduły do skryptu Pythona:

```python
import aspose.slides as slides
import aspose.pydrawing as drawing
```

## Przewodnik wdrażania

W tej sekcji przedstawimy szczegółowo poszczególne kroki tworzenia wykresu kołowego.

### Tworzenie i dostosowywanie wykresu kołowego

#### Przegląd
Utworzenie wykresu kołowego polega na zainicjowaniu obiektu prezentacji, dodaniu slajdu, a następnie wstawieniu wykresu z niestandardowymi punktami danych i elementami wizualnymi.

#### Kroki tworzenia wykresu kołowego

1. **Utwórz klasę prezentacji**
   Zacznij od utworzenia instancji prezentacji. Będzie ona służyć jako kontener dla Twoich slajdów i wykresów.

   ```python
   with slides.Presentation() as presentation:
       # Dostęp do pierwszego slajdu
       slide = presentation.slides[0]
   ```

2. **Dodaj wykres kołowy do slajdu**
   Użyj `add_chart` metoda wstawiania wykresu kołowego w określonych współrzędnych na slajdzie.

   ```python
   chart = slide.shapes.add_chart(slides.charts.ChartType.PIE, 100, 100, 400, 400)
   ```

3. **Ustaw tytuł wykresu**
   Dostosuj swój wykres, nadając mu odpowiedni tytuł i sformatuj go tak, aby wyśrodkować tekst.

   ```python
   chart.chart_title.add_text_frame_for_overriding("Sample Title")
   chart.chart_title.text_frame_for_overriding.text_frame_format.center_text = slides.NullableBool.TRUE
   chart.chart_title.height = 20
   chart.has_title = True
   ```

4. **Dostęp do skoroszytu danych wykresu**
   Użyj `chart_data_workbook` aby zarządzać kategoriami i seriami danych oraz je dostosowywać.

   ```python
   fact = chart.chart_data.chart_data_workbook
   default_worksheet_index = 0

   # Wyczyść wszystkie istniejące serie lub kategorie
   chart.chart_data.series.clear()
   chart.chart_data.categories.clear()

   # Dodaj nowe kategorie (kwartały)
   chart.chart_data.categories.add(fact.get_cell(0, 1, 0, "First Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 2, 0, "2nd Qtr"))
   chart.chart_data.categories.add(fact.get_cell(0, 3, 0, "3rd Qtr"))

   # Dodaj nową serię
   series = chart.chart_data.series.add(fact.get_cell(0, 0, 1, "Series 1"), chart.type)
   ```

5. **Wypełnij serię punktami danych**
   Wstaw punkty danych do serii, aby przedstawić różne części tortu.

   ```python
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 1, 1, 20))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 2, 1, 50))
   series.data_points.add_data_point_for_pie_series(fact.get_cell(default_worksheet_index, 3, 1, 30))
   ```

6. **Zastosuj różne kolory do wykresu**
   Dostosuj każdy kawałek ciasta, używając różnych kolorów.

   ```python
   chart.chart_data.series_groups[0].is_color_varied = True

   # Zdefiniuj funkcję do dostosowywania wyglądu punktu
   def customize_point(point, fill_color, line_color):
       point.format.fill.fill_type = slides.FillType.SOLID
       point.format.fill.solid_fill_color.color = drawing.Color(fill_color)
       
       point.format.line.fill_format.fill_type = slides.FillType.SOLID
       point.format.line.fill_format.solid_fill_color.color = drawing.Color(line_color)
       point.format.line.width = 3.0
       point.format.line.style = slides.LineStyle.THIN_THICK
       point.format.line.dash_style = slides.LineDashStyle.DASH_DOT
   
   # Dostosuj wygląd pierwszego punktu danych
   customize_point(series.data_points[0], "Cyan", "Gray")
   ```

7. **Dostosuj etykiety dla punktów danych**
   Dostosuj ustawienia etykiet, aby wyświetlać wartości, procenty lub nazwy serii.

   ```python
   def customize_label(point, show_value=True, show_legend_key=False,
                       show_percentage=False, show_series_name=False):
       lbl = point.label
       lbl.data_label_format.show_value = show_value
       lbl.data_label_format.show_legend_key = show_legend_key
       lbl.data_label_format.show_percentage = show_percentage
       lbl.data_label_format.show_series_name = show_series_name
   
   # Ustaw właściwości etykiety dla pierwszego punktu danych
   customize_label(series.data_points[0], True)
   ```

8. **Włącz linie odniesienia i obracaj wycinki koła**
   Aby zwiększyć czytelność, włącz linie pomocnicze i obracaj wycinki w razie potrzeby.

   ```python
   series.labels.default_data_label_format.show_leader_lines = True

   # Obróć pierwszy kawałek ciasta o 180 stopni
   chart.chart_data.series_groups[0].first_slice_angle = 180
   ```

9. **Zapisz prezentację**
   Na koniec zapisz prezentację ze wszystkimi zastosowanymi dostosowaniami.

   ```python
   presentation.save("YOUR_OUTPUT_DIRECTORY/charts_pie_chart_out.pptx", slides.export.SaveFormat.PPTX)
   ```

### Porady dotyczące rozwiązywania problemów
- Upewnij się, że Aspose.Slides został prawidłowo zainstalowany i zaimportowany.
- Sprawdź, czy w nazwach metod i parametrach nie występują literówki, gdyż może to prowadzić do błędów.
- Sprawdź, czy istnieje ścieżka do katalogu, w którym zapisujesz plik wyjściowy.

## Zastosowania praktyczne

Wykresy kołowe są uniwersalne i przydatne w wielu dziedzinach:
1. **Analityka biznesowa**:Wizualizacja podziału przychodów pomiędzy różnymi produktami lub usługami.
2. **Raporty marketingowe**:Pokaż udziały rynkowe konkurentów w danej branży.
3. **Prezentacje edukacyjne**: Przedstaw dane statystyczne dotyczące wyników uczniów lub danych demograficznych.

## Rozważania dotyczące wydajności
- Zminimalizuj wykorzystanie zasobów poprzez optymalizację elementów wykresu i redukcję zbędnej złożoności.
- Przy obsłudze dużych zbiorów danych na potrzeby wykresów należy stosować wydajne struktury danych.
- Zarządzaj pamięcią efektywnie, zwalniając zasoby natychmiast po ich wykorzystaniu.

## Wniosek

Postępując zgodnie z tym przewodnikiem, nauczyłeś się, jak utworzyć wykres kołowy w programie PowerPoint przy użyciu Aspose.Slides dla języka Python. Teraz możesz zastosować te techniki w swoich prezentacjach i odkryć dalsze opcje dostosowywania. Rozważ zintegrowanie innych typów wykresów lub wykorzystanie dodatkowych funkcji Aspose.Slides, aby udoskonalić swoje umiejętności wizualizacji danych.

### Następne kroki
- Eksperymentuj z różnymi dostosowaniami wykresów
- Poznaj integrację wykresów w dynamicznych raportach
- Zapoznaj się szczegółowo z dokumentacją Aspose.Slides, aby poznać bardziej zaawansowane funkcje

## Sekcja FAQ

1. **Czym jest Aspose.Slides?**
   - Potężna biblioteka umożliwiająca programowe tworzenie i modyfikowanie prezentacji PowerPoint.
2. **Czy mogę używać Aspose.Slides za darmo?**
   - Tak, możesz zacząć od licencji próbnej lub ocenić jej możliwości przed zakupem.
3. **Jakie inne typy wykresów mogę utworzyć?**
   - Oprócz wykresów kołowych można tworzyć także wykresy słupkowe, liniowe, punktowe i inne za pomocą Aspose.Slides.

## Rekomendacje słów kluczowych
- „Aspose.Slides dla Pythona”
- „Wykres kołowy programu PowerPoint”
- „Wykresy PowerPoint w języku Python”

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}