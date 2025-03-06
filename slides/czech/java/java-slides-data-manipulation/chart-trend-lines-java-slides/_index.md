---
title: Graf trendových čar v Java Slides
linktitle: Graf trendových čar v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat různé trendové čáry do Java Slides pomocí Aspose.Slides for Java. Podrobný průvodce s příklady kódu pro efektivní vizualizaci dat.
weight: 15
url: /cs/java/data-manipulation/chart-trend-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Graf trendových čar v Java Slides


## Úvod do trendových linií grafu v Java Slides: Průvodce krok za krokem

V tomto komplexním průvodci prozkoumáme, jak vytvořit graf trendových čar v Java Slides pomocí Aspose.Slides pro Java. Graf trendů může být cenným doplňkem vašich prezentací, pomáhá efektivně vizualizovat a analyzovat datové trendy. Provedeme vás procesem s jasnými vysvětleními a příklady kódu.

## Předpoklady

Než se pustíme do vytváření trendových čar grafu, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí Java
- Aspose.Slides pro knihovnu Java
- Editor kódu dle vašeho výběru

## Krok 1: Začínáme

Začněme nastavením potřebného prostředí a vytvořením nové prezentace:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Vytváření prázdné prezentace
Presentation pres = new Presentation();
```

Inicializovali jsme naši prezentaci a nyní jsme připraveni přidat seskupený sloupcový graf:

```java
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 2: Přidání exponenciální trendové linie

Začněme přidáním exponenciální trendové linie do naší řady grafů:

```java
// Přidání exponenciální trendové čáry pro grafovou řadu 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Krok 3: Přidání linie lineárního trendu

Dále do naší řady grafů přidáme lineární trendovou linii:

```java
// Přidání lineární trendové linie pro řadu grafů 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 4: Přidání logaritmické trendové linie

Nyní přidejte logaritmickou trendovou linii k jiné řadě grafů:

```java
// Přidání logaritmické trendové linie pro grafovou řadu 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Krok 5: Přidání linie trendu klouzavého průměru

Můžeme také přidat trendovou linii klouzavého průměru:

```java
// Přidání trendové linie klouzavého průměru pro řadu grafů 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Krok 6: Přidání polynomické čáry trendu

Přidání polynomické trendové čáry:

```java
// Přidání polynomické trendové čáry pro řadu grafů 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Krok 7: Přidání čáry trendu výkonu

Nakonec přidáme linii trendu výkonu:

```java
// Přidání čáry trendu výkonu pro řadu grafů 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Krok 8: Uložení prezentace

Nyní, když jsme do našeho grafu přidali různé trendové čáry, uložme prezentaci:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste vytvořili prezentaci s různými typy trendových čar v Java Slides pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro čáry trendu grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Vytváření prázdné prezentace
Presentation pres = new Presentation();
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Přidání čáry ponenciálního trendu pro řadu grafů 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Přidání linie lineárního trendu pro řadu grafů 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Přidání logaritmické trendové linie pro grafovou řadu 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Přidání trendové linie MovingAverage pro řadu grafů 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Přidání polynomické trendové čáry pro řadu grafů 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Přidání spojnice trendu výkonu pro řadu grafů 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Ukládání prezentace
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jsme se naučili, jak přidat různé typy trendových čar do grafů v Java Slides pomocí knihovny Aspose.Slides for Java. Ať už pracujete na analýze dat nebo vytváříte informativní prezentace, schopnost vizualizace trendů může být mocným nástrojem.

## FAQ

### Jak změním barvu trendové čáry v Aspose.Slides pro Java?

 Chcete-li změnit barvu trendové čáry, můžete použít`getSolidFillColor().setColor(Color)` metoda, jak je ukázáno v příkladu pro přidání lineární trendové linie.

### Mohu přidat více trendových čar do jedné řady grafu?

Ano, do jedné řady grafu můžete přidat více trendových čar. Jednoduše zavolejte na`getTrendLines().add()` metoda pro každou trendovou linii, kterou chcete přidat.

### Jak odstraním spojnici trendu z grafu v Aspose.Slides for Java?

 Chcete-li odstranit trendovou čáru z grafu, můžete použít`removeAt(int index)` určující index spojnice trendu, kterou chcete odstranit.

### Je možné přizpůsobit zobrazení rovnice trendové čáry?

 Ano, zobrazení rovnice trendové čáry můžete přizpůsobit pomocí`setDisplayEquation(boolean)` způsobem, jak je ukázáno v příkladu.

### Jak mohu získat přístup k dalším zdrojům a příkladům pro Aspose.Slides pro Java?

 Máte přístup k dalším zdrojům, dokumentaci a příkladům pro Aspose.Slides for Java na[Aspose webové stránky](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
