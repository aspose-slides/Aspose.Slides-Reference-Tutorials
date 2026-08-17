---
date: '2026-05-29'
description: Lär dig hur du skapar pie chart med Aspose.Slides Maven, lägger till
  pie chart java på en slide och anpassar chart data. Steg‑för‑steg‑guide med Maven‑setup
  och real‑world‑exempel.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Skapa pie chart med Aspose – Lägg till ett diagram i en presentation med Maven
url: /sv/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man lägger till ett cirkeldiagram i en presentation med Aspose.Slides Java

## Introduktion
I den här guiden kommer du att **create pie chart aspose** med Aspose.Slides Maven och se hur du bäddar in den i en PowerPoint-bild. Att skapa visuellt tilltalande presentationer är avgörande för att effektivt förmedla information, särskilt när datavisualisering spelar en nyckelroll. Om du vill automatisera denna process med **aspose slides maven**, har du kommit till rätt ställe. Vi kommer att gå igenom hur man lägger till ett diagram på en bild — specifikt ett cirkeldiagram — och anpassar det för verkliga scenarier.

### Vad du kommer att lära dig
- Hur man initierar ett presentationsobjekt i Java.  
- Steg för att **add a pie chart java** på den första bilden i en presentation.  
- Åtkomst till diagramdataarbetsböcker och listning av kalkylblad i dem.  

Låt oss dyka in i hur du kan utnyttja Aspose.Slides Java för att förbättra dina presentationer med dynamiska diagram!

## Snabba svar
- **Vilket bibliotek lägger till diagram via Maven?** aspose slides maven  
- **Vilken diagramtyp demonstreras?** Pie chart (add chart to slide)  
- **Minsta Java-version som krävs?** JDK 16 or later  
- **Behöver jag en licens för testning?** A free trial works; production needs a license  
- **Var kan jag hitta Maven‑beroendet?** In the setup section below  

## Vad är Aspose Slides Maven?
Aspose.Slides för Java är ett kraftfullt API som låter utvecklare skapa, modifiera och rendera PowerPoint‑filer programatiskt. Maven‑paketet (`aspose-slides`) förenklar beroendehantering, så att du kan fokusera på att bygga och anpassa bilder—som att lägga till ett cirkeldiagram—utan att behöva hantera låg‑nivå filhantering.

## Varför använda Aspose.Slides Maven för att lägga till ett diagram på en bild?
Att använda Aspose.Slides Maven låter dig generera diagram direkt från Java‑kod utan manuell PowerPoint‑redigering. Det ger full programmatisk kontroll över diagramtyper, datakällor och stil, vilket säkerställer konsekvent varumärkesprofil och noggrannhet. Maven‑artefakten hanterar också alla nödvändiga beroenden, förenklar byggen och möjliggör sömlös integration i CI/CD‑pipelines.

## Förutsättningar
- **Aspose.Slides for Java** version 25.4 eller senare (Maven/Gradle).  
- JDK 16+ installerat.  
- En IDE (IntelliJ IDEA, Eclipse, etc.).  
- Grundläggande Java‑kunskaper och bekantskap med Maven eller Gradle.

## Konfigurera Aspose.Slides för Java
Först, inkludera Aspose.Slides i ditt projekt via Maven eller Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativt kan du [ladda ner den senaste versionen](https://releases.aspose.com/slides/java/) direkt från Asposes webbplats.

### Licensanskaffning
Aspose.Slides for Java erbjuder en gratis provversion med en tillfällig licens för testning. För obegränsad produktionsanvändning, köp en licens via [purchase page](https://purchase.aspose.com/buy).

## Implementeringsguide
Nedan delar vi upp lösningen i två funktioner: att lägga till ett cirkeldiagram och att komma åt dess dataarbetsbok.

### Funktion 1: Skapa en presentation och lägga till ett diagram
#### Översikt
Denna del visar hur man skapar en ny presentation och **add a pie chart** på den första bilden.

#### Hur man skapar pie chart aspose?
Läs in `Presentation`‑klassen, lägg till ett diagram av typen `ChartType.Pie` och spara filen. Hela operationen kräver bara tre API‑anrop och körs på under en sekund för en typisk 10‑bilds‑deck, vilket gör den idealisk för automatiserad rapportgenerering.

#### Steg‑för‑steg

**Steg 1: Initiera ett nytt presentationsobjekt**  
`Presentation`‑klassen är Aspose.Slides översta objekt som representerar en PowerPoint‑fil i minnet.  
```java
Presentation pres = new Presentation();
```
*Skapar `Presentation`‑instansen som kommer att hålla alla bilder.*

**Steg 2: Lägg till ett cirkeldiagram**  
`ChartType.Pie` instruerar Aspose att rendera ett cirkeldiagram.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Placerar ett cirkeldiagram på koordinaterna (50, 50) med en bredd på 400 och höjd på 500.*

**Steg 3: Frigör resurser**  
Anrop av `dispose()` frigör inhemska resurser och förhindrar minnesläckor.  
```java
if (pres != null) pres.dispose();
```
*Frigör inhemska resurser; anropa alltid `dispose()` när du är klar.*

### Funktion 2: Åtkomst till diagramdataarbetsbok och kalkylblad
#### Översikt
Lär dig hur du når den underliggande arbetsboken som lagrar diagramdata och itererar genom dess kalkylblad.

#### Hur man får åtkomst till diagramdataarboken?
Hämta `IChartDataWorkbook` från diagrammet, loopa sedan igenom dess `Worksheets`‑samling. Denna arbetsbok efterliknar en Excel‑fil, vilket gör att du kan läsa, modifiera eller lägga till dataserier programatiskt, och diagrammet kommer att reflektera förändringarna omedelbart när det uppdateras under körning utan att starta om.

#### Steg‑för‑steg

**Steg 1: (Återanvänd) Initiera ett nytt presentationsobjekt**  
*Samma som Funktion 1, Steg 1.*

**Steg 2: (Återanvänd) Lägg till ett cirkeldiagram**  
*Samma som Funktion 1, Steg 2.*

**Steg 3: Hämta diagramdataarboken**  
`IChartDataWorkbook` är gränssnittet som ger läs‑/skriv‑åtkomst till diagrammets interna Excel‑liknande arbetsbok.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Hämtar `IChartDataWorkbook` som är länkat till diagrammet.*

**Steg 4: Iterera genom kalkylblad**  
`Worksheet`‑objekt representerar enskilda blad i arbetsboken.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Skriver ut varje kalkylblads namn, så att du kan verifiera datastrukturen.*

**Steg 5: Frigör resurser**  
*Samma som Funktion 1, Steg 3.*

## Praktiska tillämpningar
- **Data Reporting:** Auto‑generera bilddäck med aktuella mätvärden för affärsintelligens.  
- **Academic Presentations:** Visualisera forskningsresultat utan manuell diagramskapning.  
- **Marketing Material:** Visa produktprestanda eller enkätresultat omedelbart.

## Prestandaöverväganden
- Aspose.Slides kan hantera **50+ in‑ och utdataformat** och bearbeta presentationer med flera hundra sidor utan att ladda in hela filen i minnet.  
- Håll antalet bilder och diagram rimligt; varje diagram förbrukar inhemskt minne.  
- Anropa alltid `dispose()` för att snabbt frigöra resurser.  
- Optimera hantering av arbetsboksdata—undvik att ladda enorma dataset i ett enda diagram.

## Slutsats
Vi har gått igenom hur **aspose slides maven** gör att du kan **add chart to slide** programatiskt och hur du arbetar med diagrammets dataarbetsbok. Med dessa byggstenar kan du automatisera alla rapporteringsarbetsflöden som kräver ett polerat PowerPoint‑resultat.

### Nästa steg
- Utforska diagramstilsalternativ (färger, legender, datamärkningar).  
- Anslut till externa datakällor (CSV, databaser) för att dynamiskt fylla diagram.  
- Kombinera flera diagramtyper i en enda presentation för rikare berättande.

## Vanliga frågor

**Q: Hur installerar jag Aspose.Slides för Java?**  
A: Använd Maven‑ eller Gradle‑beroendet som visas ovan, eller ladda ner biblioteket från releases‑sidan.

**Q: Vad är systemkraven för Aspose.Slides?**  
A: JDK 16 eller senare; biblioteket körs på alla plattformar som stödjer Java.

**Q: Kan jag lägga till andra diagramtyper förutom cirkeldiagram?**  
A: Ja, Aspose.Slides stödjer stapel, linje, spridnings-, radar‑diagram och mer än 20 diagramtyper.

**Q: Hur hanterar jag stora presentationer på ett effektivt sätt?**  
A: Frigör objekt omedelbart, begränsa högupplösta bilder och återanvänd diagrammallar för att hålla minnesanvändningen låg.

**Q: Var kan jag hitta mer information om Aspose.Slides‑funktioner?**  
A: Besök [Aspose documentation](https://reference.aspose.com/slides/java/) för en komplett API‑referens.

**Q: Krävs en licens för kommersiell användning?**  
A: En giltig licens krävs för produktion; en gratis provversion finns tillgänglig för utvärdering.

**Q: Inkluderar Maven‑paketet alla diagramfunktioner?**  
A: Ja, `aspose-slides` Maven‑artefakten innehåller hela diagrammotorn.

## Resurser
- Dokumentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Nedladdning: [Latest Releases](https://releases.aspose.com/slides/java/)
- Köp och provversion: [Purchase Page](https://purchase.aspose.com/buy)
- Gratis provversion: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Tillfällig licens: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Supportforum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Senast uppdaterad:** 2026-05-29  
**Testad med:** Aspose.Slides 25.4 for Java (jdk16)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man anpassar färger i cirkeldiagram i Java med Aspose.Slides – En komplett guide](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Skapa ett Pie of Pie-diagram i Java med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animera diagram i PowerPoint med Aspose.Slides för Java – En steg‑för‑steg guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}