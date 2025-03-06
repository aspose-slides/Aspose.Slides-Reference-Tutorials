---
title: Zmień dane obiektu OLE w programie PowerPoint
linktitle: Zmień dane obiektu OLE w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zmieniać dane obiektu OLE w programie PowerPoint przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku dotyczący skutecznych i łatwych aktualizacji.
weight: 14
url: /pl/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Zmiana danych obiektu OLE w prezentacjach programu PowerPoint może być kluczowym zadaniem, gdy zachodzi potrzeba aktualizacji osadzonej zawartości bez ręcznej edycji każdego slajdu. Ten obszerny przewodnik przeprowadzi Cię przez proces korzystania z Aspose.Slides dla Java, potężnej biblioteki przeznaczonej do obsługi prezentacji PowerPoint. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten samouczek będzie pomocny i łatwy do zrozumienia.
## Warunki wstępne
Zanim zagłębimy się w kod, upewnijmy się, że masz wszystko, czego potrzebujesz, aby zacząć.
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie. Można go pobrać z[stronie Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję z[Strona pobierania Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Można używać dowolnego środowiska Java IDE, takiego jak IntelliJ IDEA, Eclipse lub NetBeans.
4.  Aspose.Cells for Java: Jest to wymagane do modyfikowania danych osadzonych w obiekcie OLE. Pobierz go z[Strona pobierania Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Plik prezentacji: Przygotuj plik programu PowerPoint z osadzonym obiektem OLE. Na potrzeby tego samouczka nazwijmy to`ChangeOLEObjectData.pptx`.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do Twojego projektu Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Podzielmy teraz proces na proste, łatwe do wykonania kroki.
## Krok 1: Załaduj prezentację programu PowerPoint
Aby rozpocząć, należy załadować prezentację PowerPoint zawierającą obiekt OLE.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Krok 2: Uzyskaj dostęp do slajdu zawierającego obiekt OLE
Następnie pobierz slajd, w którym osadzony jest obiekt OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Znajdź obiekt OLE na slajdzie
Przeglądaj kształty na slajdzie, aby zlokalizować obiekt OLE.
```java
OleObjectFrame ole = null;
// Przemierzanie wszystkich kształtów dla ramy Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Krok 4: Wyodrębnij osadzone dane z obiektu OLE
Jeśli zostanie znaleziony obiekt OLE, wyodrębnij jego osadzone dane.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Krok 5: Zmodyfikuj osadzone dane za pomocą Aspose.Cells
Teraz użyj Aspose.Cells, aby odczytać i zmodyfikować osadzone dane, którymi w tym przypadku jest prawdopodobnie skoroszyt programu Excel.
```java
    Workbook wb = new Workbook(msln);
    // Zmodyfikuj dane skoroszytu
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Krok 6: Zapisz zmodyfikowane dane z powrotem do obiektu OLE
Po dokonaniu niezbędnych zmian zapisz zmodyfikowany skoroszyt z powrotem w obiekcie OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Krok 7: Zapisz zaktualizowaną prezentację
Na koniec zapisz zaktualizowaną prezentację programu PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Wniosek
Aktualizowanie danych obiektów OLE w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla języka Java jest prostym procesem, jeśli podzielisz go na proste kroki. Ten przewodnik przeprowadził Cię przez ładowanie prezentacji, uzyskiwanie dostępu do osadzonych danych OLE i ich modyfikowanie oraz zapisywanie zaktualizowanej prezentacji. Wykonując te czynności, możesz efektywnie zarządzać treścią osadzoną na slajdach programu PowerPoint i programowo ją aktualizować.
## Często zadawane pytania
### Co to jest obiekt OLE w programie PowerPoint?
Obiekt OLE (Object Linking and Embedding) umożliwia osadzanie treści z innych aplikacji, takich jak arkusze kalkulacyjne Excel, w slajdach programu PowerPoint.
### Czy mogę używać Aspose.Slides z innymi językami programowania?
Tak, Aspose.Slides obsługuje kilka języków, w tym .NET, Python i C++.
### Czy potrzebuję Aspose.Cells do modyfikowania obiektów OLE w programie PowerPoint?
Tak, jeśli obiekt OLE jest arkuszem kalkulacyjnym Excel, będziesz potrzebować Aspose.Cells, aby go zmodyfikować.
### Czy istnieje wersja próbna Aspose.Slides?
 Tak, możesz dostać[bezpłatna wersja próbna](https://releases.aspose.com/) aby przetestować funkcje Aspose.Slides.
### Gdzie mogę znaleźć dokumentację Aspose.Slides?
 Szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
