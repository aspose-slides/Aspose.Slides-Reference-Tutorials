---
"date": "2025-04-22"
"description": "Dowiedz się, jak bez wysiłku wyświetlać etykiety procentowe na wykresach w prezentacjach PowerPoint za pomocą Aspose.Slides dla Pythona. Idealne do ulepszania wizualizacji danych."
"title": "Jak wyświetlać etykiety procentowe na wykresach za pomocą Aspose.Slides dla Pythona? Kompleksowy przewodnik"
"url": "/pl/python-net/charts-graphs/display-percentage-labels-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak wyświetlać etykiety procentowe na wykresach za pomocą Aspose.Slides dla Pythona

## Wstęp

Skuteczna wizualizacja danych jest kluczowa w prezentacjach i raportach, zwłaszcza gdy chcesz wyraźnie podkreślić proporcje lub rozkłady. Ale co, jeśli potrzebujesz, aby te procenty były wyświetlane bezpośrednio na wykresach? Ten kompleksowy przewodnik przeprowadzi Cię przez korzystanie z **Aspose.Slides dla Pythona** aby bez problemu wyświetlać wartości procentowe w postaci etykiet na wykresie.

### Czego się nauczysz:
- Jak tworzyć i osadzać wykresy w prezentacjach PowerPoint za pomocą Aspose.Slides dla języka Python.
- Wyświetlanie punktów danych jako etykiet procentowych na wykresach.
- Efektywne zapisywanie i zarządzanie prezentacjami PowerPoint.

Gotowy, aby zacząć dodawać wnikliwe wizualizacje do swoich danych? Najpierw przyjrzyjmy się temu, czego potrzebujesz, zanim zagłębimy się w kod!

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- **Aspose.Slides dla Pythona**:Ta biblioteka jest niezbędna do tworzenia i modyfikowania prezentacji PowerPoint za pomocą programowania.
- **Środowisko Pythona**:Podstawowa znajomość programowania w języku Python i konfiguracji środowiska.
- **Menedżer pakietów PIP**: Służy do instalowania Aspose.Slides.

## Konfigurowanie Aspose.Slides dla Pythona

Aby zacząć korzystać z Aspose.Slides, musisz go najpierw zainstalować:

```bash
pip install aspose.slides
```

### Etapy uzyskania licencji:
Możesz zacząć od bezpłatnej wersji próbnej lub uzyskać tymczasową licencję, aby odkryć pełne możliwości Aspose.Slides. W celu dłuższego użytkowania rozważ zakup subskrypcji.

#### Podstawowa inicjalizacja i konfiguracja

Po zainstalowaniu zainicjuj środowisko prezentacji w następujący sposób:

```python
import aspose.slides as slides

# Zainicjuj obiekt prezentacji
def create_presentation():
    with slides.Presentation() as presentation:
        # Twój kod tutaj
```

## Przewodnik wdrażania

Teraz, gdy już wszystko skonfigurowaliśmy, możemy zająć się wyświetlaniem procentów na wykresach.

### Tworzenie wykresu i dodawanie danych

#### Przegląd
Utworzymy wykres kolumnowy z etykietami procentowymi dla każdego punktu danych, dzięki czemu czytelnicy będą mogli na pierwszy rzut oka zobaczyć dokładne proporcje.

##### Krok 1: Dodaj wykres do slajdu

```python
# Uzyskaj dostęp do pierwszego slajdu w swojej prezentacji
def add_chart_to_slide(presentation):
    slide = presentation.slides[0]

    # Dodaj wykres kolumnowy skumulowany
    chart = slide.shapes.add_chart(slides.charts.ChartType.STACKED_COLUMN, 20, 20, 400, 400)
```

Ten fragment kodu dodaje podstawowy wykres do pierwszego slajdu. `add_chart` Metoda ta określa typ wykresu, jego pozycję i rozmiar.

##### Krok 2: Oblicz wartości całkowite dla kategorii

```python
def calculate_totals(chart):
    total_for_category = []
    # Podsumuj wartości we wszystkich seriach dla każdej kategorii
    for k in range(len(chart.chart_data.categories)):
        value = sum(
            chart.chart_data.series[i].data_points[k].value.data 
            for i in range(len(chart.chart_data.series))
        )
        total_for_category.append(value)
```

Pętla ta oblicza sumę wszystkich punktów danych w seriach, co jest kluczowe dla obliczeń procentowych.

#### Ustawianie etykiet procentowych

##### Krok 3: Skonfiguruj punkty danych serii

```python
def set_percentage_labels(chart, totals):
    for series in chart.chart_data.series:
        # Ustaw domyślne opcje etykiet, aby ukryć nieistotne informacje
        series.labels.default_data_label_format.show_legend_key = False
        
        # Oblicz i ustaw etykiety procentowe
        for j in range(len(series.data_points)):
            lbl = series.data_points[j].label
            data_point_percent = (series.data_points[j].value.data / totals[j]) * 100.0
            
            # Utwórz część tekstową z wartością procentową
            port = slides.Portion()
            port.text = "{0:4.2f} %".format(data_point_percent)
            port.portion_format.font_height = 8

            # Wyczyść istniejące etykiety i dodaj nową etykietę procentową
            lbl.text_frame_for_overriding.text = ""
            para = lbl.text_frame_for_overriding.paragraphs[0]
            para.portions.add(port)

            # Ukryj inne elementy etykiety danych
            lbl.data_label_format.show_series_name = False
            lbl.data_label_format.show_percentage = False
            lbl.data_label_format.show_legend_key = False
            lbl.data_label_format.show_category_name = False
            lbl.data_label_format.show_bubble_size = False
```

Ten segment przetwarza każdy punkt danych, aby obliczyć jego procentowy udział w całości i przypisuje go jako etykietę.

### Zapisywanie prezentacji

```python
def save_presentation(presentation, output_directory):
    # Zapisz swoją prezentację ze zmianami
    presentation.save(f"{output_directory}/charts_display_percentage_as_labels_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}