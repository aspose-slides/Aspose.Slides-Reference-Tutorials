---
"description": "Dowiedz się, jak zmienić dane obiektu OLE w programie PowerPoint za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku dotyczący wydajnych i łatwych aktualizacji."
"linktitle": "Zmiana danych obiektu OLE w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zmiana danych obiektu OLE w programie PowerPoint"
"url": "/pl/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zmiana danych obiektu OLE w programie PowerPoint

## Wstęp
Zmiana danych obiektów OLE w prezentacjach PowerPoint może być kluczowym zadaniem, gdy trzeba zaktualizować osadzoną zawartość bez ręcznej edycji każdego slajdu. Ten kompleksowy przewodnik przeprowadzi Cię przez proces przy użyciu Aspose.Slides for Java, potężnej biblioteki zaprojektowanej do obsługi prezentacji PowerPoint. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek okaże się pomocny i łatwy do naśladowania.
## Wymagania wstępne
Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć.
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w swoim systemie. Możesz go pobrać z [Strona Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides dla Java: Pobierz najnowszą wersję ze strony [Strona pobierania Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Możesz używać dowolnego środowiska IDE Java, takiego jak IntelliJ IDEA, Eclipse lub NetBeans.
4. Aspose.Cells dla Java: Jest to wymagane do modyfikacji osadzonych danych w obiekcie OLE. Pobierz z [Strona pobierania Aspose.Cells](https://releases.aspose.com/cells/java/).
5. Plik prezentacji: Przygotuj plik PowerPoint z osadzonym obiektem OLE. W tym samouczku nazwijmy go `ChangeOLEObjectData.pptx`.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do Twojego projektu Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Teraz podzielimy ten proces na proste i łatwe do opanowania kroki.
## Krok 1: Załaduj prezentację PowerPoint
Na początek musisz załadować prezentację PowerPoint zawierającą obiekt OLE.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Krok 2: Uzyskaj dostęp do slajdu zawierającego obiekt OLE
Następnie przejdź do slajdu, na którym osadzony jest obiekt OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Znajdź obiekt OLE na slajdzie
Przeglądaj kształty na slajdzie, aby znaleźć obiekt OLE.
```java
OleObjectFrame ole = null;
// Przechodzenie przez wszystkie kształty dla ramki Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Krok 4: Wyodrębnij osadzone dane z obiektu OLE
Jeśli obiekt OLE zostanie znaleziony, wyodrębnij jego osadzone dane.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Krok 5: Modyfikowanie osadzonych danych za pomocą Aspose.Cells
Teraz użyj Aspose.Cells, aby odczytać i zmodyfikować osadzone dane, które w tym przypadku są najprawdopodobniej skoroszytem programu Excel.
```java
    Workbook wb = new Workbook(msln);
    // Modyfikuj dane skoroszytu
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Krok 6: Zapisywanie zmodyfikowanych danych z powrotem do obiektu OLE
Po wprowadzeniu niezbędnych zmian zapisz zmodyfikowany skoroszyt z powrotem w obiekcie OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Krok 7: Zapisz zaktualizowaną prezentację
Na koniec zapisz zaktualizowaną prezentację PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Wniosek
Aktualizacja danych obiektów OLE w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java to prosty proces, gdy rozbijesz go na proste kroki. Ten przewodnik przeprowadzi Cię przez ładowanie prezentacji, dostęp do osadzonych danych OLE i ich modyfikację oraz zapisywanie zaktualizowanej prezentacji. Dzięki tym krokom możesz sprawnie zarządzać osadzoną zawartością w slajdach PowerPoint i aktualizować ją programowo.
## Najczęściej zadawane pytania
### Czym jest obiekt OLE w programie PowerPoint?
Obiekt OLE (Object Linking and Embedding) umożliwia osadzanie zawartości z innych aplikacji, np. arkuszy kalkulacyjnych Excel, w slajdach programu PowerPoint.
### Czy mogę używać Aspose.Slides z innymi językami programowania?
Tak, Aspose.Slides obsługuje wiele języków, w tym .NET, Python i C++.
### Czy potrzebuję Aspose.Cells do modyfikowania obiektów OLE w programie PowerPoint?
Tak, jeśli obiekt OLE jest arkuszem kalkulacyjnym programu Excel, do jego modyfikacji będziesz potrzebować Aspose.Cells.
### Czy istnieje wersja próbna Aspose.Slides?
Tak, możesz dostać [bezpłatny okres próbny](https://releases.aspose.com/) aby przetestować funkcje Aspose.Slides.
### Gdzie mogę znaleźć dokumentację Aspose.Slides?
Szczegółową dokumentację można znaleźć na stronie [Strona dokumentacji Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}