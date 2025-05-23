---
"date": "2025-04-16"
"description": "Lär dig hur du ställer in språkattribut för text i former med Aspose.Slides för .NET. Den här guiden beskriver hur du lägger till automatiska former, anger språk-ID&#58;n och sparar presentationer."
"title": "Så här ställer du in språk i PowerPoint-former med hjälp av Aspose.Slides för .NET"
"url": "/sv/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Så här ställer du in språk i PowerPoint-former med hjälp av Aspose.Slides för .NET

den digitala presentationsvärlden kan det vara en utmaning att säkerställa att ditt innehåll är tillgängligt och korrekt formaterat på olika språk. Med Aspose.Slides för .NET kan du enkelt ställa in språkattribut för text i former i PowerPoint-bilder. Den här funktionen är särskilt fördelaktig när du förbereder flerspråkiga dokument eller säkerställer konsekvens i global kommunikation.

**Vad du kommer att lära dig:**
- Lägga till automatiska former och infoga text i dem.
- Ställa in språk-ID för textdelar med Aspose.Slides.
- Spara presentationer med anpassade konfigurationer.

Låt oss dyka in i hur du kan implementera den här funktionen smidigt.

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

- **Bibliotek och beroenden**Du behöver ha Aspose.Slides för .NET installerat. Det här biblioteket är viktigt för att hantera PowerPoint-presentationer i C#.
  
- **Miljöinställningar**En utvecklingsmiljö med .NET Core eller .NET Framework krävs.

- **Kunskapsförkunskaper**Bekantskap med grundläggande C#-programmeringskoncept och förståelse för objektorienterad programmering är meriterande.

## Konfigurera Aspose.Slides för .NET

För att komma igång måste du installera Aspose.Slides-biblioteket. Du kan göra detta med någon av följande metoder:

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**Pakethanterare**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gränssnitt**
Sök efter "Aspose.Slides" och installera den senaste versionen.

### Licensförvärv

Du kan börja med en gratis provperiod genom att ladda ner en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/)För kontinuerlig användning, överväg att köpa en licens via [den här länken](https://purchase.aspose.com/buy).

När du har din installation klar, initiera Aspose.Slides i ditt projekt:

```csharp
using Aspose.Slides;
```

## Implementeringsguide

Nu när vi är konfigurerade, låt oss implementera funktionen för att ställa in språk för formtext.

### Funktionsöversikt: Ställa in språk för formtext

Med den här funktionen kan du ange språk för texten i en PowerPoint-form. Genom att ange språk-ID:t säkerställer du att stavningskontroll och andra språkspecifika funktioner tillämpas korrekt.

#### Steg 1: Initiera presentationen

Börja med att skapa en instans av `Presentation` klass.

```csharp
using (Presentation pres = new Presentation())
{
    // Din kod här
}
```

Detta initierar ett nytt PowerPoint-presentationsobjekt som vi kommer att manipulera.

#### Steg 2: Lägg till automatisk form och textram

Lägg till en rektangelform på din bild och infoga text i den:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Här, `AddAutoShape` lägger till en rektangel till den första bilden. Parametrarna definierar dess position och storlek.

#### Steg 3: Ange språk-ID

Ställ in språket för textdelen i formen:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Detta tilldelar engelska (Storbritannien) som språk för stavningskontroll.

#### Steg 4: Spara presentationen

Slutligen, spara din presentation till en angiven sökväg:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}