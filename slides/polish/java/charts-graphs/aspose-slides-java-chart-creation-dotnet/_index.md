---
date: '2026-02-06'
description: Dowiedz się, jak zainicjować prezentację Aspose Slides i dostosować wykres
  słupkowy grupowany w .NET przy użyciu Aspose.Slides for Java. Postępuj zgodnie z
  tym przewodnikiem krok po kroku, aby ulepszyć wizualizację danych.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Zainicjuj prezentację przy użyciu Aspose Slides: wykresy .NET'
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów w prezentacjach .NET przy użyciu Aspose.Slides for Java

## Introduction
W tym samouczku **zainicjujesz prezentację Aspose Slides** i nauczysz się osadzać dynamiczne, konfigurowalne wykresy w swoich slajdach .NET. Wizualne dane — takie jak wykresy słupkowe grupowane — pomagają odbiorcom natychmiast zrozumieć trendy, a Aspose.Slides for Java daje pełną kontrolę programistyczną, nawet gdy celujesz w środowisko .NET. Przejdziemy przez konfigurację biblioteki, tworzenie nowej prezentacji, dodawanie wykresu, wypełnianie danymi oraz stosowanie trików formatowania, takich jak kolorowanie wartości ujemnych.

**What You’ll Learn**
- Jak skonfigurować Aspose.Slides for Java w projekcie .NET.  
- Jak **zainicjować prezentację Aspose Slides** i dodać wykres.  
- Jak **dostosować wykres słupkowy grupowany** — serie i kategorie.  
- Zarządzanie skoroszytem danych wykresu oraz stosowanie formatowania warunkowego.  

### Quick Answers
- **What is the first step?** Initialize a `Presentation` object.  
- **Which chart type is used in the example?** `ClusteredColumn`.  
- **Can I format negative values differently?** Yes, using conditional fill colors.  
- **Do I need a license for testing?** A free trial license works for development.  
- **Which Maven artifact is required?** `com.aspose:aspose-slides:25.4` with `jdk16` classifier.

## What is “initialize presentation Aspose Slides”?
Inicjalizacja prezentacji tworzy w pamięci plik PPTX, który możesz modyfikować przed zapisaniem. Aspose.Slides abstrahuje format pliku, umożliwiając dodawanie slajdów, kształtów i wykresów bez konieczności pracy z niskopoziomowymi strukturami OPC.

## Why customize a clustered column chart?
Wykresy słupkowe grupowane są idealne do porównywania wielu serii danych w różnych kategoriach. Dostosowanie kolorów, punktów danych i etykiet pozwala podkreślić kluczowe wnioski — np. wyróżnienie wartości ujemnych na czerwono i dodatnich na zielono — co sprawia, że slajdy są bardziej przekonujące.

## Prerequisites
- **Aspose.Slides for Java** ≥ 25.4  
- Środowisko programistyczne .NET (Visual Studio, zalecany .NET 6+)  
- Podstawowa znajomość Javy (napiszesz kod Java, który uruchamia się na JVM i jest wywoływany z .NET przez JNI lub warstwę mostu)  

### Required Libraries and Versions
- **Aspose.Slides for Java**: wersja 25.4 lub nowsza.

### Environment Setup Requirements
- Środowisko uruchomieniowe Java kompatybilne z .NET (np. AdoptOpenJDK 16).  
- Maven lub Gradle do zarządzania zależnościami.

### Knowledge Prerequisites
- Znajomość tworzenia prezentacji w kontekście .NET.  
- Rozumienie konfiguracji projektu Java (Maven/Gradle).

## Setting Up Aspose.Slides for Java
Dodaj bibliotekę do swojego projektu przy użyciu wybranego narzędzia budującego.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Możesz także pobrać najnowszy plik JAR ze strony wydania: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Free Trial** – wygeneruj tymczasowy plik licencji do celów deweloperskich.  
- **Purchase** – uzyskaj pełną licencję do wdrożeń produkcyjnych.

#### Basic Initialization and Setup
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Blok `try/finally` zapewnia zwolnienie zasobów natywnych, zapobiegając wyciekom pamięci.

## How to initialize presentation Aspose Slides
Poniżej przedstawiamy konkretne kroki tworzenia nowej prezentacji i przygotowania jej do wstawienia wykresu.

### Initializing Presentation
**Overview:**  
Utworzenie instancji prezentacji przygotowuje scenę dla wszystkich kolejnych operacji.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
```

#### Step 2: Create a New Presentation Object
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*To zapewnia, że obiekt prezentacji zostanie prawidłowo zwolniony po użyciu, zapobiegając wyciekom pamięci.*

## How to customize clustered column chart
Teraz, gdy prezentacja jest gotowa, dodajmy i dopasujmy wykres słupkowy grupowany.

### Adding Chart to Slide
**Overview:**  
Dodanie wykresu ożywia dane na slajdzie.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Step 2: Initialize Presentation and Add Chart
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Tutaj dodajemy wykres słupkowy grupowany do pierwszego slajdu w określonych współrzędnych i wymiarach.*

### Managing Chart Data Workbook
**Overview:**  
Efektywne zarządzanie skoroszytem danych wykresu pozwala płynnie manipulować seriami i kategoriami.

#### Step 1: Import Necessary Packages
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Step 2: Access and Clear Data Workbook
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Wyczyszczenie skoroszytu jest kluczowe, aby rozpocząć od czystego stanu przy dodawaniu nowych serii i kategorii.*

### Adding Series and Categories to Chart
**Overview:**  
Ten krok pokazuje, jak dodać istotne punkty danych, zarządzając seriami i kategoriami.

#### Step 1: Add Series and Categories
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Dodanie serii i kategorii umożliwia bardziej uporządkowaną prezentację danych.*

### Populating Series Data and Formatting
**Overview:**  
Wypełnij wykres punktami danych i sformatuj wygląd, aby zwiększyć czytelność, zwłaszcza przy wartościach ujemnych.

#### Step 1: Populate Series Data
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Ten fragment demonstruje, jak wypełnić dane i zastosować formatowanie kolorów dla lepszej wizualizacji.*

## Common Issues and Solutions
- **Memory leaks** – Zawsze otaczaj obiekt `Presentation` blokiem `try/finally`, jak pokazano, aby zagwarantować jego zwolnienie.  
- **Incorrect cell coordinates** – Pamiętaj, że wiersze i kolumny są indeksowane od zera; niezgodne indeksy powodują `NullPointerException`.  
- **License not found** – Umieść plik licencji w katalogu roboczym aplikacji lub ustaw ścieżkę explicite za pomocą `License.setLicense("Aspose.Slides.Java.lic")`.

## Frequently Asked Questions

**Q: Can I use this approach with .NET Core?**  
A: Yes. Aspose.Slides for Java runs on any JVM, and you can call the Java code from .NET Core using a bridge such as IKVM or JNI.

**Q: Do I need a paid license for development?**  
A: A free trial license is sufficient for development and testing. Production deployments require a purchased license.

**Q: How do I change the chart type after creation?**  
A: You can call `chart.getChartData().setChartType(ChartType.Pie)` to switch to a different chart type.

**Q: Is it possible to add data labels programmatically?**  
A: Yes. Use `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` to display values on the chart.

**Q: What formats can I save the presentation in?**  
A: Aspose.Slides supports PPTX, PPT, PDF, XPS, and several image formats like PNG and JPEG.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}