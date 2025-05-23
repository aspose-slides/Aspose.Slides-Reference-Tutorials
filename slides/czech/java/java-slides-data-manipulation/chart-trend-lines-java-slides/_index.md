---
"description": "Naučte se, jak přidat různé trendové linie do Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod s příklady kódu pro efektivní vizualizaci dat."
"linktitle": "Trendové linie grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Trendové linie grafů v Javě Slides"
"url": "/cs/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Trendové linie grafů v Javě Slides


## Úvod do trendových linií grafů v Javě Slides: Podrobný průvodce

tomto komplexním průvodci se podíváme na to, jak vytvářet trendové čáry grafů v Java Slides pomocí Aspose.Slides pro Javu. Trendové čáry grafů mohou být cenným doplňkem vašich prezentací a pomáhají efektivně vizualizovat a analyzovat trendy v datech. Provedeme vás celým procesem s jasným vysvětlením a příklady kódu.

## Předpoklady

Než se pustíme do vytváření trendových linií grafu, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí v Javě
- Aspose.Slides pro knihovnu Java
- Editor kódu dle vašeho výběru

## Krok 1: Začínáme

Začněme nastavením potřebného prostředí a vytvořením nové prezentace:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Vytvoření prázdné prezentace
Presentation pres = new Presentation();
```

Inicializovali jsme naši prezentaci a nyní jsme připraveni přidat klastrovaný sloupcový graf:

```java
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 2: Přidání exponenciální trendové linie

Začněme přidáním exponenciální trendové linie do naší série grafů:

```java
// Přidání exponenciální trendové linie pro sérii grafů 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Krok 3: Přidání lineární trendové linie

Dále do naší série grafů přidáme lineární trendovou linii:

```java
// Přidání lineární trendové linie pro sérii grafů 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 4: Přidání logaritmické trendové linie

Nyní přidejme logaritmickou trendovou linii do jiné série grafů:

```java
// Přidání logaritmické trendové linie pro sérii grafů 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Krok 5: Přidání trendové linie klouzavého průměru

Můžeme také přidat trendovou linii klouzavého průměru:

```java
// Přidání trendové linie klouzavého průměru pro sérii grafů 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Krok 6: Přidání polynomiální trendové linie

Přidání polynomiální trendové linie:

```java
// Přidání polynomiální trendové linie pro sérii grafů 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Krok 7: Přidání trendové linie výkonu

Nakonec přidejme trendovou linii síly:

```java
// Přidání trendové linie síly pro sérii grafů 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Krok 8: Uložení prezentace

Nyní, když jsme do našeho grafu přidali různé trendové linie, uložme prezentaci:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste vytvořili prezentaci s různými typy trendových linií v Java Slides pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro trendové čáry grafu v Javě - Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Vytvoření prázdné prezentace
Presentation pres = new Presentation();
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Přidání potenciální trendové linie pro sérii grafů 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Přidání lineární trendové linie pro sérii grafů 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Přidání logaritmické trendové linie pro sérii grafů 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Přidání trendové linie klouzavého průměru pro sérii grafů 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Přidání polynomiální trendové linie pro sérii grafů 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Přidání trendové linie výkonu pro sérii grafů 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Ukládání prezentace
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jsme se naučili, jak přidávat různé typy trendových čar do grafů v Java Slides pomocí knihovny Aspose.Slides pro Javu. Ať už pracujete na analýze dat nebo vytváříte informativní prezentace, schopnost vizualizovat trendy může být mocným nástrojem.

## Často kladené otázky

### Jak změním barvu trendové čáry v Aspose.Slides pro Javu?

Chcete-li změnit barvu trendové linie, můžete použít `getSolidFillColor().setColor(Color)` metodu, jak je znázorněno v příkladu pro přidání lineární trendové linie.

### Mohu do jedné série grafů přidat více trendových linií?

Ano, do jedné série grafů můžete přidat více trendových linií. Jednoduše zavolejte funkci `getTrendLines().add()` metodu pro každou trendovou linii, kterou chcete přidat.

### Jak odstraním trendovou čáru z grafu v Aspose.Slides pro Javu?

Chcete-li z grafu odstranit trendovou linii, můžete použít `removeAt(int index)` metodu s uvedením indexu trendové linie, kterou chcete odstranit.

### Je možné přizpůsobit zobrazení rovnice trendové čáry?

Ano, zobrazení rovnice trendové čáry si můžete přizpůsobit pomocí `setDisplayEquation(boolean)` metodu, jak je ukázáno v příkladu.

### Jak mohu získat přístup k dalším zdrojům a příkladům pro Aspose.Slides pro Javu?

Další zdroje, dokumentaci a příklady pro Aspose.Slides pro Javu naleznete na [Webové stránky Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}