---
"description": "Lär dig hur du skapar fantastiska diagram med Aspose.Slides för .NET. Förbättra din datavisualisering med vår steg-för-steg-guide."
"linktitle": "Diagramenheter och formatering"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Skapa vackra diagram med Aspose.Slides för .NET"
"url": "/sv/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skapa vackra diagram med Aspose.Slides för .NET


I dagens datadrivna värld är effektiv datavisualisering nyckeln till att förmedla information till din publik. Aspose.Slides för .NET är ett kraftfullt bibliotek som låter dig skapa fantastiska presentationer och bilder, inklusive iögonfallande diagram. I den här handledningen kommer vi att guida dig genom processen att skapa vackra diagram med Aspose.Slides för .NET. Vi kommer att dela upp varje exempel i flera steg för att hjälpa dig att förstå och implementera diagramenheter och formatering. Så, låt oss komma igång!

## Förkunskapskrav

Innan vi börjar skapa vackra diagram med Aspose.Slides för .NET måste du se till att du har följande förutsättningar på plats:

1. Aspose.Slides för .NET: Se till att du har biblioteket Aspose.Slides för .NET installerat. Du kan ladda ner det från [webbplats](https://releases.aspose.com/slides/net/).

2. Utvecklingsmiljö: Du bör ha en fungerande utvecklingsmiljö med Visual Studio eller någon annan IDE som stöder .NET-utveckling.

3. Grundläggande C#-kunskaper: Bekantskap med C#-programmering är avgörande för den här handledningen.

Nu när vi har sorterat våra förutsättningar, låt oss fortsätta med att skapa vackra diagram med Aspose.Slides för .NET.

## Importera namnrymder

Först måste du importera de namnrymder som krävs för att fungera med Aspose.Slides för .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Steg 1: Skapa en presentation

Vi börjar med att skapa en ny presentation att arbeta med. Denna presentation kommer att fungera som arbetsyta för vårt diagram.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";

// Skapa katalog om den inte redan finns.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Instansierar presentation
Presentation pres = new Presentation();
```

## Steg 2: Öppna den första bilden

Nu går vi till den första bilden i presentationen där vi ska placera vårt diagram.

```csharp
// Åtkomst till den första bilden
ISlide slide = pres.Slides[0];
```

## Steg 3: Lägg till ett exempeldiagram

Nu ska vi lägga till ett exempeldiagram i vår bild. I det här exemplet skapar vi ett linjediagram med markörer.

```csharp
// Lägga till exempeldiagrammet
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Steg 4: Ange diagramtitel

Vi kommer att ge vårt diagram en titel, vilket gör det mer informativt och visuellt tilltalande.

```csharp
// Titel på inställningstabell
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Steg 5: Anpassa vertikala axelrutnät

I det här steget anpassar vi rutnätet på den vertikala axeln för att göra vårt diagram mer visuellt tilltalande.

```csharp
// Ställa in format för huvudrutnät för värdeaxel
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Ställa in format för mindre rutnät för värdeaxel
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Inställning av värdeaxelns talformat
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Steg 6: Definiera vertikalt axelområde

I det här steget ställer vi in max-, minimum- och enhetsvärden för den vertikala axeln.

```csharp
// Maximala och minimala värden i spridningstabellen
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Steg 7: Anpassa text på vertikal axel

Vi ska nu anpassa utseendet på texten på den vertikala axeln.

```csharp
// Inställning av värdeaxeltextegenskaper
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Inställning av värdeaxeltitel
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Steg 8: Anpassa horisontella axelrutnät

Nu ska vi anpassa rutnätet för den horisontella axeln.

```csharp
// Ställa in format för huvudrutnät för kategoriaxel
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Ställa in format för mindre rutnät för kategoriaxel
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Ställa in textegenskaper för kategoriaxeln
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Steg 9: Anpassa etiketter för horisontella axlar

I det här steget justerar vi positionen och rotationen för etiketter på den horisontella axeln.

```csharp
// Ställa in kategoriaxelns etikettposition
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Inställning av rotationsvinkel för kategoriaxeletikett
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Steg 10: Anpassa förklaringar

Låt oss förbättra förklaringarna i vårt diagram för bättre läsbarhet.

```csharp
// Ställa in egenskaper för förklaringar
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ställ in att visa diagramförklaringar utan överlappande diagram
chart.Legend.Overlay = true;
```

## Steg 11: Anpassa diagrambakgrunden

Vi kommer att anpassa bakgrundsfärgerna på diagrammet, bakväggen och golvet.

```csharp
// Sättningstabell för bakväggsfärg
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Ställa in färgen på ritningsområdet
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Steg 12: Spara presentationen

Slutligen, låt oss spara vår presentation med det formaterade diagrammet.

```csharp
// Spara presentation
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Slutsats

Att skapa vackra och informativa diagram i dina presentationer är nu enklare än någonsin med Aspose.Slides för .NET. I den här handledningen har vi gått igenom de viktigaste stegen för att anpassa olika aspekter av ett diagram, vilket gör det visuellt tilltalande och informativt. Med dessa tekniker kan du skapa fantastiska diagram som effektivt förmedlar dina data till din publik.

Börja experimentera med Aspose.Slides för .NET och ta din datavisualisering till nästa nivå!

## Vanliga frågor

### 1. Vad är Aspose.Slides för .NET?

Aspose.Slides för .NET är ett kraftfullt bibliotek som låter .NET-utvecklare skapa, manipulera och konvertera Microsoft PowerPoint-presentationer. Det erbjuder ett brett utbud av funktioner för att arbeta med bilder, former, diagram och mer.

### 2. Var kan jag ladda ner Aspose.Slides för .NET?

Du kan ladda ner Aspose.Slides för .NET från webbplatsen [här](https://releases.aspose.com/slides/net/).

### 3. Finns det en gratis testversion av Aspose.Slides för .NET?

Ja, du kan få en gratis provperiod av Aspose.Slides för .NET från [här](https://releases.aspose.com/).

### 4. Hur kan jag få en tillfällig licens för Aspose.Slides för .NET?

Om du behöver ett tillfälligt körkort kan du få ett från [den här länken](https://purchase.aspose.com/temporary-license/).

### 5. Finns det en community eller ett supportforum för Aspose.Slides för .NET?

Ja, du kan hitta Aspose.Slides community och supportforum [här](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}