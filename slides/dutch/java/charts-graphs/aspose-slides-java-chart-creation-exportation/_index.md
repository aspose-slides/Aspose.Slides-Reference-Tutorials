---
date: '2026-02-09'
description: Leer hoe je een grafiek maakt en een grafiek exporteert naar Excel met
  Aspose.Slides voor Java. Beheers gegevensvisualisatie, zakelijke rapportdia’s en
  het genereren van werkbladen.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Hoe maak je een grafiek met Aspose.Slides Java
url: /nl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je een diagram met Aspose.Slides voor Java

**Beheers data‑visualisatietechnieken met Aspose.Slides voor Java**

In het huidige data‑gedreven landschap is *how to create chart* programmatisch een vaardigheid die ruwe cijfers kan omzetten in overtuigende visuele verhalen. Of je nu een business‑rapport‑slide‑deck bouwt of een interactief analytics‑dashboard, Aspose.Slides voor Java geeft je de mogelijkheid om diagrammen direct vanuit je code te genereren, aanpassen en exporteren. In deze tutorial leer je hoe je diagramobjecten maakt, diagramgegevens exporteert naar Excel en diagrammen koppelt aan externe werkboeken voor naadloos databeheer.

## Quick Answers
- **Welke bibliotheek is nodig?** Aspose.Slides for Java (v25.4+).  
- **Kan ik diagramgegevens exporteren naar Excel?** Ja – gebruik `readWorkbookStream()` en schrijf de bytes naar een *.xlsx* bestand.  
- **Welke Java‑versie is vereist?** JDK 16 of hoger.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor evaluatie; een permanente licentie is vereist voor productie.  
- **Welk diagramtype wordt gedemonstreerd?** Een taartdiagram, maar dezelfde aanpak werkt voor staaf-, lijn‑ en andere diagramtypen.

## Wat is Aspose.Slides voor Java?
Aspose.Slides for Java is een pure‑Java API die ontwikkelaars in staat stelt PowerPoint‑presentaties te maken, bewerken en converteren zonder Microsoft Office. Het ondersteunt een volledig scala aan diagramtypen, databinding en exportmogelijkheden, waardoor het ideaal is voor **data visualization java**‑projecten.

## Waarom Aspose.Slides gebruiken om diagram te maken en diagram te exporteren naar Excel?
- **Geen Office‑installatie** – werkt op elke server of cloud‑omgeving.  
- **Rijke diagrambibliotheek** – tientallen diagramtypen en volledige stijlcontrole.  
- **Directe Excel‑export** – genereer een extern werkboek voor downstream‑analyse.  
- **Prestaties‑gericht** – lage geheugengebruik en snelle verwerking voor grote presentaties.

## Vereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

### Vereiste bibliotheken en versies
- **Aspose.Slides for Java** versie 25.4 of later

### Omgevingsinstellingen
- Java Development Kit (JDK) 16 of hoger  
- Een IDE zoals IntelliJ IDEA of Eclipse (of elke teksteditor die je verkiest)

### Kennisvereisten
- Basis Java‑programmeervaardigheden  
- Vertrouwdheid met Maven of Gradle build‑tools

## Aspose.Slides voor Java instellen
Voeg de bibliotheek toe aan je project met je favoriete build‑systeem.

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

Of download de nieuwste versie rechtstreeks via [download the latest version directly](https://releases.aspose.com/slides/java/).

### Stappen voor licentie‑acquisitie
Aspose.Slides biedt een gratis proeflicentie om de volledige mogelijkheden te verkennen. Je kunt ook een tijdelijke licentie aanvragen of er een kopen voor uitgebreid gebruik. Volg deze stappen:

1. Bezoek de [Aspose Purchase page](https://purchase.aspose.com/buy) om je licentie te verkrijgen.  
2. Voor een gratis proefversie, download van [Releases](https://releases.aspose.com/slides/java/).  
3. Vraag een tijdelijke licentie aan [hier](https://purchase.aspose.com/temporary-license/).

Zodra je het licentiebestand hebt, initialiseert je het in je Java‑applicatie:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Stapsgewijze handleiding

### Hoe diagram maken – Een presentatie laden
Het laden van een bestaande PowerPoint‑file is de eerste stap voordat je diagrammen kunt toevoegen of wijzigen.

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
- `Presentation` vertegenwoordigt het PowerPoint‑bestand.  
- Roep altijd `dispose()` aan om native resources vrij te geven.

### Hoe diagram maken – Een taartdiagram toevoegen aan een dia
Nu voegen we een taartdiagram in, perfect om proportionele data te tonen.

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
- `addChart` voegt het diagram toe aan de eerste dia.  
- De parameters definiëren diagramtype, X/Y‑positie en grootte.

### Hoe diagram exporteren naar Excel – Diagramgegevens exporteren
Diagramgegevens exporteren stelt analisten in staat de cijfers in Excel te bewerken, waardoor diepere inzichten mogelijk zijn.

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
- `readWorkbookStream()` haalt het onderliggende Excel‑werkboek van het diagram op als een byte‑array.  
- De byte‑array wordt geschreven naar `externalWorkbook1.xlsx`, waardoor je een kant‑klaar Excel‑bestand krijgt.

### Hoe diagram maken – Extern werkboek instellen voor dynamische gegevens
Een diagram koppelen aan een extern werkboek maakt het mogelijk het diagram bij te werken door simpelweg het Excel‑bestand te bewerken.

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
- `setExternalWorkbook` bindt het diagram aan het opgegeven Excel‑bestand, waardoor live‑databijwerkingen mogelijk zijn zonder de dia opnieuw te bouwen.

## Praktische toepassingen
Aspose.Slides biedt veelzijdige oplossingen voor diverse real‑world scenario’s:

1. **Business Report Slides:** Genereer automatisch kwartaal‑prestatie‑diagrammen vanuit je datapijplijnen.  
2. **Academic Presentations:** Zet onderzoeksgegevens om in duidelijke visualisaties zonder handmatig diagrammen maken.  
3. **Financial Analysis:** Exporteer diagramgegevens naar Excel zodat auditors de cijfers kunnen verifiëren.  
4. **Marketing Analytics:** Visualiseer campagnemetingen en deel bewerkbare werkboeken met belanghebbenden.

## Veelvoorkomende problemen & probleemoplossing
- **`FileNotFoundException`** – Controleer of `dataDir` naar een geldige map wijst en of het uitvoerpad schrijfbaar is.  
- **Memory leaks** – Roep altijd `pres.dispose()` aan in een `finally`‑blok om native resources vrij te geven.  
- **Chart not appearing** – Zorg ervoor dat de dia‑index (`get_Item(0)`) overeenkomt met een dia die daadwerkelijk bestaat.

## Veelgestelde vragen

**Q: Kan ik een ander diagramtype (bijv. Staaf, Lijn) gebruiken met dezelfde code?**  
A: Ja. Vervang `ChartType.Pie` door een andere `ChartType`‑enumwaarde zoals `ChartType.Bar` of `ChartType.Line`.

**Q: Is het mogelijk om het externe werkboek bij te werken nadat het diagram is gemaakt?**  
A: Absoluut. Pas het Excel‑bestand direct aan; het gekoppelde diagram zal de wijzigingen weergeven de volgende keer dat de presentatie wordt geopend.

**Q: Heb ik een aparte licentie nodig voor de Excel‑exportfunctie?**  
A: Nee. De Excel‑exportfunctie is inbegrepen in de standaard Aspose.Slides for Java‑licentie.

**Q: Welke Java‑versies worden ondersteund?**  
A: Aspose.Slides for Java ondersteunt JDK 16 en nieuwer; eerdere versies kunnen werken maar worden niet officieel getest.

**Q: Hoe kan ik het gegenereerde Excel‑werkboek in het PPTX‑bestand insluiten?**  
A: Gebruik `chart.getChartData().setExternalWorkbook(null)` om het werkboek in te sluiten, of behoud de externe koppeling voor dynamische updates.

---

**Laatst bijgewerkt:** 2026-02-09  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}