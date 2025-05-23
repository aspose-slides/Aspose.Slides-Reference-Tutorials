---
"date": "2025-04-15"
"description": "Lär dig hur du förbättrar dina presentationer med punktdiagram med hjälp av Aspose.Slides för .NET. Följ den här omfattande guiden för att skapa och anpassa diagram effektivt."
"title": "Lägg till punktdiagram i presentationer med Aspose.Slides .NET – en steg-för-steg-guide"
"url": "/sv/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Lägg till punktdiagram i presentationer med Aspose.Slides .NET: En steg-för-steg-guide

## Introduktion
Vill du förbättra dina presentationer genom att enkelt integrera punktdiagram? Med kraften i Aspose.Slides för .NET blir det enkelt att skapa och anpassa diagram. Den här handledningen guidar dig genom att lägga till punktdiagram i dina bilder med Aspose.Slides för .NET. Genom att bemästra dessa tekniker presenterar du data mer effektivt och skapar visuellt tilltalande presentationer.

**Vad du kommer att lära dig:**
- Konfigurera Aspose.Slides för .NET i ditt projekt
- Skapa en ny presentation och öppna dess första bild
- Lägga till punktdiagram med mjuka linjer på bilder
- Rensa befintliga serier och lägga till nya i diagram
- Ändra datapunkter och markörstilar för förbättrad visualisering
- Spara presentationen till en angiven katalog

Låt oss börja med att granska förutsättningarna.

## Förkunskapskrav
Innan du implementerar Aspose.Slides för .NET, se till att du har följande:
- **Aspose.Slides för .NET-biblioteket**Version 23.7 eller senare.
- **Utvecklingsmiljö**Visual Studio 2019 eller senare med .NET Framework 4.6.1+ eller .NET Core/5+.
- **Grundläggande C#-kunskaper**Bekantskap med objektorienterad programmering i C#.

## Konfigurera Aspose.Slides för .NET
För att börja använda Aspose.Slides måste du installera biblioteket i ditt projekt. Så här gör du:

**Använda .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Använda pakethanterarkonsolen:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-pakethanterarens användargränssnitt:**
- Sök efter "Aspose.Slides" och installera den senaste versionen.

### Licensförvärv
Du kan börja med en gratis provperiod eller ansöka om en tillfällig licens för att utforska alla funktioner. Följ dessa steg för att köpa:
1. Besök [Köp Aspose.Slides](https://purchase.aspose.com/buy) att köpa en fullständig licens.
2. För en tillfällig licens, besök [Sida för tillfällig licens](https://purchase.aspose.com/temporary-license/).

När du har fått din licensfil, lägg till den i ditt projekt med hjälp av:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Implementeringsguide
Vi kommer att dela upp implementeringen i logiska avsnitt baserat på funktioner.

### Skapa presentation och lägg till bild
Det här avsnittet visar hur man skapar en presentation och öppnar den första bilden.

#### Översikt
Börja med att skapa en instans av `Presentation` klass, som representerar din PowerPoint-fil. Det är enkelt att komma åt bilder med hjälp av den här objektmodellen.

#### Implementeringssteg
**Steg 1: Initiera presentationen**
```csharp
using Aspose.Slides;

// Skapa en ny presentation
t Presentation pres = new Presentation();
```
Denna kod initierar ett nytt presentationsdokument.

**Steg 2: Åtkomst till första bilden**
```csharp
// Åtkomst till den första bilden i presentationen
ISlide slide = pres.Slides[0];
```
Här, `pres.Slides[0]` öppnar den allra första bilden. 

### Lägg till punktdiagram till bild
Nu ska vi lägga till ett punktdiagram i din presentation.

#### Översikt
Att lägga till diagram kan hjälpa dig att representera data visuellt i presentationer. Aspose.Slides gör det enkelt att införliva olika typer av diagram, inklusive punktdiagram.

#### Implementeringssteg
**Steg 1: Skapa och lägg till punktdiagram**
```csharp
using Aspose.Slides.Charts;

// Skapa och lägg till ett standardspridningsdiagram med mjuka linjer
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Det här kodavsnittet lägger till ett punktdiagram vid den angivna positionen och storleken.

### Rensa och lägg till serier i diagramdata
#### Översikt
Du kan behöva anpassa ditt diagram genom att rensa befintliga serier och lägga till nya. Det här avsnittet behandlar den funktionen.

#### Implementeringssteg
**Steg 1: Åtkomst till arbetsboken för diagramdata**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Rensa alla befintliga serier
chart.ChartData.Series.Clear();
```
Den här koden rensar befintliga data för att börja om från början med nya serier.

**Steg 2: Lägg till ny serie**
```csharp
// Lägg till en ny serie med namnet "Serie 1"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Lägg till ytterligare en serie med namnet "Serie 2"
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Dessa steg lägger till två nya serier i diagrammet.

### Ändra datapunkter och markörstil för första serien
#### Översikt
Anpassa datapunkter och markörstilar för bättre visualisering av dina spridningsdiagram.

#### Implementeringssteg
**Steg 1: Åtkomst till och lägg till datapunkter**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Lägg till datapunkterna (1, 3) och (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Steg 2: Ändra markörstil**
```csharp
// Ändra serietyp och modifiera markörstil
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Ändra datapunkter och markörstil för andra serien
#### Översikt
På samma sätt kan du anpassa den andra serien för att skräddarsy dina presentationsbehov.

#### Implementeringssteg
**Steg 1: Åtkomst till och lägg till flera datapunkter**
```csharp
// Få åtkomst till den andra diagramserien
series = chart.ChartData.Series[1];

// Lägg till flera datapunkter
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Steg 2: Ändra markörstil**
```csharp
// Ändra markörstorlek och symbol för den andra serien
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Spara presentation
Slutligen, spara din presentation till en angiven katalog.

#### Implementeringssteg
**Steg 1: Definiera katalog**
Se till att utdatakatalogen finns. Om inte, skapa den:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Spara presentationen
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Den här koden sparar din presentationsfil på en angiven plats.

## Slutsats
Du har nu lagt till punktdiagram i dina presentationer med Aspose.Slides för .NET. Fortsätt utforska ytterligare funktioner och anpassningar som finns i biblioteket för att förbättra dina datavisualiseringsfärdigheter.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}