---
"date": "2025-04-23"
"description": "Dowiedz się, jak dostosować kolory hiperłączy w prezentacjach PowerPoint za pomocą Aspose.Slides dla Pythona. Ulepszaj swoje slajdy za pomocą spersonalizowanych stylów łączy."
"title": "Jak ustawić kolory hiperłączy w programie PowerPoint za pomocą Aspose.Slides dla języka Python"
"url": "/pl/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić kolory hiperłączy w programie PowerPoint za pomocą Aspose.Slides dla języka Python

## Wstęp

Poprawa atrakcyjności wizualnej prezentacji PowerPoint poprzez dostosowywanie kolorów hiperłączy jest prosta dzięki Aspose.Slides for Python. Ten przewodnik przeprowadzi Cię przez ustawianie hiperłączy z określonymi kolorami na slajdach za pomocą Pythona.

**Czego się nauczysz:**
- Jak ustawić kolor hiperłącza w kształtach tekstowych w programie PowerPoint.
- Etapy tworzenia atrakcyjnej wizualnie prezentacji.
- Główne cechy Aspose.Slides dla języka Python, które ułatwiają taką personalizację.

Zanim zaczniemy, omówmy szczegółowo wymagania wstępne.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że Twoje środowisko jest gotowe, wykonując następujące czynności:
- **Biblioteki i wersje:** Zainstalować `aspose.slides` biblioteka. Upewnij się, że Python jest zainstalowany na twoim komputerze.
- **Wymagania dotyczące konfiguracji środowiska:** W tym samouczku założono podstawową konfigurację języka Python w systemie Windows, Mac lub Linux.
- **Wymagania wstępne dotyczące wiedzy:** Znajomość programowania w języku Python będzie dodatkowym atutem.

## Konfigurowanie Aspose.Slides dla Pythona

Aby rozpocząć korzystanie z Aspose.Slides dla języka Python, zainstaluj pakiet za pomocą pip:

```bash
pip install aspose.slides
```

**Etapy uzyskania licencji:**
- **Bezpłatna wersja próbna:** Pobierz wersję próbną z [Strona wydania Aspose](https://releases.aspose.com/slides/python-net/).
- **Licencja tymczasowa:** Poproś o tymczasową licencję na [strona zakupu](https://purchase.aspose.com/temporary-license/) dla rozszerzonego dostępu.
- **Zakup:** Aby w pełni odblokować funkcje bez ograniczeń, rozważ zakup licencji od [Strona zakupu Aspose](https://purchase.aspose.com/buy).

**Podstawowa inicjalizacja:**
Po zainstalowaniu i uzyskaniu licencji zaimportuj Aspose.Slides do swojego skryptu:

```python
import aspose.slides as slides
```

## Przewodnik wdrażania

W tej sekcji dowiesz się, jak ustawić kolory hiperłączy w prezentacji programu PowerPoint.

### Ustaw funkcję koloru hiperłącza

#### Przegląd

Dostosuj kolor hiperłączy osadzonych w kształtach tekstu za pomocą Aspose.Slides dla Pythona. Zwiększa to czytelność i atrakcyjność wizualną.

##### Krok 1: Utwórz nową prezentację

Utwórz wystąpienie prezentacji:

```python
with slides.Presentation() as presentation:
    # Twój kod tutaj
```

##### Krok 2: Dodaj kształt z tekstem

Dodaj prostokąt do pierwszego slajdu i wstaw tekst zawierający hiperłącze.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Krok 3: Ustaw właściwości hiperłącza

Przypisz hiperłącze i ustaw jego kolor. `hyperlink_click` Właściwość określa, gdzie link ma prowadzić po kliknięciu.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Ustaw źródło koloru dla formatu porcji hiperłącza oraz zdefiniuj typ wypełnienia i kolor.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Krok 4: Zapisz prezentację

Zapisz swoją prezentację w określonym katalogu:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}