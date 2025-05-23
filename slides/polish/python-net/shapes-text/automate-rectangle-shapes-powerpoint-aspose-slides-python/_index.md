---
"date": "2025-04-23"
"description": "Dowiedz się, jak zautomatyzować tworzenie i formatowanie kształtów prostokątnych w programie PowerPoint za pomocą Aspose.Slides dla języka Python. Bez wysiłku udoskonalaj swoje umiejętności prezentacyjne."
"title": "Automatyzacja kształtów prostokątnych w programie PowerPoint za pomocą Aspose.Slides dla języka Python"
"url": "/pl/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć i sformatować kształt prostokąta w programie PowerPoint za pomocą Aspose.Slides dla języka Python
## Wstęp
Czy zdarzyło Ci się kiedyś, że musiałeś szybko dodać niestandardowe kształty do prezentacji PowerPoint, ale miałeś problem z brakiem automatyzacji? Jeśli masz dość ręcznego formatowania prostokątów slajd po slajdzie, ten samouczek jest tutaj, aby uratować sytuację. Wykorzystując „Aspose.Slides for Python”, zautomatyzujemy dodawanie i stylizowanie kształtu prostokąta za pomocą zaledwie kilku linijek kodu. Do końca tego przewodnika opanujesz:
- Tworzenie kształtu prostokąta programowo
- Stosowanie opcji formatowania, takich jak kolor i styl linii
- Łatwe zapisywanie prezentacji
Przyjrzyjmy się bliżej temu, jak możesz odmienić proces tworzenia slajdów!
### Wymagania wstępne
Zanim zaczniemy kodować, upewnij się, że masz przygotowane następujące rzeczy:
- **Pyton** zainstalowany na Twoim komputerze (zalecana jest wersja 3.6 lub nowsza)
- **Aspose.Slides dla Pythona** biblioteka, która umożliwia nam manipulowanie prezentacjami PowerPoint
- Podstawowa znajomość koncepcji programowania w języku Python i znajomość instalowania pakietów za pomocą pip
## Konfigurowanie Aspose.Slides dla Pythona
### Instalacja
Aby zainstalować pakiet Aspose.Slides, otwórz terminal lub wiersz poleceń i uruchom:
```bash
pip install aspose.slides
```
To polecenie pobiera i instaluje najnowszą wersję Aspose.Slides dla języka Python z PyPI.
### Nabycie licencji
Aspose.Slides to produkt komercyjny, ale możesz zacząć z nim korzystać, korzystając z bezpłatnej licencji próbnej. Oto jak ją zdobyć:
1. **Bezpłatna wersja próbna:** Odwiedzać [Aspose Bezpłatna wersja próbna](https://releases.aspose.com/slides/python-net/) i zapisz się na ocenę.
2. **Licencja tymczasowa:** Aby uzyskać bardziej rozbudowane testy bez ograniczeń, poproś o tymczasową licencję na stronie [Strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
3. **Zakup:** Gdy będziesz gotowy do uruchomienia, kup licencję za pośrednictwem [Strona zakupu Aspose](https://purchase.aspose.com/buy).
Po nabyciu licencji postępuj zgodnie z dokumentacją, aby zastosować ją w swoim projekcie.
### Podstawowa inicjalizacja
Oto jak można zainicjować Aspose.Slides dla języka Python:
```python
import aspose.slides as slides
\# Zainicjuj klasę Prezentacja
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Ten fragment kodu tworzy nową prezentację i potwierdza, że jest ona gotowa do edycji.
## Przewodnik wdrażania
### Tworzenie kształtu prostokąta
#### Przegląd
W tej sekcji skupimy się na dodawaniu kształtu prostokąta do slajdu programu PowerPoint za pomocą Aspose.Slides dla języka Python.
#### Kroki tworzenia kształtu
1. **Otwórz lub utwórz prezentację:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Dodamy tutaj nasz prostokąt
   ```
2. **Dostęp do slajdu:**
   Pobierz pierwszy slajd, do którego chcesz dodać kształt.
   ```python
   slide = pres.slides[0]
   ```
3. **Dodaj kształt prostokąta:**
   Użyj `add_auto_shape` metoda tworzenia prostokąta na slajdzie.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Parametry: `ShapeType.RECTANGLE`, pozycja x (50), pozycja y (150), szerokość (150), wysokość (50).
### Formatowanie prostokąta
#### Przegląd
Następnie zastosujemy formatowanie do kształtu prostokąta, łącznie z kolorem wypełnienia i stylem linii.
#### Kroki formatowania
1. **Kolor wypełnienia:**
   Ustaw jednolite wypełnienie o określonym kolorze dla tła prostokąta.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Styl linii:**
   Dostosuj linię prostokąta, łącznie z jej kolorem i szerokością.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Zapisz prezentację:**
   Na koniec zapisz prezentację do pliku.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}