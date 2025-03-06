---
title: Konwertuj przy użyciu rozmiaru niestandardowego w slajdach Java
linktitle: Konwertuj przy użyciu rozmiaru niestandardowego w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak konwertować prezentacje programu PowerPoint do obrazów TIFF o niestandardowym rozmiarze przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu dla programistów.
weight: 31
url: /pl/java/presentation-conversion/convert-custom-size-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do konwersji z niestandardowym rozmiarem w slajdach Java

W tym artykule przyjrzymy się, jak konwertować prezentacje programu PowerPoint do obrazów TIFF o niestandardowym rozmiarze za pomocą interfejsu API Aspose.Slides for Java. Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom programową pracę z plikami programu PowerPoint. Przejdziemy krok po kroku i udostępnimy Ci kod Java niezbędny do wykonania tego zadania.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- Zainstalowany zestaw Java Development Kit (JDK).
- Aspose.Slides dla biblioteki Java

 Bibliotekę Aspose.Slides for Java możesz pobrać ze strony internetowej:[Pobierz Aspose.Slides dla Java](https://releases.aspose.com/slides/java/)

## Krok 1: Zaimportuj bibliotekę Aspose.Slides

Aby rozpocząć, musisz zaimportować bibliotekę Aspose.Slides do swojego projektu Java. Oto jak możesz to zrobić:

```java
// Dodaj niezbędną instrukcję importu
import com.aspose.slides.*;
```

## Krok 2: Załaduj prezentację programu PowerPoint

 Następnie musisz załadować prezentację programu PowerPoint, którą chcesz przekonwertować na obraz TIFF. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz instancję obiektu Prezentacja, który reprezentuje plik Prezentacji
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Krok 3: Ustaw opcje konwersji TIFF

Teraz ustawmy opcje konwersji TIFF. Określimy typ kompresji, DPI (punkty na cal), rozmiar obrazu i położenie notatek. Możesz dostosować te opcje zgodnie ze swoimi wymaganiami.

```java
// Utwórz instancję klasy TiffOptions
TiffOptions opts = new TiffOptions();

// Ustawianie rodzaju kompresji
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

Po skonfigurowaniu wszystkich opcji możesz teraz zapisać prezentację jako obraz TIFF z określonymi ustawieniami.

```java
// Zapisz prezentację w formacie TIFF o określonym rozmiarze obrazu
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Kompletny kod źródłowy do konwersji z niestandardowym rozmiarem w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję obiektu Prezentacja, który reprezentuje plik Prezentacji
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Utwórz instancję klasy TiffOptions
	TiffOptions opts = new TiffOptions();
	// Ustawianie rodzaju kompresji
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Typy kompresji
	// Domyślny — określa domyślny schemat kompresji (LZW).
	// Brak — określa brak kompresji.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Głębokość zależy od rodzaju kompresji i nie można jej ustawić ręcznie.
	// Jednostka rozdzielczości jest zawsze równa „2” (punktów na cal)
	// Ustawianie DPI obrazu
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Ustaw rozmiar obrazu
	opts.setImageSize(new Dimension(1728, 1078));
	// Zapisz prezentację w formacie TIFF o określonym rozmiarze obrazu
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Gratulacje! Pomyślnie przekonwertowałeś prezentację programu PowerPoint na obraz TIFF o niestandardowym rozmiarze przy użyciu Aspose.Slides for Java. Może to być cenna funkcja, gdy trzeba wygenerować wysokiej jakości obrazy z prezentacji do różnych celów.

## Często zadawane pytania

### Jak zmienić typ kompresji obrazu TIFF?

 Możesz zmienić typ kompresji, modyfikując plik`setCompressionType` metoda w`TiffOptions` klasa. Dostępne są różne typy kompresji, takie jak Domyślna, Brak, CCITT3, CCITT4, LZW i RLE.

### Czy mogę dostosować DPI (punkty na cal) obrazu TIFF?

Tak, możesz dostosować DPI za pomocą`setDpiX` I`setDpiY` metody w`TiffOptions` klasa. Wystarczy ustawić żądane wartości, aby kontrolować rozdzielczość obrazu.

### Jakie są dostępne opcje położenia notatek na obrazie TIFF?

 Położenie notatek na obrazie TIFF można skonfigurować za pomocą opcji`setNotesPosition` metodę z opcjami takimi jak BottomFull, BottomTruncated i SlideOnly. Wybierz ten, który najlepiej odpowiada Twoim potrzebom.

### Czy można określić niestandardowy rozmiar obrazu do konwersji TIFF?

 Absolutnie! Możesz ustawić niestandardowy rozmiar obrazu za pomocą opcji`setImageSize` metoda w`TiffOptions` klasa. Podaj żądane wymiary (szerokość i wysokość) obrazu wyjściowego.

### Gdzie mogę znaleźć więcej informacji na temat Aspose.Slides dla Java?

 Aby uzyskać szczegółową dokumentację i dodatkowe informacje na temat Aspose.Slides for Java, odwiedź dokumentację:[Aspose.Slides dla odniesienia do API Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
