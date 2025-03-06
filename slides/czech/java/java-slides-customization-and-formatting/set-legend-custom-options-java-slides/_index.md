---
title: Nastavte vlastní možnosti legendy v aplikaci Java Slides
linktitle: Nastavte vlastní možnosti legendy v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit vlastní možnosti legendy v Java Slides pomocí Aspose.Slides for Java. Přizpůsobte umístění a velikost legendy v grafech PowerPoint.
weight: 14
url: /cs/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod k nastavení vlastních možností legendy v Java Slides

V tomto tutoriálu si ukážeme, jak upravit vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides for Java. Pozici, velikost a další atributy legendy můžete upravit tak, aby vyhovovaly vašim potřebám prezentace.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Aspose.Slides for Java API nainstalováno.
- Nastavení vývojového prostředí Java.

## Krok 1: Importujte potřebné třídy:

```java
// Import Aspose.Slides pro třídy Java
import com.aspose.slides.*;
```

## Krok 2: Zadejte cestu k adresáři dokumentů:

```java
String dataDir = "Your Document Directory";
```

##  Krok 3: Vytvořte instanci souboru`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## Krok 4: Přidejte snímek do prezentace:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Krok 5: Přidejte na snímek seskupený sloupcový graf:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Krok 6. Nastavte vlastnosti legendy:

- Nastavte polohu X legendy (vzhledem k šířce grafu):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Nastavte polohu Y legendy (vzhledem k výšce grafu):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Nastavte šířku legendy (vzhledem k šířce grafu):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Nastavte výšku legendy (vzhledem k výšce grafu):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## Krok 7: Uložte prezentaci na disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

je to! Úspěšně jste přizpůsobili vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro nastavení vlastních možností legendy v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
try
{
	// Získejte referenci na snímek
	ISlide slide = presentation.getSlides().get_Item(0);
	// Přidejte na snímek seskupený sloupcový graf
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Nastavte vlastnosti legendy
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Zápis prezentace na disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Závěr

V tomto tutoriálu jsme se naučili, jak upravit vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Můžete upravit polohu, velikost a další atributy legendy, abyste vytvořili vizuálně přitažlivé a informativní prezentace.

## FAQ

## Jak mohu změnit polohu legendy?

 Chcete-li změnit polohu legendy, použijte`setX` a`setY` metody objektu legendy. Hodnoty jsou určeny relativně k šířce a výšce grafu.

## Jak mohu upravit velikost legendy?

 Velikost legendy můžete upravit pomocí`setWidth` a`setHeight` metody objektu legendy. Tyto hodnoty jsou také relativní k šířce a výšce grafu.

## Mohu upravit další atributy legend?

Ano, můžete přizpůsobit různé atributy legendy, jako je styl písma, ohraničení, barva pozadí a další. Prozkoumejte dokumentaci Aspose.Slides, kde najdete podrobné informace o dalším přizpůsobení legend.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
