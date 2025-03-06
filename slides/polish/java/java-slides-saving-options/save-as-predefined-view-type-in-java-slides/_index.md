---
title: Zapisz jako predefiniowany typ widoku w slajdach Java
linktitle: Zapisz jako predefiniowany typ widoku w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić predefiniowane typy widoków w Java Slides za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu i często zadawanymi pytaniami.
weight: 10
url: /pl/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do zapisywania jako predefiniowanego typu widoku w slajdach Java

W tym przewodniku krok po kroku dowiemy się, jak zapisać prezentację ze wstępnie zdefiniowanym typem widoku za pomocą Aspose.Slides for Java. Dostarczymy Ci niezbędny kod i wyjaśnienia, aby pomyślnie wykonać to zadanie.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz następujące elementy:

- Podstawowa znajomość programowania w języku Java.
- Zainstalowana biblioteka Aspose.Slides dla Java.
- Zintegrowane środowisko programistyczne (IDE) według własnego wyboru.

## Konfigurowanie środowiska

Aby rozpocząć, wykonaj następujące kroki, aby skonfigurować środowisko programistyczne:

1. Utwórz nowy projekt Java w swoim IDE.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu jako zależność.

Teraz, gdy środowisko jest skonfigurowane, przejdźmy do kodu.

## Krok 1: Tworzenie prezentacji

Aby zademonstrować zapisywanie prezentacji ze wstępnie zdefiniowanym typem widoku, najpierw utworzymy nową prezentację. Oto kod umożliwiający utworzenie prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Otwieranie pliku prezentacji
Presentation presentation = new Presentation();
```

 W tym kodzie tworzymy nowy`Presentation` obiekt, który reprezentuje naszą prezentację PowerPoint.

## Krok 2: Ustawianie typu widoku

Następnie ustawimy typ widoku naszej prezentacji. Typy widoków definiują sposób wyświetlania prezentacji po otwarciu. W tym przykładzie ustawimy go na „Widok wzorca slajdów”. Oto kod:

```java
// Ustawianie typu widoku
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 W powyższym kodzie używamy metody`setLastView` metoda`ViewProperties` class, na którą chcesz ustawić typ widoku`SlideMasterView`. W razie potrzeby możesz wybrać inne typy widoków.

## Krok 3: Zapisywanie prezentacji

Teraz, gdy stworzyliśmy naszą prezentację i ustawiliśmy typ widoku, czas zapisać prezentację. Zapiszemy go w formacie PPTX. Oto kod:

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 W tym kodzie używamy`save` metoda`Presentation` class, aby zapisać prezentację z określoną nazwą pliku i formatem.

## Kompletny kod źródłowy do zapisania jako predefiniowany typ widoku w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Otwieranie pliku prezentacji
Presentation presentation = new Presentation();
try
{
	// Ustawianie typu widoku
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Zapisywanie prezentacji
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak zapisać prezentację z predefiniowanym typem widoku w Javie przy użyciu Aspose.Slides for Java. Postępując zgodnie z dostarczonym kodem i krokami, możesz łatwo ustawić typ widoku swoich prezentacji i zapisać je w żądanym formacie.

## Często zadawane pytania

### Jak zmienić typ widoku na inny niż „Widok wzorca slajdów”?

 Aby zmienić typ widoku na inny niż „Widok wzorca slajdów”, po prostu zamień`ViewType.SlideMasterView` z żądanym typem widoku, np`ViewType.NormalView` Lub`ViewType.SlideSorterView`, w kodzie, w którym ustawiamy typ widoku.

### Czy mogę ustawić właściwości widoku dla poszczególnych slajdów w prezentacji?

Tak, możesz ustawić właściwości widoku dla poszczególnych slajdów za pomocą Aspose.Slides for Java. Możesz uzyskać dostęp do właściwości każdego slajdu i manipulować nimi oddzielnie, przeglądając slajdy w prezentacji.

### W jakich innych formatach mogę zapisać prezentację?

Aspose.Slides for Java obsługuje różne formaty wyjściowe, w tym PPTX, PDF, TIFF, HTML i inne. Możesz określić żądany format podczas zapisywania prezentacji, używając odpowiedniego`SaveFormat` wartość wyliczeniowa.

### Czy Aspose.Slides for Java nadaje się do wsadowego przetwarzania prezentacji?

Tak, Aspose.Slides for Java dobrze nadaje się do zadań przetwarzania wsadowego. Możesz zautomatyzować przetwarzanie wielu prezentacji, zastosować zmiany i zapisać je zbiorczo za pomocą kodu Java.

### Gdzie mogę znaleźć więcej informacji i dokumentacji dla Aspose.Slides dla Java?

 Aby uzyskać obszerną dokumentację i odniesienia związane z Aspose.Slides for Java, odwiedź witrynę z dokumentacją:[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
