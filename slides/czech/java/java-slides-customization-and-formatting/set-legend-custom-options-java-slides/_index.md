---
"description": "Naučte se, jak nastavit vlastní možnosti legendy v Java Slides pomocí Aspose.Slides pro Javu. Přizpůsobte si umístění a velikost legendy v grafech PowerPoint."
"linktitle": "Nastavení vlastních možností legendy v prezentaci Java"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení vlastních možností legendy v prezentaci Java"
"url": "/cs/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení vlastních možností legendy v prezentaci Java


## Úvod do nastavení vlastních možností legendy v Javě Slides

tomto tutoriálu si ukážeme, jak přizpůsobit vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Můžete upravit pozici, velikost a další atributy legendy tak, aby vyhovovaly potřebám vaší prezentace.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Nainstalováno rozhraní Aspose.Slides pro Java API.
- Nastavení vývojového prostředí v Javě.

## Krok 1: Importujte potřebné třídy:

```java
// Import Aspose.Slides pro třídy Java
import com.aspose.slides.*;
```

## Krok 2: Zadejte cestu k adresáři s dokumenty:

```java
String dataDir = "Your Document Directory";
```

## Krok 3: Vytvořte instanci `Presentation` třída:

```java
Presentation presentation = new Presentation();
```

## Krok 4: Přidání snímku do prezentace:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## Krok 5: Přidání shlukového sloupcového grafu na snímek:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## Krok 6. Nastavení vlastností legendy:

- Nastavte pozici legendy na ose X (vzhledem k šířce grafu):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Nastavte pozici legendy na ose Y (vzhledem k výšce grafu):

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

## Krok 7: Uložení prezentace na disk:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

To je vše! Úspěšně jste upravili vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro nastavení vlastních možností legendy v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
try
{
	// Získat odkaz na snímek
	ISlide slide = presentation.getSlides().get_Item(0);
	// Přidání seskupeného sloupcového grafu na snímek
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Nastavení vlastností legendy
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Zapsat prezentaci na disk
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Závěr

V tomto tutoriálu jsme se naučili, jak přizpůsobit vlastnosti legendy grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Můžete upravit pozici, velikost a další atributy legendy a vytvořit tak vizuálně přitažlivé a informativní prezentace.

## Často kladené otázky

## Jak mohu změnit pozici legendy?

Chcete-li změnit polohu legendy, použijte `setX` a `setY` metody objektu legendy. Hodnoty jsou zadány vzhledem k šířce a výšce grafu.

## Jak mohu upravit velikost legendy?

Velikost legendy můžete upravit pomocí `setWidth` a `setHeight` metody objektu legendy. Tyto hodnoty jsou také relativní vzhledem k šířce a výšce grafu.

## Mohu si přizpůsobit další atributy legendy?

Ano, můžete si přizpůsobit různé atributy legendy, jako je styl písma, ohraničení, barva pozadí a další. Pro podrobnější informace o dalším přizpůsobení legend si prohlédněte dokumentaci k Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}