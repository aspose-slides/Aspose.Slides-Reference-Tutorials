---
"description": "Zoptymalizuj swoje slajdy Java za pomocą opcji niestandardowych znaczników wykresu. Naucz się wizualnie ulepszać punkty danych za pomocą Aspose.Slides dla Java. Zapoznaj się z instrukcjami krok po kroku i często zadawanymi pytaniami."
"linktitle": "Opcje znaczników wykresu w punkcie danych w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Opcje znaczników wykresu w punkcie danych w slajdach Java"
"url": "/pl/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opcje znaczników wykresu w punkcie danych w slajdach Java


## Wprowadzenie do opcji znaczników wykresu w punkcie danych w slajdach Java

Jeśli chodzi o tworzenie efektownych prezentacji, możliwość dostosowywania i manipulowania znacznikami wykresów w punktach danych może mieć ogromne znaczenie. Dzięki Aspose.Slides for Java masz możliwość przekształcania wykresów w dynamiczne i wizualnie angażujące elementy.

## Wymagania wstępne

Zanim przejdziemy do części poświęconej kodowaniu, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Aspose.Slides dla biblioteki Java
- Zintegrowane środowisko programistyczne Java (IDE)
- Przykładowy dokument prezentacji (np. „Test.pptx”)

## Krok 1: Konfigurowanie środowiska

Najpierw upewnij się, że masz zainstalowane i gotowe niezbędne narzędzia. Utwórz projekt Java w swoim IDE i zaimportuj bibliotekę Aspose.Slides for Java.

## Krok 2: Ładowanie prezentacji

Aby rozpocząć, załaduj przykładowy dokument prezentacji. W podanym kodzie zakładamy, że dokument nosi nazwę „Test.pptx”.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Krok 3: Tworzenie wykresu

Teraz utwórzmy wykres w prezentacji. W tym przykładzie użyjemy wykresu liniowego z markerami.

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

Oto ekscytująca część - dostosowywanie znaczników na punktach danych. W tym przykładzie użyjemy obrazów jako znaczników.

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

// Zmiana rozmiaru znacznika serii wykresu
series.getMarker().setSize(15);
```

## Krok 6: Zapisywanie prezentacji

Po dostosowaniu znaczników wykresu zapisz prezentację, aby zobaczyć zmiany w działaniu.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla opcji znaczników wykresu w punkcie danych w slajdach Java

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
//Zmiana znacznika serii wykresu
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Wniosek

Dzięki Aspose.Slides for Java możesz podnieść poziom swoich prezentacji, dostosowując znaczniki wykresów na punktach danych. Pozwala to tworzyć wizualnie oszałamiające i informacyjne slajdy, które zachwycą odbiorców.

## Najczęściej zadawane pytania

### Jak mogę zmienić rozmiar znacznika punktów danych?

Aby zmienić rozmiar znacznika dla punktów danych, użyj `series.getMarker().setSize()` metodę i podaj żądany rozmiar jako argument.

### Czy mogę używać obrazów jako niestandardowych znaczników?

Tak, możesz używać obrazów jako niestandardowych znaczników dla punktów danych. Ustaw typ wypełnienia na `FillType.Picture` i podaj obraz, którego chcesz użyć.

### Czy Aspose.Slides for Java nadaje się do tworzenia dynamicznych wykresów?

Oczywiście! Aspose.Slides for Java zapewnia rozbudowane możliwości tworzenia dynamicznych i interaktywnych wykresów w prezentacjach.

### Czy mogę dostosować inne aspekty wykresu za pomocą Aspose.Slides?

Tak, możesz dostosować różne aspekty wykresu, w tym tytuły, osie, etykiety danych i inne, korzystając z Aspose.Slides dla Java.

### Gdzie mogę uzyskać dostęp do dokumentacji Aspose.Slides for Java i pobrać pliki?

Dokumentację znajdziesz pod adresem [Tutaj](https://reference.aspose.com/slides/java/) i pobierz bibliotekę na [Tutaj](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}