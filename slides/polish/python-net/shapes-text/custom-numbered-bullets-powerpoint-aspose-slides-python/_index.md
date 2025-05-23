---
"date": "2025-04-24"
"description": "Dowiedz się, jak tworzyć niestandardowe numerowane listy punktowane w programie PowerPoint za pomocą Aspose.Slides dla języka Python. Ulepsz swoje prezentacje dzięki unikalnemu formatowaniu."
"title": "Niestandardowe numerowane listy punktowane w programie PowerPoint przy użyciu Aspose.Slides dla języka Python"
"url": "/pl/python-net/shapes-text/custom-numbered-bullets-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Niestandardowe numerowane listy punktowane w programie PowerPoint przy użyciu Aspose.Slides dla języka Python

## Wstęp
Czy chcesz podnieść atrakcyjność wizualną swoich prezentacji PowerPoint poza domyślne punkty wypunktowane? Niezależnie od tego, czy chodzi o raporty korporacyjne, wykłady akademickie czy spotkania biznesowe, dostosowywanie list wypunktowanych może skuteczniej przyciągnąć i utrzymać uwagę odbiorców. Dzięki **Aspose.Slides dla Pythona**, możesz elastycznie dostosowywać numerowane punkty do swoich unikalnych potrzeb w zakresie formatowania.

W tym kompleksowym przewodniku pokażemy, jak skonfigurować niestandardowe numerowane punkty za pomocą Aspose.Slides w programie PowerPoint z Pythonem. Dzięki zintegrowaniu tej funkcji z prezentacjami możesz uzyskać profesjonalny i dopracowany wygląd.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla Pythona
- Tworzenie niestandardowych list punktowanych z numeracją
- Konfigurowanie ustawień punktorów programowo
- Optymalizacja wydajności i rozwiązywanie typowych problemów

Zaczynajmy! Upewnij się, że masz wszystko gotowe, aby kontynuować.

## Wymagania wstępne
Przed wdrożeniem niestandardowych numerowanych punktów za pomocą Aspose.Slides dla języka Python upewnij się, że masz:

### Wymagane biblioteki:
- **Aspose.Slides dla Pythona**:Solidna biblioteka do tworzenia i edytowania prezentacji PowerPoint.

### Konfiguracja środowiska:
- Python 3.x zainstalowany w Twoim systemie.
- Podstawowa znajomość zagadnień programowania w języku Python jest pomocna, ale nie obowiązkowa.

## Konfigurowanie Aspose.Slides dla Pythona
Aby rozpocząć, zainstaluj `aspose.slides` biblioteka używająca pip:

```bash
pip install aspose.slides
```

### Nabycie licencji:
Aspose.Slides to produkt komercyjny oferujący bezpłatną wersję próbną do testowania jego możliwości. Możesz nabyć tymczasową licencję lub kupić jedną do dalszego użytkowania.

- **Bezpłatna wersja próbna**: Dostęp do podstawowych funkcji bez ograniczeń.
- **Licencja tymczasowa**: Złóż wniosek na stronie internetowej Aspose, aby uzyskać tymczasowy pełny dostęp.
- **Zakup**:Rozważ zakup licencji na projekty długoterminowe.

### Podstawowa inicjalizacja:
Po zainstalowaniu zainicjuj prezentację w następujący sposób:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Twój kod tutaj...
```

Ta konfiguracja przygotowuje środowisko do dodawania niestandardowych numerowanych punktów do slajdów programu PowerPoint.

## Przewodnik wdrażania
Zanurzmy się w tworzeniu niestandardowych numerowanych list punktowanych. Każdy krok jest rozbity na części w celu zapewnienia przejrzystości i łatwości implementacji.

### Dodawanie kształtu prostokąta za pomocą ramek tekstowych
#### Przegląd:
Najpierw dodaj kształt, który będzie zawierał ramki tekstowe dla punktów wypunktowanych.

```python
# Dodaj kształt prostokąta do pierwszego slajdu
shape = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 200, 200, 400, 200)
```
- **Wyjaśnienie parametrów**:Ten `add_auto_shape` Metoda przyjmuje parametry określające typ kształtu (prostokąt), pozycję (współrzędne x i y) i wymiary (szerokość i wysokość).

### Konfigurowanie ramek tekstowych
#### Przegląd:
Aby dodać punkty wypunktowania, uzyskaj dostęp do ramki tekstowej prostokąta.

```python
# Uzyskaj dostęp do ramki tekstowej utworzonego kształtu automatycznego
text_frame = shape.text_frame

# Usuń dowolny domyślny istniejący akapit, jeśli jest obecny
text_frame.paragraphs.clear()
```
- **Zamiar**:Zapewnia czystą kartę przed dodaniem niestandardowych punktów wypunktowanych.

### Dodawanie niestandardowych numerowanych punktów
#### Przegląd:
Dodaj akapity ze szczegółowymi ustawieniami punktowania:

```python
# Dodawaj akapity z niestandardowymi numerowanymi punktami
for start_number, bullet_text in [(2, "bullet 2"), (3, "bullet 3"), (7, "bullet 7")]:
    paragraph = slides.Paragraph()
    paragraph.text = bullet_text
    paragraph.paragraph_format.depth = 4
    paragraph.paragraph_format.bullet.numbered_bullet_start_with = start_number
    paragraph.paragraph_format.bullet.type = slides.BulletType.NUMBERED
    text_frame.paragraphs.add(paragraph)
```
- **Konfiguracja**:Każdy akapit zaczyna się od określonego numeru, co zapewnia elastyczność i kontrolę nad formatowaniem prezentacji.

### Zapisywanie prezentacji
Na koniec zapisz skonfigurowaną prezentację:

```python
# Zapisz prezentację\presentation.save("TWOJ_KATALOG_WYJŚCIOWY/text_set_custom_bullets_number_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}