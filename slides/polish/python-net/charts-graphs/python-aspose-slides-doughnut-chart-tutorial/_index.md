---
"date": "2025-04-22"
"description": "Dowiedz się, jak tworzyć wykresy pierścieniowe za pomocą Pythona i Aspose.Slides. Ten przewodnik krok po kroku obejmuje konfigurację, dostosowywanie i najlepsze praktyki ulepszania prezentacji."
"title": "Jak tworzyć wykresy pierścieniowe w Pythonie za pomocą Aspose.Slides? Przewodnik krok po kroku"
"url": "/pl/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy pierścieniowe w Pythonie za pomocą Aspose.Slides: przewodnik krok po kroku

dziedzinie wizualizacji danych skuteczne prezentowanie informacji może znacząco wpłynąć na zrozumienie i podejmowanie decyzji. Niezależnie od tego, czy tworzysz prezentację biznesową, czy analizujesz złożone zestawy danych, wykresy są niezbędnymi narzędziami. Spośród różnych typów wykresów wykresy pierścieniowe zapewniają atrakcyjny sposób przedstawiania proporcjonalnych danych z intuicyjnym otworem środkowym. Ten przewodnik krok po kroku przeprowadzi Cię przez proces tworzenia wykresu pierścieniowego w Pythonie przy użyciu Aspose.Slides — potężnej biblioteki do manipulowania prezentacjami.

## Czego się nauczysz
- Jak skonfigurować i używać Aspose.Slides dla języka Python
- Proces dodawania wykresu pierścieniowego do slajdów prezentacji
- Dostosowywanie serii i kategorii w wykresie
- Dostosowywanie elementów wizualnych, takich jak etykiety, kolory i efekty eksplozji
- Najlepsze praktyki optymalizacji wydajności z Aspose.Slides

## Wymagania wstępne
Przed rozpoczęciem upewnij się, że masz:
- **Środowisko Pythona**:Na Twoim komputerze zainstalowano Python 3.x.
- **Aspose.Slides dla Pythona**: Zainstaluj tę bibliotekę za pomocą pip.
- **Podstawowa wiedza na temat programowania w Pythonie**:Przydatna będzie znajomość pętli i programowania obiektowego.

## Konfigurowanie Aspose.Slides dla Pythona
Aby rozpocząć, zainstaluj bibliotekę Aspose.Slides za pomocą pip:

```bash
pip install aspose.slides
```

### Nabycie licencji
Aspose oferuje bezpłatną wersję próbną do testowania funkcji bez ograniczeń przez ograniczony czas. Aby ją uzyskać:
1. Odwiedź [Bezpłatna wersja próbna](https://releases.aspose.com/slides/python-net/) strona.
2. Postępuj zgodnie z instrukcjami, aby pobrać i zastosować tymczasową licencję.

Aby kontynuować korzystanie z usługi, rozważ zakup subskrypcji od [Strona zakupu](https://purchase.aspose.com/buy).

### Podstawowa inicjalizacja
Po skonfigurowaniu Aspose.Slides zainicjuj go w następujący sposób:

```python
import aspose.slides as slides

# Utwórz instancję klasy Presentation.
with slides.Presentation() as pres:
    # Tutaj wpisz swój kod umożliwiający manipulowanie prezentacjami.

# Po wprowadzeniu zmian zapisz prezentację.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Przewodnik wdrażania
Po skonfigurowaniu Aspose.Slides wykonaj poniższe kroki, aby dodać wykres kołowy do prezentacji slajd po slajdzie.

### Tworzenie nowej prezentacji i dodawanie slajdu
Zacznij od utworzenia instancji `Presentation` klasa:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Uzyskaj dostęp do slajdów lub utwórz je w tym kontekście.
```

### Dodawanie wykresu pierścieniowego do pierwszego slajdu
Przejdź do pierwszego slajdu i użyj `add_chart` metoda. Określ typ wykresu jako `DOUGHNUT`, wraz z pozycją i rozmiarem:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Konfigurowanie danych wykresu
Wyczyść istniejące dane i skonfiguruj ustawienia, takie jak ukrywanie legendy:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Dodawanie serii i kategorii
Dodaj wiele serii i kategorii dla wykresu pierścieniowego. Oto jak utworzyć 15 serii o określonych właściwościach:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Dodaj kategorie w podobny sposób:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Dodaj punkty danych dla każdej serii.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Dostosuj wygląd każdego punktu danych.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Skonfiguruj ustawienia etykiet dla ostatniej serii.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Zapisywanie prezentacji
Na koniec zapisz prezentację w określonym katalogu:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Zastosowania praktyczne
Wykresy pierścieniowe są uniwersalne i można je stosować w różnych sytuacjach, takich jak:
1. **Alokacja budżetu**:Pokazywanie, w jaki sposób różne działy wykorzystują przydzielone im fundusze.
2. **Analiza udziałów rynkowych**:Porównanie udziałów rynkowych konkurencyjnych produktów lub firm.
3. **Wyniki ankiety**:Wizualizacja odpowiedzi na pytania ankietowe dotyczące preferencji i poziomów satysfakcji.

## Rozważania dotyczące wydajności
Aby zapewnić optymalną wydajność podczas korzystania z Aspose.Slides:
- Zminimalizuj użycie pamięci poprzez prawidłową utylizację obiektów po użyciu.
- Ładuj prezentacje do pamięci tylko wtedy, gdy jest to konieczne, i zamykaj je tak szybko, jak to możliwe.
- Jeśli pracujesz z dużą liczbą wykresów, rozważ zastosowanie przetwarzania wsadowego slajdów.

## Wniosek
Dzięki temu przewodnikowi nauczyłeś się, jak tworzyć dynamiczne wykresy pierścieniowe za pomocą Aspose.Slides dla Pythona. Te wizualizacje mogą ulepszyć Twoje prezentacje, czyniąc dane bardziej przyswajalnymi i angażującymi. Kontynuuj eksplorację funkcji biblioteki, aby dalej dostosowywać i optymalizować swoje wykresy.

## Sekcja FAQ
1. **Czy mogę używać Aspose.Slides bez zakupu licencji?**
   - Tak, możesz zacząć od bezpłatnej licencji próbnej w celach ewaluacyjnych.
2. **Jak zmienić kolory wykresu w Aspose.Slides?**
   - Użyj `fill_format` Właściwość umożliwiająca ustawienie pożądanego koloru dla elementów wykresu.
3. **Czy można eksportować wykresy jako obrazy?**
   - Tak, możesz renderować slajdy zawierające wykresy do formatów graficznych, korzystając z funkcji renderowania dostępnych w bibliotece.
4. **Jakie są najczęstsze problemy występujące przy dodawaniu wykresów?**
   - Przed próbą zapisania lub wyświetlenia wykresu upewnij się, że wszystkie punkty danych i kategorie zostały poprawnie dodane.
5. **Czy mogę zintegrować Aspose.Slides z innymi bibliotekami Pythona?**
   - Oczywiście! Możesz używać go razem z bibliotekami takimi jak Pandas, aby zwiększyć możliwości manipulacji danymi.

## Zasoby
- [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/python-net/)
- [Pobierz Aspose.Slides](https://releases.aspose.com/slides/python-net/)
- [Kup licencję](https://purchase.aspose.com/buy)
- [Bezpłatna wersja próbna i licencja tymczasowa](https://releases.aspose.com/slides/python-net/)
- [Forum społeczności Aspose](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}