---
title: Wijzig OLE-objectgegevens in PowerPoint
linktitle: Wijzig OLE-objectgegevens in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u OLE-objectgegevens in PowerPoint kunt wijzigen met Aspose.Slides voor Java. Een stap-voor-stap handleiding voor efficiënte en gemakkelijke updates.
weight: 14
url: /nl/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Invoering
Het wijzigen van OLE-objectgegevens in PowerPoint-presentaties kan een cruciale taak zijn wanneer u ingesloten inhoud moet bijwerken zonder elke dia handmatig te bewerken. Deze uitgebreide gids leidt u door het proces met Aspose.Slides voor Java, een krachtige bibliotheek ontworpen voor het verwerken van PowerPoint-presentaties. Of u nu een doorgewinterde ontwikkelaar bent of net begint, u zult deze tutorial nuttig en gemakkelijk te volgen vinden.
## Vereisten
Voordat we in de code duiken, zorgen we ervoor dat u alles heeft wat u nodig heeft om aan de slag te gaan.
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. Je kunt het downloaden van[Oracle-site](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides voor Java: Download de nieuwste versie van de[Aspose.Slides downloadpagina](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): U kunt elke Java IDE gebruiken, zoals IntelliJ IDEA, Eclipse of NetBeans.
4.  Aspose.Cells voor Java: Dit is vereist om de ingebedde gegevens in het OLE-object te wijzigen. Download het van[Aspose.Cells downloadpagina](https://releases.aspose.com/cells/java/).
5.  Presentatiebestand: Zorg ervoor dat u een PowerPoint-bestand bij de hand heeft met een ingesloten OLE-object. Laten we deze tutorial een naam geven`ChangeOLEObjectData.pptx`.
## Pakketten importeren
Laten we eerst de benodigde pakketten in uw Java-project importeren.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Laten we het proces nu opsplitsen in eenvoudige, beheersbare stappen.
## Stap 1: Laad de PowerPoint-presentatie
Om te beginnen moet u de PowerPoint-presentatie laden die het OLE-object bevat.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Stap 2: Open de dia met het OLE-object
Haal vervolgens de dia op waarin het OLE-object is ingesloten.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Stap 3: Zoek het OLE-object in de dia
Blader door de vormen in de dia om het OLE-object te vinden.
```java
OleObjectFrame ole = null;
// Alle vormen doorkruisen voor het Ole-frame
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Stap 4: Extraheer de ingebedde gegevens uit het OLE-object
Als het OLE-object wordt gevonden, extraheert u de ingesloten gegevens ervan.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Stap 5: Wijzig de ingebedde gegevens met Aspose.Cells
Gebruik nu Aspose.Cells om de ingesloten gegevens te lezen en te wijzigen, wat in dit geval waarschijnlijk een Excel-werkmap is.
```java
    Workbook wb = new Workbook(msln);
    // Wijzig de werkmapgegevens
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Stap 6: Sla de gewijzigde gegevens terug naar het OLE-object
Nadat u de nodige wijzigingen heeft aangebracht, slaat u de gewijzigde werkmap weer op in het OLE-object.
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
Het bijwerken van OLE-objectgegevens in PowerPoint-presentaties met Aspose.Slides voor Java is een eenvoudig proces als u het eenmaal in eenvoudige stappen opsplitst. Deze handleiding begeleidt u bij het laden van een presentatie, het openen en wijzigen van ingesloten OLE-gegevens en het opslaan van de bijgewerkte presentatie. Met deze stappen kunt u ingesloten inhoud in uw PowerPoint-dia's efficiënt programmatisch beheren en bijwerken.
## Veelgestelde vragen
### Wat is een OLE-object in PowerPoint?
Met een OLE-object (Object Linking and Embedding) kunt u inhoud uit andere toepassingen, zoals Excel-spreadsheets, in PowerPoint-dia's insluiten.
### Kan ik Aspose.Slides met andere programmeertalen gebruiken?
Ja, Aspose.Slides ondersteunt verschillende talen, waaronder .NET, Python en C++.
### Heb ik Aspose.Cells nodig om OLE-objecten in PowerPoint te wijzigen?
Ja, als het OLE-object een Excel-spreadsheet is, hebt u Aspose.Cells nodig om het te wijzigen.
### Is er een proefversie van Aspose.Slides?
 Ja, je kunt een[gratis proefperiode](https://releases.aspose.com/) om de functies van Aspose.Slides te testen.
### Waar kan ik de documentatie voor Aspose.Slides vinden?
 Uitgebreide documentatie vindt u op de website[Aspose.Slides documentatiepagina](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
