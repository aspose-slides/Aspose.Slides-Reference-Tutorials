---
date: '2026-09-02'
description: Lär dig hur du lägger till ett stapeldiagram med grupperade kolumner
  i en PowerPoint-bildruta med Aspose.Slides för Java, inklusive skapande av diagram,
  formatering och sparande som PPTX.
keywords:
- add clustered column chart
- save powerpoint as pptx
- powerpoint chart formatting
- add chart to slide
- java create chart slide
lastmod: '2026-09-02'
og_description: Lär dig hur du lägger till ett stapeldiagram med grupperade kolumner
  i en PowerPoint-bildruta med Aspose.Slides för Java, inklusive skapande av diagram,
  formatering och sparande som PPTX.
og_image_alt: Guide showing how to add a clustered column chart to a PowerPoint slide
  with Aspose.Slides for Java
og_title: Lägg till stapeldiagram med grupperade kolumner i PPT med Aspose.Slides
  Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to add clustered column chart to a PowerPoint slide using
    Aspose.Slides for Java, covering chart creation, formatting, and saving as PPTX.
  headline: Add clustered column chart to PPT using Aspose.Slides Java
  type: TechArticle
- questions:
  - answer: Replace `ChartType.ClusteredColumn` with any other enum value such as
      `ChartType.Pie`, `ChartType.Line`, or `ChartType.Bar`.
    question: How do I add different types of charts using Aspose.Slides?
  - answer: Double‑check that you’re using JDK 16 or newer and that the Maven/Gradle
      dependency version matches the library you downloaded.
    question: What should I do if I encounter compilation errors?
  - answer: Yes. Access the chart’s `getChartData()` collection, create series and
      categories, and fill them with values retrieved at runtime.
    question: Can I populate the chart with data from a database?
  - answer: Split the work into multiple `Presentation` instances, reuse chart templates,
      and always dispose of objects promptly.
    question: How can I improve performance for very large presentations?
  type: FAQPage
tags:
- add clustered column chart
- Aspose.Slides
- Java PowerPoint automation
- chart formatting
- PPTX
title: Lägg till stapeldiagram med grupperade kolumner i PPT med Aspose.Slides Java
url: /sv/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till stapeldiagram med grupperade kolumner i PPT med Aspose.Slides Java

## Introduktion
I den här guiden kommer du att **lägga till ett stapeldiagram med grupperade kolumner** i en PowerPoint-presentation programatiskt med Aspose.Slides för Java. Oavsett om du bygger affärsrapporter, utbildningspresentationer eller marknadsföringspresentationer, sparar automatisering av diagramskapande tid och garanterar konsekvens. Vi går igenom hur du installerar biblioteket, skapar en bild, lägger till diagrammet, applicerar linjestilar och rundade hörn, och slutligen sparar filen som PPTX. I slutet kommer du att känna dig bekväm med hela arbetsflödet för att **lägga till diagram på bild** och även **skapa PowerPoint‑bild Java**‑baserade lösningar.

### Snabba svar
- **Vilken är den primära klassen att börja med?** `Presentation`
- **Vilken diagramtyp används?** `ChartType.ClusteredColumn`
- **Hur aktiverar du rundade hörn?** `chart.setRoundedCorners(true);`
- **Vilket format rekommenderas för sparande?** `SaveFormat.Pptx`
- **Behöver jag en licens för utveckling?** A free trial works for testing; a purchased license is required for production.

## Vad är ett stapeldiagram med grupperade kolumner?
Ett stapeldiagram med grupperade kolumner grupperar flera dataserier sida‑vid‑sida för varje kategori, vilket gör det idealiskt för att jämföra värden över olika grupper. Aspose.Slides låter dig generera denna diagramtyp helt i kod utan att öppna PowerPoint, och du kan anpassa färger, markörer och axelalternativ för att matcha ditt varumärke.

## Varför använda Aspose.Slides för Java för att lägga till stapeldiagram med grupperade kolumner?
Du kan automatisera hela diagram‑skapandepipelinen utan UI‑interaktion, vilket är avgörande för server‑sidig rapportgenerering. Aspose.Slides körs på alla Java‑kompatibla operativsystem, hanterar presentationer med upp till 500 bilder utan att ladda dem helt, och erbjuder över 50 inbyggda diagramstilar. Detta tar bort COM‑beroenden och låter dig bädda in högkvalitativa visuella element direkt från Java.

## Förutsättningar
- **Aspose.Slides for Java** (v25.4 eller nyare) – stöder 50+ diagramtyper och 30+ bildformat.  
- **JDK 16** (eller senare) – krävs för de senaste språkfunktionerna.  
- En IDE såsom IntelliJ IDEA, Eclipse eller NetBeans.  

## Konfigurera Aspose.Slides för Java
Du kan lägga till biblioteket via Maven, Gradle eller en direkt nedladdning.

### Använda Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Använda Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Free trial** – testa alla funktioner utan tidsgräns.  
- **Temporary license** – begär en från Aspose‑portalen för fullständig funktionsutvärdering.  
- **Purchase** – skaffa en permanent licens för produktionsanvändning.

## Implementeringsguide

### Skapa en presentation och lägga till en bild
`Presentation` är det centrala Aspose.Slides‑objektet som representerar en PowerPoint‑fil i minnet. Efter att du har skapat en instans kan du komma åt, ändra eller lägga till bilder.

#### Översikt
Först skapar vi ett nytt `Presentation`‑objekt och hämtar standardbilden som medföljer en ny fil.

#### Steg‑för‑steg
**1. initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```  

**2. hämta den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```  

### Lägga till ett diagram på en bild
`IChart` är gränssnittet som representerar alla diagram som läggs till på en bild. Genom att ange `ChartType.ClusteredColumn` talar du om för Aspose.Slides att rendera ett stapeldiagram med grupperade kolumner.

#### Översikt
Nu bäddar vi in ett **stapeldiagram med grupperade kolumner** i bilden vi just förberedde.

#### Steg‑för‑steg
**1. initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```  

**2. hämta den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. lägg till ett stapeldiagram med grupperade kolumner**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```  

### Formatera diagrammets linjestil och sätta rundade hörn
`Chart` tillhandahåller en metod `getChartFormat()` som returnerar ett `ChartFormat`‑objekt, vilket du kan använda för att justera linjefyllningar, streckstilar och hörnrundning.

`Chart` är den konkreta klassen som implementerar `IChart` och representerar ett diagramobjekt på en bild.

#### Översikt
Förbättra det visuella intrycket genom att applicera en solid linjefyllning, en enkel linjestil och rundade hörn.

#### Steg‑för‑steg
**1. initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```  

**2. hämta den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```  

**3. lägg till ett stapeldiagram med grupperade kolumner**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```  

**4. sätt linjeformat till solid fyllningstyp**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```  

**5. applicera enkel linjestil**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```  

**6. aktivera rundade hörn för diagramområdet**  
```java
chart.setRoundedCorners(true);
```  

**7. frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```  

### Spara en presentation
`SaveFormat.Pptx` är det rekommenderade formatet för moderna PowerPoint‑filer, vilket bevarar all diagramformatering och möjliggör efterföljande redigering.

#### Översikt
Till sist skriver vi presentationen till disk i PPTX‑format, vilket är standarden för **spara PowerPoint som PPTX**‑operationer.

#### Steg‑för‑steg
**1. initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```  

**2. definiera utdata‑katalog och filnamn**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```  

**3. spara presentationen i PPTX‑format**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```  

**4. frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```  

## Praktiska tillämpningar
- **Business reports** – automatisera kvartalsvisa finansiella presentationer med dynamiska diagram.  
- **Educational content** – generera föreläsningsbilder som hämtar data från en databas.  
- **Marketing presentations** – visualisera produkttrender med polerade, varumärkesanpassade diagram.

## Prestandaöverväganden
- **Resource management** – anropa alltid `dispose()` eller använd try‑with‑resources för att frigöra native‑minne.  
- **Memory optimisation** – bearbeta stora datamängder i mindre batcher; Aspose.Slides kan hantera presentationer på upp till 500 MB utan full laddning.  
- **Best practices** – föredra oföränderliga datastrukturer för diagramserier när det är möjligt; detta minskar GC‑belastning och förbättrar genomströmning.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **`NullPointerException` on `getSlides()`** | Säkerställ att `Presentation`‑objektet har skapats framgångsrikt innan du får åtkomst till bilder. |
| **Chart not appearing** | Verifiera att diagrammets dimensioner (x, y, bredd, höjd) ligger inom bildens gränser och att `ChartType.ClusteredColumn` används. |
| **License not applied** | Ladda din licensfil innan du skapar `Presentation`‑objektet: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Vanliga frågor

**Q: Hur lägger jag till olika typer av diagram med Aspose.Slides?**  
A: Ersätt `ChartType.ClusteredColumn` med något annat enum‑värde såsom `ChartType.Pie`, `ChartType.Line` eller `ChartType.Bar`.

**Q: Vad ska jag göra om jag får kompileringsfel?**  
A: Dubbelkolla att du använder JDK 16 eller nyare och att Maven/Gradle‑beroendets version matchar det bibliotek du laddade ner.

**Q: Kan jag fylla diagrammet med data från en databas?**  
A: Ja. Åtkomst till diagrammets `getChartData()`‑samling, skapa serier och kategorier, och fyll dem med värden som hämtas vid körning.

**Q: Hur kan jag förbättra prestandan för mycket stora presentationer?**  
A: Dela upp arbetet i flera `Presentation`‑instanser, återanvänd diagrammallar och frigör alltid objekt omedelbart.

## Slutsats
Du har nu ett komplett, end‑to‑end‑recept för **att lägga till ett stapeldiagram med grupperade kolumner** på en PowerPoint‑bild med Aspose.Slides för Java. Experimentera med andra diagramtyper, bind live‑datakällor och integrera denna logik i större rapporteringspipelines för att automatisera ditt presentationsarbetsflöde.

---

**Senast uppdaterad:** 2026-09-02  
**Testad med:** Aspose.Slides 25.4 för Java (JDK 16)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Skapa PowerPoint‑diagram Java – Spara presentationer med diagram med Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Lägg till animation till PowerPoint‑diagram med Aspose.Slides för Java – En steg‑för‑steg‑guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}