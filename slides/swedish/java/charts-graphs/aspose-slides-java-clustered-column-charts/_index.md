---
date: '2026-03-18'
description: Lär dig hur du skapar ett grupperat stapeldiagram i Java med Aspose.Slides,
  hur du lägger till diagram, ställer in färger och sparar presentationen som PPTX.
  Steg‑för‑steg‑guide med kodexempel.
keywords:
- create clustered column chart
- aspose slides java tutorial
- clustered column chart java
title: Hur man skapar ett klustrat stapeldiagram i Java med Aspose.Slides
url: /sv/java/charts-graphs/aspose-slides-java-clustered-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Så skapar du ett grupperat stapeldiagram i Java med Aspose.Slides

## Introduktion
Att skapa visuellt tilltalande datarepresentationer är avgörande för effektfulla affärspresentationer, och att lära sig **hur man skapar ett grupperat stapeldiagram** programatiskt kan spara dig timmar av manuellt arbete. I den här handledningen kommer du att se **hur man lägger till ett diagram**, automatiskt **sätter färger**, och slutligen **sparar presentationen som PPTX** med **Aspose.Slides för Java**. Vi går igenom allt du behöver – från att konfigurera biblioteket till att lägga till diagrammet, anpassa seriefärger och spara filen.

### Vad du kommer att uppnå
- Installera och konfigurera Aspose.Slides för Java  
- **Skapa ett grupperat stapeldiagram** i en helt ny presentation  
- Applicera automatiskt seriefärger (**how to set colors**)  
- **Spara presentationen som PPTX** på disk (**how to save presentation**)  

Låt oss gå igenom förutsättningarna innan vi börjar bygga diagrammet.

## Snabba svar
- **Vad är den primära klassen?** `Presentation` från `com.aspose.slides`  
- **Hur lägger jag till ett diagram?** Använd `addChart(ChartType.ClusteredColumn, …)` på en bilds shape‑samling (**how to add chart**)  
- **Kan jag sätta färger automatiskt?** Ja, anropa `setAutomaticSeriesColor(true)` på varje serie (**how to set colors**)  
- **Vilket format används för sparning?** `SaveFormat.Pptx` (PowerPoint) (**save presentation as pptx**)  
- **Behöver jag en licens?** En provversion fungerar för testning; en full licens krävs för produktion  

## Förutsättningar
Innan du börjar, se till att du har de nödvändiga verktygen och kunskapen:

### Nödvändiga bibliotek och beroenden
Du behöver Aspose.Slides för Java-biblioteket. Se till att du använder version 25.4 med JDK16‑stöd.

### Krav för miljöinställning
Din utvecklingsmiljö bör stödja Java (helst JDK16) och kunna bygga projekt med Maven eller Gradle.

### Kunskapsförutsättningar
Bekantskap med grundläggande Java‑programmering, arbete med bibliotek via Maven/Gradle och förståelse för PowerPoint‑presentationer är fördelaktigt.

## Installera Aspose.Slides för Java
För att integrera Aspose.Slides i ditt projekt, följ installationsinstruktionerna nedan:

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

**Direktnedladdning**  
För dem som föredrar direktnedladdning, besök [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Steg för att skaffa licens
- **Gratis provversion**: Börja med en gratis provversion för att utforska funktionerna.  
- **Tillfällig licens**: Skaffa en tillfällig licens för att testa utan begränsningar.  
- **Köp**: För kontinuerlig användning, köp en full licens.

**Grundläggande initiering och inställning**  
Initiera Aspose.Slides på följande sätt:
```java
import com.aspose.slides.Presentation;
// Initialize the Presentation class
Presentation presentation = new Presentation();
```

## Så lägger du till ett grupperat stapeldiagram
Att lägga till ett diagram är det första funktionella steget. Detta avsnitt förklarar **hur man lägger till ett diagram** med API:et.

### Funktion 1: Skapa ett grupperat stapeldiagram
Låt oss skapa ett grupperat stapeldiagram med Aspose.Slides för Java. Denna funktion låter dig enkelt lägga till visuellt tilltalande diagram i dina bilder.

#### Översikt
I detta avsnitt initierar vi en ny presentation och infogar ett grupperat stapeldiagram på den första bilden.

**Steg 1: Initiera Presentation**  
Skapa ett `Presentation`‑objekt för att börja arbeta med PowerPoint‑filer:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation presentation = new Presentation();
```

**Steg 2: Lägg till ett grupperat stapeldiagram**  
Lägg till diagrammet på angivna koordinater (100, 50) och dimensioner (600 × 400):
```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(ChartType.ClusteredColumn, 100, 50, 600, 400);
```

**Steg 3: Rensa resurser**  
Disposera alltid resurser för att förhindra minnesläckor:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Så sätter du färger för diagrammet
Förbättra det visuella intrycket genom att automatiskt applicera seriefärger (**how to set colors**).

### Funktion 2: Ställ in automatisk seriefyllningsfärg
Ställ in varje diagramserie automatiskt för ett enhetligt utseende.

#### Översikt
Ställ in varje diagramserie automatiskt för ett enhetligt utseende.

**Steg 1: Åtkomst till diagram och iterera serier**  
Efter att du har skapat ditt diagram, få åtkomst till det och iterera över dess serier:
```java
import com.aspose.slides.IChart;
IChart chart = presentation.getSlides().get_Item(0).getShapes()
                            .addChart(com.aspose.slides.ChartType.ClusteredColumn, 100, 50, 600, 400);

for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().get_Item(i).setAutomaticSeriesColor(true);
}
```

**Steg 2: Resurshantering**  
Disposera presentationsobjektet när du är klar:
```java
finally {
    if (presentation != null) presentation.dispose();
}
```

## Så sparar du presentationen som PPTX
När diagrammet ser bra ut vill du spara filen (**how to save presentation**).

### Funktion 3: Spara presentationen till disk
Slutligen, spara ditt arbete enkelt med Aspose.Slides.

#### Översikt
Spara dina redigerade presentationer i önskat format och plats.

**Steg 1: Definiera utsökväg**  
Ange var du vill spara filen:
```java
import com.aspose.slides.SaveFormat;
String outputPath = "YOUR_OUTPUT_DIRECTORY/AutoFillSeries_out.pptx";
```

**Steg 2: Spara presentation**  
Använd `save`‑metoden på `Presentation`‑objektet:
```java
presentation.save(outputPath, SaveFormat.Pptx);
```

## Praktiska tillämpningar
- **Finansiella rapporter**: Visualisera kvartalsresultat med tydlighet.  
- **Marknadsdataanalys**: Visa kampanjresultat med övertygande visualiseringar.  
- **Projektledning**: Följ milstolpar och framsteg visuellt i teammöten.

## Prestandaöverväganden
När du arbetar med Aspose.Slides, överväg dessa bästa praxis:

- Hantera minnet effektivt genom att snabbt disponera `Presentation`‑objekt.  
- Optimera filstorlekar vid sparning av presentationer för att spara diskutrymme.  
- Använd effektiva datastrukturer för diagramserier för att förbättra prestanda.

## Slutsats
Grattis! Du har lärt dig hur man **skapar ett grupperat stapeldiagram**, automatiskt **sätter färger**, och **sparar presentationen som PPTX** med Aspose.Slides för Java. Denna färdighet förbättrar inte bara dina presentationer utan förenklar också processen för visuell datarepresentation.

**Nästa steg:**  
Utforska ytterligare funktioner som att anpassa diagramelement, lägga till datamärkningar eller integrera med externa datakällor för att utöka ditt projekts möjligheter.

## FAQ‑avsnitt
1. **Hur installerar jag Aspose.Slides för en specifik JDK‑version?**  
   - Använd Maven/Gradle‑beroenden och specificera `classifier` som visas i installationsavsnittet.  
2. **Vad händer om min presentation inte sparas korrekt?**  
   - Se till att du har skrivrättigheter till din utskriftskatalog och att filvägen är korrekt.  
3. **Kan jag skapa andra typer av diagram med Aspose.Slides för Java?**  
   - Absolut! Utforska `ChartType`‑alternativ som paj, stapel eller linjediagram.  
4. **Hur hanterar jag stora datamängder i mitt diagram?**  
   - Optimera datastrukturer och överväg att förbehandla dina data innan visualisering.  
5. **Var kan jag hitta fler exempel på att använda Aspose.Slides för Java?**  
   - Besök [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) för omfattande guider och kodexempel.

## Resurser
- **Dokumentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Nedladdning**: [Get Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Köp**: [Buy a License](https://purchase.aspose.com/buy)  
- **Gratis provversion**: [Start a Free Trial](https://releases.aspose.com/slides/java/)  
- **Tillfällig licens**: [Request Here](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Senast uppdaterad:** 2026-03-18  
**Testat med:** Aspose.Slides 25.4 (JDK16)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}