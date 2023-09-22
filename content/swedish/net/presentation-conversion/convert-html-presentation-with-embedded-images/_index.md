---
title: Konvertera HTML-presentation med inbäddade bilder
linktitle: Konvertera HTML-presentation med inbäddade bilder
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Konvertera HTML-presentationer med inbäddade bilder utan ansträngning med Aspose.Slides för .NET. Skapa, anpassa och spara PowerPoint-filer sömlöst.
type: docs
weight: 11
url: /sv/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---

## 1. Introduktion

Aspose.Slides för .NET ger ett bekvämt sätt att konvertera PowerPoint-presentationer till HTML5-format samtidigt som inbäddade bilder bevaras. Detta kan vara otroligt användbart för att visa dina presentationer på webbplatser eller i webbapplikationer.

## 2. Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar på plats:

- Visual Studio eller någon C#-utvecklingsmiljö.
- Aspose.Slides för .NET-bibliotek.
- Ett exempel på PowerPoint-presentation med inbäddade bilder.
- Grundläggande kunskaper i C#-programmering.

## 3. Konfigurera ditt projekt

Börja med att skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö. Se till att du har korrekt referens till Aspose.Slides för .NET-biblioteket i ditt projekt.

## 4. Laddar källpresentationen

```csharp
string dataDir = "Your Document Directory";
string presentationName = Path.Combine(dataDir, "PresentationDemo.pptx");

using (Presentation pres = new Presentation(presentationName))
{
    // Din kod för att bearbeta presentationen går här
}
```

## 5. Konfigurera HTML-konverteringsalternativ

 För att konfigurera HTML-konverteringsalternativ kan du använda`Html5Options` klass. Här är ett exempel på hur du ställer in några alternativ:

```csharp
Html5Options options = new Html5Options()
{
    EmbedImages = false, // Spara inte bilder i HTML5-dokument
    OutputPath = "Your Output Directory" // Ställ in sökvägen för externa bilder
};
```

## 6. Skapa utdatakatalogen

Innan du sparar presentationen i HTML5-format är det bra att skapa utdatakatalogen om den inte redan finns:

```csharp
string outFilePath = Path.Combine(outPath, "HTMLConversion");

if (!Directory.Exists(outFilePath))
{
    Directory.CreateDirectory(outFilePath);
}
```

## 7. Spara presentationen i HTML5-format

Låt oss nu spara presentationen i HTML5-format:

```csharp
pres.Save(Path.Combine(outFilePath, "pres.html"), SaveFormat.Html5, options);
```

## 8. Slutsats

Grattis! Du har framgångsrikt konverterat en PowerPoint-presentation med inbäddade bilder till HTML5-format med Aspose.Slides för .NET. Detta kan vara ett värdefullt verktyg för att dela dina presentationer online.

## 9. Vanliga frågor

**Q1: Can I customize the appearance of the HTML5 presentation?**
Ja, du kan anpassa utseendet genom att ändra HTML- och CSS-filerna som genereras av Aspose.Slides.

**Q2: Does Aspose.Slides for .NET support other output formats?**
Ja, det stöder olika utdataformat, inklusive PDF, bilder och mer.

**Q3: Are there any limitations to converting presentations with embedded images?**
Även om Aspose.Slides för .NET är kraftfullt, kan du stöta på vissa begränsningar med mycket komplexa presentationer.

**Q4: Is Aspose.Slides for .NET compatible with the latest PowerPoint versions?**
Ja, det är kompatibelt med PowerPoint-filer från olika versioner, inklusive de senaste.

**Q5: Where can I find more documentation and resources for Aspose.Slides for .NET?**
 För omfattande dokumentation och resurser, besök[Aspose.Slides för .NET-dokumentation](https://reference.aspose.com/slides/net/).