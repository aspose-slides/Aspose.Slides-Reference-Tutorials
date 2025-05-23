---
"date": "2025-04-23"
"description": "Dowiedz się, jak dostosować kąt obrotu tytułów wykresów w prezentacjach za pomocą Aspose.Slides dla języka Python, zwiększając czytelność i estetykę."
"title": "Jak ustawić obrót tytułu osi pionowej wykresu w Aspose.Slides dla języka Python"
"url": "/pl/python-net/charts-graphs/aspose-slides-python-chart-vertical-axis-title-rotation/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić obrót tytułu osi pionowej wykresu w Aspose.Slides dla języka Python

## Wstęp

W prezentacjach danych poprawa czytelności wykresu jest kluczowa. Dostosowanie kąta obrotu tytułu osi pionowej wykresu za pomocą Aspose.Slides for Python może sprawić, że tytuły będą pasować lub wyróżniać się na slajdach. Ten samouczek przeprowadzi Cię przez ustawianie tego kąta obrotu, aby zwiększyć zarówno funkcjonalność, jak i atrakcyjność wizualną.

**Czego się nauczysz:**
- Jak zainstalować i skonfigurować Aspose.Slides dla języka Python.
- Instrukcje dodawania i dostosowywania wykresów na slajdach.
- Techniki ustawiania kąta obrotu tytułów wykresów.
- Praktyczne zastosowania tych funkcji w wizualizacji danych.

Zanim przejdziemy do wdrażania, na początek omówmy wymagania wstępne.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:
- **Środowisko Pythona**: Zainstaluj Python 3.x z [python.org](https://www.python.org/).
- **Biblioteka Aspose.Slides**: Zainstaluj za pomocą pip, aby skutecznie manipulować prezentacjami.
- **Podstawowa wiedza z zakresu programowania w Pythonie**:Znajomość składni języka Python i operacji na plikach ułatwi Ci zrozumienie tekstu.

## Konfigurowanie Aspose.Slides dla Pythona

Aby użyć Aspose.Slides, zainstaluj go za pomocą pip. Otwórz terminal lub wiersz poleceń i uruchom:

```bash
pip install aspose.slides
```

### Etapy uzyskania licencji

Aspose oferuje różne opcje licencjonowania:
- **Bezpłatna wersja próbna**:Pobierz wersję próbną z [Strona wydania Aspose](https://releases.aspose.com/slides/python-net/).
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na rozszerzone funkcje za pośrednictwem [portal zakupowy](https://purchase.aspose.com/temporary-license/).
- **Zakup**:Rozważ zakup, jeśli uważasz, że narzędzie jest niezbędne, dostępne w sklepie [Strona zakupu Aspose](https://purchase.aspose.com/buy).

#### Podstawowa inicjalizacja i konfiguracja

Oto jak zainicjować Aspose.Slides w skrypcie Pythona:

```python
import aspose.slides as slides

# Utwórz obiekt prezentacji
def main():
    with slides.Presentation() as pres:
        # Twój kod będzie tutaj
        pass

if __name__ == "__main__":
    main()
```

## Przewodnik wdrażania

### Dodawanie i dostosowywanie wykresów

#### Przegląd

W tej sekcji dodamy do slajdu wykres kolumnowy i dostosujemy go, ustawiając kąt obrotu tytułu jego osi pionowej.

#### Kroki:

##### Krok 1: Dodaj wykres kolumnowy klastrowany

Zacznij od dodania wykresu w określonych współrzędnych z określonymi wymiarami:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        # Dodaj wykres kolumnowy klastrowany do slajdu 1
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
```

##### Krok 2: Skonfiguruj tytuł osi pionowej

Włącz i ustaw kąt obrotu dla tytułu osi pionowej:

```python
def configure_chart(chart):
    # Włącz tytuł osi pionowej
    chart.axes.vertical_axis.has_title = True
    
    # Ustaw kąt obrotu na 90 stopni
    chart.axes.vertical_axis.title.text_format.text_block_format.rotation_angle = 90
```

##### Krok 3: Zapisz swoją prezentację

Na koniec zapisz prezentację ze zmianami:

```python
def main():
    import aspose.slides as slides

    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.CLUSTERED_COLUMN, 50, 50, 450, 300)
        configure_chart(chart)
        
        # Zapisz prezentację
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_setting_rotation_angle_out.pptx

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}