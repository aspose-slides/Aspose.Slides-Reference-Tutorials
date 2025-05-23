---
"description": "Vytvořte normální grafy v Javě pomocí Aspose.Slides pro Javu. Podrobný návod a zdrojový kód pro vytváření, úpravu a ukládání grafů v prezentacích PowerPoint."
"linktitle": "Normální grafy v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Normální grafy v Javě Slides"
"url": "/cs/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Normální grafy v Javě Slides


## Úvod do normálních grafů v Javě – Slidy

V tomto tutoriálu si projdeme procesem vytváření normálních grafů v Java Slides pomocí rozhraní Aspose.Slides for Java API. Pomocí podrobných pokynů spolu se zdrojovým kódem si ukážeme, jak vytvořit klastrovaný sloupcový graf v prezentaci v PowerPointu.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Nainstalováno rozhraní Aspose.Slides pro Java API.
2. Nastavení vývojového prostředí v Javě.
3. Základní znalost programování v Javě.

## Krok 1: Nastavení projektu

Ujistěte se, že máte adresář pro svůj projekt. Nazvěme ho „Adresář vašich dokumentů“, jak je uvedeno v kódu. Můžete jej nahradit skutečnou cestou k adresáři vašeho projektu.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## Krok 2: Vytvoření prezentace

Nyní si vytvořme prezentaci v PowerPointu a otevřeme její první snímek.

```java
// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation pres = new Presentation();
// Přístup k prvnímu snímku
ISlide sld = pres.getSlides().get_Item(0);
```

## Krok 3: Přidání grafu

Na snímek přidáme klastrovaný sloupcový graf a nastavíme jeho název.

```java
// Přidat graf s výchozími daty
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Název grafu nastavení
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## Krok 4: Nastavení dat grafu

Dále nastavíme data grafu definováním řad a kategorií.

```java
// Nastavit první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;

// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Smazat výchozí generované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Přidávání nových sérií
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## Krok 5: Naplnění dat série

Nyní naplňme datové body řady pro graf.

```java
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Naplňování dat série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Vezměte si druhou sérii grafů
series = chart.getChartData().getSeries().get_Item(1);

// Naplňování dat série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 6: Přizpůsobení štítků

Pojďme si přizpůsobit popisky dat pro sérii grafů.

```java
// První štítek zobrazí název kategorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// Zobrazit hodnotu pro třetí popisek s názvem série a oddělovačem
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## Krok 7: Uložení prezentace

Nakonec uložte prezentaci s grafem do adresáře projektu.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste vytvořili klastrovaný sloupcový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Tento graf si můžete dále přizpůsobit podle svých požadavků.

## Kompletní zdrojový kód pro normální grafy v Javě - Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Vytvoření instance třídy Presentation, která reprezentuje soubor PPTX
Presentation pres = new Presentation();
// Přístup k prvnímu snímku
ISlide sld = pres.getSlides().get_Item(0);
// Přidat graf s výchozími daty
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Název grafu nastavení
// Chart.getChartTitle().getTextFrameForOverriding().setText("Ukázkový název");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Nastavit první sérii na Zobrazit hodnoty
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Nastavení indexu datového listu grafu
int defaultWorksheetIndex = 0;
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Smazat výchozí generované série a kategorie
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Přidávání nových sérií
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Přidávání nových kategorií
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vezměte si první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Vezměte si druhou sérii grafů
series = chart.getChartData().getSeries().get_Item(1);
// Nyní se naplňují data série
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Nastavení barvy výplně pro sérii
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// První štítek bude zobrazovat název kategorie
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Zobrazit hodnotu pro třetí štítek
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Uložit prezentaci s grafem
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Závěr

V tomto tutoriálu jsme se naučili, jak vytvářet normální grafy v Java Slides pomocí rozhraní Aspose.Slides for Java API. Prošli jsme si podrobný návod se zdrojovým kódem pro vytvoření klastrovaného sloupcového grafu v prezentaci PowerPoint.

## Často kladené otázky

### Jak mohu změnit typ grafu?

Chcete-li změnit typ grafu, upravte `ChartType` parametr při přidávání grafu pomocí `sld.getShapes().addChart()`V Aspose.Slides si můžete vybrat z různých typů grafů.

### Mohu změnit barvy grafické série?

Ano, barvy grafických řad můžete změnit nastavením barvy výplně pro každou řadu pomocí `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Jak mohu do grafu přidat další kategorie nebo série?

Do grafu můžete přidat další kategorie nebo řady přidáním nových datových bodů a popisků pomocí `chart.getChartData().getCategories().add()` a `chart.getChartData().getSeries().add()` metody.

### Jak mohu dále přizpůsobit název grafu?

Název grafu můžete dále přizpůsobit úpravou vlastností `chart.getChartTitle()` jako je zarovnání textu, velikost písma a barva.

### Jak uložím graf do jiného formátu souboru?

Chcete-li graf uložit do jiného formátu souboru, změňte `SaveFormat` parametr v `pres.save()` metodu do požadovaného formátu (např. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}