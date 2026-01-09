---
date: '2026-01-09'
description: Odkryj, jak używać Aspose.Slides Maven, aby dodać wykres do slajdu i
  dostosować wykres kołowy w prezentacjach Java. Krok po kroku konfiguracja, kod i
  przykłady z rzeczywistego świata.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven: Dodaj wykres kołowy do prezentacji'
url: /pl/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres kołowy do prezentacji przy użyciu Aspose.Slides Java

## Introduction
Tworzenie wizualnie atrakcyjnych prezentacji jest kluczowe dla skutecznego przekazywania informacji, szczególnie gdy wizualizacja danych odgrywa istotną rolę. Jeśli chcesz zautomatyzować ten proces przy użyciu **aspose slides maven**, trafiłeś we właściwe miejsce. W tym samouczku dowiesz się, jak **add chart to slide** — konkretnie wykres kołowy — przy użyciu Aspose.Slides for Java oraz jak go dostosować do rzeczywistych scenariuszy.

### What You'll Learn
- Jak zainicjować obiekt prezentacji w Javie.  
- Kroki do **add a pie chart java** na pierwszym slajdzie prezentacji.  
- Dostęp do skoroszytów danych wykresu i wyświetlanie listy arkuszy w nich.  

Zanurzmy się w to, jak możesz wykorzystać Aspose.Slides Java, aby wzbogacić swoje prezentacje o dynamiczne wykresy!

## Quick Answers
- **Jaka biblioteka dodaje wykresy przez Maven?** aspose slides maven  
- **Jaki typ wykresu jest pokazany?** Pie chart (add chart to slide)  
- **Minimalna wymagana wersja Javy?** JDK 16 lub nowsza  
- **Czy potrzebna jest licencja do testów?** A free trial works; production needs a license  
- **Gdzie mogę znaleźć zależność Maven?** In the setup section below  

## What is Aspose Slides Maven?
Aspose.Slides for Java jest potężnym API, które pozwala programistom tworzyć, modyfikować i renderować pliki PowerPoint programowo. Pakiet Maven (`aspose-slides`) upraszcza zarządzanie zależnościami, umożliwiając skupienie się na budowaniu i dostosowywaniu slajdów — takich jak dodanie wykresu kołowego — bez konieczności zajmowania się niskopoziomową obsługą plików.

## Why Use Aspose.Slides Maven to Add a Chart to a Slide?
- **Automatyzacja:** Automatyczne generowanie raportów i pulpitów nawigacyjnych.  
- **Precyzja:** Pełna kontrola nad typami wykresów, danymi i stylizacją.  
- **Cross‑Platform:** Działa w każdym środowisku kompatybilnym z Javą.  

## Prerequisites
- **Aspose.Slides for Java** wersja 25.4 lub nowsza (Maven/Gradle).  
- Zainstalowany JDK 16+.  
- IDE (IntelliJ IDEA, Eclipse, itp.).  
- Podstawowa znajomość Javy oraz Maven lub Gradle.

## Setting Up Aspose.Slides for Java
Najpierw dołącz Aspose.Slides do swojego projektu za pomocą Maven lub Gradle.

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz [download the latest release](https://releases.aspose.com/slides/java/) bezpośrednio ze strony Aspose.

### License Acquisition
Aspose.Slides for Java offers a free trial with a temporary license for testing. For unrestricted production use, purchase a license through the [purchase page](https://purchase.aspose.com/buy).

## Implementation Guide
Poniżej dzielimy rozwiązanie na dwie funkcje: dodanie wykresu kołowego oraz dostęp do jego skoroszytu danych.

### Feature 1: Creating a Presentation and Adding a Chart
#### Overview
Ta część pokazuje, jak stworzyć nową prezentację i **add a pie chart** na pierwszym slajdzie.

#### Step‑by‑Step

**Step 1: Initialize a New Presentation Object**  
```java
Presentation pres = new Presentation();
```
*Tworzy instancję `Presentation`, która będzie przechowywać wszystkie slajdy.*

**Step 2: Add a Pie Chart**  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Umieszcza wykres kołowy w współrzędnych (50, 50) o szerokości 400 i wysokości 500. Enum `ChartType.Pie` informuje Aspose, aby renderował wykres kołowy.*

**Step 3: Dispose of Resources**  
```java
if (pres != null) pres.dispose();
```
*Zwalnia zasoby natywne; zawsze wywołuj `dispose()`, gdy skończysz.*

### Feature 2: Accessing Chart Data Workbook and Worksheets
#### Overview
Naucz się, jak dotrzeć do podstawowego skoroszytu przechowującego dane wykresu i iterować po jego arkuszach.

#### Step‑by‑Step

**Step 1: (Reuse) Initialize a New Presentation Object**  
*Tak jak w Funkcji 1, Krok 1.*

**Step 2: (Reuse) Add a Pie Chart**  
*Tak jak w Funkcji 1, Krok 2.*

**Step 3: Get the Chart Data Workbook**  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Pobiera `IChartDataWorkbook` powiązany z wykresem.*

**Step 4: Iterate Through Worksheets**  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Wypisuje nazwę każdego arkusza, umożliwiając weryfikację struktury danych.*

**Step 5: Dispose of Resources**  
*Tak jak w Funkcji 1, Krok 3.*

## Practical Applications
- **Data Reporting:** Automatyczne generowanie zestawów slajdów z aktualnymi metrykami dla Business Intelligence.  
- **Academic Presentations:** Wizualizacja wyników badań bez ręcznego tworzenia wykresów.  
- **Marketing Material:** Prezentacja wydajności produktu lub wyników ankiet natychmiastowo.

## Performance Considerations
- Keep the slide and chart count reasonable; each consumes memory.  
- Always call `dispose()` to free native resources.  
- Optimize workbook data handling—avoid loading massive datasets into a single chart.

## Conclusion
Omówiliśmy, jak **aspose slides maven** umożliwia **add chart to slide** programowo oraz jak pracować ze skoroszytem danych wykresu. Dzięki tym elementom możesz zautomatyzować każdy proces raportowania wymagający eleganckiego wyjścia w formacie PowerPoint.

### Next Steps
- Explore chart styling options (colors, legends, data labels).  
- Connect to external data sources (CSV, databases) to populate charts dynamically.  
- Combine multiple chart types in a single presentation for richer storytelling.

## Frequently Asked Questions

**Q: How do I install Aspose.Slides for Java?**  
A: Use the Maven or Gradle dependency shown above, or download the library from the releases page.

**Q: What are the system requirements for Aspose.Slides?**  
A: JDK 16 or later; the library is platform‑independent.

**Q: Can I add other chart types besides pie charts?**  
A: Yes, Aspose.Slides supports bar, line, scatter, and many more chart types.

**Q: How should I handle large presentations efficiently?**  
A: Dispose of objects promptly, limit the number of high‑resolution images, and reuse chart templates when possible.

**Q: Where can I find more details about Aspose.Slides features?**  
A: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/) for a complete API reference.

**Q: Is a license required for commercial use?**  
A: A valid license is required for production; a free trial is available for evaluation.

**Q: Does the Maven package include all chart capabilities?**  
A: Yes, the `aspose-slides` Maven artifact contains the full charting engine.

---  

**Last Updated:** 2026-01-09  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

## Resources
- Documentation: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Download: [Latest Releases](https://releases.aspose.com/slides/java/)
- Purchase and Trial: [Purchase Page](https://purchase.aspose.com/buy)
- Free trial: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Temporary License: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Support Forum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)