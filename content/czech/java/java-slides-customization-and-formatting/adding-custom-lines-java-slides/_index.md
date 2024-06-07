---
title: Přidání vlastních čar do snímků Java
linktitle: Přidání vlastních čar do snímků Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete své snímky Java pomocí vlastních čar. Průvodce krok za krokem pomocí Aspose.Slides pro Java. Naučte se přidávat a přizpůsobovat čáry v prezentacích pro působivé vizuály.
type: docs
weight: 10
url: /cs/java/customization-and-formatting/adding-custom-lines-java-slides/
---

## Úvod do přidávání vlastních čar v Java Slides

tomto tutoriálu se naučíte, jak přidat vlastní čáry do vašich snímků Java pomocí Aspose.Slides for Java. Vlastní čáry lze použít k vylepšení vizuální reprezentace vašich snímků a zvýraznění konkrétního obsahu. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, jak toho dosáhnout. Začněme!

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nastavenou knihovnu Aspose.Slides pro Javu. Knihovnu si můžete stáhnout z webu:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## Krok 1: Inicializujte prezentaci

Nejprve musíte vytvořit novou prezentaci. V tomto příkladu vytvoříme prázdnou prezentaci.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf

Dále na snímek přidáme graf. V tomto příkladu přidáváme seskupený sloupcový graf. Můžete si vybrat typ grafu, který vyhovuje vašim potřebám.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## Krok 3: Přidejte vlastní řádek

 Nyní do grafu přidáme vlastní čáru. Vytvoříme`IAutoShape` typu`ShapeType.Line` a umístěte jej do grafu.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Krok 4: Přizpůsobte čáru

Vzhled čáry můžete upravit nastavením jejích vlastností. V tomto příkladu nastavujeme barvu čáry na červenou.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 5: Uložte prezentaci

Nakonec prezentaci uložte na požadované místo.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro přidání vlastních řádků v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Gratulujeme! Úspěšně jste přidali vlastní řádek do snímku Java pomocí Aspose.Slides for Java. Vlastnosti čáry můžete dále upravit, abyste dosáhli požadovaných vizuálních efektů.

## FAQ

### Jak změním barvu čáry?

Chcete-li změnit barvu čáry, použijte následující kód:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 Nahradit`YOUR_COLOR` s požadovanou barvou.

### Mohu přidat vlastní čáry k jiným tvarům?

 Ano, můžete přidat vlastní čáry do různých tvarů, nejen do grafů. Jednoduše vytvořte`IAutoShape` a přizpůsobte si jej podle svých potřeb.

### Jak mohu změnit tloušťku čáry?

 Tloušťku čáry můžete změnit nastavením`Width` vlastnost formátu řádku. Například:
```java
shape.getLineFormat().setWidth(2); // Nastavte tloušťku čáry na 2 body
```

### Je možné na snímek přidat více řádků?

Ano, na snímek můžete přidat více řádků opakováním kroků uvedených v tomto návodu. Každý řádek může být přizpůsoben nezávisle.