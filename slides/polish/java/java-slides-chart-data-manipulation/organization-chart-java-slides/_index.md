---
"description": "Dowiedz się, jak tworzyć oszałamiające schematy organizacyjne w Java Slides dzięki samouczkom krok po kroku Aspose.Slides. Dostosuj i wizualizuj swoją strukturę organizacyjną bez wysiłku."
"linktitle": "Schemat organizacyjny w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Schemat organizacyjny w slajdach Java"
"url": "/pl/java/chart-data-manipulation/organization-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Schemat organizacyjny w slajdach Java


## Wprowadzenie do tworzenia schematu organizacyjnego w slajdach Java przy użyciu Aspose.Slides

W tym samouczku pokażemy, jak utworzyć schemat organizacyjny w Java Slides przy użyciu Aspose.Slides for Java API. Schemat organizacyjny to wizualna reprezentacja hierarchicznej struktury organizacji, zwykle używana do zilustrowania relacji i hierarchii wśród pracowników lub działów.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:

- [Aspose.Slides dla Java](https://products.aspose.com/slides/java) biblioteka zainstalowana w Twoim projekcie Java.
- Zintegrowane środowisko programistyczne Java (IDE), takie jak IntelliJ IDEA lub Eclipse.

## Krok 1: Skonfiguruj swój projekt Java

1. Utwórz nowy projekt Java w preferowanym środowisku IDE.
2. Dodaj bibliotekę Aspose.Slides for Java do swojego projektu. Możesz pobrać bibliotekę ze strony [Strona internetowa Aspose](https://products.aspose.com/slides/java) i uwzględnij to jako zależność.

## Krok 2: Importuj wymagane biblioteki
W swojej klasie Java zaimportuj niezbędne biblioteki, aby pracować z Aspose.Slides:

```java
import com.aspose.slides.*;
```

## Krok 3: Utwórz schemat organizacyjny

Teraz utwórzmy schemat organizacyjny za pomocą Aspose.Slides. Wykonamy następujące kroki:

1. Podaj ścieżkę do katalogu dokumentów.
2. Załaduj istniejącą prezentację programu PowerPoint lub utwórz nową.
3. Dodaj kształt schematu organizacyjnego do slajdu.
4. Zapisz prezentację ze schematem organizacyjnym.

Oto kod pozwalający to osiągnąć:

```java
// Podaj ścieżkę do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Załaduj istniejącą prezentację lub utwórz nową.
Presentation pres = new Presentation(dataDir + "test.pptx");
try {
    // Dodaj kształt schematu organizacyjnego do pierwszego slajdu.
    ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);

    // Zapisz prezentację ze schematem organizacyjnym.
    pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Zastępować `"Your Document Directory"` z rzeczywistą ścieżką do katalogu dokumentów i `"test.pptx"` nazwą prezentacji PowerPoint, którą chcesz wprowadzić.

## Krok 4: Uruchom kod

Teraz, gdy dodałeś kod do utworzenia schematu organizacyjnego, uruchom swoją aplikację Java. Upewnij się, że biblioteka Aspose.Slides została poprawnie dodana do projektu i że niezbędne zależności zostały rozwiązane.

## Kompletny kod źródłowy dla schematu organizacyjnego w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	ISmartArt smartArt = pres.getSlides().get_Item(0).getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.PictureOrganizationChart);
	pres.save(dataDir + "OrganizationChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku dowiedziałeś się, jak utworzyć schemat organizacyjny w Java Slides przy użyciu Aspose.Slides for Java API. Możesz dostosować wygląd i zawartość schematu organizacyjnego zgodnie ze swoimi konkretnymi wymaganiami. Aspose.Slides oferuje szeroki zakres funkcji do pracy z prezentacjami PowerPoint, co czyni go potężnym narzędziem do zarządzania i tworzenia treści wizualnych.

## Najczęściej zadawane pytania

### Jak mogę dostosować wygląd schematu organizacyjnego?

Możesz dostosować wygląd schematu organizacyjnego, modyfikując jego właściwości, takie jak kolory, style i czcionki. Zapoznaj się z dokumentacją Aspose.Slides, aby uzyskać szczegółowe informacje na temat dostosowywania kształtów SmartArt.

### Czy mogę dodać dodatkowe kształty lub tekst do schematu organizacyjnego?

Tak, możesz dodać dodatkowe kształty, tekst i łączniki do schematu organizacyjnego, aby dokładnie przedstawić strukturę organizacyjną. Użyj interfejsu API Aspose.Slides, aby dodać i sformatować kształty w diagramie SmartArt.

### Jak mogę wyeksportować schemat organizacyjny do innych formatów, np. PDF lub obrazu?

Możesz eksportować prezentację zawierającą schemat organizacyjny do różnych formatów za pomocą Aspose.Slides. Na przykład, aby eksportować do PDF, użyj `SaveFormat.Pdf` opcja podczas zapisywania prezentacji. Podobnie, możesz eksportować do formatów obrazów, takich jak PNG lub JPEG.

### Czy możliwe jest stworzenie złożonych struktur organizacyjnych z wieloma poziomami?

Tak, Aspose.Slides pozwala tworzyć złożone struktury organizacyjne z wieloma poziomami poprzez dodawanie i układanie kształtów w schemacie organizacyjnym. Możesz zdefiniować hierarchiczne relacje między kształtami, aby przedstawić pożądaną strukturę.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}