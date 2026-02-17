---
date: '2026-02-17'
description: Lär dig hur du lägger till cirkeldiagram i PowerPoint-presentationer
  med Aspose.Slides för Java. Följ den här steg‑för‑steg‑guiden för att skapa och
  anpassa professionella cirkeldiagram.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Hur man lägger till ett cirkeldiagram i PowerPoint med Aspose.Slides för Java
url: /sv/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa och anpassa pajdiagram i PowerPoint med Aspose.Slides för Java

## Introduction

Kämpar du med att visualisera data effektivt i dina PowerPoint‑presentationer? **Att lägga till ett pajdiagram PowerPoint**‑bildspel kan omedelbart förvandla råa siffror till en tydlig visuell berättelse. Med Aspose.Slides för Java kan du programatiskt **lägga till pajdiagram PowerPoint**‑filer, vilket ger dig full kontroll över design och data utan att någonsin öppna PowerPoint manuellt. I den här handledningen går vi igenom hela processen – från att konfigurera biblioteket till att anpassa enskilda datapunkter – så att du kan leverera polerade, datadrivna bilder på några minuter.

### Quick Answers
- **Vilket bibliotek behöver jag?** Aspose.Slides för Java (senaste versionen).  
- **Kan jag skapa ett diagram utan att PowerPoint är installerat?** Ja, API‑et fungerar helt offline.  
- **Vilken Java‑version krävs?** JDK 16 eller senare rekommenderas.  
- **Hur ändrar jag färgen på en skiva?** Använd metoderna `setFillType` och `setSolidFillColor` på datapunkten.  
- **Är en licens obligatorisk?** En provversion fungerar för utveckling; en permanent licens tar bort utvärderingsgränserna.

### What You’ll Learn
- Hur du **lägger till pajdiagram PowerPoint** programatiskt med Java.  
- Sätt att anpassa skivexplosion, färger och andra visuella egenskaper.  
- Bästa praxis för resurshantering och prestanda när du hanterar stora presentationer.

## Why add pie chart PowerPoint using Aspose.Slides for Java?
Att bädda in ett pajdiagram direkt från kod låter dig generera aktuella rapporter, automatisera månatliga instrumentpaneler eller skapa personliga bildspel i farten. Det eliminerar manuella kopierings‑ och klistringsfel, säkerställer konsistens över presentationer och integreras smidigt med befintliga Java‑back‑ends.

## Prerequisites

Innan du börjar, se till att du har:

- **Aspose.Slides för Java‑biblioteket** – handledningen refererar till version 25.4 (den senaste utgåvan vid skrivtillfället).  
- En kompatibel **Java Development Kit (JDK)** – JDK 16+ föredras.  
- Grundläggande kunskap om **Maven** eller **Gradle** för beroendehantering.  

## Setting Up Aspose.Slides for Java

För att komma igång, inkludera Aspose.Slides‑biblioteket i ditt projekt.

### Maven
Lägg till detta beroende i din `pom.xml`‑fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inkludera följande i din `build.gradle`‑fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativt kan du ladda ner den senaste versionen direkt från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensing
För att använda Aspose.Slides utan begränsningar:

- Börja med en **gratis provperiod** för att utvärdera API‑et.  
- Begär en **tillfällig licens** för förlängd testning på sidan [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Köp ett fullständigt abonnemang via [Purchase page](https://purchase.aspose.com/buy).

## How to add pie chart PowerPoint using Aspose.Slides for Java

Nedan följer en steg‑för‑steg‑guide som visar exakt hur du skapar och anpassar ett pajdiagram.

### Step 1: Initialize the Presentation
Först, skapa ett nytt `Presentation`‑objekt. Detta representerar en tom PowerPoint‑fil.
```java
Presentation pres = new Presentation();
```

### Step 2: Add the Pie Chart
Infoga ett pajdiagram på den första bilden. Koordinaterna (50, 50) och storleken (600 × 400) fungerar bra för en standard 16:9‑bild.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Step 3: Save the Presentation
Skriv presentationen till disk. Ersätt `YOUR_OUTPUT_DIRECTORY` med mappen där du vill spara filen.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Step 4: Clean Up Resources
Frigör `Presentation`‑objektet för att släppa inhemska resurser.
```java
if (pres != null) pres.dispose();
```

## Customizing Data Point Explosion and Color

Att anpassa enskilda skivor gör ditt diagram lättare att läsa, särskilt när du vill framhäva ett specifikt värde.

### Step 1: Load an Existing Presentation (or reuse the one you just created)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Step 2: Access the Chart and Target Data Point
Här hämtar vi den andra datapunkten (index 1) från den första serien.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Step 3: Apply Explosion and Color
Separera skivan visuellt och ändra dess fyllningsfärg till blå.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Step 4: Save and Dispose
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Practical Applications
- **Försäljningsrapporter:** Markera bäst‑säljande produkter med exploderade skivor.  
- **Budgetanalys:** Tilldela olika färger till avdelningar för snabb visuell jämförelse.  
- **Utbildningsbilder:** Dela upp komplexa koncept i lättsmälta diagramsegment.

## Performance Considerations
- **Dispose‑objekt** omedelbart för att undvika minnesläckor, särskilt när du genererar många bilder i en loop.  
- **Övervaka heap‑användning** för stora presentationer; överväg att strömma utdata med `Save`‑överladdningar som accepterar `OutputStream`.  
- Håll dig till **JDK 16+** för att dra nytta av de senaste förbättringarna i skräpsamlingen.

## Conclusion
Du har nu ett komplett, produktionsklart arbetsflöde för att **lägga till pajdiagram PowerPoint**‑filer med Aspose.Slides för Java. Experimentera med olika explosionsavstånd, färger och dataset för att matcha ditt varumärke. När du är redo, utforska andra diagramtyper – stapel, linje eller spridning – för att bygga en fullständig analys‑instrumentpanel i PowerPoint.

## FAQ Section
1. **Vad är den främsta fördelen med att använda Aspose.Slides för Java?**  
   - Det förenklar skapandet och manipulationen av PowerPoint‑filer programatiskt och erbjuder ett brett utbud av funktioner.  
2. **Kan jag anpassa andra diagramtyper med Aspose.Slides?**  
   - Absolut! Aspose.Slides stöder olika diagramtyper såsom stapel-, linje‑ och spridningsdiagram.  
3. **Hur hanterar jag flera bilder när jag skapar diagram?**  
   - Åtkomst till varje bild via index med `get_Item()`‑metoden för att applicera ändringar på olika bilder.  
4. **Vad gör jag om mitt pajdiagram inte visas korrekt efter anpassning?**  
   - Verifiera koordinaterna och dimensionerna som används i `addChart()`, så att de passar in i din bildlayout.  
5. **Var kan jag hitta mer avancerade funktioner för Aspose.Slides?**  
   - Utforska [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) för att lära dig om ytterligare funktioner och alternativ.

## Resources
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}