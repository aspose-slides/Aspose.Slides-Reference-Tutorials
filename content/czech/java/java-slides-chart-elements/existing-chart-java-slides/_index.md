---
title: Stávající graf v Java Slides
linktitle: Stávající graf v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete své prezentace v PowerPointu pomocí Aspose.Slides for Java. Naučte se programově upravovat existující grafy. Podrobný průvodce se zdrojovým kódem pro přizpůsobení grafu.
type: docs
weight: 12
url: /cs/java/chart-elements/existing-chart-java-slides/
---

## Úvod do existujícího grafu v Java Slides pomocí Aspose.Slides pro Java

V tomto tutoriálu si ukážeme, jak upravit existující graf v prezentaci PowerPoint pomocí Aspose.Slides for Java. Projdeme si kroky ke změně dat grafu, názvů kategorií, názvů řad a přidání nové řady do grafu. Ujistěte se, že máte v projektu nastavené Aspose.Slides for Java.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1. Knihovna Aspose.Slides for Java je součástí vašeho projektu.
2. Stávající PowerPoint prezentace s grafem, který chcete upravit.
3. Nastavení vývojového prostředí Java.

## Krok 1: Načtěte prezentaci

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Třída okamžité prezentace, která představuje soubor PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## Krok 2: Otevřete snímek a graf

```java
// Otevřete první snímek
ISlide sld = pres.getSlides().get_Item(0);

// Otevřete graf na snímku
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## Krok 3: Změňte data grafu a názvy kategorií

```java
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;

//Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Změňte názvy kategorií grafu
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## Krok 4: Aktualizujte první řadu grafů

```java
// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aktualizujte název série
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Aktualizujte data série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## Krok 5: Aktualizujte druhou řadu grafů

```java
// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);

// Aktualizujte název série
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Aktualizujte data série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## Krok 6: Přidejte do grafu novou řadu

```java
// Přidání nové série
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Vezměte si třetí sérii grafů
series = chart.getChartData().getSeries().get_Item(2);

// Vyplňte data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## Krok 7: Změňte typ grafu

```java
//Změňte typ grafu na Clustered Cylinder
chart.setType(ChartType.ClusteredCylinder);
```

## Krok 8: Uložte upravenou prezentaci

```java
// Uložte prezentaci s upraveným grafem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulujeme! Úspěšně jste upravili existující graf v prezentaci PowerPoint pomocí Aspose.Slides for Java. Nyní můžete tento kód použít k programovému přizpůsobení grafů v prezentacích PowerPoint.

## Kompletní zdrojový kód pro existující graf v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Třída okamžité prezentace, která představuje soubor PPTX// Třída okamžité prezentace, která představuje soubor PPTX
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Otevřete první slideMarker
ISlide sld = pres.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
//Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Změna názvu kategorie grafu
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nyní se aktualizují údaje o sérii
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Úprava názvu série
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Vezměte druhou řadu grafů
series = chart.getChartData().getSeries().get_Item(1);
// Nyní se aktualizují údaje o sérii
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Úprava názvu série
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Nyní přidáváme novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Vezměte 3. řadu grafů
series = chart.getChartData().getSeries().get_Item(2);
// Nyní se vyplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Uložit prezentaci s grafem
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Závěr

tomto komplexním tutoriálu jsme se naučili, jak upravit existující graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Pokud budete postupovat podle podrobného průvodce a pomocí příkladů zdrojového kódu, můžete snadno přizpůsobit a aktualizovat grafy tak, aby vyhovovaly vašim specifickým požadavkům. Zde je rekapitulace toho, co jsme probrali:

## FAQ

### Jak mohu změnit typ grafu?

 Typ grafu můžete změnit pomocí`chart.setType(ChartType.ChartTypeHere)` metoda. Nahradit`ChartTypeHere` s požadovaným typem grafu, jako je např`ChartType.ClusteredCylinder` v našem příkladu.

### Mohu do série přidat více datových bodů?

 Ano, do řady můžete přidat další datové body pomocí`series.getDataPoints().addDataPointForBarSeries(cell)` metoda. Ujistěte se, že jste poskytli příslušná data buňky.

### Jak aktualizuji názvy kategorií?

 Názvy kategorií můžete aktualizovat pomocí`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pro nastavení nových názvů kategorií.

### Jak upravím názvy seriálů?

 Chcete-li upravit názvy sérií, použijte`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` pro nastavení nových názvů seriálů.

### Existuje způsob, jak odstranit řadu z grafu?

 Ano, řadu můžete z grafu odstranit pomocí`chart.getChartData().getSeries().removeAt(index)` metoda, kde`index`je index řady, kterou chcete odstranit.