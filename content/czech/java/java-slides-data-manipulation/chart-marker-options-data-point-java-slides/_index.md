---
title: Možnosti značek grafu na datovém bodu v Java Slides
linktitle: Možnosti značek grafu na datovém bodu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimalizujte své snímky Java pomocí vlastních možností značek grafů. Naučte se vylepšovat datové body vizuálně pomocí Aspose.Slides pro Java. Prozkoumejte podrobné pokyny a často kladené dotazy.
type: docs
weight: 14
url: /cs/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Úvod do možností značek grafu na datovém bodu v Java Slides

Pokud jde o vytváření působivých prezentací, schopnost přizpůsobit a manipulovat se značkami grafu v datových bodech může znamenat velký rozdíl. S Aspose.Slides for Java máte možnost přeměnit své grafy na dynamické a vizuálně poutavé prvky.

## Předpoklady

Než se ponoříme do kódovací části, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí Java
- Aspose.Slides pro knihovnu Java
- Java Integrated Development Environment (IDE)
- Vzorový prezentační dokument (např. "Test.pptx")

## Krok 1: Nastavení prostředí

Nejprve se ujistěte, že máte nainstalované a připravené potřebné nástroje. Vytvořte Java projekt ve vašem IDE a importujte knihovnu Aspose.Slides for Java.

## Krok 2: Načtení prezentace

Chcete-li začít, načtěte vzorový dokument prezentace. V poskytnutém kódu předpokládáme, že se dokument jmenuje "Test.pptx."

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Krok 3: Vytvoření grafu

Nyní vytvoříme graf v prezentaci. V tomto příkladu použijeme spojnicový graf se značkami.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Krok 4: Práce s daty grafu

Abychom mohli manipulovat s daty grafu, potřebujeme získat přístup k sešitu dat grafu a připravit datové řady. Vymažeme výchozí řadu a přidáme vlastní data.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Krok 5: Přidání vlastních značek

Zde přichází ta vzrušující část – přizpůsobení značek na datových bodech. V tomto příkladu použijeme obrázky jako značky.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Přidání vlastních značek do datových bodů
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Opakujte pro další datové body
// ...

// Změna velikosti značky řady grafu
series.getMarker().setSize(15);
```

## Krok 6: Uložení prezentace

Jakmile si přizpůsobíte značky grafu, uložte prezentaci, abyste viděli změny v akci.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro možnosti značek grafu na datovém bodu v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Vytvoření výchozího grafu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Získání výchozího indexu listu dat grafu
int defaultWorksheetIndex = 0;
//Získání listu dat grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Smazat ukázkovou sérii
chart.getChartData().getSeries().clear();
//Přidat novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Nastavte obrázek
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Nastavte obrázek
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Vezměte první sérii grafů
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Přidejte tam nový bod (1:3).
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//Změna značky řady grafu
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Závěr

S Aspose.Slides for Java můžete pozvednout své prezentace přizpůsobením značek grafu na datových bodech. To vám umožní vytvářet vizuálně ohromující a informativní snímky, které zaujmou vaše publikum.

## FAQ

### Jak mohu změnit velikost značky pro datové body?

 Chcete-li změnit velikost značky pro datové body, použijte`series.getMarker().setSize()` a zadejte požadovanou velikost jako argument.

### Mohu použít obrázky jako vlastní značky?

 Ano, můžete použít obrázky jako vlastní značky pro datové body. Nastavte typ výplně na`FillType.Picture` poskytněte obrázek, který chcete použít.

### Je Aspose.Slides for Java vhodný pro vytváření dynamických grafů?

Absolutně! Aspose.Slides for Java poskytuje rozsáhlé možnosti pro vytváření dynamických a interaktivních grafů ve vašich prezentacích.

### Mohu upravit další aspekty grafu pomocí Aspose.Slides?

Ano, pomocí Aspose.Slides for Java můžete přizpůsobit různé aspekty grafu, včetně nadpisů, os, štítků dat a dalších.

### Kde mohu získat přístup k dokumentaci Aspose.Slides for Java a ke stažení?

 Dokumentaci najdete na[tady](https://reference.aspose.com/slides/java/) a stáhněte si knihovnu na[tady](https://releases.aspose.com/slides/java/).