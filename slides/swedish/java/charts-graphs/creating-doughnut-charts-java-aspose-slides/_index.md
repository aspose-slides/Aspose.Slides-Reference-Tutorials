---
date: '2026-07-27'
description: Lär dig hur du skapar en doughnut chart i Java med Aspose.Slides – en
  snabb guide för att konfigurera biblioteket, lägga till ett anpassningsbart doughnut
  chart, justera hole size och spara presentationen.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Lär dig hur du skapar en doughnut chart i Java med Aspose.Slides –
  en snabb guide för att konfigurera biblioteket, lägga till ett anpassningsbart doughnut
  chart, justera hole size och spara presentationen.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Skapa Doughnut Chart i Java – Steg‑för‑steg med Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Skapa Doughnut Chart i Java – Steg‑för‑steg med Aspose.Slides
url: /sv/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar munkdiagram i Java med Aspose.Slides för presentationer

## Introduktion
Att skapa visuellt tilltalande presentationer är avgörande för att effektivt förmedla information. **Create doughnut chart java** är ett vanligt krav när du behöver illustrera proportionell data med ett modernt utseende. I den här handledningen kommer du att lära dig hur du konfigurerar Aspose.Slides för Java, bygger ett munkdiagram, anpassar dess hålstorlek och färger, och slutligen sparar presentationsfilen. I slutet har du ett återanvändbart mönster som du kan lägga in i vilket Java‑projekt som helst som automatiskt genererar PowerPoint‑presentationer.

**Vad du kommer att lära dig:**
- Installera Aspose.Slides för Java
- Skapa och konfigurera munkdiagram i presentationer
- Justera diagrammets estetik, t.ex. hålstorlek
- Spara presentationen med ditt nya diagram

Låt oss börja med att konfigurera vår miljö!

## Snabba svar
- **Vilket bibliotek skapar munkdiagram java?** Aspose.Slides for Java.
- **Hur många kodrader behövs för ett grundläggande munkdiagram?** Ungefär 8–10 rader efter att presentationen har instansierats.
- **Kan jag ändra hålstorleken?** Ja, metoden `setHoleSize(double)` accepterar värden från 0 % till 100 %.
- **Vilka utdataformat stöds?** PPTX, PDF, XPS, PNG, JPEG och flera andra (över 50 totalt).
- **Behöver jag en licens för produktion?** En kommersiell licens krävs för obegränsad användning; en gratis provversion fungerar för utvärdering.

## Vad är Aspose.Slides för Java?
**Aspose.Slides for Java** är ett fullständigt hanterat API som gör det möjligt för utvecklare att skapa, modifiera, konvertera och rendera PowerPoint‑filer utan Microsoft Office. Det stöder mer än 50 filformat och kan hantera presentationer med tusentals bilder samtidigt som minnesanvändningen hålls låg.

## Varför använda munkdiagram i presentationer?
Munkdiagram visar del‑till‑helhets‑förhållanden samtidigt som de frigör utrymme i mitten för etiketter eller bilder. Aspose.Slides kan rendera munkdiagram med upp till **500 bilder per minut** på en typisk 2,5 GHz‑server, och det bearbetar **presentationer med flera hundra sidor** utan att ladda hela filen i minnet, vilket gör det idealiskt för rapporteringslösningar i stor skala.

## Förutsättningar
Innan du börjar, se till att du har uppfyllt dessa förutsättningar:

### Nödvändiga bibliotek och versioner
För att arbeta med Aspose.Slides för Java, inkludera det i ditt projekt via Maven eller Gradle, eller ladda ner direkt.

#### Krav för miljöinställning
- Ett fungerande Java Development Kit (JDK), helst version 8 eller högre.
- En integrerad utvecklingsmiljö (IDE) som IntelliJ IDEA eller Eclipse.

### Kunskapsförutsättningar
Bekantskap med Java och grundläggande programmeringskoncept är fördelaktigt. Grundläggande kunskap om Maven eller Gradle underlättar installationsprocessen.

## Så installerar du Aspose.Slides för Java
Att integrera Aspose.Slides i ditt projekt kan göras på flera sätt:

**Maven:**  
Lägg till detta beroende i din `pom.xml`‑fil:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Inkludera detta i din `build.gradle`‑fil:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direktnedladdning:**  
Alternativt, ladda ner den senaste versionen från [Aspose.Slides för Java-utgåvor](https://releases.aspose.com/slides/java/).

### Licensförvärv
- **Gratis provversion:** Börja med att ladda ner en provversion för att utforska Aspose.Slides‑funktionerna.  
- **Tillfällig licens:** Skaffa en tillfällig licens för utökad funktionalitet utan begränsningar.  
- **Köp:** För fortsatt användning krävs ett licensköp.

När du har biblioteket installerat och din miljö klar, låt oss gå vidare till att implementera vårt munkdiagram.

## Hur skapar man ett munkdiagram i Java?
Läs in ett nytt `Presentation`‑objekt, lägg till ett munkdiagram på en bild, ställ in hålstorleken och spara filen – allt i ett fåtal enkla API‑anrop. Detta tillvägagångssätt ger dig full kontroll över diagramdata, utseende och exportformat, och det fungerar utan att Microsoft PowerPoint behöver vara installerat på servern.

### Initiera Presentation‑objekt
Klassen `Presentation` är Aspose.Slides översta objekt som representerar en PowerPoint‑fil i minnet.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Detta steg skapar en tom presentation där du kan lägga till bilder, former och diagram.

### Lägg till munkdiagram på bild
`ISlide` är gränssnittet för en enskild bild; du kan hämta den första bilden eller lägga till en ny.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Metoden `addChart` skapar ett munkdiagram; parametrarna definierar dess position (X, Y) och storlek (bredd, höjd) på bilden.

### Konfigurera munkens hålstorlek
`Chart` exponerar `setHoleSize(double)` för att styra den inre radien som en procentandel av diagrammets radie.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Att sätta hålstorleken till 90 % får diagrammet att se nästan ut som en hel cirkel, vilket är användbart när du vill framhäva de yttre segmenten.

### Spara presentation
`presentation.save(String, SaveFormat)` skriver filen till disk i det valda formatet.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Exemplet sparar resultatet som `DoughnutHoleSize_out.pptx`, men du kan också välja PDF, PNG eller något av de 50+ stödda formaten.

### Rensa resurser
Anropet `presentation.dispose()` frigör inhemska resurser och förhindrar minnesläckor, vilket är särskilt viktigt i långvariga serverapplikationer.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## Praktiska tillämpningar
Munkdiagram är mångsidiga. Här är några scenarier där de glänser:
1. **Budgetfördelning:** Visa hur en budget fördelas över avdelningar.  
2. **Undersökningsresultat:** Visualisera svar på frågor med flervalsalternativ.  
3. **Webbtrafikkällor:** Visa procentandelen trafik som kommer från olika kanaler (organisk, betald, hänvisning osv.).

## Prestandaöverväganden
När du arbetar med Aspose.Slides, överväg dessa tips för optimal prestanda:
- Avsluta `Presentation`‑objekt så snart du är klar för att frigöra inhemskt minne.  
- Använd strömmar (`FileInputStream`, `ByteArrayOutputStream`) för stora datamängder för att undvika att ladda hela filer i RAM.  
- Återanvänd diagramobjekt när du genererar många bilder i en loop för att minska overhead för objekt‑skapande.

## Vanliga problem och lösningar
- **Fel vid sparning:** Verifiera att målkatalogen finns och att applikationen har skrivbehörighet.  
- **Saknad diagramdata:** Se till att du fyller diagrammets `ChartData`‑samling innan du anropar `setHoleSize`.  
- **Minnesökningar:** För presentationer med tusentals bilder, aktivera `Presentation.setSlideSize` till en mindre storlek och rensa mellanslagade bilder omedelbart.

## Vanliga frågor

**Q: Kan jag justera färgerna på mina munkdiagramsegment?**  
A: Ja. Använd `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` och ange sedan önskad RGB‑färg.

**Q: Hur lägger jag till datalabels i mitt diagram?**  
A: Anropa `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` för att visa värdet i varje segment.

**Q: Är det möjligt att spara diagram i andra format än PPTX?**  
A: Absolut. Aspose.Slides stöder PDF, XPS, PNG, JPEG, TIFF och många andra format—över 50 totalt.

**Q: Vad ska jag göra om jag får ett undantag när jag laddar en stor presentation?**  
A: Använd `Presentation`‑konstruktorn som accepterar en ström och aktivera `loadOptions.setLoadFormat(LoadFormat.Pptx)` för att strömma filen och minska minnesförbrukningen.

**Q: Kan jag automatisera diagramuppdateringar med live‑datakällor?**  
A: Ja. Hämta data från en databas eller REST‑API, uppdatera `ChartData`‑samlingen och anropa `chart.refresh()` innan du sparar presentationen.

## Resurser
- **Dokumentation:** Utforska detaljerade API‑referenser på [Aspose.Slides för Java](https://reference.aspose.com/slides/java/).  
- **Nedladdning:** Hämta den senaste biblioteksversionen från [Aspose.Slides-utgåvor](https://releases.aspose.com/slides/java/).  
- **Köp:** För full åtkomst, köp en licens på [Aspose Köp](https://purchase.aspose.com/buy).  
- **Gratis provversion:** Prova Aspose.Slides med en gratis provversion som finns på deras nedladdningssida.  
- **Tillfällig licens:** Skaffa en tillfällig licens för utökad testning utan begränsningar.  
- **Support:** Har du frågor? Besök [Aspose Forum](https://forum.aspose.com/c/slides/11) för hjälp.

---

**Senast uppdaterad:** 2026-07-27  
**Testat med:** Aspose.Slides for Java 24.12  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man lägger till diagram i PowerPoint med Aspose.Slides för Java: En steg‑för‑steg‑guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hur man skapar diagram i Java med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}