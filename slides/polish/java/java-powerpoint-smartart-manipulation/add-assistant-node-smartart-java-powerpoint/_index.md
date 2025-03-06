---
title: Dodaj węzeł asystenta do grafiki SmartArt w programie Java PowerPoint
linktitle: Dodaj węzeł asystenta do grafiki SmartArt w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodać węzeł asystenta do grafiki SmartArt w prezentacjach Java PowerPoint przy użyciu Aspose.Slides. Popraw swoje umiejętności edycji programu PowerPoint.
weight: 17
url: /pl/java/java-powerpoint-smartart-manipulation/add-assistant-node-smartart-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj węzeł asystenta do grafiki SmartArt w programie Java PowerPoint

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces dodawania węzła asystenta do grafiki SmartArt w prezentacjach Java PowerPoint przy użyciu Aspose.Slides.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Możesz pobrać i zainstalować najnowszy pakiet JDK ze strony[Tutaj](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Pobierz i zainstaluj bibliotekę Aspose.Slides for Java ze strony[ten link](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Na początek zaimportuj niezbędne pakiety do swojego kodu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Skonfiguruj prezentację
Rozpocznij od utworzenia instancji prezentacji, korzystając ze ścieżki do pliku programu PowerPoint:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "AssistantNode.pptx");
```
## Krok 2: Przejdź przez kształty
Przejdź przez każdy kształt na pierwszym slajdzie prezentacji:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes())
```
## Krok 3: Sprawdź kształty SmartArt
Sprawdź, czy kształt jest typu SmartArt:
```java
if (shape instanceof ISmartArt)
```
## Krok 4: Przejdź przez węzły grafiki SmartArt
Przejdź przez wszystkie węzły kształtu SmartArt:
```java
for (ISmartArtNode node : smart.getAllNodes())
```
## Krok 5: Sprawdź, czy istnieje węzeł asystenta
Sprawdź, czy węzeł jest węzłem pomocniczym:
```java
if (node.isAssistant())
```
## Krok 6: Ustaw węzeł asystenta na Normalny
Jeśli węzeł jest węzłem pomocniczym, ustaw go na węzeł normalny:
```java
node.setAssistant(false);
```
## Krok 7: Zapisz prezentację
Zapisz zmodyfikowaną prezentację:
```java
pres.save(dataDir + "ChangeAssistantNode_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Gratulacje! Pomyślnie dodałeś węzeł asystenta do grafiki SmartArt w prezentacji Java PowerPoint przy użyciu Aspose.Slides.

## Często zadawane pytania
### Czy mogę dodać wiele węzłów asystenta do grafiki SmartArt w prezentacji?
Tak, możesz dodać wiele węzłów asystentów, powtarzając proces dla każdego węzła.
### Czy ten samouczek działa zarówno w przypadku szablonów programu PowerPoint, jak i programu PowerPoint?
Tak, możesz zastosować ten samouczek zarówno do prezentacji PowerPoint, jak i szablonów.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje wersje programu PowerPoint od 97-2003 do najnowszej wersji.
### Czy mogę dostosować wygląd węzła asystenta?
Tak, możesz dostosować wygląd, korzystając z różnych właściwości i metod udostępnianych przez Aspose.Slides.
### Czy istnieje ograniczenie liczby węzłów w sztuce SmartArt?
Grafika SmartArt w programie PowerPoint obsługuje dużą liczbę węzłów, ale zaleca się zachowanie rozsądnej liczby węzłów, aby zapewnić lepszą czytelność.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
