---
title: Aangepaste geometrie maken in C# met Aspose.Slides voor .NET
linktitle: Aangepaste geometrie in geometrische vorm maken met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u aangepaste geometrie maakt in Aspose.Slides voor .NET. Geef uw presentaties een boost met unieke vormen. Stapsgewijze handleiding voor C#-ontwikkelaars.
weight: 15
url: /nl/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aangepaste geometrie maken in C# met Aspose.Slides voor .NET

## Invoering
In de dynamische wereld van presentaties kan het toevoegen van unieke vormen en geometrieën uw inhoud naar een hoger niveau tillen, waardoor deze aantrekkelijker en visueel aantrekkelijker wordt. Aspose.Slides voor .NET biedt een krachtige oplossing voor het maken van aangepaste geometrieën binnen vormen, waardoor u zich kunt losmaken van conventionele ontwerpen. Deze tutorial leidt u door het proces van het maken van aangepaste geometrie in een GeometryShape met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een basiskennis van de programmeertaal C#.
- Aspose.Slides voor .NET-bibliotheek geïnstalleerd in uw ontwikkelomgeving.
- Visual Studio of een andere C#-ontwikkelomgeving van uw voorkeur.
## Naamruimten importeren
Importeer om te beginnen de benodigde naamruimten in uw C#-project:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Stap 1: Stel uw project in
Maak een nieuw C#-project in de ontwikkelomgeving van uw voorkeur. Zorg ervoor dat Aspose.Slides voor .NET correct is geïnstalleerd.
## Stap 2: Definieer uw documentenmap
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Stap 3: Stel de buitenste en binnenste sterradius in
```csharp
float R = 100, r = 50; // Buitenste en binnenste sterradius
```
## Stap 4: Creëer een stergeometriepad
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Stap 5: Maak een presentatie
```csharp
using (Presentation pres = new Presentation())
{
    // Creëer een nieuwe vorm
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Stel een nieuw geometriepad in op de vorm
    shape.SetGeometryPath(starPath);
    // Bewaar de presentatie
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Stap 6: Definieer de CreateStarGeometry-methode
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
## Conclusie
Gefeliciteerd! Je hebt met succes geleerd hoe je aangepaste geometrie kunt maken in een GeometryShape met behulp van Aspose.Slides voor .NET. Dit opent een wereld aan mogelijkheden voor het creëren van unieke en visueel verbluffende presentaties.
## Veelgestelde vragen
### 1. Kan ik Aspose.Slides voor .NET gebruiken met andere programmeertalen?
Ja, Aspose.Slides ondersteunt verschillende programmeertalen, maar deze tutorial richt zich op C#.
### 2. Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
 Bezoek de[documentatie](https://reference.aspose.com/slides/net/) voor gedetailleerde informatie.
### 3. Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 Ja, u kunt een verkennen[gratis proefperiode](https://releases.aspose.com/) om de functies te ervaren.
### 4. Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Zoek hulp en ga in gesprek met de gemeenschap van het[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### 5. Waar kan ik Aspose.Slides voor .NET kopen?
 U kunt Aspose.Slides voor .NET kopen[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
