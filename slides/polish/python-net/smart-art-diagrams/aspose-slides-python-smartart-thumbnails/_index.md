---
"date": "2025-04-23"
"description": "Dowiedz się, jak zautomatyzować tworzenie grafik SmartArt w prezentacjach PowerPoint za pomocą Aspose.Slides dla języka Python, w tym jak efektywnie wyodrębniać i zapisywać miniatury."
"title": "Jak tworzyć i pobierać miniatury SmartArt za pomocą Aspose.Slides dla Pythona"
"url": "/pl/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć i pobierać miniatury SmartArt za pomocą Aspose.Slides dla Pythona

## Wstęp

Tworzenie atrakcyjnych wizualnie prezentacji jest niezbędne, aby przyciągnąć uwagę odbiorców. Jednym ze skutecznych sposobów na ulepszenie slajdów jest włączenie dynamicznej grafiki, takiej jak SmartArt, do prezentacji PowerPoint. Jeśli szukasz zautomatyzowanej metody generowania tych wizualizacji i wyodrębniania z nich miniatur, ten przewodnik „Aspose.Slides Python” będzie nieoceniony.

Używając Aspose.Slides dla Pythona, możesz bez wysiłku tworzyć grafiki SmartArt, uzyskiwać dostęp do określonych węzłów w grafice, pobierać miniatury obrazów tych węzłów i zapisywać te obrazy dla swoich projektów. Ten samouczek przeprowadzi Cię przez każdy krok szczegółowo.

**Czego się nauczysz:**
- Jak zainstalować i skonfigurować Aspose.Slides dla języka Python.
- Tworzenie grafiki SmartArt w prezentacji programu PowerPoint.
- Uzyskiwanie dostępu do węzłów w grafice SmartArt.
- Wyodrębnianie i zapisywanie miniatury obrazu z określonego węzła.

Zanim zaczniemy, przyjrzyjmy się bliżej wymaganiom wstępnym.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz przygotowane następujące rzeczy:

- **Wymagane biblioteki:** Będziesz potrzebować Aspose.Slides dla Pythona. Upewnij się, że Twoje środowisko obsługuje Pythona 3.x.
- **Wymagania dotyczące konfiguracji środowiska:** Działająca instalacja Pythona i odpowiednie środowisko IDE lub edytor tekstu, np. VSCode lub PyCharm.
- **Wymagania wstępne dotyczące wiedzy:** Podstawowa znajomość programowania w języku Python, obejmująca definicje funkcji i operacje na plikach.

## Konfigurowanie Aspose.Slides dla Pythona

Najpierw musisz zainstalować bibliotekę Aspose.Slides. Można to łatwo zrobić za pomocą pip:

```bash
pip install aspose.slides
```

Po zainstalowaniu uzyskaj licencję, jeśli chcesz eksplorować wszystkie funkcje bez ograniczeń. Możesz zacząć od bezpłatnej wersji próbnej, złożyć wniosek o tymczasową licencję lub kupić ją do długoterminowego użytkowania.

Aby zainicjować Aspose.Slides w środowisku Python, zaimportuj bibliotekę na początku skryptu:

```python
import aspose.slides as slides
```

## Przewodnik wdrażania

Podzielmy proces na proste kroki umożliwiające utworzenie i pobranie miniatury SmartArt.

### Krok 1: Utwórz nową instancję prezentacji

Zacznij od utworzenia instancji prezentacji. Będzie to kontener, do którego dodasz grafikę SmartArt.

```python
with slides.Presentation() as pres:
```

Używanie `with` zapewnia prawidłowe zarządzanie zasobami, automatycznie zapisując i zamykając plik przy wyjściu.

### Krok 2: Dodaj SmartArt do pierwszego slajdu

Następnie dodamy grafikę SmartArt do naszego pierwszego slajdu. Oto jak możesz to zrobić:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Dodaje podstawowy układ cyklu dla grafiki SmartArt w pozycji (10, 10) o wymiarach 400x300 pikseli.

### Krok 3: Uzyskaj dostęp do drugiego węzła

Uzyskaj dostęp do określonych węzłów w ramach SmartArt. W tym przykładzie uzyskujemy dostęp do drugiego węzła:

```python
node = smart.nodes[1]
```

Węzły są indeksowane od zera; stąd `nodes[1]` odnosi się do drugiego węzła na liście.

### Krok 4: Pobierz miniaturę obrazu

Aby uzyskać miniaturę obrazu kształtu w wybranym węźle:

```python
image = node.shapes[0].get_image()
```

Pobiera obraz pierwszego kształtu jako miniaturę ze wskazanego węzła SmartArt.

### Krok 5: Zapisz pobrany obraz

Na koniec zapisz tę miniaturę w wybranym przez siebie miejscu w formacie JPEG:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}