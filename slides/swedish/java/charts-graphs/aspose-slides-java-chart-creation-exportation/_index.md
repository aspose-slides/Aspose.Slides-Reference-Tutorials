---
date: '2026-06-03'
description: Lär dig hur du exporterar diagram till Excel och skapar diagram i Java
  med Aspose.Slides för Java. Behärska datavisualisering, affärsrapportbilder och
  generering av arbetsböcker.
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
title: Exportera diagram till Excel och skapa diagram med Aspose.Slides
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Exportera diagram till Excel och skapa diagram med Aspose.Slides

**Behärska tekniker för datavisualisering med Aspose.Slides för Java**

I dagens datadrivna landskap är *export chart to excel* programatiskt en färdighet som kan förvandla råa siffror till övertygande visuella berättelser. Oavsett om du bygger en affärsrapport‑presentation eller en interaktiv analys‑dashboard, ger Aspose.Slides för Java dig möjlighet att generera, anpassa och exportera diagram direkt från din kod. I den här handledningen lär du dig hur du skapar diagramobjekt, exporterar diagramdata till Excel och länkar diagram till externa arbetsböcker för sömlös datahantering.

## Snabba svar
- **Vilket bibliotek behövs?** Aspose.Slides for Java (v25.4+).  
- **Kan jag exportera diagramdata till Excel?** Ja – använd `readWorkbookStream()` och skriv bytes till en *.xlsx*‑fil.  
- **Vilken Java‑version krävs?** JDK 16 eller högre.  
- **Behöver jag en licens?** En gratis provlicens fungerar för utvärdering; en permanent licens krävs för produktion.  
- **Vilken diagramtyp demonstreras?** Ett cirkeldiagram, men samma metod fungerar för stapel-, linje‑ och andra diagramtyper.

## Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett rent Java‑API som låter utvecklare skapa, redigera och konvertera PowerPoint‑presentationer utan Microsoft Office. Det erbjuder ett omfattande set av klasser för bildmanipulation, diagramgenerering och formatkonvertering, vilket möjliggör automatiserade rapporteringslösningar. Det stödjer **50+ diagramtyper**, fullständig databindning och direkt Excel‑export, vilket gör det idealiskt för **data visualization java**‑projekt.

## Varför använda Aspose.Slides för att skapa diagram och exportera diagram till Excel?
Exportera diagram till Excel snabbt och pålitligt. Aspose.Slides eliminerar behovet av Office‑installationer, erbjuder **över 50 inbyggda diagramstilar** och bearbetar presentationer **upp till 300 MB på under 30 sekunder** på standard serverhårdvara. Du får också inbyggd Excel‑arbetsboksgenerering, vilket låter downstream‑analytiker arbeta med råa siffror utan manuellt kopiera‑och‑klistra.

## Förutsättningar
Innan vi dyker ner, se till att du har följande:

### Nödvändiga bibliotek och versioner
- **Aspose.Slides for Java** version 25.4 eller senare (stödjer JDK 16+)

### Miljöinställningskrav
- Java Development Kit (JDK) 16 eller högre  
- En IDE såsom IntelliJ IDEA eller Eclipse (eller någon textredigerare du föredrar)

### Kunskapsförutsättningar
- Grundläggande Java‑programmeringskunskaper  
- Bekantskap med Maven‑ eller Gradle‑byggverktyg

## Installera Aspose.Slides för Java
Lägg till biblioteket i ditt projekt med ditt föredragna byggsystem.

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

Alternativt kan du [ladda ner den senaste versionen direkt](https://releases.aspose.com/slides/java/).

### Steg för att skaffa licens
Aspose.Slides erbjuder en gratis provlicens för att utforska dess fulla funktioner. Du kan också ansöka om en tillfällig licens eller köpa en för utökad användning. Följ dessa steg:

1. Besök [Aspose Purchase page](https://purchase.aspose.com/buy) för att få din licens.  
2. För en gratis provversion, ladda ner från [Releases](https://releases.aspose.com/slides/java/).  
3. Ansök om en tillfällig licens [här](https://purchase.aspose.com/temporary-license/).

När du har licensfilen, initiera den i din Java‑applikation:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Steg‑för‑steg‑guide

### Hur man skapar diagram – Ladda en presentation
Läs in en befintlig PowerPoint‑fil innan du kan lägga till eller ändra diagram.  
Klassen `Presentation` representerar en PowerPoint‑fil i minnet och exponerar bilder, former och diagramobjekt.  
Läs in din fil med `new Presentation("input.pptx")`, arbeta sedan med den första bilden via `presentation.getSlides().get_Item(0)`. Anropa alltid `presentation.dispose()` i ett `finally`‑block för att frigöra inhemska resurser.

### Hur man skapar diagram – Lägg till ett cirkeldiagram på en bild
Infoga ett cirkeldiagram, perfekt för att visa proportionell data.  
Gränssnittet `IChart` är huvudingångspunkten för diagrammanipulation; `addChart` skapar ett nytt diagram på målbilden. Ange diagramtypen (`ChartType.Pie`), X/Y‑koordinater samt bredd/höjd. Efter skapandet kan du anpassa titlar, legend och dataserier via `ChartData`‑objektet.

### Hur man exporterar diagram till Excel – Exportera diagramdata
Att exportera diagramdata låter analytiker arbeta med siffrorna i Excel, vilket möjliggör djupare insikter.  
`readWorkbookStream()` returnerar diagrammets underliggande Excel‑arbetsbok som en byte‑array. Anropa `chart.getChartData().readWorkbookStream()` för att hämta arbetsboken och skriv denna array till en fil med namnet `externalWorkbook1.xlsx` med standard Java‑I/O. Den resulterande Excel‑filen innehåller exakt de data som diagrammet använder, redo för vidare analys.

### Hur man skapar diagram – Ställ in extern arbetsbok för dynamisk data
Länka ett diagram till en extern arbetsbok för att möjliggöra live‑datauppdateringar utan att bygga om bilden.  
`setExternalWorkbook()` binder diagrammet till en extern Excel‑fil för dynamiska datauppdateringar. Använd `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` för att binda diagrammet till den externa filen. När Excel‑arbetsboken redigeras reflekteras förändringarna automatiskt i diagrammet nästa gång presentationen öppnas, vilket stödjer dynamiska rapporteringsscenarier.

## Praktiska tillämpningar
Aspose.Slides erbjuder mångsidiga lösningar för olika verkliga scenarier:

1. **Affärsrapportslides:** Generera kvartalsvisa prestationsdiagram automatiskt från dina datapipelines.  
2. **Akademiska presentationer:** Omvandla forskningsdata till tydliga visualiseringar utan manuellt diagramarbete.  
3. **Finansiell analys:** Exportera diagramdata till Excel för revisorer att verifiera siffror, vilket minskar manuella fel.  
4. **Marknadsanalys:** Visualisera kampanjmått och dela redigerbara arbetsböcker med intressenter för samarbetsbeslut.  
5. **Automatiserad dashboard‑generering:** Kombinera diagram‑skapande‑API:t med schemalagda jobb för att producera uppdaterade bildspel varje morgon.

## Vanliga problem & felsökning
- **`FileNotFoundException`** – Verifiera att `dataDir` pekar på en giltig mapp och att utskriftsvägen är skrivbar.  
- **Minnesläckor** – Anropa alltid `presentation.dispose()` i ett `finally`‑block för att frigöra inhemska resurser.  
- **Diagram visas inte** – Säkerställ att bildindexet (`get_Item(0)`) motsvarar en befintlig bild och att diagrammets dimensioner ligger inom bildens gränser.  
- **Excel‑export skapar tom fil** – Bekräfta att diagrammet faktiskt innehåller dataserier innan du anropar `readWorkbookStream()`.

## Vanliga frågor

**Q: Kan jag använda en annan diagramtyp (t.ex. Stapel, Linje) med samma kod?**  
A: Ja. Ersätt `ChartType.Pie` med någon annan `ChartType`‑enum‑värde såsom `ChartType.Bar` eller `ChartType.Line`.

**Q: Är det möjligt att uppdatera den externa arbetsboken efter att diagrammet har skapats?**  
A: Absolut. Modifiera Excel‑filen direkt; det länkade diagrammet kommer att reflektera förändringarna nästa gång presentationen öppnas.

**Q: Behöver jag en separat licens för Excel‑exportfunktionen?**  
A: Nej. Excel‑exportfunktionen ingår i den vanliga Aspose.Slides för Java‑licensen.

**Q: Vilka Java‑versioner stöds?**  
A: Aspose.Slides för Java stödjer JDK 16 och nyare; äldre versioner kan fungera men är inte officiellt testade.

**Q: Hur kan jag bädda in den genererade Excel‑arbetsboken i PPTX‑filen?**  
A: Använd `chart.getChartData().setExternalWorkbook(null)` för att bädda in arbetsboken, eller behåll den externa länken för dynamiska uppdateringar.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

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

## Relaterade handledningar

- [Skapa diagram i Java med Aspose.Slides – Lägg till och validera diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Återställ arbetsboksdata från PowerPoint-diagram med Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Hur man uppdaterar PowerPoint-diagramdataområde med Aspose.Slides för Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}