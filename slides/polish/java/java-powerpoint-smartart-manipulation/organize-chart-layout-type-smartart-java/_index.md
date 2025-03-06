---
title: Organizuj układ wykresu Wpisz grafikę SmartArt przy użyciu języka Java
linktitle: Organizuj układ wykresu Wpisz grafikę SmartArt przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Opanuj organizowanie typów układów wykresów w SmartArt przy użyciu języka Java z Aspose.Slides, bez wysiłku ulepszając wizualizacje prezentacji.
weight: 13
url: /pl/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Organizuj układ wykresu Wpisz grafikę SmartArt przy użyciu języka Java

## Wstęp
tym samouczku omówimy proces organizowania układu wykresu w SmartArt przy użyciu języka Java, w szczególności z wykorzystaniem biblioteki Aspose.Slides. Grafika SmartArt w prezentacjach może znacznie poprawić atrakcyjność wizualną i przejrzystość danych, dlatego konieczne jest opanowanie manipulacji nimi.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Pobrano i skonfigurowano bibliotekę Aspose.Slides. Jeśli jeszcze tego nie zrobiłeś, pobierz go z[Tutaj](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość programowania w języku Java.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.*;
```
Podzielmy podany przykład na kilka kroków:
## Krok 1: Zainicjuj obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
Utwórz nowy obiekt prezentacji.
## Krok 2: Dodaj grafikę SmartArt do slajdu
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Dodaj grafikę SmartArt do żądanego slajdu z określonymi wymiarami i typem układu.
## Krok 3: Ustaw układ schematu organizacyjnego
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Ustaw typ układu schematu organizacyjnego. W tym przykładzie używamy układu wiszącego po lewej stronie.
## Krok 4: Zapisz prezentację
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Zapisz prezentację ze zorganizowanym układem wykresu.

## Wniosek
Opanowanie organizacji typów układów wykresów w SmartArt przy użyciu języka Java umożliwia łatwe tworzenie atrakcyjnych wizualnie prezentacji. Dzięki Aspose.Slides proces staje się usprawniony i wydajny, dzięki czemu możesz skupić się na tworzeniu wpływowych treści.
## Często zadawane pytania
### Czy Aspose.Slides jest kompatybilny z różnymi środowiskami programistycznymi Java?
Tak, Aspose.Slides jest kompatybilny z różnymi środowiskami programistycznymi Java, zapewniając programistom elastyczność.
### Czy mogę dostosować wygląd elementów SmartArt za pomocą Aspose.Slides?
Absolutnie Aspose.Slides zapewnia szerokie opcje dostosowywania elementów SmartArt, umożliwiając dostosowanie ich do konkretnych wymagań.
### Czy Aspose.Slides oferuje kompleksową dokumentację dla programistów?
Tak, programiści mogą zapoznać się ze szczegółową dokumentacją dostarczoną przez Aspose.Slides dla Java, oferując wgląd w jej funkcjonalności i wykorzystanie.
### Czy dostępna jest wersja próbna Aspose.Slides?
Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Slides, aby zapoznać się z jej funkcjami przed podjęciem decyzji o zakupie.
### Gdzie mogę uzyskać pomoc w przypadku zapytań związanych z Aspose.Slides?
 Aby uzyskać pomoc lub pytania dotyczące Aspose.Slides, możesz odwiedzić forum pomocy technicznej[Tutaj](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
