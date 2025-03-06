---
title: Ustawianie osi pozycji w slajdach Java
linktitle: Ustawianie osi pozycji w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Ulepsz swoje wykresy za pomocą Aspose.Slides dla Java. Dowiedz się, jak ustawić oś pozycji na slajdach Java, tworzyć wspaniałe prezentacje i z łatwością dostosowywać układy wykresów.
weight: 16
url: /pl/java/customization-and-formatting/setting-position-axis-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do ustawiania osi pozycji w Aspose.Slides dla Java

tym samouczku nauczymy się ustawiać oś pozycji na wykresie za pomocą Aspose.Slides dla Java. Pozycjonowanie osi może być przydatne, gdy chcesz dostosować wygląd i układ wykresu. Stworzymy grupowany wykres kolumnowy i dopasujemy położenie osi poziomej pomiędzy kategoriami.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Tworzenie prezentacji

Najpierw utwórzmy nową prezentację, z którą będziemy pracować:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Pamiętaj o wymianie`"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów.

## Krok 2: Dodawanie wykresu

Następnie dodamy do slajdu grupowany wykres kolumnowy. Określamy typ wykresu, położenie (współrzędne x, y) oraz wymiary (szerokość i wysokość) wykresu:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Tutaj dodaliśmy grupowany wykres kolumnowy w pozycjach (50, 50) o szerokości 450 i wysokości 300. Możesz dostosować te wartości według potrzeb.

## Krok 3: Ustawianie osi pozycji

Aby ustawić oś pozycji pomiędzy kategoriami, możesz użyć następującego kodu:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Ten kod ustawia oś poziomą do wyświetlania pomiędzy kategoriami, co może być przydatne w przypadku niektórych układów wykresów.

## Krok 4: Zapisywanie prezentacji

Na koniec zapiszmy prezentację z wykresem:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Zastępować`"AsposeClusteredColumnChart.pptx"` z żądaną nazwą pliku.

Otóż to! Pomyślnie utworzyłeś grupowany wykres kolumnowy i ustawiłeś oś pozycji pomiędzy kategoriami za pomocą Aspose.Slides for Java.

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

W tym samouczku omówiliśmy, jak ustawić oś pozycji na wykresie za pomocą Aspose.Slides dla Java. Wykonując czynności opisane w tym przewodniku, wiesz, jak utworzyć grupowany wykres kolumnowy i dostosować jego wygląd, umieszczając oś poziomą pomiędzy kategoriami. Aspose.Slides for Java zapewnia zaawansowane funkcje do pracy z wykresami i prezentacjami, co czyni go cennym narzędziem dla programistów Java.

## Często zadawane pytania

### Jak mogę bardziej dostosować wykres?

Możesz dostosować różne aspekty wykresu, w tym serie danych, tytuł wykresu, legendy i inne. Patrz[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) szczegółowe instrukcje i przykłady.

### Czy mogę zmienić typ wykresu?

 Tak, możesz zmienić typ wykresu, modyfikując plik`ChartType` parametr podczas dodawania wykresu. Aspose.Slides dla Java obsługuje różne typy wykresów, takie jak wykresy słupkowe, wykresy liniowe i inne.

### Gdzie mogę znaleźć więcej przykładów i dokumentacji?

 Obszerną dokumentację i więcej przykładów można znaleźć na stronie[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) strona.

Pamiętaj, aby po zakończeniu pracy pozbyć się obiektu prezentacji, aby zwolnić zasoby systemowe:

```java
if (pres != null) pres.dispose();
```

To wszystko w tym samouczku. Nauczyłeś się, jak ustawić oś pozycji na wykresie za pomocą Aspose.Slides dla Java.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
