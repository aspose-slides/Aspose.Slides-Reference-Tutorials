---
"date": "2025-04-23"
"description": "Dowiedz się, jak tworzyć i dostosowywać grafiki SmartArt w programie PowerPoint za pomocą pakietu Aspose.Slides dla języka Python, wzbogacając swoje prezentacje o dynamiczne schematy organizacyjne."
"title": "Jak tworzyć i dostosowywać SmartArt w programie PowerPoint za pomocą Aspose.Slides dla języka Python"
"url": "/pl/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć i dostosowywać SmartArt w programie PowerPoint za pomocą Aspose.Slides dla języka Python

## Wstęp

Prezentacje są niezbędnym narzędziem do wizualnego przedstawiania struktur organizacyjnych lub sesji burzy mózgów. Dzięki Aspose.Slides for Python możesz bez wysiłku tworzyć i dostosowywać grafiki SmartArt. Ten samouczek przeprowadzi Cię przez proces dodawania grafiki SmartArt schematu organizacyjnego do slajdów programu PowerPoint.

**Czego się nauczysz:**
- Dodawanie grafiki SmartArt w programie PowerPoint przy użyciu Aspose.Slides dla języka Python.
- Dostosowywanie układu węzła SmartArt.
- Efektywne zapisywanie i eksportowanie prezentacji.

Zacznijmy konfigurować Twoje środowisko!

## Wymagania wstępne

Zanim zaczniesz tworzyć grafikę SmartArt, upewnij się, że spełniasz następujące wymagania:

### Wymagane biblioteki
- **Aspose.Slides dla Pythona**: Zainstaluj tę bibliotekę za pomocą pip, jeśli jeszcze tego nie zrobiłeś.

### Wymagania dotyczące konfiguracji środowiska
- Działająca instalacja Pythona (zalecana wersja 3.x).
- Podstawowa znajomość programowania w języku Python.
- Znajomość programu Microsoft PowerPoint jest pomocna, ale niekonieczna.

## Konfigurowanie Aspose.Slides dla Pythona

Aby rozpocząć, skonfiguruj bibliotekę Aspose.Slides w swoim środowisku Python:

**Instalacja Pip:**
```bash
pip install aspose.slides
```

### Etapy uzyskania licencji
Aspose oferuje różne opcje licencjonowania:
- **Bezpłatna wersja próbna**:Pobierz tymczasową licencję, aby przetestować wszystkie funkcje.
- **Licencja tymczasowa**:Uzyskaj bezpłatną licencję tymczasową do krótkoterminowego użytku.
- **Zakup**:Rozważ zakup subskrypcji w przypadku projektów długoterminowych.

### Podstawowa inicjalizacja i konfiguracja

Po zainstalowaniu zainicjuj skrypt Pythona za pomocą Aspose.Slides w następujący sposób:

```python
import aspose.slides as slides

# Zainicjuj klasę Presentation za pomocą slides.Presentation() jako presentation:
    # Twój kod do dodania SmartArt będzie tutaj
```

## Przewodnik wdrażania

Teraz omówimy szczegółowo proces dodawania i dostosowywania obiektów SmartArt w programie PowerPoint za pomocą Aspose.Slides dla języka Python.

### Dodawanie grafiki SmartArt

#### Przegląd
Utwórz nowy slajd i dodaj do niego grafikę SmartArt typu schemat organizacyjny:

```python
import aspose.slides as slides

# Utwórz instancję prezentacji\z slides.Presentation() jako prezentację:
    # Dodaj SmartArt o określonych wymiarach w pozycji (10, 10)
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parametry i cel metody
- **x, y**:Położenie grafiki SmartArt na slajdzie.
- **szerokość, wysokość**:Wymiary zapewniające odpowiednią widoczność.
- **typ_układu**: Określa typ układu SmartArt, w tym przypadku schemat organizacyjny.

### Dostosowywanie układu schematu organizacyjnego

#### Przegląd
Dostosuj pierwszy węzeł w naszej grafice SmartArt, ustawiając jego układ na LEFT_HANGING:

```python
# Ustaw pierwszy węzeł na układ z wiszącą po lewej stronie
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Wyjaśnienie kluczowych opcji konfiguracji
- **Typ układu diagramu organizacyjnego**:Określa sposób wyświetlania węzłów, zwiększając czytelność i atrakcyjność estetyczną.

### Zapisywanie prezentacji

Na koniec zapisz prezentację w określonym katalogu:

```python
# Zapisz prezentację za pomocą SmartArt\presentation.save("YOUR_OUTPUT_DIRECTORY/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}