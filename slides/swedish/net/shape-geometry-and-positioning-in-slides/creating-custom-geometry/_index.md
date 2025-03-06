---
title: Skapa anpassad geometri i C# med Aspose.Slides för .NET
linktitle: Skapa anpassad geometri i geometrisk form med Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig att skapa anpassad geometri i Aspose.Slides för .NET. Lyft dina presentationer med unika former. Steg-för-steg-guide för C#-utvecklare.
weight: 15
url: /sv/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa anpassad geometri i C# med Aspose.Slides för .NET

## Introduktion
den dynamiska presentationsvärlden kan lägga till unika former och geometrier lyfta ditt innehåll, göra det mer engagerande och visuellt tilltalande. Aspose.Slides för .NET tillhandahåller en kraftfull lösning för att skapa anpassade geometrier inom former, så att du kan bryta dig loss från konventionella mönster. Denna handledning guidar dig genom processen att skapa anpassad geometri i en GeometryShape med Aspose.Slides för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En grundläggande förståelse för programmeringsspråket C#.
- Aspose.Slides för .NET-bibliotek installerat i din utvecklingsmiljö.
- Visual Studio eller valfri C#-utvecklingsmiljö som ställs in.
## Importera namnområden
För att komma igång, importera de nödvändiga namnrymden till ditt C#-projekt:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Steg 1: Konfigurera ditt projekt
Skapa ett nytt C#-projekt i din föredragna utvecklingsmiljö. Se till att Aspose.Slides för .NET är korrekt installerat.
## Steg 2: Definiera din dokumentkatalog
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Steg 3: Ställ in yttre och inre stjärnradie
```csharp
float R = 100, r = 50; // Yttre och inre stjärnradie
```
## Steg 4: Skapa Star Geometry Path
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Steg 5: Skapa en presentation
```csharp
using (Presentation pres = new Presentation())
{
    // Skapa ny form
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Ange en ny geometrisk väg till formen
    shape.SetGeometryPath(starPath);
    // Spara presentationen
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Steg 6: Definiera CreateStarGeometry-metoden
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du skapar anpassad geometri i en GeometryShape med Aspose.Slides för .NET. Detta öppnar upp en värld av möjligheter för att skapa unika och visuellt fantastiska presentationer.
## Vanliga frågor
### 1. Kan jag använda Aspose.Slides för .NET med andra programmeringsspråk?
Ja, Aspose.Slides stöder olika programmeringsspråk, men den här handledningen fokuserar på C#.
### 2. Var kan jag hitta dokumentationen för Aspose.Slides för .NET?
 Besök[dokumentation](https://reference.aspose.com/slides/net/) för detaljerad information.
### 3. Finns det en gratis testversion tillgänglig för Aspose.Slides för .NET?
 Ja, du kan utforska en[gratis provperiod](https://releases.aspose.com/) för att uppleva funktionerna.
### 4. Hur kan jag få support för Aspose.Slides för .NET?
 Sök hjälp och engagera dig i samhället på[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### 5. Var kan jag köpa Aspose.Slides för .NET?
 Du kan köpa Aspose.Slides för .NET[här](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
