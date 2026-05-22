---
date: '2026-03-15'
description: Lär dig hur du lägger till ett grupperat stapeldiagram i en PowerPoint-bild
  med Aspose.Slides för Java, inklusive steg för att lägga till diagrammet på bilden
  och skapa PowerPoint-bilder i Java på ett effektivt sätt.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Lägg till ett grupperat kolumndiagram i PPT med Aspose.Slides Java
url: /sv/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

. Eg "**`NullPointerException` on `getSlides()`**" translate to "**`NullPointerException` på `getSlides()`**". "Ensure the `Presentation` object is successfully instantiated before accessing slides." translate.

Similarly other rows.

Also FAQ: translate Q and A.

Make sure to keep markdown formatting.

Let's craft translation.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Lägg till stapeldiagram med grupperade kolumner i PPT med Aspose.Slides Java

## Introduktion
I den här guiden kommer du **lägga till ett stapeldiagram med grupperade kolumner** i en PowerPoint‑presentation programatiskt med Aspose.Slides för Java. Oavsett om du bygger affärsrapporter, utbildningspresentationer eller marknadsförings‑decks, sparar automatisering av diagramskapande tid och garanterar konsekvens. Vi går igenom hur du ställer in biblioteket, skapar en bild, lägger till diagrammet, tillämpar linjestilar och rundade hörn, och slutligen sparar filen. När du är klar kommer du att känna dig bekväm med hela arbetsflödet för att **lägga till diagram på en bild** och även **skapa PowerPoint‑bilder med Java**‑baserade lösningar.

### Snabba svar
- **Vilken är huvudklassen för att börja?** `Presentation`
- **Vilken diagramtyp används?** `ChartType.ClusteredColumn`
- **Hur aktiverar du rundade hörn?** `chart.setRoundedCorners(true);`
- **Vilket format rekommenderas för sparning?** `SaveFormat.Pptx`
- **Behöver jag en licens för utveckling?** En gratis provversion fungerar för testning; en köpt licens krävs för produktion.

## Vad är ett stapeldiagram med grupperade kolumner?
Ett stapeldiagram med grupperade kolumner grupperar flera dataserier sida‑vid‑sida för varje kategori, vilket gör det idealiskt för att jämföra värden mellan olika grupper. Aspose.Slides låter dig generera denna diagramtyp helt i kod utan att öppna PowerPoint.

## Varför använda Aspose.Slides för Java för att lägga till stapeldiagram med grupperade kolumner?
- **Full automatisering** – Ingen manuell UI‑interaktion krävs.  
- **Plattformsoberoende** – Fungerar på alla OS som stödjer Java.  
- **Rik formatering** – Kontrollera linjestilar, fyllningar, rundade hörn och mer.  
- **Inga COM‑beroenden** – Till skillnad från Office Interop kör den säkert på servrar.

## Förutsättningar
- **Aspose.Slides för Java** (v25.4 eller nyare)  
- **JDK 16** (eller senare)  
- En IDE såsom IntelliJ IDEA, Eclipse eller NetBeans  

## Installera Aspose.Slides för Java
Du kan lägga till biblioteket via Maven, Gradle eller en direkt nedladdning.

### Använd Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Använd Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Gratis provversion** – Testa alla funktioner utan tidsbegränsning.  
- **Tillfällig licens** – Begär en från Aspose‑portalen för fullständig funktionsutvärdering.  
- **Köp** – Skaffa en permanent licens för produktionsbruk.

## Implementeringsguide

### Skapa en presentation och lägga till en bild
#### Översikt
Först skapar vi ett nytt `Presentation`‑objekt och hämtar standardbilden som medföljer en ny fil.

#### Steg‑för‑steg
**1. Initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```

**2. Åtkomst till den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```

### Lägga till ett diagram på en bild
#### Översikt
Nu bäddar vi in ett **stapeldiagram med grupperade kolumner** i den bild vi just förberett.

#### Steg‑för‑steg
**1. Initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```

**2. Åtkomst till den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Lägg till ett stapeldiagram med grupperade kolumner**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```

### Formatera diagrammets linjestil och sätta rundade hörn
#### Översikt
Förbättra det visuella intrycket genom att tillämpa en solid linjefyllning, en enkel linjestil och rundade hörn.

#### Steg‑för‑steg
**1. Initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```

**2. Åtkomst till den första bilden**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Lägg till ett stapeldiagram med grupperade kolumner**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Ställ in linjeformat till solid fyllningstyp**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Tillämpa enkel linjestil**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Aktivera rundade hörn för diagramområdet**  
```java
chart.setRoundedCorners(true);
```

**7. Frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```

### Spara en presentation
#### Översikt
Till sist skriver vi presentationen till disk i PPTX‑format.

#### Steg‑för‑steg
**1. Initiera Presentation‑objektet**  
```java
Presentation presentation = new Presentation();
```

**2. Definiera utdata‑katalog och filnamn**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Spara presentationen i PPTX‑format**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Frigör resurser**  
```java
if (presentation != null) presentation.dispose();
```

## Praktiska tillämpningar
- **Affärsrapporter** – Automatisera kvartalsvisa finansiella decks med dynamiska diagram.  
- **Utbildningsmaterial** – Generera föreläsningsbilder som hämtar data från en databas.  
- **Marknadsföringspresentationer** – Visualisera produkttrender med polerade diagram.

## Prestandaöverväganden
- **Resurshantering** – Anropa alltid `dispose()` eller använd try‑with‑resources.  
- **Minnesoptimering** – Bearbeta stora datamängder i mindre batchar.  
- **Bästa praxis** – Föredra oföränderliga datastrukturer för diagramserier när det är möjligt.

## Vanliga problem och lösningar
| Problem | Lösning |
|-------|----------|
| **`NullPointerException` på `getSlides()`** | Säkerställ att `Presentation`‑objektet har skapats korrekt innan du åtkommer till bilder. |
| **Diagrammet visas inte** | Kontrollera att diagrammets dimensioner (x, y, bredd, höjd) ligger inom bildens gränser. |
| **Licensen har inte tillämpats** | Läs in din licensfil innan du skapar `Presentation`‑objektet: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Vanliga frågor

**Q: Hur lägger jag till olika typer av diagram med Aspose.Slides?**  
A: Byt ut `ChartType.ClusteredColumn` mot någon annan enum‑värde såsom `ChartType.Pie`, `ChartType.Line` eller `ChartType.Bar`.

**Q: Vad gör jag om jag får kompileringsfel?**  
A: Dubbelkolla att du använder JDK 16 eller senare och att Maven/Gradle‑beroendet matchar versionen som visas ovan.

**Q: Kan jag fylla diagrammet med data från en databas?**  
A: Ja. Åtkom diagrammets `getChartData()`‑samling, skapa serier och kategorier, och fyll dem med värden som hämtas vid körning.

**Q: Hur kan jag förbättra prestandan för mycket stora presentationer?**  
A: Dela upp arbetet i flera `Presentation`‑instanser, återanvänd diagrammallar och frigör alltid objekt så snart de är klara.

## Slutsats
Du har nu ett komplett, end‑to‑end‑recept för att **lägga till ett stapeldiagram med grupperade kolumner** i en PowerPoint‑bild med Aspose.Slides för Java. Experimentera med andra diagramtyper, bind live‑datakällor och integrera denna logik i större rapporteringspipeline för att automatisera ditt presentationsarbetsflöde.

---

**Senast uppdaterad:** 2026-03-15  
**Testad med:** Aspose.Slides 25.4 för Java (JDK 16)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}