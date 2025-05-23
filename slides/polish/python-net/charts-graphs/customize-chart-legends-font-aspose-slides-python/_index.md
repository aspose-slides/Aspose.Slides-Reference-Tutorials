---
"date": "2025-04-22"
"description": "Dowiedz się, jak dostosować właściwości czcionki legend wykresów za pomocą Aspose.Slides dla Pythona. Ulepsz swoje prezentacje za pomocą pogrubionych, kursywnych i kolorowych czcionek dla poszczególnych wpisów legendy."
"title": "Dostosuj czcionkę legend wykresów za pomocą Aspose.Slides dla języka Python – kompleksowy przewodnik"
"url": "/pl/python-net/charts-graphs/customize-chart-legends-font-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dostosowywanie czcionki legend wykresów w prezentacjach przy użyciu Aspose.Slides dla języka Python

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji jest niezbędne, szczególnie podczas wyświetlania danych za pomocą wykresów. Częstym wyzwaniem jest dostosowywanie legend wykresów do stylu prezentacji lub potrzeb marki. Ten przewodnik pokazuje, jak dostosować właściwości czcionki, takie jak pogrubienie, kursywa, rozmiar i kolor dla poszczególnych wpisów legendy na wykresie za pomocą Aspose.Slides dla Pythona.

**Czego się nauczysz:**
- Konfigurowanie i używanie Aspose.Slides dla Pythona
- Dostosowywanie właściwości czcionek legend wykresów
- Stosowanie określonych stylów czcionek, takich jak pogrubienie, kursywa i zmiana kolorów
- Praktyczne przykłady ulepszania wykresów za pomocą niestandardowych czcionek

Przyjrzyjmy się bliżej, w jaki sposób można osiągnąć takie dostosowanie.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- **Biblioteki**: Aspose.Slides dla Pythona. Zainstaluj za pomocą pip.
- **Środowisko**: Środowisko Pythona (najlepiej Python 3.x) skonfigurowane na Twoim komputerze.
- **Wiedza**:Podstawowa znajomość programowania w języku Python i znajomość obsługi prezentacji programowo.

## Konfigurowanie Aspose.Slides dla Pythona
### Instalacja
Aby rozpocząć, zainstaluj bibliotekę Aspose.Slides, uruchamiając następujące polecenie w terminalu:

```bash
pip install aspose.slides
```

### Nabycie licencji
Aspose.Slides jest produktem komercyjnym z różnymi opcjami licencjonowania:
- **Bezpłatna wersja próbna**:Uzyskaj tymczasową licencję zapewniającą pełną funkcjonalność.
- **Licencja tymczasowa**:Złóż wniosek o tymczasową licencję, aby przetestować wszystkie funkcje bez ograniczeń.
- **Zakup**:Kup subskrypcję lub licencję wieczystą, zależnie od swoich potrzeb.

### Podstawowa inicjalizacja
Oto jak możesz zainicjować i skonfigurować Aspose.Slides w skrypcie Pythona:

```python
import aspose.slides as slides

# Zainicjuj instancję prezentacji\za pomocą slides.Presentation() jako pres:
    # Twój kod tutaj
```

## Przewodnik wdrażania
W tej sekcji pokażemy Ci, jak dostosować właściwości czcionki poszczególnych wpisów legendy.

### Dodawanie i uzyskiwanie dostępu do wykresu
Najpierw dodajmy do slajdu wykres kolumnowy:

```python
# Dodaj wykres kolumnowy klastrowany na pozycji (50, 50) o szerokości 600 i wysokości 400
class ShapeCollection:
    def __init__(self):
        self.chart = None

    def add_chart(self, chart_type, x, y, width, height):
        # Jest to tylko symbol zastępczy dla właściwej metody Aspose.Slides.
        return "ChartObject"

class SlideCollection:
    def __init__(self):
        self.shapes = ShapeCollection()

# Symulowanie pres.slides[0].shapes
slide_shapes = SlideCollection()
chart = slide_shapes.shapes.add_chart(slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 600, 400)
```

### Dostosowywanie właściwości czcionki legendy
#### Uzyskiwanie dostępu do formatu tekstowego wpisu legendy
Aby zmodyfikować właściwości czcionki określonego wpisu legendy:

```python
class Chart:
    def __init__(self):
        self.legend = "LegendObject"

# Symulacja chart.legend.entries[1].text_format
chart_object = Chart()
tf = "SimulatedTextFormatObject"
```

#### Ustawianie właściwości czcionki
Tutaj dostosowujemy takie aspekty jak pogrubienie, rozmiar, kursywę i kolor:

```python
class TextFormat:
    def __init__(self):
        self.portion_format = PortionFormat()

class PortionFormat:
    def __init__(self):
        self.font_bold = False
        self.font_height = 0
        self.font_italic = False
        self.fill_format = FillFormat()

class FillFormat:
    def __init__(self):
        self.fill_type = "None"
        self.solid_fill_color = SolidFillColor()

class SolidFillColor:
    def __init__(self):
        self.color = None

class Color:
    blue = 'blue'

tf.portion_format.font_bold = True
# Ustaw rozmiar czcionki na 20 punktów
tf.portion_format.font_height = 20  
tf.portion_format.font_italic = True

# Ustaw kolor czcionki na niebieski, używając wypełnienia pełnego
tf.portion_format.fill_format.fill_type = "SOLID"
tf.portion_format.fill_format.solid_fill_color.color = Color.blue
```

### Zapisywanie prezentacji
Na koniec zapisz prezentację z następującymi dostosowaniami:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_font_properties_for_individual_legend_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}