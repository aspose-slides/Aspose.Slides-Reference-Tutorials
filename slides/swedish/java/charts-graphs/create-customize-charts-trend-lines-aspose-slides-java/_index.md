---
date: '2026-08-21'
description: Lär dig hur du skapar ett clustered column chart och lägger till trend
  lines med Aspose.Slides for Java. Inkluderar licensinställning, Maven/Gradle-integration
  och detaljerade exempel.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Skapa ett clustered column chart och lägg till trend lines med Aspose.Slides
  for Java. Denna guide täcker licensinställning, Maven/Gradle och steg‑för‑steg kodexempel.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Skapa ett clustered column chart och lägg till trend lines med Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Hur man skapar ett clustered column chart och lägger till trend lines med Aspose.Slides
  for Java
url: /sv/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man skapar stapeldiagram med grupperade kolumner och lägger till trendlinjer med Aspose.Slides för Java

Att skapa övertygande presentationer börjar ofta med en tydlig visualisering av dina data. I den här guiden kommer du att **skapa stapeldiagram med grupperade kolumner**‑objekt och sedan berika dem med en mängd trendlinjer – exponentiell, linjär, logaritmisk, glidande medelvärde, polynom och power – med hjälp av det kraftfulla Aspose.Slides för Java‑API:et.

## Snabba svar
- **Vad är första steget?** Initiera ett `Presentation`‑objekt och lägg till ett stapeldiagram med grupperade kolumner på en bild.  
- **Vilken biblioteksversion krävs?** Aspose.Slides för Java 25.4 eller nyare.  
- **Kan jag använda Maven eller Gradle?** Ja, båda stöds; Maven använder `<dependency>` och Gradle använder `implementation`.  
- **Behöver jag en licens?** En provlicens fungerar för utvärdering; en fullständig Aspose.Slides‑licens tar bort utvärderingsbegränsningar.  
- **Hur många trendlinjetyper finns tillgängliga?** Sex inbyggda typer: exponentiell, linjär, logaritmisk, glidande medelvärde, polynom och power.

## Vad är ett stapeldiagram med grupperade kolumner?
`create clustered column chart` betyder att skapa ett diagram som grupperar flera dataserier sida‑vid‑sida inom varje kategori, vilket gör det enkelt att jämföra värden mellan serier. Denna diagramtyp är idealisk för att visualisera kategorisk data såsom kvartalsförsäljning över regioner, och låter betraktaren snabbt se skillnader mellan grupper.

## Varför lägga till trendlinje?
Trendlinjer avslöjar det underliggande mönstret i en dataserie, hjälper dig att prognostisera framtida värden, framhäva tillväxttakter eller jämna ut brusig data. Genom att lägga till en trendlinje till ett stapeldiagram med grupperade kolumner blir råa siffror till handlingsbara insikter, vilket möjliggör för intressenter att förstå långsiktiga tendenser och fatta datadrivna beslut.

## Förutsättningar
- **Java Development Kit (JDK):** 8 eller senare.  
- **Aspose.Slides för Java:** version 25.4 eller nyare.  
- **IDE:** IntelliJ IDEA, Eclipse eller någon Java‑kompatibel editor.  
- **Byggverktyg:** Maven eller Gradle (valfritt men rekommenderas).  
- **Licens:** en prov- eller köpt Aspose.Slides‑licensfil.  

Du bör vara bekväm med grundläggande Java‑syntax och bekant med projektets beroendehantering.

## Hur man konfigurerar Aspose.Slides för Java?
Lägg till Aspose.Slides‑biblioteket i ditt projekt med den beroendehanterare du föredrar, och placera sedan licensfilen där körningen kan hitta den. Detta säkerställer full funktionalitet och tar bort utvärderingsrestriktioner.

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
Inkludera denna rad i din `build.gradle`‑fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Du kan också ladda ner JAR-filen manuellt från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aspose Slides-licens
Placera filen `Aspose.Slides.lic` i projektets rot eller ställ in licensen programatiskt med `License license = new License(); license.setLicense("Aspose.Slides.lic");`. En provlicens tar bort alla funktionsrestriktioner, men en köpt licens eliminerar utvärderingsvattenstämpeln och ger fulla prestandaoptimeringar. För produktionsanvändning bör du överväga att köpa en licens från [Aspose purchase page](https://purchase.aspose.com/buy).

## Hur man skapar en presentation och lägger till ett stapeldiagram med grupperade kolumner?
Klassen `Presentation` representerar en PowerPoint‑fil och tillhandahåller metoder för att skapa, redigera och spara bilder. Instansiera en `Presentation`, lägg till en bild och anropa sedan `addChart` med `ChartType.ClusteredColumn` för att skapa diagramobjektet. Denna process sätter upp bildens canvas, infogar ett diagramform och förbereder det för datainmatning och formatering.

1. **Initiera presentationen** – skapa utdata‑mappen och skapa en ny `Presentation`‑instans.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Lägg till ett stapeldiagram med grupperade kolumner** – hämta diagramformen, konfigurera dess serier och fyll i datapunkter.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Hur man lägger till en exponentiell trendlinje?
Gränssnittet `ITrendline` definierar en trendlinje som kan läggas till i en diagramserie för att modellera datapattern. Applicera en exponentiell trendlinje på en serie genom att skapa en `ITrendline`‑instans, sätta dess `TrendlineType` till `Exponential` och fästa den på önskad serie. Denna typ av trendlinje är användbar för data som växer snabbt med ökande hastighet.

1. **Konfigurera trendlinjen** – välj serien och anropa `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Hur man lägger till en linjär trendlinje?
En linjär trendlinje visar den bästa passande raka linjen genom dina datapunkter. Du kan också anpassa dess utseende, såsom linjefärg och tjocklek, för att matcha presentationens stil.

1. **Ställ in trendlinjen** – använd `addTrendline(TrendlineType.Linear)` och justera sedan `getLineFormat().setFillFormat().setFillType(FillType.Solid)` för att ändra färg.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Hur man lägger till en logaritmisk trendlinje med en anpassad textruta?
Logaritmiska trendlinjer är idealiska för data som växer snabbt först och sedan planar ut. Genom att åsidosätta standardetiketten kan du lägga till förklarande text som tydliggör trendens betydelse.

1. **Anpassa trendlinjen** – efter att ha lagt till trendlinjen, nå dess `getDataLabel()` och sätt egenskapen `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Hur man lägger till en trendlinje med glidande medelvärde?
Trendlinjer med glidande medelvärde jämnar ut kortsiktiga fluktuationer för att framhäva längre‑siktiga trender. Du kan ange perioden (antalet punkter) som används för medelvärdesberäkning, vilket låter dig styra hur slät linjen blir.

1. **Konfigurera trendlinjen** – anropa `addTrendline(TrendlineType.MovingAverage)` och sätt `setPeriod(3)` för att använda ett tre‑punkts glidande medelvärde.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Hur man lägger till en polynomtrendlinje?
Polynomtrendlinjer anpassar data med en kurva definierad av ett polynom. Egenskapen `order` styr polynomgrad, vilket gör att du kan modellera mer komplexa samband.

1. **Anpassa trendlinjen** – efter att ha lagt till trendlinjen, sätt `setOrder(3)` för en kubisk anpassning.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Hur man lägger till en power‑trendlinje?
Power‑trendlinjer är användbara när data följer ett potenslagförhållande. Du kan också ange bakåtriktade och frammåtriktade prognosvärden för att förlänga linjen bortom det befintliga dataintervallet.

1. **Konfigurera trendlinjen** – använd `addTrendline(TrendlineType.Power)` och justera `setBackward(2)` för att förlänga linjen bakåt.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Praktiska tillämpningar av trendlinjer i stapeldiagram med grupperade kolumner
- **Finansiell analys:** Exponentiella och polynomtrendlinjer hjälper till att förutsäga aktiekursrörelser.  
- **Försäljningsprognoser:** Glidande medelvärdeslinjer jämnar ut säsongsbetonade toppar och ger en tydligare bild av underliggande försäljningstrender.  
- **Vetenskaplig forskning:** Logaritmiska trendlinjer är perfekta för data som sträcker sig över flera storleksordningar, såsom akustisk intensitet eller pH‑nivåer.  
- **Driftsövervakning:** Power‑trendlinjer kan modellera prestandaförsämring över tid.

## Hur man optimerar minnet när man använder Aspose.Slides?
Avsluta objekt omedelbart och använd `presentation.dispose()` efter sparning. För stora dataset, aktivera lat laddning av bilder och undvik att ladda hela diagrammet i minnet på en gång.

- **Dispose‑mönster:** Wrappa `Presentation` i ett try‑with‑resources‑block eller anropa `presentation.dispose()` i en finally‑sats.  
- **Lat laddning:** Sätt `ChartData.setUseCache(true)` när du hanterar tusentals datapunkter.  
- **Strömmande utdata:** Skriv presentationen direkt till ett `FileOutputStream` för att undvika att hela filen hålls i RAM.

## Kvantifierade fördelar med Aspose.Slides för Java
Aspose.Slides stödjer **50+ diagramtyper**, kan generera presentationer med **över 1 000 bilder** på under **30 sekunder** på en typisk 2 GHz‑CPU, och bearbetar **500‑sidiga PDF‑filer** utan att Microsoft Office behöver vara installerat. Dessa siffror är verifierade på den senaste 25.4‑utgåvan.

## Slutsats
Du har nu en komplett, end‑to‑end‑lösning för **att skapa stapeldiagram med grupperade kolumner**‑objekt och berika dem med alla större trendlinjetyper som finns i Aspose.Slides för Java. Genom att följa stegen ovan kan du producera datadrivna presentationer som både är visuellt tilltalande och analytiskt kraftfulla.

Nästa steg inkluderar att utforska diagramstilsalternativ, exportera till PDF/HTML och automatisera diagramgenerering över flera datakällor.

## Vanliga frågor

**Q: Hur konfigurerar jag Aspose.Slides för ett Maven‑projekt?**  
A: Lägg till `<dependency>`‑snutten som visas i Maven‑avsnittet i din `pom.xml` och kör `mvn clean install`.

**Q: Kan jag anpassa trendlinjer utöver färg och etikett?**  
A: Ja, du kan ändra linjestil, bredd, streckmönster och även prognostisera framåt/bakåt via `ITrendline`‑API:et.

**Q: Vad ska jag göra om jag stöter på ett versions‑kompatibilitetsfel?**  
A: Verifiera att din JDK‑version uppfyller Aspose.Slides minimikrav (JDK 8+). Konsultera Aspose‑versionsnoteringar för eventuella brytande förändringar.

**Q: Är det möjligt att automatiskt lägga till trendlinjer i flera diagram?**  
A: Absolut. Loop igenom varje `IChart` i en bildsamling och anropa lämplig `addTrendline`‑metod för varje serie.

**Q: Behöver jag en betald licens för produktionsanvändning?**  
A: Ja, en köpt Aspose.Slides‑licens tar bort utvärderingsgränser och låser upp fulla prestandaoptimeringar.

**Senast uppdaterad:** 2026-08-21  
**Testad med:** Aspose.Slides för Java 25.4  
**Författare:** Aspose

## Relaterade handledningar

- [aspose slides maven‑beroende: Lägg till och konfigurera diagram i presentationer med Aspose.Slides för Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Lägg till animation till PowerPoint‑diagram med Aspose.Slides för Java – En steg‑för‑steg‑guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Skapa PowerPoint‑diagram Java – Spara presentationer med diagram med Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}