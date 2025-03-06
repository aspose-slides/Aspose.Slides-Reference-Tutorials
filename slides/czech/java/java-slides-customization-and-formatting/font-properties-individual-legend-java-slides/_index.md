---
title: Vlastnosti písma pro jednotlivé legendy v Java Slides
linktitle: Vlastnosti písma pro jednotlivé legendy v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete PowerPointové prezentace o vlastní styly písma, velikosti a barvy pro jednotlivé legendy v Java Slides pomocí Aspose.Slides for Java.
weight: 12
url: /cs/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do vlastností písma pro jednotlivé legendy v Java Slides

V tomto tutoriálu prozkoumáme, jak nastavit vlastnosti písma pro jednotlivou legendu v Java Slides pomocí Aspose.Slides pro Java. Přizpůsobením vlastností písma můžete vytvořit své legendy vizuálně přitažlivějšími a informativnějšími v prezentacích PowerPoint.

## Předpoklady

 Než začnete, ujistěte se, že máte do projektu integrovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

## Krok 1: Inicializujte prezentaci a přidejte graf

Nejprve začněme inicializací prezentace PowerPoint a přidáním grafu do ní. V tomto příkladu použijeme jako ilustraci seskupený sloupcový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Zbytek kódu je zde
} finally {
    if (pres != null) pres.dispose();
}
```

 Nahradit`"Your Document Directory"` se skutečným adresářem, kde je umístěn váš PowerPoint dokument.

## Krok 2: Upravte vlastnosti písma pro Legend

Nyní přizpůsobíme vlastnosti písma pro jednotlivé položky legendy v grafu. V tomto příkladu cílíme na druhý záznam legendy (index 1), ale index můžete upravit podle svých konkrétních požadavků.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Zde je to, co dělá každý řádek kódu:

- `get_Item(1)` načte druhý záznam legendy (index 1). Můžete změnit index tak, aby cílil na jinou položku legendy.
- `setFontBold(NullableBool.True)` nastaví písmo na tučné.
- `setFontHeight(20)` nastaví velikost písma na 20 bodů.
- `setFontItalic(NullableBool.True)` nastaví písmo na kurzívu.
- `setFillType(FillType.Solid)` určuje, že text položky legendy by měl mít plnou výplň.
- `getSolidFillColor().setColor(Color.BLUE)` nastaví barvu výplně na modrou. Můžete vyměnit`Color.BLUE` s vámi požadovanou barvou.

## Krok 3: Uložte upravenou prezentaci

Nakonec uložte upravenou prezentaci do nového souboru, abyste zachovali své změny.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Nahradit`"output.pptx"` s preferovaným názvem výstupního souboru.

A je to! Úspěšně jste přizpůsobili vlastnosti písma pro jednotlivé položky legendy v prezentaci Java Slides pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro vlastnosti písma pro jednotlivé legendy v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak upravit vlastnosti písma pro jednotlivou legendu v Java Slides pomocí Aspose.Slides for Java. Úpravou stylů, velikostí a barev písma můžete zvýšit vizuální přitažlivost a jasnost prezentací PowerPoint.

## FAQ

### Jak mohu změnit barvu písma?

 Chcete-li změnit barvu písma, použijte`tf.getPortionFormat().getFontColor().setColor(yourColor)` místo změny barvy výplně. Nahradit`yourColor` s požadovanou barvou písma.

### Jak mohu upravit další vlastnosti legendy?

Můžete upravit různé další vlastnosti legendy, jako je poloha, velikost a formát. Podrobné informace o práci s legendami naleznete v dokumentaci Aspose.Slides for Java.

### Mohu tyto změny použít na více záznamů legendy?

 Ano, můžete procházet záznamy legendy a použít tyto změny na více záznamů úpravou indexu`get_Item(index)` a opakování kódu přizpůsobení.

Nezapomeňte zlikvidovat objekt prezentace, když budete s uvolněním prostředků hotovi:

```java
if (pres != null) pres.dispose();
```
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
