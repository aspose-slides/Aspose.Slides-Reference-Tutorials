---
title: Opcje znaczników wykresów w punkcie danych w slajdach Java
linktitle: Opcje znaczników wykresów w punkcie danych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Zoptymalizuj slajdy Java za pomocą niestandardowych opcji znaczników wykresów. Dowiedz się, jak wizualnie ulepszyć punkty danych za pomocą Aspose.Slides dla Java. Zapoznaj się ze wskazówkami krok po kroku i często zadawanymi pytaniami.
weight: 14
url: /pl/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opcje znaczników wykresów w punkcie danych w slajdach Java


## Wprowadzenie do opcji znaczników wykresów w punkcie danych w slajdach Java

Jeśli chodzi o tworzenie efektownych prezentacji, możliwość dostosowywania znaczników wykresu w punktach danych i manipulowania nimi może mieć ogromne znaczenie. Dzięki Aspose.Slides dla Java masz moc przekształcania wykresów w dynamiczne i wciągające wizualnie elementy.

## Warunki wstępne

Zanim przejdziemy do części dotyczącej kodowania, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Aspose.Slides dla biblioteki Java
- Zintegrowane środowisko programistyczne Java (IDE)
- Przykładowy dokument prezentacji (np. „Test.pptx”)

## Krok 1: Konfigurowanie środowiska

Najpierw upewnij się, że masz zainstalowane i gotowe niezbędne narzędzia. Utwórz projekt Java w swoim IDE i zaimportuj bibliotekę Aspose.Slides for Java.

## Krok 2: Ładowanie prezentacji

Aby rozpocząć, załaduj przykładowy dokument prezentacji. W dostarczonym kodzie zakładamy, że dokument nosi nazwę „Test.pptx”.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Krok 3: Tworzenie wykresu

Utwórzmy teraz wykres w prezentacji. W tym przykładzie użyjemy wykresu liniowego ze znacznikami.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Krok 4: Praca z danymi wykresu

Aby manipulować danymi wykresu, musimy uzyskać dostęp do skoroszytu danych wykresu i przygotować serię danych. Wyczyścimy domyślną serię i dodamy nasze niestandardowe dane.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Krok 5: Dodawanie niestandardowych znaczników

Nadchodzi ekscytująca część – dostosowywanie znaczników w punktach danych. W tym przykładzie użyjemy obrazów jako znaczników.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Dodawanie niestandardowych znaczników do punktów danych
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Powtórz dla innych punktów danych
// ...

// Zmiana rozmiaru znacznika serii wykresów
series.getMarker().setSize(15);
```

## Krok 6: Zapisywanie prezentacji

Po dostosowaniu znaczników wykresu zapisz prezentację, aby zobaczyć zmiany w działaniu.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy opcji znaczników wykresów w punkcie danych w slajdach Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Tworzenie domyślnego wykresu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Pobieranie domyślnego indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
//Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Usuń serię demonstracyjną
chart.getChartData().getSeries().clear();
//Dodaj nową serię
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Ustaw obraz
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Ustaw obraz
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Weź pierwszą serię wykresów
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Dodaj tam nowy punkt (1:3).
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
//Zmiana znacznika serii wykresów
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Wniosek

Dzięki Aspose.Slides for Java możesz ulepszyć swoje prezentacje, dostosowując znaczniki wykresów w punktach danych. Dzięki temu możesz tworzyć oszałamiające wizualnie i pouczające slajdy, które przykują uwagę odbiorców.

## Często zadawane pytania

### Jak zmienić rozmiar znacznika punktów danych?

 Aby zmienić rozmiar znacznika punktów danych, użyj opcji`series.getMarker().setSize()` metodę i podaj żądany rozmiar jako argument.

### Czy mogę używać obrazów jako niestandardowych znaczników?

 Tak, możesz używać obrazów jako niestandardowych znaczników punktów danych. Ustaw typ wypełnienia na`FillType.Picture` i podaj obraz, którego chcesz użyć.

### Czy Aspose.Slides for Java nadaje się do tworzenia dynamicznych wykresów?

Absolutnie! Aspose.Slides dla Java zapewnia szerokie możliwości tworzenia dynamicznych i interaktywnych wykresów w prezentacjach.

### Czy mogę dostosować inne aspekty wykresu za pomocą Aspose.Slides?

Tak, możesz dostosować różne aspekty wykresu, w tym tytuły, osie, etykiety danych i inne, używając Aspose.Slides for Java.

### Gdzie mogę uzyskać dostęp do dokumentacji i plików do pobrania Aspose.Slides for Java?

 Dokumentację można znaleźć pod adresem[Tutaj](https://reference.aspose.com/slides/java/) i pobierz bibliotekę pod adresem[Tutaj](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
