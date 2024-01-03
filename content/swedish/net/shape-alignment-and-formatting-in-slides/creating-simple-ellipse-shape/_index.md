---
title: Skapa Ellipse Shape enkelt med Aspose.Slides .NET
linktitle: Skapa enkel ellipsform i presentationsbilder med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du skapar fantastiska ellipsformer i presentationsbilder med Aspose.Slides för .NET. Enkla steg för dynamisk design!
type: docs
weight: 11
url: /sv/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---
## Introduktion
den dynamiska världen av presentationsdesign kan inkorporering av former som ellipser lägga till en touch av kreativitet och professionalism. Aspose.Slides för .NET erbjuder en kraftfull lösning för att manipulera presentationsfiler programmatiskt. Denna handledning guidar dig genom processen att skapa en enkel ellipsform i presentationsbilder med Aspose.Slides för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
-  Aspose.Slides för .NET: Se till att du har installerat Aspose.Slides-biblioteket för .NET. Du kan ladda ner den från[släpper sida](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö på din maskin.
## Importera namnområden
I ditt .NET-projekt börjar du med att importera de nödvändiga namnrymden:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Dessa namnutrymmen tillhandahåller de grundläggande klasserna och metoderna som krävs för att arbeta med presentationsbilder och former.
## Steg 1: Konfigurera presentationen
Börja med att skapa en ny presentation och komma åt den första bilden. Lägg till följande kod för att uppnå detta:
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
// Skapa katalog om den inte redan finns.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instant presentation klass
using (Presentation pres = new Presentation())
{
    // Få den första bilden
    ISlide sld = pres.Slides[0];
```
Den här koden initierar en ny presentation och väljer den första bilden för vidare manipulation.
## Steg 2: Lägg till Ellipse Shape
Låt oss nu lägga till en ellipsform till bilden med hjälp av`AddAutoShape` metod:
```csharp
// Lägg till autoform av ellipstyp
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Denna kodrad skapar en ellipsform vid koordinater (50, 150) med en bredd på 150 enheter och en höjd på 50 enheter.
## Steg 3: Spara presentationen
Slutligen, spara den modifierade presentationen på disk med ett specificerat filnamn med hjälp av följande kod:
```csharp
// Skriv PPTX-filen till disken
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Det här steget säkerställer att dina ändringar kvarstår, och du kan se den resulterande presentationen med den nyligen tillagda ellipsformen.
## Slutsats
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Vanliga frågor
### Kan jag anpassa ellipsformen ytterligare?
Ja, du kan ändra olika egenskaper för ellipsformen, såsom färg, storlek och position, för att möta dina specifika designkrav.
### Är Aspose.Slides kompatibel med de senaste .NET-ramverken?
Ja, Aspose.Slides uppdateras regelbundet för att säkerställa kompatibilitet med de senaste .NET-ramverken.
### Var kan jag hitta fler handledningar och exempel för Aspose.Slides?
 Besök[dokumentation](https://reference.aspose.com/slides/net/) för omfattande guider och exempel.
### Hur kan jag få en tillfällig licens för Aspose.Slides?
 Följ[tillfällig licenslänk](https://purchase.aspose.com/temporary-license/) att begära en tillfällig licens för teständamål.
### Behöver du hjälp eller har specifika frågor?
 Besök[Aspose.Slides supportforum](https://forum.aspose.com/c/slides/11) att få hjälp från samhället och experter.