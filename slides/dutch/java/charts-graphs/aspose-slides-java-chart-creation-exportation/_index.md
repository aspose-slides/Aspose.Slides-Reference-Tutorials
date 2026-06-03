---
date: '2026-06-03'
description: Leer hoe u een grafiek exporteert naar Excel en een grafiek maakt met
  Java met behulp van Aspose.Slides for Java. Beheers data visualization, business
  report slides en workbook generation.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Grafiek exporteren naar Excel en grafieken maken met Aspose.Slides
url: /nl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Grafiek exporteren naar Excel en grafieken maken met Aspose.Slides

**Beheers data‑visualisatietechnieken met Aspose.Slides for Java**

In het huidige data‑gedreven landschap is *export chart to excel* programmatisch een vaardigheid die ruwe cijfers kan omzetten in overtuigende visuele verhalen. Of je nu een business‑rapportpresentatie maakt of een interactieve analytics‑dashboard, Aspose.Slides for Java geeft je de mogelijkheid om grafieken te genereren, aan te passen en rechtstreeks vanuit je code te exporteren. In deze tutorial leer je hoe je grafiekobjecten maakt, grafiekgegevens exporteert naar Excel en grafieken koppelt aan externe werkmappen voor naadloos gegevensbeheer.

## Snelle antwoorden
- **Welke bibliotheek is nodig?** Aspose.Slides for Java (v25.4+).  
- **Kan ik grafiekgegevens exporteren naar Excel?** Ja – gebruik `readWorkbookStream()` en schrijf de bytes naar een *.xlsx*‑bestand.  
- **Welke Java‑versie is vereist?** JDK 16 of hoger.  
- **Heb ik een licentie nodig?** Een gratis proeflicentie werkt voor evaluatie; een permanente licentie is vereist voor productie.  
- **Welk grafiektype wordt gedemonstreerd?** Een Pie chart, maar dezelfde aanpak werkt voor Bar, Line en andere grafiektypen.

## Wat is Aspose.Slides for Java?
Aspose.Slides for Java is een pure‑Java API die ontwikkelaars in staat stelt PowerPoint‑presentaties te maken, bewerken en converteren zonder Microsoft Office. Het biedt een uitgebreide set klassen voor slide‑manipulatie, grafiekgeneratie en formaatconversie, waardoor geautomatiseerde rapportageoplossingen mogelijk zijn. Het ondersteunt **50+ chart types**, volledige databinding en directe Excel‑export, waardoor het ideaal is voor **data visualization java** projecten.

## Waarom Aspose.Slides gebruiken om een grafiek te maken en grafiek te exporteren naar Excel?
Grafiek snel en betrouwbaar exporteren naar Excel. Aspose.Slides elimineert de noodzaak voor Office‑installaties, biedt **meer dan 50 ingebouwde grafiekstijlen**, en verwerkt presentaties **tot 300 MB in minder dan 30 seconden** op standaard serverhardware. Je krijgt ook native Excel‑werkmapgeneratie, waardoor downstream‑analisten met ruwe cijfers kunnen werken zonder handmatig kopiëren‑en‑plakken.

## Voorvereisten
Voordat we beginnen, zorg ervoor dat je het volgende hebt:

### Vereiste bibliotheken en versies
- **Aspose.Slides for Java** versie 25.4 of later (ondersteunt JDK 16+)

### Omgevingsvereisten voor installatie
- Java Development Kit (JDK) 16 of hoger  
- Een IDE zoals IntelliJ IDEA of Eclipse (of elke teksteditor die je verkiest)

### Kennisvereisten
- Basis Java‑programmeervaardigheden  
- Vertrouwdheid met Maven‑ of Gradle‑buildtools

## Instellen van Aspose.Slides for Java
Voeg de bibliotheek toe aan je project met behulp van je favoriete build‑systeem.

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

Alternatief kun je [download de nieuwste versie direct](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie
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

### Hoe een grafiek te maken – Een presentatie laden
Laad een bestaand PowerPoint‑bestand voordat je grafieken kunt toevoegen of wijzigen.  
De `Presentation`‑klasse vertegenwoordigt een PowerPoint‑bestand in het geheugen en geeft toegang tot slides, vormen en grafiekobjecten.  
Laad je bestand met `new Presentation("input.pptx")`, werk vervolgens met de eerste slide via `presentation.getSlides().get_Item(0)`. Roep altijd `presentation.dispose()` aan in een `finally`‑blok om native bronnen vrij te geven.

### Hoe een grafiek te maken – Een taartgrafiek toevoegen aan een slide
Voeg een taartgrafiek in, perfect om proportionele gegevens weer te geven.  
De `IChart`‑interface is het primaire toegangspunt voor grafiekmanipulatie; `addChart` maakt een nieuwe grafiek op de doel‑slide. Geef het grafiektype (`ChartType.Pie`), X/Y‑coördinaten en breedte/hoogte op. Na creatie kun je titels, legenda en gegevensreeksen aanpassen via het `ChartData`‑object.

### Hoe grafiek te exporteren naar Excel – Grafiekgegevens exporteren
Het exporteren van grafiekgegevens stelt analisten in staat om met de cijfers in Excel te werken, waardoor diepere inzichten mogelijk worden.  
`readWorkbookStream()` retourneert de onderliggende Excel‑werkmap van de grafiek als een byte‑array. Roep `chart.getChartData().readWorkbookStream()` aan om de werkmap op te halen en schrijf deze array naar een bestand met de naam `externalWorkbook1.xlsx` met standaard Java‑I/O. Het resulterende Excel‑bestand bevat de exacte gegevens die door de grafiek worden gebruikt, klaar voor verdere analyse.

### Hoe een grafiek te maken – Externe werkmap instellen voor dynamische gegevens
Koppel een grafiek aan een externe werkmap om live gegevensupdates mogelijk te maken zonder de slide opnieuw te bouwen.  
`setExternalWorkbook()` bindt de grafiek aan een extern Excel‑bestand voor dynamische gegevensupdates. Gebruik `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` om de grafiek aan het externe bestand te koppelen. Wanneer de Excel‑werkmap wordt bewerkt, reflecteert de grafiek automatisch de wijzigingen de volgende keer dat de presentatie wordt geopend, wat dynamische rapportagescenario's ondersteunt.

## Praktische toepassingen
Aspose.Slides biedt veelzijdige oplossingen voor verschillende real‑world scenario's:

1. **Business Report Slides:** Genereer kwartaalprestatiegrafieken automatisch vanuit je datastromen.  
2. **Academic Presentations:** Zet onderzoeksgegevens om in duidelijke visualisaties zonder handmatig grafieken maken.  
3. **Financial Analysis:** Exporteer grafiekgegevens naar Excel zodat auditors de cijfers kunnen verifiëren, waardoor handmatige fouten worden verminderd.  
4. **Marketing Analytics:** Visualiseer campagnemetri­cs en deel bewerkbare werkmappen met belanghebbenden voor gezamenlijke besluitvorming.  
5. **Automated Dashboard Generation:** Combineer de grafiek‑creatie‑API met geplande taken om elke ochtend up‑to‑date slide‑decks te produceren.

## Veelvoorkomende problemen & probleemoplossing
- **`FileNotFoundException`** – Controleer of `dataDir` naar een geldige map wijst en of het uitvoerpad schrijfbaar is.  
- **Memory leaks** – Roep altijd `presentation.dispose()` aan in een `finally`‑blok om native bronnen vrij te geven.  
- **Chart not appearing** – Zorg ervoor dat de slide‑index (`get_Item(0)`) overeenkomt met een bestaande slide, en dat de afmetingen van de grafiek binnen de slide‑grenzen vallen.  
- **Excel export produces empty file** – Bevestig dat de grafiek daadwerkelijk gegevensreeksen bevat voordat `readWorkbookStream()` wordt aangeroepen.

## Veelgestelde vragen

**Q: Kan ik een ander grafiektype (bijv. Bar, Line) gebruiken met dezelfde code?**  
A: Ja. Vervang `ChartType.Pie` door een andere `ChartType`‑enumwaarde zoals `ChartType.Bar` of `ChartType.Line`.

**Q: Is het mogelijk om de externe werkmap bij te werken nadat de grafiek is gemaakt?**  
A: Absoluut. Pas het Excel‑bestand direct aan; de gekoppelde grafiek zal de wijzigingen weergeven de volgende keer dat de presentatie wordt geopend.

**Q: Heb ik een aparte licentie nodig voor de Excel‑exportfunctie?**  
A: Nee. De Excel‑exportfunctionaliteit is inbegrepen in de standaard Aspose.Slides for Java‑licentie.

**Q: Welke Java‑versies worden ondersteund?**  
A: Aspose.Slides for Java ondersteunt JDK 16 en hoger; eerdere versies kunnen werken maar zijn niet officieel getest.

**Q: Hoe kan ik de gegenereerde Excel‑werkmap in het PPTX‑bestand insluiten?**  
A: Gebruik `chart.getChartData().setExternalWorkbook(null)` om de werkmap in te sluiten, of behoud de externe link voor dynamische updates.

---

**Laatst bijgewerkt:** 2026-06-03  
**Getest met:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Auteur:** Aspose  

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

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Grafiek maken in Java met Aspose.Slides – Grafieken toevoegen & valideren](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Werkmapgegevens herstellen van PowerPoint‑grafieken met Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Hoe het gegevensbereik van een PowerPoint‑grafiek bij te werken met Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}