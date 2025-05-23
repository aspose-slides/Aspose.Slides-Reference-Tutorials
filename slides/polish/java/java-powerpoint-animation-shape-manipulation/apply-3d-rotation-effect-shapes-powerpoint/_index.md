---
"description": "Dowiedz się, jak stosować efekty obrotu 3D do kształtów w programie PowerPoint za pomocą Aspose.Slides dla Java, korzystając z tego kompleksowego samouczka krok po kroku."
"linktitle": "Zastosuj efekt obrotu 3D do kształtów w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zastosuj efekt obrotu 3D do kształtów w programie PowerPoint"
"url": "/pl/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj efekt obrotu 3D do kształtów w programie PowerPoint

## Wstęp
Czy jesteś gotowy, aby przenieść swoje prezentacje PowerPoint na wyższy poziom? Dodanie efektów obrotu 3D może sprawić, że Twoje slajdy będą bardziej dynamiczne i angażujące. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek krok po kroku pokaże Ci, jak stosować efekty obrotu 3D do kształtów w programie PowerPoint przy użyciu Aspose.Slides dla Java. Zaczynajmy!
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w swoim systemie. Możesz go pobrać ze strony [Strona internetowa Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides dla Java: Pobierz najnowszą wersję Aspose.Slides dla Java ze strony [link do pobrania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): do kodowania użyj środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse.
4. Ważne prawo jazdy: Jeśli nie masz prawa jazdy, możesz je uzyskać [licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby wypróbować funkcje.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do projektu Java. Te importy pomogą Ci obsługiwać prezentacje i kształty za pomocą Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Krok 1: Skonfiguruj swój projekt
Zanim zagłębisz się w kod, skonfiguruj środowisko swojego projektu. Upewnij się, że dodałeś Aspose.Slides for Java do zależności swojego projektu.
Dodaj Aspose.Slides do swojego projektu:
1. Pobierz pliki JAR Aspose.Slides z [strona do pobrania](https://releases.aspose.com/slides/java/).
2. Dodaj te pliki JAR do ścieżki kompilacji swojego projektu.
## Krok 2: Utwórz nową prezentację programu PowerPoint
W tym kroku utworzymy nową prezentację PowerPoint.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation pres = new Presentation();
```
Ten fragment kodu inicjuje nowy obiekt prezentacji, do którego dodamy nasze kształty.
## Krok 3: Dodaj kształt prostokąta
Następnie dodajmy prostokąt do pierwszego slajdu.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Ten kod dodaje prostokątny kształt w określonym miejscu i rozmiarze na pierwszym slajdzie.
## Krok 4: Zastosuj obrót 3D do prostokąta
Teraz zastosujmy efekt obrotu 3D do kształtu prostokąta.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Tutaj ustawiamy głębokość, kąty obrotu kamery, typ kamery i typ oświetlenia, aby nadać naszemu prostokątowi wygląd 3D.
## Krok 5: Dodaj kształt linii
Dodajmy do slajdu kolejny kształt, tym razem linię.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Ten kod umieszcza linię na slajdzie.
## Krok 6: Zastosuj obrót 3D do linii
Na koniec zastosujemy efekt obrotu 3D do kształtu linii.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Podobnie jak w przypadku prostokąta, ustawiamy właściwości 3D dla kształtu linii.
## Krok 7: Zapisz prezentację
Po dodaniu i skonfigurowaniu kształtów zapisz prezentację.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Ten kod zapisuje prezentację pod określoną nazwą pliku i w wybranym formacie.
## Wniosek
Gratulacje! Udało Ci się zastosować efekty rotacji 3D do kształtów w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Wykonując te kroki, możesz tworzyć atrakcyjne wizualnie i dynamiczne prezentacje. Aby uzyskać więcej opcji dostosowywania i bardziej zaawansowanych funkcji, zapoznaj się z [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/).
## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to zaawansowany interfejs API umożliwiający programowe tworzenie, modyfikowanie i manipulowanie prezentacjami PowerPoint.
### Czy mogę wypróbować Aspose.Slides for Java za darmo?
Tak, możesz dostać [bezpłatny okres próbny](https://releases.aspose.com/) lub [licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby przetestować funkcje.
### Do jakich typów kształtów mogę dodawać efekty 3D w Aspose.Slides?
Możesz dodawać efekty 3D do różnych kształtów, takich jak prostokąty, linie, elipsy i kształty niestandardowe.
### Jak uzyskać pomoc techniczną dotyczącą Aspose.Slides dla Java?
Możesz odwiedzić [forum wsparcia](https://forum.aspose.com/c/slides/11) w celu uzyskania pomocy i omówienia wszelkich problemów.
### Czy mogę używać Aspose.Slides for Java w projektach komercyjnych?
Tak, ale musisz kupić licencję. Możesz kupić ją od [strona zakupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}