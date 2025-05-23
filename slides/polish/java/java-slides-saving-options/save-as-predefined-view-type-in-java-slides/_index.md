---
"description": "Dowiedz się, jak ustawić wstępnie zdefiniowane typy widoków w Java Slides przy użyciu Aspose.Slides for Java. Przewodnik krok po kroku z przykładami kodu i często zadawanymi pytaniami."
"linktitle": "Zapisz jako wstępnie zdefiniowany typ widoku w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zapisz jako wstępnie zdefiniowany typ widoku w slajdach Java"
"url": "/pl/java/saving-options/save-as-predefined-view-type-in-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zapisz jako wstępnie zdefiniowany typ widoku w slajdach Java


## Wprowadzenie do zapisywania jako wstępnie zdefiniowany typ widoku w slajdach Java

W tym przewodniku krok po kroku pokażemy, jak zapisać prezentację z predefiniowanym typem widoku przy użyciu Aspose.Slides dla Java. Dostarczymy Ci niezbędny kod i wyjaśnienia, aby pomyślnie wykonać to zadanie.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- Podstawowa znajomość programowania w Javie.
- Zainstalowano bibliotekę Aspose.Slides for Java.
- Zintegrowane środowisko programistyczne (IDE) według Twojego wyboru.

## Konfigurowanie środowiska

Aby rozpocząć, wykonaj poniższe kroki, aby skonfigurować środowisko programistyczne:

1. Utwórz nowy projekt Java w swoim IDE.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu jako zależność.

Teraz gdy Twoje środowisko jest już skonfigurowane, możemy zająć się kodem.

## Krok 1: Tworzenie prezentacji

Aby zademonstrować zapisywanie prezentacji z predefiniowanym typem widoku, najpierw utworzymy nową prezentację. Oto kod do utworzenia prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Otwieranie pliku prezentacji
Presentation presentation = new Presentation();
```

W tym kodzie tworzymy nowy `Presentation` obiekt, który reprezentuje naszą prezentację PowerPoint.

## Krok 2: Ustawianie typu widoku

Następnie ustawimy typ widoku dla naszej prezentacji. Typy widoku definiują sposób wyświetlania prezentacji po jej otwarciu. W tym przykładzie ustawimy go na „Widok wzorca slajdów”. Oto kod:

```java
// Ustawianie typu widoku
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

W powyższym kodzie używamy `setLastView` metoda `ViewProperties` klasa do ustawienia typu widoku `SlideMasterView`. W razie potrzeby możesz wybrać inne typy widoku.

## Krok 3: Zapisywanie prezentacji

Teraz, gdy utworzyliśmy prezentację i ustawiliśmy typ widoku, czas zapisać prezentację. Zapiszemy ją w formacie PPTX. Oto kod:

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

W tym kodzie używamy `save` metoda `Presentation` klasa umożliwiająca zapisanie prezentacji z określoną nazwą pliku i formatem.

## Kompletny kod źródłowy do zapisania jako wstępnie zdefiniowany typ widoku w slajdach Java

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

tym samouczku nauczyliśmy się, jak zapisać prezentację z predefiniowanym typem widoku w Javie, używając Aspose.Slides dla Javy. Postępując zgodnie z podanym kodem i krokami, możesz łatwo ustawić typ widoku swoich prezentacji i zapisać je w żądanym formacie.

## Najczęściej zadawane pytania

### Jak zmienić typ widoku na inny niż „Widok wzorca slajdów”?

Aby zmienić typ widoku na inny niż „Widok wzorca slajdów”, wystarczy zastąpić `ViewType.SlideMasterView` z żądanym typem widoku, takim jak `ViewType.NLubmalView` or `ViewType.SlideSorterView`, w kodzie, w którym ustawiamy typ widoku.

### Czy mogę ustawić właściwości widoku dla poszczególnych slajdów w prezentacji?

Tak, możesz ustawić właściwości widoku dla poszczególnych slajdów za pomocą Aspose.Slides dla Java. Możesz uzyskać dostęp i manipulować właściwościami dla każdego slajdu oddzielnie, iterując slajdy w prezentacji.

### W jakich innych formatach mogę zapisać swoją prezentację?

Aspose.Slides for Java obsługuje różne formaty wyjściowe, w tym PPTX, PDF, TIFF, HTML i inne. Możesz określić żądany format podczas zapisywania prezentacji, używając odpowiedniego `SaveFormat` wartość wyliczeniowa.

### Czy Aspose.Slides for Java nadaje się do przetwarzania wsadowego prezentacji?

Tak, Aspose.Slides for Java jest dobrze przystosowany do zadań przetwarzania wsadowego. Możesz zautomatyzować przetwarzanie wielu prezentacji, stosować zmiany i zapisywać je zbiorczo za pomocą kodu Java.

### Gdzie mogę znaleźć więcej informacji i dokumentację dotyczącą Aspose.Slides dla Java?

Aby uzyskać pełną dokumentację i odnośniki dotyczące Aspose.Slides dla Java, odwiedź witrynę dokumentacji: [Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}