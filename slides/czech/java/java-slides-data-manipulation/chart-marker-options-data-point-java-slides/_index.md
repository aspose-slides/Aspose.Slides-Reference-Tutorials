---
"description": "Optimalizujte své slidy v Javě pomocí vlastních možností značek grafů. Naučte se vizuálně vylepšovat datové body pomocí Aspose.Slides pro Javu. Prozkoumejte podrobné pokyny a často kladené otázky."
"linktitle": "Možnosti značek grafu na datových bodech v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Možnosti značek grafu na datových bodech v Java Slides"
"url": "/cs/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Možnosti značek grafu na datových bodech v Java Slides


## Úvod do možností značek grafu na datových bodech v Javě – Slides

Pokud jde o vytváření působivých prezentací, může být klíčová schopnost přizpůsobit a manipulovat s značkami grafů na datových bodech. S Aspose.Slides pro Javu máte možnost transformovat své grafy do dynamických a vizuálně poutavých prvků.

## Předpoklady

Než se pustíme do kódování, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí v Javě
- Aspose.Slides pro knihovnu Java
- Integrované vývojové prostředí (IDE) pro Javu
- Ukázkový prezentační dokument (např. „Test.pptx“)

## Krok 1: Nastavení prostředí

Nejprve se ujistěte, že máte nainstalované a připravené potřebné nástroje. Vytvořte projekt Java ve vašem IDE a importujte knihovnu Aspose.Slides pro Javu.

## Krok 2: Načtení prezentace

Chcete-li začít, načtěte si vzorový dokument prezentace. V poskytnutém kódu předpokládáme, že dokument má název „Test.pptx“.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Krok 3: Vytvoření grafu

Nyní si v prezentaci vytvořme graf. V tomto příkladu použijeme spojnicový graf se značkami.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Krok 4: Práce s daty grafu

Pro manipulaci s daty grafu potřebujeme přístup k sešitu s daty grafu a připravit datové řady. Vymažeme výchozí řady a přidáme vlastní data.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Krok 5: Přidání vlastních značek

A tady přichází ta vzrušující část – přizpůsobení značek na datových bodech. V tomto příkladu použijeme jako značky obrázky.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Přidávání vlastních značek k datovým bodům
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Opakujte pro další datové body.
// ...

// Změna velikosti značky řady grafů
series.getMarker().setSize(15);
```

## Krok 6: Uložení prezentace

Jakmile si upravíte značky grafu, uložte prezentaci, abyste viděli změny v akci.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro možnosti značek grafu na datových bodech v Javě Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Vytvoření výchozího grafu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Získání výchozího indexu listu s daty grafu
int defaultWorksheetIndex = 0;
//Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Smazat demo sérii
chart.getChartData().getSeries().clear();
//Přidat novou sérii
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Nastavte obrázek
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Nastavte obrázek
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Vezměte si první sérii grafů
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

S Aspose.Slides pro Javu můžete vylepšit své prezentace přizpůsobením značek grafů na datových bodech. To vám umožní vytvářet vizuálně ohromující a informativní snímky, které zaujmou vaše publikum.

## Často kladené otázky

### Jak mohu změnit velikost značek pro datové body?

Chcete-li změnit velikost značek pro datové body, použijte `series.getMarker().setSize()` metodu a jako argument uveďte požadovanou velikost.

### Mohu použít obrázky jako vlastní značky?

Ano, obrázky můžete použít jako vlastní značky pro datové body. Nastavte typ výplně na `FillType.Picture` a poskytněte obrázek, který chcete použít.

### Je Aspose.Slides pro Javu vhodný pro vytváření dynamických grafů?

Rozhodně! Aspose.Slides pro Javu nabízí rozsáhlé možnosti pro vytváření dynamických a interaktivních grafů ve vašich prezentacích.

### Mohu si pomocí Aspose.Slides přizpůsobit další aspekty grafu?

Ano, pomocí Aspose.Slides pro Javu si můžete přizpůsobit různé aspekty grafu, včetně názvů, os, popisků dat a dalších.

### Kde mohu získat přístup k dokumentaci a souborům ke stažení k Aspose.Slides pro Javu?

Dokumentaci naleznete na adrese [zde](https://reference.aspose.com/slides/java/) a stáhněte si knihovnu na adrese [zde](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}