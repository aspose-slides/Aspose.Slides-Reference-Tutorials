---
"description": "Opanuj różne rodzaje układów diagramów organizacyjnych w programie SmartArt przy użyciu języka Java z programem Aspose.Slides, bez trudu wzbogacając wizualizacje prezentacji."
"linktitle": "Organizuj układ wykresu Typ w SmartArt przy użyciu Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Organizuj układ wykresu Typ w SmartArt przy użyciu Java"
"url": "/pl/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organizuj układ wykresu Typ w SmartArt przy użyciu Java

## Wstęp
W tym samouczku przejdziemy przez proces organizowania typu układu wykresu w SmartArt przy użyciu Java, w szczególności wykorzystując bibliotekę Aspose.Slides. SmartArt w prezentacjach może znacznie poprawić atrakcyjność wizualną i przejrzystość danych, co sprawia, że opanowanie jego manipulacji jest niezbędne.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
1. Java Development Kit (JDK) zainstalowany w Twoim systemie.
2. Biblioteka Aspose.Slides pobrana i skonfigurowana. Jeśli jeszcze tego nie zrobiłeś, pobierz ją z [Tutaj](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość programowania w Javie.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.*;
```
Rozłóżmy podany przykład na kilka kroków:
## Krok 1: Zainicjuj obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
Utwórz nowy obiekt prezentacji.
## Krok 2: Dodaj SmartArt do slajdu
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Dodaj SmartArt do wybranego slajdu o określonych wymiarach i typie układu.
## Krok 3: Ustaw układ schematu organizacyjnego
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Ustaw typ układu schematu organizacyjnego. W tym przykładzie używamy układu Left Hanging.
## Krok 4: Zapisz prezentację
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Zapisz prezentację z uporządkowanym układem wykresów.

## Wniosek
Opanowanie organizacji typów układów wykresów w SmartArt przy użyciu Java pozwala na łatwe tworzenie angażujących wizualnie prezentacji. Dzięki Aspose.Slides proces ten staje się usprawniony i wydajny, co pozwala skupić się na tworzeniu treści o dużym wpływie.
## Najczęściej zadawane pytania
### Czy Aspose.Slides jest kompatybilny z różnymi środowiskami programistycznymi Java?
Tak, Aspose.Slides jest kompatybilny z różnymi środowiskami programistycznymi Java, co zapewnia programistom elastyczność.
### Czy mogę dostosować wygląd elementów SmartArt za pomocą Aspose.Slides?
Oczywiście, Aspose.Slides oferuje rozbudowane opcje personalizacji elementów SmartArt, dzięki czemu możesz dopasować je do swoich konkretnych wymagań.
### Czy Aspose.Slides oferuje kompleksową dokumentację dla programistów?
Tak, programiści mogą zapoznać się ze szczegółową dokumentacją Aspose.Slides for Java, która zawiera informacje na temat jego funkcjonalności i sposobu użycia.
### Czy jest dostępna wersja próbna Aspose.Slides?
Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides, aby zapoznać się z jej funkcjami przed podjęciem decyzji o zakupie.
### Gdzie mogę szukać pomocy w kwestiach związanych z Aspose.Slides?
W przypadku pytań lub pomocy dotyczącej Aspose.Slides możesz odwiedzić forum pomocy technicznej [Tutaj](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}