---
"date": "2025-04-17"
"description": "Lär dig hur du skapar och anpassar ett cirkeldiagram med Aspose.Slides för Java. Den här guiden behandlar installation, implementering och praktiska tillämpningar."
"title": "Skapa ett cirkeldiagram i Java med Aspose.Slides – en omfattande guide"
"url": "/sv/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa ett cirkeldiagram i Java med Aspose.Slides: En omfattande guide

## Diagram och grafer

### Introduktion

Inom datavisualisering är cirkeldiagram ett intuitivt sätt att representera proportioner inom en datamängd. Men när man hanterar komplexa datamängder där vissa segment är betydligt mindre än andra kan traditionella cirkeldiagram bli röriga och svåra att tolka. Cirkeldiagram åtgärdar detta genom att dela upp små segment i ett sekundärt diagram, vilket förbättrar läsbarheten.

den här handledningen lär du dig hur du skapar och manipulerar ett cirkeldiagram med hjälp av Aspose.Slides för Java. Du går igenom hur du konfigurerar din miljö, skapar diagrammet, anpassar egenskaper som dataetiketter och delningspositioner och sparar din presentation i PPTX-format. I slutet kommer du att ha bemästrat dessa funktioner med praktiska tillämpningar och prestandatips.

**Vad du kommer att lära dig:**
- Konfigurera Aspose.Slides för Java
- Skapa ett cirkeldiagram
- Anpassa diagramegenskaper som dataetiketter och delningskonfigurationer
- Spara din presentation på disk

Redo att komma igång? Låt oss titta på förkunskapskraven först!

## Förkunskapskrav

Innan du skapar vårt cirkeldiagram, se till att du har:

### Obligatoriska bibliotek, versioner och beroenden:
- **Aspose.Slides för Java**Viktigt för att hantera PowerPoint-presentationer programmatiskt.

### Krav för miljöinstallation:
- Ett Java Development Kit (JDK) installerat på din dator. Vi rekommenderar att du använder JDK 16 eller senare.
- En integrerad utvecklingsmiljö (IDE) som IntelliJ IDEA, Eclipse eller NetBeans.

### Kunskapsförkunskapskrav:
- Grundläggande förståelse för Java-programmering
- Bekantskap med Maven eller Gradle för beroendehantering

## Konfigurera Aspose.Slides för Java

### Installationsinformation:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkt nedladdning**Du kan ladda ner den senaste versionen från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

### Steg för att förvärva licens:
- **Gratis provperiod**Börja med en 30-dagars provperiod för att utforska alla funktioner.
- **Tillfällig licens**Begär en tillfällig licens för utökad utvärdering.
- **Köpa**Överväg att köpa en licens om Aspose.Slides uppfyller dina behov.

### Grundläggande initialisering och installation

När du har konfigurerat biblioteket i ditt projekt, initiera det genom att skapa en instans av `Presentation` klass:

```java
Presentation presentation = new Presentation();
```

Detta banar väg för att lägga till olika diagram i dina bilder. Nu ska vi gå vidare till att implementera vårt cirkeldiagram.

## Implementeringsguide

### Skapa ett "paj av paj"-diagram

#### Översikt
Vi börjar med att skapa en instans av en `Presentation` och lägg till ett cirkeldiagram på den första bilden. Diagrammet visualiserar data effektivt genom att separera mindre segment till ett sekundärt cirkeldiagram, vilket förbättrar läsbarheten.

#### Steg 1: Skapa en instans av presentationsklassen
```java
// Skapa en ny presentation
ePresentation presentation = new Presentation();
```
Den här koden initierar din presentation där vi lägger till våra diagram.

#### Steg 2: Lägg till ett "paj-av-paj"-diagram på den första bilden
```java
// Lägg till ett cirkeldiagram på den första bilden vid position (50, 50) med storleken (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Här anger vi diagramtypen (`PieOfPie`) och dess position och dimensioner på bilden.

#### Steg 3: Ställ in dataetiketter för att visa värden för serien
```java
// Konfigurera dataetiketter för att visa värden
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Det här steget säkerställer att varje segment av vårt cirkeldiagram visar motsvarande värde, vilket underlättar snabb datatolkning.

#### Steg 4: Konfigurera den andra cirkelstorleken och dela upp i procent
```java
// Ange storleken på den sekundära cirkeln
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Dela kakan i procent
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Ställ in delad position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Med dessa konfigurationer kan du anpassa hur ditt diagram delas upp och visar mindre segment, vilket förbättrar tydligheten för tittarna.

#### Steg 5: Spara presentationen på disk i PPTX-format
```java
// Definiera utdatakatalog
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Spara presentationen\presentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}