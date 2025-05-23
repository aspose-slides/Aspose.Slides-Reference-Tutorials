---
"description": "Vylepšete prezentace v PowerPointu pomocí vlastních stylů písma, velikostí a barev pro jednotlivé legendy v Java Slides pomocí Aspose.Slides pro Javu."
"linktitle": "Vlastnosti písma pro jednotlivé legendy v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vlastnosti písma pro jednotlivé legendy v Javě Slides"
"url": "/cs/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vlastnosti písma pro jednotlivé legendy v Javě Slides


## Úvod do vlastností písma pro jednotlivé legendy v Javě Slides

V tomto tutoriálu se podíváme na to, jak nastavit vlastnosti písma pro jednotlivé legendy v Java Slides pomocí Aspose.Slides pro Javu. Úpravou vlastností písma můžete legendy ve svých prezentacích v PowerPointu učinit vizuálně přitažlivějšími a informativnějšími.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu integrovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

## Krok 1: Inicializace prezentace a přidání grafu

Nejprve začneme inicializací prezentace v PowerPointu a přidáním grafu do ní. V tomto příkladu použijeme jako ilustraci seskupený sloupcový graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // Zbytek kódu jde sem
} finally {
    if (pres != null) pres.dispose();
}
```

Nahradit `"Your Document Directory"` se skutečným adresářem, kde se nachází váš dokument PowerPoint.

## Krok 2: Úprava vlastností písma pro legendu

Nyní si upravme vlastnosti písma pro jednotlivý záznam legendy v grafu. V tomto příkladu se zaměřujeme na druhý záznam legendy (index 1), ale index můžete upravit podle svých specifických požadavků.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Zde je to, co dělá každý řádek kódu:

- `get_Item(1)` načte druhou položku legendy (index 1). Index můžete změnit tak, aby cílil na jinou položku legendy.
- `setFontBold(NullableBool.True)` nastaví písmo na tučné.
- `setFontHeight(20)` nastaví velikost písma na 20 bodů.
- `setFontItalic(NullableBool.True)` nastaví písmo na kurzívu.
- `setFillType(FillType.Solid)` určuje, že text legendy by měl mít plnou výplň.
- `getSolidFillColor().setColor(Color.BLUE)` nastaví barvu výplně na modrou. Můžete nahradit `Color.BLUE` s vámi požadovanou barvou.

## Krok 3: Uložení upravené prezentace

Nakonec upravenou prezentaci uložte do nového souboru, aby se změny zachovaly.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Nahradit `"output.pptx"` s vámi preferovaným názvem výstupního souboru.

To je vše! Úspěšně jste upravili vlastnosti písma pro jednotlivou položku legendy v prezentaci Java Slides pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro vlastnosti písma pro jednotlivé legendy v Javě Slides

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

V tomto tutoriálu jsme se naučili, jak přizpůsobit vlastnosti písma pro jednotlivé legendy v Java Slides pomocí Aspose.Slides pro Javu. Úpravou stylů, velikostí a barev písma můžete vylepšit vizuální atraktivitu a srozumitelnost vašich prezentací v PowerPointu.

## Často kladené otázky

### Jak mohu změnit barvu písma?

Chcete-li změnit barvu písma, použijte `tf.getPortionFormat().getFontColor().setColor(yourColor)` místo změny barvy výplně. Nahraďte `yourColor` s požadovanou barvou písma.

### Jak mohu upravit další vlastnosti legendy?

Můžete upravit různé další vlastnosti legendy, jako je poloha, velikost a formát. Podrobné informace o práci s legendami naleznete v dokumentaci k Aspose.Slides pro Javu.

### Mohu tyto změny použít na více položek legendy?

Ano, můžete procházet položky legendy a aplikovat tyto změny na více položek úpravou indexu v `get_Item(index)` a opakování kódu pro přizpůsobení.

Nezapomeňte po dokončení zlikvidovat prezentační objekt, abyste uvolnili zdroje:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}