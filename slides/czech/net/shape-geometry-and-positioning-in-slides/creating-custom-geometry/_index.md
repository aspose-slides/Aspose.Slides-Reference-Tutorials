---
title: Vytváření vlastní geometrie v C# pomocí Aspose.Slides pro .NET
linktitle: Vytváření vlastní geometrie v Geometry Shape pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se vytvářet vlastní geometrii v Aspose.Slides pro .NET. Vylepšete své prezentace jedinečnými tvary. Podrobný průvodce pro vývojáře C#.
weight: 15
url: /cs/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytváření vlastní geometrie v C# pomocí Aspose.Slides pro .NET

## Úvod
dynamickém světě prezentací může přidání jedinečných tvarů a geometrií pozvednout váš obsah a učinit jej poutavějším a vizuálně přitažlivějším. Aspose.Slides for .NET poskytuje výkonné řešení pro vytváření vlastních geometrií v rámci tvarů, což vám umožní osvobodit se od konvenčních návrhů. Tento tutoriál vás provede procesem vytváření vlastní geometrie v GeometryShape pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Knihovna Aspose.Slides for .NET nainstalovaná ve vašem vývojovém prostředí.
- Nastavení sady Visual Studio nebo jakéhokoli preferovaného vývojového prostředí C#.
## Importovat jmenné prostory
Chcete-li začít, importujte potřebné jmenné prostory do svého projektu C#:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Krok 1: Nastavte svůj projekt
Vytvořte nový projekt C# ve vámi preferovaném vývojovém prostředí. Ujistěte se, že Aspose.Slides for .NET je správně nainstalován.
## Krok 2: Definujte svůj adresář dokumentů
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 3: Nastavte vnější a vnitřní poloměr hvězdy
```csharp
float R = 100, r = 50; // Vnější a vnitřní poloměr hvězdy
```
## Krok 4: Vytvořte geometrickou dráhu hvězdy
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Krok 5: Vytvořte prezentaci
```csharp
using (Presentation pres = new Presentation())
{
    // Vytvořte nový tvar
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Nastavte novou geometrickou cestu tvaru
    shape.SetGeometryPath(starPath);
    // Uložte prezentaci
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Krok 6: Definujte metodu CreateStarGeometry
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
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vytvořit vlastní geometrii v GeometryShape pomocí Aspose.Slides for .NET. To otevírá svět možností pro vytváření jedinečných a vizuálně úžasných prezentací.
## Nejčastější dotazy
### 1. Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Ano, Aspose.Slides podporuje různé programovací jazyky, ale tento tutoriál se zaměřuje na C#.
### 2. Kde najdu dokumentaci k Aspose.Slides pro .NET?
 Navštivte[dokumentace](https://reference.aspose.com/slides/net/) pro podrobné informace.
### 3. Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?
 Ano, můžete prozkoumat a[zkušební verze zdarma](https://releases.aspose.com/) zažít funkce.
### 4. Jak mohu získat podporu pro Aspose.Slides pro .NET?
 Vyhledejte pomoc a zapojte se do komunity na adrese[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Kde mohu zakoupit Aspose.Slides pro .NET?
 Můžete si koupit Aspose.Slides pro .NET[tady](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
