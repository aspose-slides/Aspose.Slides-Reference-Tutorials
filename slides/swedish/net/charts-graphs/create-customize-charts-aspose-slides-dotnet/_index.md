---
"date": "2025-04-15"
"description": "Lär dig hur du skapar och anpassar diagram med Aspose.Slides för .NET, inklusive hur du visar procentsatser som dataetiketter. Följ den här steg-för-steg-guiden."
"title": "Hur man skapar och anpassar diagram med Aspose.Slides .NET&#5; Visa procentandelar som etiketter"
"url": "/sv/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar och anpassar diagram med Aspose.Slides .NET: Visa procentsatser som etiketter

## Introduktion

Att presentera data effektivt är avgörande inom många områden, och diagram spelar en viktig roll genom att omvandla komplex information till tydliga visuella element. Att skapa det perfekta diagrammet innebär anpassningsuppgifter som att visa procentsatser på etiketter – en uppgift som förenklas med Aspose.Slides för .NET. Detta bibliotek förenklar processen att skapa och modifiera diagram i PowerPoint-presentationer.

den här handledningen lär du dig hur du använder Aspose.Slides för .NET för att skapa ett staplat kolumndiagram från grunden och anpassa det genom att visa procentvärden som dataetiketter. Genom att följa dessa steg förbättrar du dina bilder med exakta och visuellt tilltalande datarepresentationer.

**Vad du kommer att lära dig:**
- Initierar Aspose.Slides för .NET
- Skapa ett staplat kolumndiagram
- Beräkna och visa procentsatser på dataetiketter
- Bästa praxis för att optimera diagramprestanda

Innan vi går in i implementeringen, låt oss se till att du har allt klart för att komma igång.

## Förkunskapskrav

För att följa den här handledningen effektivt, se till att du har:
- **.NET Core SDK** installerat på din maskin.
- Grundläggande förståelse för C# och .NET applikationsutveckling.
- Visual Studio eller liknande IDE för att skriva och köra C#-kod.

Du behöver Aspose.Slides för .NET för att skapa diagram, så se till att det är konfigurerat enligt beskrivningen nedan.

## Konfigurera Aspose.Slides för .NET

Aspose.Slides för .NET är ett kraftfullt bibliotek som låter dig arbeta med PowerPoint-presentationer programmatiskt. Så här lägger du till det i ditt projekt:

### Installation

**.NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Pakethanterarkonsol:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-pakethanterarens användargränssnitt:** 
- Öppna NuGet Package Manager och sök efter "Aspose.Slides". Installera den senaste versionen.

### Licensförvärv

För att fullt ut utnyttja Aspose.Slides, börja med en gratis provperiod. För längre tids användning kan du överväga att skaffa en tillfällig licens eller köpa en från [Aspose](https://purchase.aspose.com/buy)Följ deras riktlinjer för att konfigurera din licens i din projektmiljö.

### Grundläggande initialisering

När den är installerad, initiera `Presentation` klass för att börja skapa bilder:
```csharp
using Aspose.Slides;

// Initiera Presentation-klassen
tPresentation presentation = new Presentation();
```

Nu går vi vidare till att implementera vår funktion för att skapa och anpassa diagram med hjälp av Aspose.Slides för .NET.

## Implementeringsguide

### Skapa ett staplat kolumndiagram

Vårt mål är att skapa ett staplat kolumndiagram och anpassa det genom att visa procentsatser som dataetiketter. Så här gör du:

#### Initiera presentationen

Börja med att skapa en instans av `Presentation`:
```csharp
using Aspose.Slides;

// Initiera Presentation-klassen
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Lägg till ett diagram i bilden

Lägg till ett staplat kolumndiagram till din första bild med angivna koordinater och dimensioner:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Denna linje skapar en `StackedColumn` diagram vid position (20, 20) med bredd och höjd 400.

#### Beräkna totalvärden för procentuell beräkning

För att visa procentsatser, beräkna det totala värdet för varje kategori över alla serier:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Summera värdena för alla serier för varje kategori
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Anpassa dataetiketter för att visa procentvärden

Gå sedan igenom varje serie och anpassa dataetiketterna:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Beräkna procentandel
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Rensa texten för att undvika överlappning
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Konfigurera etikettformat för att dölja standarddataetiketter
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Det här avsnittet beräknar procentandelen för varje datapunkt och ställer in den som en anpassad etikett, vilket säkerställer att det inte finns någon överlappning med standardetiketter.

#### Spara presentationen

Spara slutligen din presentation för att se resultatet:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Praktiska tillämpningar

Att visa procentsatser i diagram kan vara särskilt användbart i scenarier som:
1. **Finansiell rapportering:** Visa portföljfördelningar eller investeringsavkastning som procentandelar.
2. **Försäljningsanalys:** Representera marknadsandelsdata i procent för att belysa prestanda över olika regioner.
3. **Undersökningsresultat:** Visa enkätsvar som procentandelar för bättre visuell jämförelse.
4. **Projektledning:** Använd cirkeldiagram med procentsatser för att illustrera resursfördelning.
5. **Utbildning:** Förklara statistiska begrepp med hjälp av tydliga procentbaserade bilder.

Att integrera dessa anpassade diagram i system som CRM eller ERP kan förbättra dashboards och rapporter, vilket underlättar beslutsprocesser.

## Prestandaöverväganden

När du arbetar med Aspose.Slides för .NET, särskilt med stora datamängder:
- **Minneshantering:** Kassera presentationsobjekt på rätt sätt för att frigöra minne. `using` uttalanden där så är tillämpligt.
- **Effektiv datahantering:** Utför beräkningar utanför loopar när det är möjligt för att minska beräkningskostnaden.
- **Lastbalansering:** För webbapplikationer, se till att serverresurserna är tillräckligt tillhandahållna för samtidiga diagramgenereringsförfrågningar.

## Slutsats

Den här handledningen behandlade hur man skapar och anpassar diagram med Aspose.Slides för .NET genom att visa procentvärden som etiketter. Genom att behärska dessa tekniker kan du förbättra dina presentationer med detaljerade och visuellt tilltalande datarepresentationer.

Som nästa steg, utforska andra diagramtyper och anpassningsalternativ som finns tillgängliga i Aspose.Slides. Experimentera med olika datamängder för att omvandla dem till kraftfulla visuella element som tydligt kommunicerar insikter.

## FAQ-sektion

**F1: Hur hanterar jag stora datamängder när jag skapar diagram med Aspose.Slides för .NET?**
A1: För stora datamängder, optimera beräkningar och använd effektiva minneshanteringstekniker. Bryt ner bearbetningsuppgifter för att undvika minnesöverbelastning.

**F2: Kan jag använda Aspose.Slides för .NET i en webbapplikation?**
A2: Ja, det kan integreras i ASP.NET-applikationer. Säkerställ korrekt serverresursallokering för optimal prestanda.

**F3: Är det möjligt att exportera diagram som skapats med Aspose.Slides till andra format?**
A3: Absolut! Du kan exportera presentationer som innehåller dina anpassade diagram till olika format som PDF och bildfiler med hjälp av bibliotekets funktioner.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}