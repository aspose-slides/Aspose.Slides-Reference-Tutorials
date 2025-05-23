---
"description": "Zoptymalizuj swoje slajdy Java za pomocą Aspose.Slides for Java. Naucz się ustawiać kąty obrotu dla elementów tekstowych. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Ustawianie kąta obrotu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustawianie kąta obrotu w slajdach Java"
"url": "/pl/java/customization-and-formatting/setting-rotation-angle-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie kąta obrotu w slajdach Java


## Wprowadzenie do ustawiania kąta obrotu w slajdach Java

tym samouczku pokażemy, jak ustawić kąt obrotu tekstu w tytule osi wykresu za pomocą biblioteki Aspose.Slides for Java. Dostosowując kąt obrotu, możesz dostosować wygląd tytułów osi wykresu, aby lepiej odpowiadał potrzebom prezentacji.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w projekcie Java. Możesz pobrać bibliotekę ze strony internetowej Aspose i postępować zgodnie z instrukcjami instalacji podanymi w dokumentacji.

## Krok 1: Utwórz prezentację

Najpierw musisz utworzyć nową prezentację lub załadować istniejącą. W tym przykładzie utworzymy nową prezentację:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie dodamy wykres do slajdu. W tym przykładzie dodajemy wykres kolumnowy klastrowany:

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

## Krok 3: Ustaw kąt obrotu dla tytułu osi

Aby ustawić kąt obrotu dla tytułu osi, musisz uzyskać dostęp do tytułu osi pionowej wykresu i dostosować jego kąt obrotu. Oto, jak możesz to zrobić:

```java
    chart.getAxes().getVerticalAxis().setTitle(true);
    chart.getAxes().getVerticalAxis().getTitle().getTextFormat().getTextBlockFormat().setRotationAngle(90);
```

W tym fragmencie kodu ustawiamy kąt obrotu na 90 stopni, co spowoduje obrót tekstu w pionie. Możesz dostosować kąt do żądanej wartości.

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację w pliku PowerPoint:

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

W tym samouczku nauczyłeś się, jak ustawić kąt obrotu tekstu w tytule osi wykresu za pomocą Aspose.Slides dla Java. Ta funkcja pozwala dostosować wygląd wykresów, aby tworzyć atrakcyjne wizualnie prezentacje. Eksperymentuj z różnymi kątami obrotu, aby uzyskać pożądany wygląd wykresów.

## Najczęściej zadawane pytania

### Jak mogę zmienić kąt obrotu innych elementów tekstowych na slajdzie?

Możesz zmienić kąt obrotu dla innych elementów tekstowych, takich jak kształty lub pola tekstowe, używając podobnego podejścia. Uzyskaj dostęp do formatu tekstu elementu i ustaw kąt obrotu według potrzeb.

### Czy mogę obrócić również tekst tytułu na osi poziomej?

Tak, możesz obrócić tekst w tytule osi poziomej, dostosowując kąt obrotu. Po prostu ustaw kąt obrotu na żądaną wartość, np. 90 stopni dla tekstu pionowego lub 0 stopni dla tekstu poziomego.

### Jakie inne opcje formatowania są dostępne dla tytułów wykresów?

Aspose.Slides for Java oferuje różne opcje formatowania tytułów wykresów, w tym style czcionek, kolory i wyrównanie. Więcej szczegółów na temat dostosowywania tytułów wykresów można znaleźć w dokumentacji.

### Czy można animować obrót tekstu w tytule osi wykresu?

Tak, możesz dodawać efekty animacji do elementów tekstowych, w tym tytuły osi wykresu, używając Aspose.Slides dla Java. Zapoznaj się z dokumentacją, aby uzyskać informacje na temat dodawania animacji do prezentacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}