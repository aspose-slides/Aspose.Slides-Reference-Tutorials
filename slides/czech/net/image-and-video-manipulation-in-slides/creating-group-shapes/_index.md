---
title: Aspose.Slides - Vytváření skupinových tvarů v .NET
linktitle: Vytváření skupinových tvarů v prezentačních snímcích pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se vytvářet tvary skupin v PowerPointu pomocí Aspose.Slides pro .NET. Postupujte podle našeho podrobného průvodce pro vizuálně přitažlivé prezentace.
type: docs
weight: 11
url: /cs/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## Úvod
Pokud chcete zvýšit vizuální přitažlivost snímků vaší prezentace a efektivněji organizovat obsah, je začlenění skupinových tvarů výkonným řešením. Aspose.Slides for .NET poskytuje bezproblémový způsob vytváření a manipulace s tvary skupin v prezentacích PowerPoint. V tomto tutoriálu projdeme procesem vytváření skupinových tvarů pomocí Aspose.Slides a rozdělíme jej do snadno pochopitelných kroků.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte pracovní prostředí s IDE kompatibilním s .NET, jako je Visual Studio.
- Základní znalost C#: Seznamte se se základy programovacího jazyka C#.
## Importovat jmenné prostory
Ve svém projektu C# začněte importováním potřebných jmenných prostorů:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Okamžitá prezentace

 Vytvořte instanci souboru`Presentation` třídy a zadejte adresář, kde jsou uloženy vaše dokumenty:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Pokračujte následujícími kroky v rámci tohoto bloku použití
}
```

## Krok 2: Otevřete první snímek

Načtěte první snímek z prezentace:

```csharp
ISlide sld = pres.Slides[0];
```

## Krok 3: Přístup ke kolekci Shape Collection

Přístup ke kolekci tvarů na snímku:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Krok 4: Přidání tvaru skupiny

Přidejte na snímek tvar skupiny:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Krok 5: Přidání tvarů do skupinového tvaru

Vyplňte tvar skupiny jednotlivými tvary:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Krok 6: Přidání rámečku tvaru skupiny

Definujte rámeček pro celý tvar skupiny:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Krok 7: Uložte prezentaci

Uložte upravenou prezentaci do zadaného adresáře:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Opakujte tyto kroky ve vaší aplikaci C#, abyste úspěšně vytvořili tvary skupin ve snímcích prezentace pomocí Aspose.Slides.

## Závěr
V tomto tutoriálu jsme prozkoumali proces vytváření skupinových tvarů pomocí Aspose.Slides pro .NET. Pomocí těchto kroků můžete zlepšit vizuální přitažlivost a organizaci svých prezentací PowerPoint.
## Často kladené otázky
### Je Aspose.Slides kompatibilní s nejnovější verzí .NET?
 Ano, Aspose.Slides je pravidelně aktualizován, aby podporoval nejnovější verze .NET. Zkontrolovat[dokumentace](https://reference.aspose.com/slides/net/) pro podrobnosti o kompatibilitě.
### Mohu vyzkoušet Aspose.Slides před nákupem?
 Absolutně! Můžete si stáhnout bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu podporu pro dotazy související s Aspose.Slides?
Navštivte Aspose.Slides[Fórum](https://forum.aspose.com/c/slides/11) za podporu komunity a diskuze.
### Jak získám dočasnou licenci pro Aspose.Slides?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit plnou licenci pro Aspose.Slides?
 Licenci si můžete zakoupit od[nákupní stránku](https://purchase.aspose.com/buy).
