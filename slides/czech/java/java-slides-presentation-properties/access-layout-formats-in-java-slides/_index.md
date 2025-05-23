---
"description": "Naučte se, jak přistupovat k formátům rozvržení a manipulovat s nimi v Java Slides pomocí Aspose.Slides pro Javu. Snadno si upravte styly tvarů a čar v prezentacích PowerPoint."
"linktitle": "Přístup k formátům rozvržení v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přístup k formátům rozvržení v Javě Slides"
"url": "/cs/java/presentation-properties/access-layout-formats-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přístup k formátům rozvržení v Javě Slides


## Úvod do formátů rozvržení Accessu v aplikaci Java Slides

tomto tutoriálu se podíváme na to, jak přistupovat k formátům rozvržení v aplikaci Java Slides a jak s nimi pracovat pomocí rozhraní Aspose.Slides for Java API. Formáty rozvržení umožňují ovládat vzhled tvarů a čar v rámci snímků rozvržení prezentace. Probereme, jak načíst formáty výplní a formáty čar pro tvary na snímcích rozvržení.

## Předpoklady

1. Aspose.Slides pro knihovnu Java.
2. Prezentace v PowerPointu (formát PPTX) s rozvržením snímků.

## Krok 1: Načtení prezentace

Nejprve musíme načíst prezentaci PowerPointu, která obsahuje snímky s rozvržením. Nahraďte `"Your Document Directory"` se skutečnou cestou k adresáři dokumentů.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "pres.pptx");
```

## Krok 2: Přístup k formátům rozvržení

Nyní si projdeme snímky rozvržení v prezentaci a zpřístupníme formáty výplní a formáty čar tvarů na každém snímku rozvržení.

```java
try
{
    for (ILayoutSlide layoutSlide : pres.getLayoutSlides())
    {
        // Přístup k formátům výplní tvarů
        IFillFormat[] fillFormats = new IFillFormat[layoutSlide.getShapes().size()];
        int i = 0;
        for (IShape shape : layoutSlide.getShapes())
        {
            fillFormats[i] = shape.getFillFormat();
            i++;
        }
        
        // Formáty tvarů s přístupovými řádky
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

Ve výše uvedeném kódu:

- Procházíme každým snímkem rozvržení pomocí `for` smyčka.
- Pro každý snímek rozvržení vytváříme pole pro ukládání formátů výplní a formátů čar pro tvary na daném snímku.
- Používáme vnořené `for` smyčky pro iterování tvarů na snímku rozvržení a načtení jejich formátů výplně a čar.

## Krok 3: Práce s formáty rozvržení

Nyní, když máme přístup k formátům výplně a formátům čar pro tvary na snímcích rozvržení, můžete s nimi podle potřeby provádět různé operace. Můžete například změnit barvu výplně, styl čáry nebo jiné vlastnosti tvarů.

## Kompletní zdrojový kód pro formáty rozvržení Accessu v Javě Slides

```java
// Cesta k adresáři s dokumenty.
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

V tomto tutoriálu jsme prozkoumali, jak přistupovat k formátům rozvržení v Java Slides a jak s nimi manipulovat pomocí rozhraní Aspose.Slides for Java API. Formáty rozvržení jsou nezbytné pro ovládání vzhledu tvarů a čar v rámci rozvržených snímků v prezentacích PowerPointu.

## Často kladené otázky

### Jak změním barvu výplně tvaru?

Chcete-li změnit barvu výplně tvaru, můžete použít `IFillFormat` metody objektu. Zde je příklad:

```java
IFillFormat fillFormat = shape.getFillFormat();
fillFormat.setFillType(FillType.Solid); // Nastavit typ výplně na plnou barvu
fillFormat.getSolidFillColor().setColor(Color.RED); // Nastavte barvu výplně na červenou
```

### Jak změním styl čáry tvaru?

Chcete-li změnit styl čáry tvaru, můžete použít `ILineFormat` metody objektu. Zde je příklad:

```java
ILineFormat lineFormat = shape.getLineFormat();
lineFormat.setStyle(LineStyle.Single); // Nastavit styl čáry na jednoduchou
lineFormat.setWidth(2.0); // Nastavit šířku čáry na 2,0 bodu
lineFormat.getSolidFillColor().setColor(Color.BLUE); // Nastavit barvu čáry na modrou
```

### Jak aplikuji tyto změny na tvar na snímku s rozvržením?

Chcete-li tyto změny použít na konkrétní tvar na snímku s rozvržením, můžete k tvaru přistupovat pomocí jeho indexu v kolekci tvarů snímku s rozvržením. Například:

```java
IShape shape = layoutSlide.getShapes().get_Item(0); // Přístup k prvnímu tvaru na snímku rozvržení
```

Pak můžete použít `IFillFormat` a `ILineFormat` metody, jak je uvedeno v předchozích odpovědích, pro úpravu formátů výplně a čar tvaru.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}