---
"date": "2025-04-24"
"description": "Dowiedz się, jak tworzyć i zarządzać regułami zapasowymi czcionek za pomocą Aspose.Slides dla języka Python, aby mieć pewność, że Twoje prezentacje będą spójne w różnych systemach."
"title": "Opanowanie funkcji Font Fallback w Aspose.Slides dla języka Python – kompleksowy przewodnik"
"url": "/pl/python-net/shapes-text/aspose-slides-python-font-fallback/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie funkcji Font Fallback w Aspose.Slides dla języka Python: kompleksowy przewodnik

## Wstęp

Problemy ze zgodnością czcionek mogą być trudne podczas tworzenia prezentacji, szczególnie w przypadku znaków Unicode nieobsługiwanych przez podstawowe czcionki. **Aspose.Slides dla Pythona** zapewnia niezawodne rozwiązanie dzięki regułom zapasowym czcionek, gwarantując wizualną atrakcyjność i czytelność prezentacji w różnych systemach.

tym przewodniku pokażemy, jak tworzyć i zarządzać regułami zapasowymi czcionek przy użyciu Aspose.Slides dla Pythona. Nauczysz się:
- Konfigurowanie środowiska z Aspose.Slides
- Tworzenie zbioru reguł zapasowych czcionek
- Zarządzanie tymi regułami poprzez dodawanie lub usuwanie czcionek na podstawie zakresów Unicode
- Stosowanie reguł do prezentacji i renderowanie slajdów jako obrazów

Zacznijmy od przygotowania środowiska.

## Wymagania wstępne

Upewnij się, że Twoje środowisko jest gotowe na to zadanie. Oto, czego będziesz potrzebować:
1. **Aspose.Slides dla Pythona**:Ta biblioteka zarządza regułami zapasowymi czcionek.
2. **Środowisko Pythona**: Upewnij się, że Python (wersja 3.6 lub nowsza) jest zainstalowany.
3. **Podstawowa wiedza o Pythonie**:Znajomość składni i pojęć języka Python będzie pomocna, gdy zagłębimy się w fragmenty kodu.

## Konfigurowanie Aspose.Slides dla Pythona

### Instalacja

Aby rozpocząć, zainstaluj bibliotekę Aspose.Slides za pomocą pip:

```bash
pip install aspose.slides
```

### Nabycie licencji

Aspose oferuje bezpłatną licencję próbną, aby eksplorować jego funkcje bez ograniczeń. Oto, jak możesz ją uzyskać:
- Odwiedzać [Strona zakupów Aspose](https://purchase.aspose.com/buy) w celu zakupu opcji lub uzyskania dostępu do licencji tymczasowej.
- Alternatywnie możesz pobrać bezpłatną wersję próbną ze strony [Sekcja pobierania](https://releases.aspose.com/slides/python-net/).

### Podstawowa inicjalizacja

Po zainstalowaniu zainicjuj Aspose.Slides w skrypcie Pythona:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

## Przewodnik wdrażania

### Tworzenie i zarządzanie regułami zapasowymi czcionek

#### Przegląd

Reguły zapasowego stosowania czcionek zapewniają, że wszystkie znaki w prezentacji będą miały odpowiednią czcionkę, co pozwoli zachować czytelność w językach wykorzystujących unikalne zestawy znaków.

#### Etapy wdrażania

**1. Utwórz zbiór reguł zapasowych czcionek**

Zacznij od utworzenia kolekcji, aby zdefiniować czcionki zapasowe:

```python
import aspose.slides as slides

def create_and_manage_font_fallback_rules():
    rules_list = slides.FontFallBackRulesCollection()
```

**2. Dodaj regułę zapasową czcionki**

Zdefiniuj regułę określającą zakres Unicode i czcionkę zapasową:

```python
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))
```
- **Parametry**: `0x400` jest początkiem zakresu Unicode, `0x4FF` to koniec i `"Times New Roman"` jest czcionką zapasową.

**3. Zarządzaj istniejącymi regułami**

Powtórz każdą regułę, aby zmodyfikować ją w razie potrzeby:

```python
for fallback_rule in rules_list:
    fallback_rule.remove("Tahoma")
    if 0x4000 <= fallback_rule.range_end_index < 0x5000:
        fallback_rule.add_fallBack_fonts("Verdana")
```

**4. Usuń regułę**

W razie potrzeby usuń pierwszą regułę ze swojej kolekcji:

```python
if len(rules_list) > 0:
    rules_list.remove(rules_list[0])
```

### Stosowanie reguł zapasowych czcionek do prezentacji i renderowania obrazu

#### Przegląd

Po skonfigurowaniu reguł dotyczących czcionek zapasowych należy je zastosować w prezentacjach, aby mieć pewność, że w razie potrzeby tekst będzie korzystał z określonych czcionek zapasowych.

#### Etapy wdrażania

**1. Zainicjuj swoje środowisko**

Przygotuj katalogi do wejścia i wyjścia:

```python
data_dir = "YOUR_DOCUMENT_DIRECTORY/"
out_dir = "YOUR_OUTPUT_DIRECTORY/"
```

**2. Zastosuj reguły zapasowe do prezentacji**

Załaduj plik prezentacji i zastosuj reguły dotyczące czcionek:

```python
rules_list = slides.FontFallBackRulesCollection()
rules_list.add(slides.FontFallBackRule(0x400, 0x4FF, "Times New Roman"))

with slides.Presentation(data_dir + "welcome-to-powerpoint.pptx") as pres:
    pres.fonts_manager.font_fall_back_rules_collection = rules_list
    pres.slides[0].get_image(1, 1).save(out_dir + "text_font_fall_back_out.png\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}