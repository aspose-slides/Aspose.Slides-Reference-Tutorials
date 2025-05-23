---
"description": "Leer hoe je OLE-objectgegevens in PowerPoint wijzigt met Aspose.Slides voor Java. Een stapsgewijze handleiding voor efficiënte en eenvoudige updates."
"linktitle": "OLE-objectgegevens wijzigen in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "OLE-objectgegevens wijzigen in PowerPoint"
"url": "/nl/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# OLE-objectgegevens wijzigen in PowerPoint

## Invoering
Het wijzigen van OLE-objectgegevens in PowerPoint-presentaties kan een cruciale taak zijn wanneer u ingesloten inhoud wilt bijwerken zonder elke dia handmatig te bewerken. Deze uitgebreide handleiding begeleidt u door het proces met Aspose.Slides voor Java, een krachtige bibliotheek die speciaal is ontworpen voor PowerPoint-presentaties. Of u nu een ervaren ontwikkelaar bent of net begint, u zult deze tutorial nuttig en gemakkelijk te volgen vinden.
## Vereisten
Voordat we in de code duiken, controleren we of je alles hebt wat je nodig hebt om aan de slag te gaan.
1. Java Development Kit (JDK): Zorg ervoor dat de JDK op uw systeem is geïnstalleerd. U kunt deze downloaden van [De site van Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides voor Java: Download de nieuwste versie van de [Aspose.Slides downloadpagina](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): u kunt elke Java IDE gebruiken, zoals IntelliJ IDEA, Eclipse of NetBeans.
4. Aspose.Cells voor Java: Dit is vereist om de ingesloten gegevens in het OLE-object te wijzigen. Download het van [Aspose.Cells downloadpagina](https://releases.aspose.com/cells/java/).
5. Presentatiebestand: Zorg dat je een PowerPoint-bestand met een ingesloten OLE-object bij de hand hebt. Voor deze tutorial noemen we het `ChangeOLEObjectData.pptx`.
## Pakketten importeren
Laten we eerst de benodigde pakketten in uw Java-project importeren.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Laten we het proces nu opdelen in eenvoudige, beheersbare stappen.
## Stap 1: Laad de PowerPoint-presentatie
Om te beginnen moet u de PowerPoint-presentatie laden die het OLE-object bevat.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Stap 2: Toegang tot de dia met het OLE-object
Selecteer vervolgens de dia waarin het OLE-object is ingesloten.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Stap 3: Zoek het OLE-object in de dia
Doorloop de vormen in de dia om het OLE-object te vinden.
```java
OleObjectFrame ole = null;
// Het doorkruisen van alle vormen voor Ole-frame
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Stap 4: De ingesloten gegevens uit het OLE-object extraheren
Als het OLE-object wordt gevonden, worden de ingesloten gegevens opgehaald.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Stap 5: Wijzig de ingesloten gegevens met Aspose.Cells
Gebruik nu Aspose.Cells om de ingesloten gegevens te lezen en te wijzigen. In dit geval is dit waarschijnlijk een Excel-werkmap.
```java
    Workbook wb = new Workbook(msln);
    // De werkmapgegevens wijzigen
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Stap 6: Sla de gewijzigde gegevens terug op in het OLE-object
Nadat u de gewenste wijzigingen hebt aangebracht, slaat u de gewijzigde werkmap weer op in het OLE-object.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Stap 7: Sla de bijgewerkte presentatie op
Sla ten slotte de bijgewerkte PowerPoint-presentatie op.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Conclusie
Het bijwerken van OLE-objectgegevens in PowerPoint-presentaties met Aspose.Slides voor Java is een eenvoudig proces, opgedeeld in eenvoudige stappen. Deze handleiding begeleidde u bij het laden van een presentatie, het openen en wijzigen van ingesloten OLE-gegevens en het opslaan van de bijgewerkte presentatie. Met deze stappen kunt u ingesloten content in uw PowerPoint-dia's efficiënt beheren en bijwerken via een programma.
## Veelgestelde vragen
### Wat is een OLE-object in PowerPoint?
Met een OLE-object (Object Linking and Embedding) kunt u inhoud uit andere toepassingen, zoals Excel-spreadsheets, insluiten in PowerPoint-dia's.
### Kan ik Aspose.Slides gebruiken met andere programmeertalen?
Ja, Aspose.Slides ondersteunt meerdere talen, waaronder .NET, Python en C++.
### Heb ik Aspose.Cells nodig om OLE-objecten in PowerPoint te wijzigen?
Ja, als het OLE-object een Excel-spreadsheet is, hebt u Aspose.Cells nodig om het te wijzigen.
### Bestaat er een proefversie van Aspose.Slides?
Ja, je kunt een [gratis proefperiode](https://releases.aspose.com/) om de functies van Aspose.Slides te testen.
### Waar kan ik de documentatie voor Aspose.Slides vinden?
Gedetailleerde documentatie vindt u op de [Aspose.Slides documentatiepagina](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}