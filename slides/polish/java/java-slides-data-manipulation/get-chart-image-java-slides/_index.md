---
title: Uzyskaj obraz wykresu w slajdach Java
linktitle: Uzyskaj obraz wykresu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak uzyskać obrazy wykresów w Java Slides przy użyciu Aspose.Slides dla Java. Ten przewodnik krok po kroku zawiera kod źródłowy i wskazówki dotyczące bezproblemowej integracji.
weight: 19
url: /pl/java/data-manipulation/get-chart-image-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do pobierania obrazu wykresu w slajdach Java

Aspose.Slides for Java to potężna biblioteka, która umożliwia programową pracę z prezentacjami programu PowerPoint. Dzięki tej bibliotece możesz tworzyć, manipulować i wyodrębniać różne elementy z prezentacji, w tym wykresów. Jednym z typowych wymagań jest uzyskanie obrazów wykresów ze slajdów. W tym przewodniku pokażemy, jak to zrobić.

## Warunki wstępne

Zanim zagłębimy się w kod, upewnij się, że spełnione są następujące wymagania wstępne:

- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w Twoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Skonfiguruj swój projekt

Zacznij od utworzenia projektu Java w preferowanym zintegrowanym środowisku programistycznym (IDE). Upewnij się, że dodałeś bibliotekę Aspose.Slides for Java do zależności swojego projektu.

## Krok 2: Zainicjuj prezentację

Aby rozpocząć, musisz zainicjować prezentację programu PowerPoint. W tym przykładzie zakładamy, że masz plik programu PowerPoint o nazwie „test.pptx” w swoim katalogu dokumentów.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 3: Dodaj wykres i uzyskaj obraz

Następnie możesz dodać wykres do slajdu i uzyskać jego obraz. W tym przykładzie dodamy grupowany wykres kolumnowy.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

tym fragmencie kodu tworzymy grupowany wykres kolumnowy na pierwszym slajdzie prezentacji, a następnie uzyskujemy jego miniaturę. Obraz zostanie zapisany jako „image.png” w określonym katalogu.

## Kompletny kod źródłowy funkcji Pobierz obraz wykresu w slajdach Java

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

Uzyskiwanie obrazów wykresów z Java Slides przy użyciu Aspose.Slides for Java jest prostym procesem. Dzięki dostarczonemu kodowi możesz łatwo zintegrować tę funkcjonalność z aplikacjami Java, umożliwiając efektywną pracę z prezentacjami PowerPoint.

## Często zadawane pytania

### Jak zainstalować Aspose.Slides dla Java?

 Instalacja Aspose.Slides dla Java jest prosta. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/) i postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji.

### Czy mogę dostosować wykres przed uzyskaniem jego obrazu?

Tak, możesz dostosować wygląd wykresu, dane i inne właściwości przed uzyskaniem jego obrazu. Aspose.Slides dla Java zapewnia rozbudowane opcje dostosowywania wykresów.

### Jakie inne funkcje oferuje Aspose.Slides dla Java?

Aspose.Slides for Java oferuje szeroką gamę funkcji do pracy z prezentacjami programu PowerPoint, w tym tworzenie slajdów, manipulację tekstem, edycję kształtów i wiele więcej. Aby uzyskać szczegółowe informacje, możesz zapoznać się z dokumentacją.

### Czy Aspose.Slides dla Java nadaje się do użytku komercyjnego?

Tak, Aspose.Slides dla Java może być wykorzystywane do celów komercyjnych. Zapewnia opcje licencjonowania przeznaczone zarówno dla indywidualnych programistów, jak i przedsiębiorstw.

### Czy mogę zapisać obraz wykresu w innym formacie?

 Z pewnością! Możesz zapisać obraz wykresu w różnych formatach, takich jak JPEG lub GIF, określając odpowiednie rozszerzenie pliku w formacie`ImageIO.write` metoda.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
