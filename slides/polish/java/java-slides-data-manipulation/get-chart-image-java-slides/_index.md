---
"description": "Dowiedz się, jak uzyskać obrazy wykresów w Java Slides przy użyciu Aspose.Slides for Java. Ten przewodnik krok po kroku zawiera kod źródłowy i wskazówki dotyczące bezproblemowej integracji."
"linktitle": "Pobierz obraz wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Pobierz obraz wykresu w slajdach Java"
"url": "/pl/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Pobierz obraz wykresu w slajdach Java


## Wprowadzenie do pobierania obrazów wykresów w slajdach Java

Aspose.Slides for Java to potężna biblioteka, która umożliwia programową pracę z prezentacjami PowerPoint. Za pomocą tej biblioteki możesz tworzyć, manipulować i wyodrębniać różne elementy z prezentacji, w tym wykresy. Jednym z powszechnych wymagań jest uzyskanie obrazów wykresów ze slajdów, a my pokażemy, jak to zrobić w tym przewodniku.

## Wymagania wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w Twoim projekcie. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Skonfiguruj swój projekt

Zacznij od utworzenia projektu Java w preferowanym zintegrowanym środowisku programistycznym (IDE). Upewnij się, że dodałeś bibliotekę Aspose.Slides for Java do zależności swojego projektu.

## Krok 2: Zainicjuj prezentację

Na początek musisz zainicjować prezentację PowerPoint. W tym przykładzie zakładamy, że masz plik PowerPoint o nazwie „test.pptx” w katalogu dokumentów.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Dodaj wykres i uzyskaj obraz

Następnie możesz dodać wykres do slajdu i uzyskać jego obraz. W tym przykładzie dodamy wykres kolumnowy klastrowany.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

W tym fragmencie kodu tworzymy wykres kolumnowy klastrowany na pierwszym slajdzie prezentacji, a następnie uzyskujemy jego obraz miniatury. Obraz jest zapisywany jako „image.png” w określonym katalogu.

## Kompletny kod źródłowy dla Get Chart Image w Java Slides

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Uzyskiwanie obrazów wykresów z Java Slides przy użyciu Aspose.Slides for Java to prosty proces. Dzięki dostarczonemu kodowi możesz łatwo zintegrować tę funkcjonalność ze swoimi aplikacjami Java, co pozwoli Ci efektywnie pracować z prezentacjami PowerPoint.

## Najczęściej zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

Instalacja Aspose.Slides dla Java jest prosta. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/) i postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji.

### Czy mogę dostosować wykres przed uzyskaniem jego obrazu?

Tak, możesz dostosować wygląd wykresu, dane i inne właściwości przed uzyskaniem jego obrazu. Aspose.Slides for Java zapewnia rozbudowane opcje dostosowywania wykresu.

### Jakie inne funkcje oferuje Aspose.Slides for Java?

Aspose.Slides for Java oferuje szeroki zakres funkcji do pracy z prezentacjami PowerPoint, w tym tworzenie slajdów, manipulację tekstem, edycję kształtów i wiele więcej. Możesz przejrzeć dokumentację, aby uzyskać szczegółowe informacje.

### Czy Aspose.Slides for Java nadaje się do użytku komercyjnego?

Tak, Aspose.Slides for Java może być używany w celach komercyjnych. Zapewnia opcje licencjonowania, które odpowiadają zarówno indywidualnym programistom, jak i przedsiębiorstwom.

### Czy mogę zapisać obraz wykresu w innym formacie?

Oczywiście! Możesz zapisać obraz wykresu w różnych formatach, takich jak JPEG lub GIF, określając odpowiednie rozszerzenie pliku w `ImageIO.write` metoda.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}