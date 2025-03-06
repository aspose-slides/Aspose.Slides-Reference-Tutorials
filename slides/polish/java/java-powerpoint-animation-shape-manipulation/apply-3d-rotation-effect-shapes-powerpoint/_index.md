---
title: Zastosuj efekt obrotu 3D na kształtach w programie PowerPoint
linktitle: Zastosuj efekt obrotu 3D na kształtach w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zastosować efekty rotacji 3D do kształtów w programie PowerPoint przy użyciu Aspose.Slides dla języka Java, korzystając z tego wszechstronnego samouczka krok po kroku.
weight: 12
url: /pl/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj efekt obrotu 3D na kształtach w programie PowerPoint

## Wstęp
Czy jesteś gotowy, aby przenieść swoje prezentacje PowerPoint na wyższy poziom? Dodanie efektów rotacji 3D może sprawić, że slajdy będą bardziej dynamiczne i wciągające. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek krok po kroku pokaże Ci, jak zastosować efekty rotacji 3D do kształtów w programie PowerPoint za pomocą Aspose.Slides dla Java. Zanurkujmy od razu!
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz przygotowane następujące elementy:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję Aspose.Slides dla Java z[link do pobrania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Do kodowania używaj środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse.
4.  Ważna licencja: Jeśli nie masz licencji, możesz uzyskać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby wypróbować funkcje.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do Twojego projektu Java. Te importy pomogą Ci obsługiwać prezentacje i kształty za pomocą Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Krok 1: Skonfiguruj swój projekt
Zanim zagłębisz się w kod, skonfiguruj środowisko projektu. Upewnij się, że dodałeś Aspose.Slides for Java do zależności swojego projektu.
Dodaj Aspose.Slides do swojego projektu:
1.  Pobierz pliki JAR Aspose.Slides z[strona pobierania](https://releases.aspose.com/slides/java/).
2. Dodaj te pliki JAR do ścieżki kompilacji projektu.
## Krok 2: Utwórz nową prezentację programu PowerPoint
Na tym etapie utworzymy nową prezentację programu PowerPoint.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation pres = new Presentation();
```
Ten fragment kodu inicjuje nowy obiekt prezentacji, w którym dodamy nasze kształty.
## Krok 3: Dodaj kształt prostokąta
Następnie dodajmy kształt prostokąta do pierwszego slajdu.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Ten kod dodaje kształt prostokąta w określonym położeniu i rozmiarze na pierwszym slajdzie.
## Krok 4: Zastosuj obrót 3D do prostokąta
Teraz zastosujmy efekt obrotu 3D do kształtu prostokąta.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Tutaj ustawiamy głębokość, kąty obrotu kamery, typ kamery i rodzaj oświetlenia, aby nadać naszemu prostokątowi wygląd 3D.
## Krok 5: Dodaj kształt linii
Dodajmy do slajdu kolejny kształt, tym razem linię.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Ten kod umieszcza kształt linii na slajdzie.
## Krok 6: Zastosuj obrót 3D do linii
Na koniec zastosujemy efekt obrotu 3D do kształtu linii.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Podobnie jak w przypadku prostokąta, ustawiamy właściwości 3D kształtu linii.
## Krok 7: Zapisz prezentację
Po dodaniu i skonfigurowaniu kształtów zapisz prezentację.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Ten kod zapisuje prezentację pod określoną nazwą pliku w żądanym formacie.
## Wniosek
 Gratulacje! Pomyślnie zastosowałeś efekty rotacji 3D do kształtów w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Wykonując poniższe kroki, możesz stworzyć atrakcyjne wizualnie i dynamiczne prezentacje. Dalsze informacje dotyczące dostosowywania i bardziej zaawansowanych funkcji można znaleźć w sekcji[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/).
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API umożliwiający programowe tworzenie, modyfikowanie i manipulowanie prezentacjami programu PowerPoint.
### Czy mogę bezpłatnie wypróbować Aspose.Slides dla Java?
 Tak, możesz dostać[bezpłatna wersja próbna](https://releases.aspose.com/) lub[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby przetestować funkcje.
### Do jakich typów kształtów mogę dodać efekty 3D w Aspose.Slides?
Możesz dodawać efekty 3D do różnych kształtów, takich jak prostokąty, linie, elipsy i kształty niestandardowe.
### Jak uzyskać wsparcie dla Aspose.Slides dla Java?
 Możesz odwiedzić[forum wsparcia](https://forum.aspose.com/c/slides/11) o pomoc i omówienie wszelkich problemów.
### Czy mogę używać Aspose.Slides for Java w projektach komercyjnych?
 Tak, ale musisz kupić licencję. Możesz kupić taki od[strona zakupu](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
