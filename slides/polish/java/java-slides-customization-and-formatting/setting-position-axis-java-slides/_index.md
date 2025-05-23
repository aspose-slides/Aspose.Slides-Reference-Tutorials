---
"description": "Ulepsz swoje wykresy dzięki Aspose.Slides dla Java. Dowiedz się, jak ustawić oś położenia w slajdach Java, tworzyć oszałamiające prezentacje i łatwo dostosowywać układy wykresów."
"linktitle": "Ustawianie osi położenia w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustawianie osi położenia w slajdach Java"
"url": "/pl/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustawianie osi położenia w slajdach Java


## Wprowadzenie do ustawiania osi położenia w Aspose.Slides dla Java

tym samouczku nauczymy się, jak ustawić oś położenia na wykresie za pomocą Aspose.Slides dla Java. Pozycjonowanie osi może być przydatne, gdy chcesz dostosować wygląd i układ wykresu. Utworzymy wykres kolumnowy klastrowany i dostosujemy położenie osi poziomej między kategoriami.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać bibliotekę z [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Tworzenie prezentacji

Najpierw utwórzmy nową prezentację, z którą będziemy pracować:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Pamiętaj o wymianie `"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Dodawanie wykresu

Następnie dodamy do slajdu wykres kolumnowy klastrowany. Określamy typ wykresu, pozycję (współrzędne x, y) i wymiary (szerokość i wysokość) wykresu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Tutaj dodaliśmy wykres kolumnowy klastrowany na pozycji (50, 50) o szerokości 450 i wysokości 300. Możesz dostosować te wartości według potrzeb.

## Krok 3: Ustawienie osi położenia

Aby ustawić oś pozycji pomiędzy kategoriami, możesz użyć następującego kodu:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Ten kod ustawia oś poziomą tak, aby była wyświetlana pomiędzy kategoriami, co może być przydatne w przypadku niektórych układów wykresów.

## Krok 4: Zapisywanie prezentacji

Na koniec zapiszmy prezentację z wykresem:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Zastępować `"AsposeClusteredColumnChart.pptx"` z wybraną przez Ciebie nazwą pliku.

To wszystko! Udało Ci się utworzyć wykres kolumnowy klastrowany i ustawić oś pozycji między kategoriami za pomocą Aspose.Slides dla Java.

## Kompletny kod źródłowy
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

tym samouczku sprawdziliśmy, jak ustawić oś położenia na wykresie za pomocą Aspose.Slides for Java. Postępując zgodnie z krokami opisanymi w tym przewodniku, nauczyłeś się, jak utworzyć wykres kolumnowy klastrowany i dostosować jego wygląd, pozycjonując oś poziomą między kategoriami. Aspose.Slides for Java oferuje potężne funkcje do pracy z wykresami i prezentacjami, co czyni go cennym narzędziem dla programistów Java.

## Najczęściej zadawane pytania

### Jak mogę jeszcze bardziej dostosować wykres?

Możesz dostosować różne aspekty wykresu, w tym serie danych, tytuł wykresu, legendy i inne. Zapoznaj się z [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) Aby uzyskać szczegółowe instrukcje i przykłady.

### Czy mogę zmienić typ wykresu?

Tak, możesz zmienić typ wykresu, modyfikując `ChartType` parametr podczas dodawania wykresu. Aspose.Slides dla Java obsługuje różne typy wykresów, takie jak wykresy słupkowe, wykresy liniowe i inne.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?

Pełną dokumentację i więcej przykładów znajdziesz na stronie [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) strona.

Pamiętaj, aby po zakończeniu pracy z obiektem prezentacji usunąć go, aby zwolnić zasoby systemowe:

```java
if (pres != null) pres.dispose();
```

To wszystko w tym samouczku. Nauczyłeś się, jak ustawić oś pozycji na wykresie za pomocą Aspose.Slides dla Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}