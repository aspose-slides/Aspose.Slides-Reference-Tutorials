---
"description": "Lär dig avancerad diagramanpassning i Aspose.Slides för .NET. Skapa visuellt tilltalande diagram med steg-för-steg-vägledning."
"linktitle": "Avancerad diagramanpassning i Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Avancerad diagramanpassning i Aspose.Slides"
"url": "/sv/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Avancerad diagramanpassning i Aspose.Slides


Att skapa visuellt tilltalande och informativa diagram är en viktig del av datapresentation i många applikationer. Aspose.Slides för .NET tillhandahåller robusta verktyg för diagramanpassning, så att du kan finjustera varje aspekt av dina diagram. I den här handledningen utforskar vi avancerade tekniker för diagramanpassning med Aspose.Slides för .NET.

## Förkunskapskrav

Innan du börjar med avancerad diagramanpassning med Aspose.Slides för .NET, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för .NET-bibliotek: Du måste ha Aspose.Slides-biblioteket installerat och korrekt konfigurerat i ditt .NET-projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/net/).

2. En .NET-utvecklingsmiljö: Du bör ha en .NET-utvecklingsmiljö konfigurerad, inklusive Visual Studio eller någon annan IDE som du väljer.

3. Grundläggande kunskaper i C#: Bekantskap med programmeringsspråket C# är bra, eftersom vi kommer att skriva C#-kod för att fungera med Aspose.Slides.

Nu ska vi dela upp avancerad diagramanpassning i flera steg för att vägleda dig genom processen.

## Steg 1: Skapa en presentation

Skapa först en ny presentation med Aspose.Slides.

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

I det här steget initierar vi en ny presentation som kommer att innehålla vårt diagram.

## Steg 2: Öppna den första bilden

Gå sedan till den första bilden i presentationen där du vill lägga till diagrammet.

```csharp
// Åtkomst till den första bilden
ISlide slide = pres.Slides[0];
```

Det här kodavsnittet låter dig arbeta med den första bilden i presentationen.

## Steg 3: Lägga till ett exempeldiagram

Nu ska vi lägga till ett exempeldiagram i bilden. I det här exemplet skapar vi ett linjediagram med markörer.

```csharp
// Lägga till exempeldiagrammet
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Här anger vi diagramtypen (LineWithMarkers) och dess position och dimensioner på bilden.

## Steg 4: Ställa in diagrammets titel

Låt oss ange en titel för diagrammet för att ge sammanhang.

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

Den här koden anger en titel för diagrammet och anger dess text, utseende och teckensnitt.

## Steg 5: Anpassa huvudrutnätslinjer

Nu ska vi anpassa de huvudsakliga rutnätslinjerna för värdeaxeln.

```csharp
// Ställa in format för huvudrutnät för värdeaxel
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Det här steget konfigurerar utseendet på huvudrutnätslinjerna på värdeaxeln.

## Steg 6: Anpassa mindre rutnät

På samma sätt kan vi anpassa de mindre rutnätslinjerna för värdeaxeln.

```csharp
// Ställa in format för mindre rutnät för värdeaxel
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Den här koden justerar utseendet på mindre rutnätslinjer på värdeaxeln.

## Steg 7: Definiera värdeaxelns talformat

Anpassa talformatet för värdeaxeln.

```csharp
// Inställning av värdeaxelns talformat
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

I det här steget kan du formatera talen som visas på värdeaxeln.

## Steg 8: Ställ in diagrammets max- och lägsta värden

Definiera max- och minimivärdena för diagrammet.

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

Här anger du det värdeintervall som diagramaxeln ska visa.

## Steg 9: Anpassa textegenskaper för värdeaxeln

Du kan också anpassa textegenskaperna för värdeaxeln.

```csharp
// Inställning av värdeaxeltextegenskaper
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Den här koden låter dig justera teckensnittet och utseendet på värdeaxeletiketterna.

## Steg 10: Lägg till värdeaxeltitel

Om ditt diagram kräver en titel för värdeaxeln kan du lägga till den i det här steget.

```csharp
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

det här steget kan du ange en titel för värdeaxeln.

## Steg 11: Anpassa huvudrutnätslinjer för kategoriaxeln

Låt oss nu fokusera på de viktigaste rutnätslinjerna för kategoriaxeln.

```csharp
// Ställa in format för huvudrutnät för kategoriaxel
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Den här koden konfigurerar utseendet på större rutnätslinjer på kategoriaxeln.

## Steg 12: Anpassa mindre rutnätslinjer för kategoriaxeln

I likhet med värdeaxeln kan du anpassa de mindre rutnätslinjerna för kategoriaxeln.

```csharp
// Ställa in format för mindre rutnät för kategoriaxel
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Här justerar du utseendet på mindre rutnätslinjer på kategoriaxeln.

## Steg 13: Anpassa textegenskaper för kategoriaxeln

Anpassa textegenskaperna för kategoriaxeletiketterna.

```csharp
// Ställa in textegenskaper för kategoriaxeln
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Den här koden låter dig justera teckensnittet och utseendet på kategoriaxeletiketterna.

## Steg 14: Lägg till kategoriaxeltitel

Du kan också lägga till en titel på kategoriaxeln om det behövs.

```csharp
// Inställning av kategorititel
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

det här steget kan du ange en titel för kategoriaxeln.

## Steg 15: Ytterligare anpassningar

Du kan utforska ytterligare anpassningar, som till exempel förklaringar, diagrammets bakvägg, golv och plottområdesfärger. Dessa anpassningar låter dig förbättra diagrammets visuella attraktionskraft.

```csharp
// Ytterligare anpassningar (valfritt)

// Ställa in egenskaper för förklaringar
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ställ in att visa diagramförklaringar utan överlappande diagram
chart.Legend.Overlay = true;

// Rita första serien på sekundär värdeaxel (vid behov)
// Diagram.DiagramData.Serie[0].PlottPåAndraAxis = sant;

// Sättningstabell för bakväggsfärg
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Färg på golvet i diagrammet
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Ställa in färgen på ritningsområdet
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Spara presentationen
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Dessa ytterligare anpassningar är valfria och kan tillämpas baserat på dina specifika krav för diagramdesign.

## Slutsats

den här steg-för-steg-guiden har vi utforskat avancerad diagramanpassning med Aspose.Slides för .NET. Du har lärt dig hur du skapar en presentation, lägger till ett diagram och finjusterar dess utseende, inklusive rutnät, axeletiketter och andra visuella element. Med de kraftfulla anpassningsalternativen som Aspose.Slides erbjuder kan du skapa diagram som effektivt förmedlar dina data och engagerar din publik.

Om du har några frågor eller stöter på några utmaningar när du arbetar med Aspose.Slides för .NET, kan du gärna utforska dokumentationen. [här](https://reference.aspose.com/slides/net/) eller sök hjälp i Aspose.Slides [forum](https://forum.aspose.com/).

## Vanliga frågor

### Vilka versioner av .NET stöds av Aspose.Slides för .NET?
Aspose.Slides för .NET stöder olika .NET-versioner, inklusive .NET Framework och .NET Core. Du kan läsa dokumentationen för en komplett lista över versioner som stöds.

### Kan jag skapa diagram från datakällor som Excel-filer med hjälp av Aspose.Slides för .NET?
Ja, Aspose.Slides för .NET låter dig skapa diagram från externa datakällor som Excel-kalkylblad. Du kan utforska dokumentationen för detaljerade exempel.

### Hur kan jag lägga till anpassade dataetiketter i min diagramserie?
För att lägga till anpassade dataetiketter i din diagramserie kan du komma åt `DataLabels` egenskapen för serien och anpassa etiketterna efter behov. Se dokumentationen för kodexempel och exempel.

### Är det möjligt att exportera diagrammet till olika filformat, till exempel PDF eller bildformat?
Ja, Aspose.Slides för .NET erbjuder alternativ för att exportera din presentation med diagram till olika format, inklusive PDF- och bildformat. Du kan använda biblioteket för att spara ditt arbete i önskat utdataformat.

### Var kan jag hitta fler handledningar och exempel för Aspose.Slides för .NET?
Du hittar en mängd handledningar, kodexempel och dokumentation på Aspose.Slides. [webbplats](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}