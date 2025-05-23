---
"description": "Vylepšete své slidy v Javě pomocí vlastních čar. Podrobný návod k použití Aspose.Slides pro Javu. Naučte se přidávat a upravovat čáry v prezentacích pro působivé vizuální efekty."
"linktitle": "Přidávání vlastních řádků do snímků v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidávání vlastních řádků do snímků v Javě"
"url": "/cs/java/customization-and-formatting/adding-custom-lines-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidávání vlastních řádků do snímků v Javě


## Úvod do přidávání vlastních řádků v Javě Slides

V tomto tutoriálu se naučíte, jak přidat vlastní čáry do vašich snímků v Javě pomocí Aspose.Slides pro Javu. Vlastní čáry lze použít k vylepšení vizuální reprezentace vašich snímků a zvýraznění konkrétního obsahu. Poskytneme vám podrobné pokyny spolu se zdrojovým kódem, jak toho dosáhnout. Pojďme na to!

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z webových stránek: [Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/)

## Krok 1: Inicializace prezentace

Nejprve je třeba vytvořit novou prezentaci. V tomto příkladu vytvoříme prázdnou prezentaci.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Dále na snímek přidáme graf. V tomto příkladu přidáváme klastrovaný sloupcový graf. Můžete si vybrat typ grafu, který vyhovuje vašim potřebám.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## Krok 3: Přidání vlastního řádku

Nyní přidáme do grafu vlastní čáru. Vytvoříme `IAutoShape` typu `ShapeType.Line` a umístěte ho do grafu.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## Krok 4: Přizpůsobení čáry

Vzhled čáry můžete přizpůsobit nastavením jejích vlastností. V tomto příkladu nastavujeme barvu čáry na červenou.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 5: Uložte prezentaci

Nakonec prezentaci uložte na požadované místo.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro přidání vlastních řádků do prezentací v Javě

```java
// Cesta k adresáři s dokumenty.
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

Gratulujeme! Úspěšně jste přidali vlastní čáru do svého snímku v Javě pomocí Aspose.Slides pro Javu. Vlastnosti čáry můžete dále přizpůsobit a dosáhnout požadovaných vizuálních efektů.

## Často kladené otázky

### Jak změním barvu čáry?

Chcete-li změnit barvu čáry, použijte následující kód:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

Nahradit `YOUR_COLOR` s požadovanou barvou.

### Mohu přidat vlastní čáry k jiným tvarům?

Ano, můžete přidat vlastní čáry k různým tvarům, nejen k grafům. Jednoduše vytvořte `IAutoShape` a přizpůsobte si ho podle svých potřeb.

### Jak mohu změnit tloušťku čáry?

Tloušťku čáry můžete změnit nastavením `Width` vlastnost formátu řádku. Například:
```java
shape.getLineFormat().setWidth(2); // Nastavit tloušťku čáry na 2 body
```

### Je možné do snímku přidat více řádků?

Ano, na snímek můžete přidat více řádků opakováním kroků uvedených v tomto tutoriálu. Každý řádek lze upravit samostatně.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}