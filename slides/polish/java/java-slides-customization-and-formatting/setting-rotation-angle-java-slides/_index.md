---
title: Ustawianie kąta obrotu w slajdach Java
linktitle: Ustawianie kąta obrotu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Zoptymalizuj swoje slajdy Java za pomocą Aspose.Slides for Java. Naucz się ustawiać kąty obrotu elementów tekstowych. Przewodnik krok po kroku z kodem źródłowym.
weight: 17
url: /pl/java/customization-and-formatting/setting-rotation-angle-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do ustawiania kąta obrotu w slajdach Java

tym samouczku dowiemy się, jak ustawić kąt obrotu tekstu w tytule osi wykresu za pomocą biblioteki Aspose.Slides for Java. Dostosowując kąt obrotu, możesz dostosować wygląd tytułów osi wykresu, aby lepiej odpowiadał potrzebom prezentacji.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę ze strony Aspose i postępować zgodnie z instrukcjami instalacji zawartymi w ich dokumentacji.

## Krok 1: Utwórz prezentację

Najpierw musisz utworzyć nową prezentację lub załadować istniejącą. W tym przykładzie utworzymy nową prezentację:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie dodamy wykres do slajdu. W tym przykładzie dodajemy grupowany wykres kolumnowy:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Krok 3: Ustaw kąt obrotu tytułu osi

Aby ustawić kąt obrotu tytułu osi, musisz uzyskać dostęp do tytułu osi pionowej wykresu i dostosować jego kąt obrotu. Oto jak możesz to zrobić:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

tym fragmencie kodu ustawiamy kąt obrotu na 90 stopni, co spowoduje obrócenie tekstu w pionie. Możesz dostosować kąt do żądanej wartości.

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację w pliku programu PowerPoint:

```java
    pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Kompletny kod źródłowy do ustawiania kąta obrotu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
	pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku nauczyłeś się ustawiać kąt obrotu tekstu w tytule osi wykresu za pomocą Aspose.Slides dla Java. Ta funkcja umożliwia dostosowanie wyglądu wykresów w celu tworzenia atrakcyjnych wizualnie prezentacji. Eksperymentuj z różnymi kątami obrotu, aby uzyskać pożądany wygląd wykresów.

## Często zadawane pytania

### Jak zmienić kąt obrotu innych elementów tekstowych na slajdzie?

W podobny sposób możesz zmienić kąt obrotu innych elementów tekstowych, takich jak kształty lub pola tekstowe. Uzyskaj dostęp do formatu tekstowego elementu i ustaw kąt obrotu zgodnie z potrzebami.

### Czy mogę obracać tekst również w tytule na osi poziomej?

Tak, możesz obracać tekst w tytule osi poziomej, dostosowując kąt obrotu. Po prostu ustaw kąt obrotu na żądaną wartość, na przykład 90 stopni dla tekstu pionowego lub 0 stopni dla tekstu poziomego.

### Jakie inne opcje formatowania są dostępne dla tytułów wykresów?

Aspose.Slides dla Java zapewnia różne opcje formatowania tytułów wykresów, w tym style czcionek, kolory i wyrównanie. Więcej szczegółów na temat dostosowywania tytułów wykresów można znaleźć w dokumentacji.

### Czy można animować obrót tekstu w tytule osi wykresu?

Tak, możesz dodawać efekty animacji do elementów tekstowych, w tym tytułów osi wykresu, używając Aspose.Slides dla Java. Informacje na temat dodawania animacji do prezentacji można znaleźć w dokumentacji.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
