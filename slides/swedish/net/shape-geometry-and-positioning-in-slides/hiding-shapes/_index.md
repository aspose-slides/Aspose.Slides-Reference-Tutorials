---
"description": "Lär dig hur du döljer former i PowerPoint-bilder med Aspose.Slides för .NET. Anpassa presentationer programmatiskt med den här steg-för-steg-guiden."
"linktitle": "Dölja former i presentationsbilder med Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Dölj former i PowerPoint med Aspose.Slides .NET-handledning"
"url": "/sv/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dölj former i PowerPoint med Aspose.Slides .NET-handledning

## Introduktion
I presentationernas dynamiska värld är anpassning nyckeln. Aspose.Slides för .NET erbjuder en kraftfull lösning för att manipulera PowerPoint-presentationer programmatiskt. Ett vanligt krav är möjligheten att dölja specifika former i en bild. Den här handledningen guidar dig genom processen att dölja former i presentationsbilder med Aspose.Slides för .NET.
## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
- Aspose.Slides för .NET: Se till att du har Aspose.Slides-biblioteket installerat. Du kan ladda ner det [här](https://releases.aspose.com/slides/net/).
- Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö för .NET.
- Grundläggande kunskaper i C#: Bekanta dig med C# eftersom de kodexempel som ges är i detta språk.
## Importera namnrymder
För att börja arbeta med Aspose.Slides, importera nödvändiga namnrymder i ditt C#-projekt. Detta säkerställer att du har tillgång till nödvändiga klasser och metoder.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Nu ska vi dela upp exempelkoden i flera steg för en tydlig och koncis förståelse.
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt C#-projekt och se till att inkludera Aspose.Slides-biblioteket.
## Steg 2: Skapa en presentation
Instansiera `Presentation` klass, som representerar PowerPoint-filen. Lägg till en bild och hämta en referens till den.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Steg 3: Lägg till former på bilden
Lägg till autoformer i bilden, till exempel rektanglar och månar, med specifika dimensioner.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Steg 4: Dölj former baserat på alternativ text
Ange en alternativ text och dölj former som matchar den här texten.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Steg 5: Spara presentationen
Spara den ändrade presentationen till disk i PPTX-format.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Slutsats
Grattis! Du har lyckats dolda former i din presentation med Aspose.Slides för .NET. Detta öppnar upp en värld av möjligheter för att skapa dynamiska och anpassade bilder programmatiskt.
---
## Vanliga frågor
### Är Aspose.Slides kompatibelt med .NET Core?
Ja, Aspose.Slides stöder .NET Core, vilket ger flexibilitet i din utvecklingsmiljö.
### Kan jag dölja former baserat på andra villkor än alternativ text?
Absolut! Du kan anpassa döljningslogiken baserat på olika attribut som formtyp, färg eller position.
### Var kan jag hitta ytterligare dokumentation för Aspose.Slides?
Utforska dokumentationen [här](https://reference.aspose.com/slides/net/) för djupgående information och exempel.
### Finns tillfälliga licenser tillgängliga för Aspose.Slides?
Ja, du kan få ett tillfälligt körkort [här](https://purchase.aspose.com/temporary-license/) för teständamål.
### Hur kan jag få community-stöd för Aspose.Slides?
Gå med i Aspose.Slides-communityn på [forum](https://forum.aspose.com/c/slides/11) för diskussioner och hjälp.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}