---
title: Přístup k formátům rozvržení v aplikaci Java Slides
linktitle: Přístup k formátům rozvržení v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přistupovat a manipulovat s formáty rozvržení v Java Slides pomocí Aspose.Slides for Java. Přizpůsobte styly tvarů a čar bez námahy v prezentacích PowerPoint.
weight: 10
url: /cs/java/presentation-properties/access-layout-formats-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přístup k formátům rozvržení v aplikaci Java Slides


## Úvod do přístupu k formátům rozložení v Java Slides

V tomto tutoriálu prozkoumáme, jak přistupovat a pracovat s formáty rozložení v Java Slides pomocí Aspose.Slides for Java API. Formáty rozvržení umožňují ovládat vzhled tvarů a čar na snímcích rozvržení prezentace. Budeme se zabývat tím, jak načíst formáty výplně a formáty čar pro tvary na snímcích rozložení.

## Předpoklady

1. Aspose.Slides pro knihovnu Java.
2. PowerPointová prezentace (formát PPTX) s rozložením snímků.

## Krok 1: Načtěte prezentaci

 Nejprve musíme načíst prezentaci PowerPoint, která obsahuje snímky rozložení. Nahradit`"Your Document Directory"` se skutečnou cestou k vašemu adresáři dokumentů.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Krok 2: Přístup k formátům rozložení

Nyní si projdeme snímky rozvržení v prezentaci a zpřístupníme formáty výplně a formáty čar tvarů na každém snímku rozvržení.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Přístup k formátům výplně tvarů
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Přístup k řádkovým formátům tvarů
        ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
        int j = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            lineFormats[j] = shape.getLineFormat();
            j++;
        }
    }
}
finally
{
    if (pres != null) pres.dispose();
}
```

V kódu výše:

- Každý snímek rozvržení iterujeme pomocí a`for` smyčka.
- Pro každý snímek rozvržení vytvoříme pole pro uložení formátů výplně a formátů čar pro obrazce na tomto snímku.
-  Používáme vnořené`for` smyčky pro iteraci tvarů na snímku rozvržení a načtení jejich formátů výplně a čar.

## Krok 3: Práce s formáty rozvržení

Nyní, když jsme se dostali k formátům výplně a formátům čar pro obrazce na snímcích rozvržení, můžete s nimi podle potřeby provádět různé operace. Můžete například změnit barvu výplně, styl čáry nebo jiné vlastnosti tvarů.

## Kompletní zdrojový kód pro přístup k formátům rozložení v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
try
{
	for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
	{
		IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
		int i = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			fillFormats[i] = shape.getFillFormat();
			i++;
		}
		ILineFormat[] lineFormats = new ILineFormat[layoutSlide.getShapes().size()];
		int j = 0;
		for (IShape shape : layoutSlide.getShapes())
		{
			lineFormats[j] = shape.getLineFormat();
			j++;
		}
	}
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak přistupovat k formátům rozvržení v Java Slides a jak s nimi manipulovat pomocí Aspose.Slides for Java API. Formáty rozvržení jsou nezbytné pro ovládání vzhledu tvarů a čar na snímcích rozvržení v prezentacích PowerPoint.

## FAQ

### Jak změním barvu výplně tvaru?

 Chcete-li změnit barvu výplně tvaru, můžete použít`IFillFormat`objektové metody. Zde je příklad:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Nastavte typ výplně na plnou barvu
fillFormat.getSolidFillColor().setColor(Color.RED); // Nastavte barvu výplně na červenou
```

### Jak změním styl čáry tvaru?

 Chcete-li změnit styl čáry tvaru, můžete použít`ILineFormat`objektové metody. Zde je příklad:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Nastavte styl čáry na jeden
lineFormat.setWidth(2.0); // Nastavte šířku čáry na 2,0 bodů
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Nastavte barvu čáry na modrou
```

### Jak tyto změny použiji na tvar na snímku rozložení?

Chcete-li tyto změny použít na konkrétní obrazec na snímku rozvržení, můžete k tvaru přistupovat pomocí jeho indexu v kolekci obrazců snímku rozvržení. Například:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Přístup k prvnímu tvaru na snímku rozvržení
```

 Poté můžete použít`IFillFormat` a`ILineFormat` metody, jak je uvedeno v předchozích odpovědích, k úpravě formátů výplně a čar tvaru.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
