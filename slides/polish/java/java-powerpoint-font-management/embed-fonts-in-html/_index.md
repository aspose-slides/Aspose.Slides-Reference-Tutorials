---
"description": "Dowiedz się, jak osadzać czcionki w kodzie HTML za pomocą Aspose.Slides for Java, aby zapewnić spójną typografię na różnych platformach i urządzeniach."
"linktitle": "Osadzanie czcionek w HTML przy użyciu Aspose.Slides dla Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Osadzanie czcionek w HTML przy użyciu Aspose.Slides dla Java"
"url": "/pl/java/java-powerpoint-font-management/embed-fonts-in-html/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Osadzanie czcionek w HTML przy użyciu Aspose.Slides dla Java

## Wstęp
Aspose.Slides for Java to potężne narzędzie dla programistów Java, którzy chcą programowo manipulować prezentacjami PowerPoint. W tym samouczku zagłębimy się w proces osadzania czcionek w HTML przy użyciu Aspose.Slides for Java. Dzięki osadzeniu czcionek masz pewność, że Twoje prezentacje zachowają zamierzony wygląd na różnych platformach i urządzeniach, nawet jeśli wymagane czcionki nie są zainstalowane lokalnie.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełnione są następujące wymagania wstępne:
1. Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany JDK.
2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [strona do pobrania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko IDE do tworzenia oprogramowania w języku Java, np. IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby rozpocząć osadzanie czcionek w kodzie HTML za pomocą Aspose.Slides dla Java.
```java
import com.aspose.slides.*;
```
## Krok 1: Zdefiniuj katalogi dokumentów i wyjściowe
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
Upewnij się, że wymieniasz `"Your Document Directory"` I `"Your Output Directory"` ze ścieżkami do wejściowej prezentacji PowerPoint i pożądanego katalogu wyjściowego.
## Krok 2: Załaduj prezentację
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Ten krok powoduje załadowanie prezentacji programu PowerPoint do pamięci, co umożliwia wykonywanie na niej różnych operacji.
## Krok 3: Wyklucz domyślne czcionki
```java
String[] fontNameExcludeList = { "Arial" };
```
Określ czcionki, które chcesz wykluczyć z osadzania. W tym przykładzie wykluczamy Arial.
## Krok 4: Osadź czcionki w HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
W tym kroku tworzymy instancję `EmbedAllFontsHtmlController` aby osadzić wszystkie czcionki z wyjątkiem tych określonych na liście wykluczeń. Następnie definiujemy `HtmlOptions` i ustaw niestandardowy formater HTML, aby osadzić czcionki. Na koniec zapisujemy prezentację jako HTML z osadzonymi czcionkami.

## Wniosek
tym samouczku przyjrzeliśmy się sposobowi osadzania czcionek w HTML przy użyciu Aspose.Slides dla Java. Postępując zgodnie z podanymi krokami, możesz upewnić się, że Twoje prezentacje będą miały spójną typografię na różnych platformach i urządzeniach, co poprawi ogólne wrażenia wizualne.
## Najczęściej zadawane pytania
### Czy mogę osadzić określone czcionki zamiast je wykluczać?
Tak, możesz określić czcionki, które chcesz osadzić, modyfikując `fontNameExcludeList` ułóż odpowiednio.
### Czy Aspose.Slides for Java obsługuje osadzanie czcionek w innych formatach niż HTML?
Tak, Aspose.Slides obsługuje osadzanie czcionek w różnych formatach wyjściowych, w tym PDF i obrazach.
### Czy jest dostępna wersja próbna Aspose.Slides dla Java?
Tak, możesz pobrać bezpłatną wersję próbną z [Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dodatkową pomoc lub wsparcie dotyczące Aspose.Slides dla Java?
Możesz odwiedzić [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) Jeśli potrzebujesz wsparcia ze strony społeczności lub skontaktuj się z pomocą techniczną Aspose, aby uzyskać profesjonalną pomoc.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla Java?
Tak, możesz uzyskać tymczasową licencję od [strona zakupu](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}