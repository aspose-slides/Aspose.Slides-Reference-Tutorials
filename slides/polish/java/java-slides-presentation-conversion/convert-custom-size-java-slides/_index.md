---
"description": "Dowiedz się, jak konwertować prezentacje PowerPoint na obrazy TIFF o niestandardowym rozmiarze za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu dla programistów."
"linktitle": "Konwertuj z niestandardowym rozmiarem w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Konwertuj z niestandardowym rozmiarem w slajdach Java"
"url": "/pl/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konwertuj z niestandardowym rozmiarem w slajdach Java


## Wprowadzenie do konwersji z niestandardowym rozmiarem w slajdach Java

tym artykule przyjrzymy się sposobowi konwersji prezentacji PowerPoint na obrazy TIFF o niestandardowym rozmiarze przy użyciu interfejsu API Aspose.Slides for Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom programową pracę z plikami PowerPoint. Przejdziemy przez to krok po kroku i dostarczymy Ci niezbędny kod Java do wykonania tego zadania.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Zainstalowano Java Development Kit (JDK)
- Biblioteka Aspose.Slides dla Java

Bibliotekę Aspose.Slides for Java można pobrać ze strony internetowej: [Pobierz Aspose.Slides dla Java](https://releases.aspose.com/slides/java/)

## Krok 1: Importuj bibliotekę Aspose.Slides

Aby zacząć, musisz zaimportować bibliotekę Aspose.Slides do swojego projektu Java. Oto, jak możesz to zrobić:

```java
// Dodaj niezbędne polecenie importu
import com.aspose.slides.*;
```

## Krok 2: Załaduj prezentację PowerPoint

Następnie musisz załadować prezentację PowerPoint, którą chcesz przekonwertować na obraz TIFF. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz obiekt Prezentacja reprezentujący plik Prezentacji
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Krok 3: Ustaw opcje konwersji TIFF

Teraz ustawmy opcje konwersji TIFF. Określimy typ kompresji, DPI (punkty na cal), rozmiar obrazu i położenie notatek. Możesz dostosować te opcje zgodnie ze swoimi wymaganiami.

```java
// Utwórz instancję klasy TiffOptions
TiffOptions opts = new TiffOptions();

// Ustawianie typu kompresji
opts.setCompressionType(TiffCompressionTypes.Default);

// Ustawianie DPI obrazu
opts.setDpiX(200);
opts.setDpiY(100);

// Ustaw rozmiar obrazu
opts.setImageSize(new Dimension(1728, 1078));

// Ustaw pozycję notatek
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 4: Zapisz jako TIFF

Po skonfigurowaniu wszystkich opcji możesz zapisać prezentację jako obraz TIFF z określonymi ustawieniami.

```java
// Zapisz prezentację w formacie TIFF z określonym rozmiarem obrazu
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Kompletny kod źródłowy do konwersji z niestandardowym rozmiarem w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz obiekt Prezentacja reprezentujący plik Prezentacji
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Utwórz instancję klasy TiffOptions
	TiffOptions opts = new TiffOptions();
	// Ustawianie typu kompresji
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Typy kompresji
	// Domyślny — określa domyślny schemat kompresji (LZW).
	// Brak – określa brak kompresji.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Głębokość zależy od rodzaju kompresji i nie można jej ustawić ręcznie.
	// Jednostka rozdzielczości jest zawsze równa „2” (punkty na cal)
	// Ustawianie DPI obrazu
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Ustaw rozmiar obrazu
	opts.setImageSize(new Dimension(1728, 1078));
	// Zapisz prezentację w formacie TIFF z określonym rozmiarem obrazu
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Gratulacje! Udało Ci się przekonwertować prezentację PowerPoint na obraz TIFF o niestandardowym rozmiarze przy użyciu Aspose.Slides dla Java. Może to być cenna funkcja, gdy musisz wygenerować wysokiej jakości obrazy ze swoich prezentacji do różnych celów.

## Najczęściej zadawane pytania

### Jak mogę zmienić typ kompresji obrazu TIFF?

Możesz zmienić typ kompresji, modyfikując `setCompressionType` metoda w `TiffOptions` Klasa. Dostępne są różne typy kompresji, takie jak Domyślna, Brak, CCITT3, CCITT4, LZW i RLE.

### Czy mogę zmienić rozdzielczość (DPI) obrazu TIFF?

Tak, możesz dostosować DPI za pomocą `setDpiX` I `setDpiY` metody w `TiffOptions` Klasa. Po prostu ustaw żądane wartości, aby kontrolować rozdzielczość obrazu.

### Jakie są dostępne opcje dotyczące położenia notatek w obrazie TIFF?

Pozycję notatek w obrazie TIFF można skonfigurować za pomocą `setNotesPosition` metoda z opcjami takimi jak BottomFull, BottomTruncated i SlideOnly. Wybierz tę, która najlepiej odpowiada Twoim potrzebom.

### Czy można określić niestandardowy rozmiar obrazu dla konwersji TIFF?

Oczywiście! Możesz ustawić niestandardowy rozmiar obrazu, używając `setImageSize` metoda w `TiffOptions` Klasa. Podaj wymiary (szerokość i wysokość), jakie chcesz dla obrazu wyjściowego.

### Gdzie mogę znaleźć więcej informacji o Aspose.Slides dla Java?

Aby uzyskać szczegółową dokumentację i dodatkowe informacje na temat Aspose.Slides dla Java, zapoznaj się z dokumentacją: [Aspose.Slides dla Java API Reference](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}