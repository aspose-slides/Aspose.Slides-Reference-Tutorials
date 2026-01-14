---
date: '2026-01-14'
description: Leer hoe je een diagram naar Excel exporteert met Aspose.Slides voor
  Java en een taartdiagramdia aan presentaties toevoegt. Stapsgewijze handleiding
  met code.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Grafiek exporteren naar Excel met Aspose.Slides Java
url: /nl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportgrafiek naar Excel met Aspose.Slides voor Java

**Beheers data‑gedreven visualisatietechnieken met Aspose.Slides voor Java**

In het huidige data‑gedreven landschap maakt de mogelijkheid om **export chart to excel** direct vanuit uw Java‑applicatie statische PowerPoint‑visualisaties om te zetten in herbruikbare, analyseerbare datasets. Of u nu rapporten moet genereren, analytics‑pijplijnen moet voeden, of simpelweg zakelijke gebruikers de grafiekgegevens in Excel wilt laten bewerken, Aspose.Slides maakt het eenvoudig. Deze tutorial leidt u door het maken van een grafiek, het toevoegen van een taartgrafiek‑dia en het exporteren van die grafiekgegevens naar een Excel‑werkmap.

**Wat u zult leren:**
- Presentatiebestanden moeiteloos laden en manipuleren
- **Add pie chart slide** en andere grafiektype toevoegen aan uw dia's
- **Export chart to excel** (excel genereren vanuit grafiek) voor downstream‑analyse
- Stel een extern werkmappad in om **embed chart in presentation** te koppelen en de gegevens gesynchroniseerd te houden

Laten we beginnen!

## Snelle antwoorden
- **Wat is het primaire doel?** Grafiekgegevens exporteren van een PowerPoint‑dia naar een Excel‑bestand.  
- **Welke bibliotheekversie is vereist?** Aspose.Slides for Java 25.4 of later.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik een taartgrafiek‑dia toevoegen?** Ja – de tutorial laat zien hoe u een Pie‑grafiek toevoegt.  
- **Is Java 16 minimaal?** Ja, JDK 16 of hoger wordt aanbevolen.

## Hoe exporteer je een grafiek naar Excel met Aspose.Slides?
Grafiekgegevens exporteren naar Excel is net zo eenvoudig als een presentatie laden, een grafiek maken en vervolgens de werkmap‑stroom van de grafiek naar een bestand schrijven. De onderstaande stappen begeleiden u door het volledige proces, van projectconfiguratie tot eindverificatie.

## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende klaar heeft:

### Vereiste bibliotheken en versies
- **Aspose.Slides for Java** versie 25.4 of later

### Vereisten voor omgeving
- Java Development Kit (JDK) 16 of hoger
- Een code‑editor of IDE zoals IntelliJ IDEA of Eclipse

### Kennisvereisten
- Basisvaardigheden in Java‑programmeren
- Bekendheid met Maven‑ of Gradle‑buildsystemen

## Aspose.Slides voor Java instellen
Om Aspose.Slides te gebruiken, voegt u het toe aan uw project via Maven of Gradle.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

U kunt ook [de nieuwste versie direct downloaden](https://releases.aspose.com/slides/java/).

### Stappen voor licentie‑acquisitie
Aspose.Slides biedt een gratis proeflicentie om de volledige mogelijkheden te verkennen. U kunt ook een tijdelijke licentie aanvragen of er een kopen voor langdurig gebruik. Volg deze stappen:

1. Bezoek de [Aspose Purchase‑pagina](https://purchase.aspose.com/buy) om uw licentie te verkrijgen.  
2. Voor een gratis proefversie, download van [Releases](https://releases.aspose.com/slides/java/).  
3. Vraag een tijdelijke licentie aan [hier](https://purchase.aspose.com/temporary-license/).

Zodra u het licentiebestand heeft, initialiseert u het in uw Java‑applicatie:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Implementatie‑gids

### Functie 1: Presentatie laden
Het laden van een presentatie is de eerste stap in elke manipulatie‑taak.

#### Overzicht
Deze functie toont hoe u een bestaand PowerPoint‑bestand laadt met Aspose.Slides voor Java.

#### Stapsgewijze implementatie
**Presentatie laden**
```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```
**Uitleg:**  
- `Presentation` wordt geïnitialiseerd met het pad naar uw `.pptx`‑bestand.  
- Disposeer altijd het `Presentation`‑object om native bronnen vrij te geven.

### Functie 2: Taartgrafiek‑dia toevoegen
Het toevoegen van een grafiek kan de datavisualisatie aanzienlijk verbeteren, en veel ontwikkelaars vragen **how to add chart slide** in Java.

#### Overzicht
Deze functie laat zien hoe u een **pie chart slide** (het klassieke “add pie chart slide” scenario) toevoegt aan de eerste dia van een presentatie.

#### Stapsgewijze implementatie
**Taartgrafiek toevoegen**
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Uitleg:**  
- `addChart` voegt een Pie‑grafiek in.  
- De parameters definiëren het grafiektype en de positie/grootte op de dia.

### Functie 3: Excel genereren vanuit grafiek
Het exporteren van de grafiekgegevens stelt u in staat **generate excel from chart** voor diepere analyse.

#### Overzicht
Deze functie demonstreert het exporteren van grafiekgegevens van een presentatie naar een externe Excel‑werkmap.

#### Stapsgewijze implementatie
**Gegevens exporteren**
```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Uitleg:**  
- `readWorkbookStream` haalt de werkmapgegevens van de grafiek op.  
- De byte‑array wordt naar een `.xlsx`‑bestand geschreven met `FileOutputStream`.

### Functie 4: Grafiek insluiten in presentatie met externe werkmap
Het koppelen van een grafiek aan een externe werkmap helpt u **embed chart in presentation** en houdt de gegevens gesynchroniseerd.

#### Overzicht
Deze functie toont het instellen van een extern werkmappad zodat de grafiek direct vanuit Excel kan lezen/schrijven.

#### Stapsgewijze implementatie
**Extern werkmappad instellen**
```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```
**Uitleg:**  
- `setExternalWorkbook` koppelt de grafiek aan een Excel‑bestand, waardoor dynamische updates mogelijk zijn zonder de dia opnieuw te bouwen.

## Praktische toepassingen
Aspose.Slides biedt veelzijdige oplossingen voor verschillende scenario's:

1. **Business‑rapporten:** Maak gedetailleerde rapporten met grafieken direct vanuit Java‑applicaties.  
2. **Academische presentaties:** Versterk lezingen met interactieve taartgrafiek‑dia's.  
3. **Financiële analyse:** **Export chart to excel** voor diepgaande financiële modellering.  
4. **Marketing‑analyse:** Visualiseer campagneresultaten en **generate excel from chart** voor het analyse‑team.

## Veelgestelde vragen

**V: Kan ik deze aanpak gebruiken met andere grafiektype (bijv. Bar, Line)?**  
A: Absoluut. Vervang `ChartType.Pie` door een andere `ChartType`‑enumwaarde.

**V: Heb ik een aparte Excel‑bibliotheek nodig om het geëxporteerde bestand te lezen?**  
A: Nee. Het geëxporteerde `.xlsx`‑bestand is een standaard Excel‑werkmap die met elke spreadsheet‑applicatie geopend kan worden.

**V: Hoe beïnvloedt de externe werkmap de dia‑grootte?**  
A: Het koppelen aan een externe werkmap vergroot de PPTX‑bestandsgrootte niet significant; de grafiek verwijst tijdens runtime naar de werkmap.

**V: Is het mogelijk om de Excel‑gegevens bij te werken en de dia automatisch de wijzigingen te laten weergeven?**  
A: Ja. Na het aanroepen van `setExternalWorkbook` worden alle wijzigingen die in de werkmap zijn opgeslagen, weergegeven de volgende keer dat de presentatie wordt geopend.

**V: Wat als ik meerdere grafieken uit dezelfde presentatie moet exporteren?**  
A: Itereer over de grafiekcollectie van elke dia, roep `readWorkbookStream()` aan voor elk, en schrijf naar afzonderlijke werkmapbestanden.

---

**Laatst bijgewerkt:** 2026-01-14  
**Getest met:** Aspose.Slides 25.4 for Java  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}