---
"description": "Vylepšete své prezentace v PowerPointu s Aspose.Slides pro Javu. Naučte se programově upravovat existující grafy. Podrobný návod se zdrojovým kódem pro přizpůsobení grafů."
"linktitle": "Existující graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Existující graf v Javě Slides"
"url": "/cs/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Existující graf v Javě Slides


## Úvod do existujících grafů v Javě pomocí Aspose.Slides pro Javu

tomto tutoriálu si ukážeme, jak upravit existující graf v prezentaci PowerPointu pomocí Aspose.Slides pro Javu. Projdeme si kroky pro změnu dat grafu, názvů kategorií, názvů řad a přidání nové řady do grafu. Ujistěte se, že máte ve svém projektu nastavený Aspose.Slides pro Javu.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1. Knihovna Aspose.Slides pro Javu je součástí vašeho projektu.
2. Existující prezentace v PowerPointu s grafem, který chcete upravit.
3. Nastavení vývojového prostředí v Javě.

## Krok 1: Načtení prezentace

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Krok 2: Přístup ke snímku a grafu

```java
// Přístup k prvnímu snímku
ISlide sld = pres.getSlides().get_Item(0);

// Přístup k grafu na snímku
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Krok 3: Změna dat grafu a názvů kategorií

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;

// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Změna názvů kategorií grafů
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Krok 4: Aktualizace první série grafů

```java
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aktualizovat název série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Aktualizace dat série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Krok 5: Aktualizace druhé série grafů

```java
// Vezměte si druhou sérii grafů
series = chart.getChartData().getSeries().get_Item(1);

// Aktualizovat název série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Aktualizace dat série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Krok 6: Přidání nové série do grafu

```java
// Přidání nové série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Vezměte si třetí sérii grafů
series = chart.getChartData().getSeries().get_Item(2);

// Naplnění dat série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Krok 7: Změna typu grafu

```java
// Změňte typ grafu na Shluklý válec
chart.setType(ChartType.ClusteredCylinder);
```

## Krok 8: Uložení upravené prezentace

```java
// Uložte prezentaci s upraveným grafem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste upravili existující graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Nyní můžete tento kód použít k programovému přizpůsobení grafů ve vašich prezentacích PowerPoint.

## Kompletní zdrojový kód pro existující graf v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation, která představuje soubor PPTX // Vytvoření instance třídy Presentation, která představuje soubor PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Přístup k prvnímu slideMarkeru
ISlide sld = pres.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Změna názvu kategorie grafu
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nyní aktualizujeme data série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Úprava názvu série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Série grafů Take Second
series = chart.getChartData().getSeries().get_Item(1);
// Nyní aktualizujeme data série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Úprava názvu série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nyní přidávám novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Vezměte si 3. sérii grafů
series = chart.getChartData().getSeries().get_Item(2);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Uložit prezentaci s grafem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Závěr

V tomto komplexním tutoriálu jsme se naučili, jak upravit existující graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Dodržováním podrobných pokynů a využitím příkladů zdrojového kódu můžete snadno přizpůsobit a aktualizovat grafy tak, aby splňovaly vaše specifické požadavky. Zde je shrnutí toho, co jsme probrali:

## Často kladené otázky

### Jak mohu změnit typ grafu?

Typ grafu můžete změnit pomocí `chart.setType(ChartType.ChartTypeHere)` metoda. Nahraďte `ChartTypeHere` s požadovaným typem grafu, například `ChartType.ClusteredCylinder` našem příkladu.

### Mohu do série přidat další datové body?

Ano, do série můžete přidat další datové body pomocí `series.getDataPoints().addDataPointForBarSeries(cell)` metoda. Ujistěte se, že jste poskytli správná data buňky.

### Jak aktualizuji názvy kategorií?

Názvy kategorií můžete aktualizovat pomocí `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pro nastavení názvů nových kategorií.

### Jak mohu upravit názvy sérií?

Chcete-li upravit názvy sérií, použijte `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` nastavit názvy nových sérií.

### Existuje způsob, jak odstranit sérii z grafu?

Ano, sérii můžete z grafu odstranit pomocí `chart.getChartData().getSeries().removeAt(index)` metoda, kde `index` je index série, kterou chcete odstranit.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}