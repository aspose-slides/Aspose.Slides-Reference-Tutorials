---
"description": "Dowiedz się, jak uzyskać dostęp do wbudowanych właściwości w programie PowerPoint za pomocą Aspose.Slides dla Java. Ten samouczek przeprowadzi Cię przez pobieranie autora, daty utworzenia i innych."
"linktitle": "Dostęp do wbudowanych właściwości w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dostęp do wbudowanych właściwości w programie PowerPoint"
"url": "/pl/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dostęp do wbudowanych właściwości w programie PowerPoint

## Wstęp
tym samouczku pokażemy, jak uzyskać dostęp do wbudowanych właściwości w prezentacjach PowerPoint za pomocą Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom Java pracę z prezentacjami PowerPoint programowo, umożliwiając bezproblemowe wykonywanie zadań, takich jak odczytywanie i modyfikowanie właściwości.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w swoim systemie. Możesz go pobrać ze strony [Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [ten link](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego projektu Java. Dodaj następującą instrukcję importu na początku swojego pliku Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Krok 1: Skonfiguruj obiekt prezentacji
Zacznij od skonfigurowania obiektu Presentation, aby reprezentował prezentację PowerPoint, z którą chcesz pracować. Oto, jak możesz to zrobić:
```java
// Ścieżka do katalogu zawierającego plik prezentacji
String dataDir = "path_to_your_presentation_directory/";
// Utwórz instancję klasy Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Krok 2: Uzyskaj dostęp do właściwości dokumentu
Po skonfigurowaniu obiektu Presentation możesz uzyskać dostęp do wbudowanych właściwości prezentacji za pomocą interfejsu IDocumentProperties. Oto, jak możesz pobrać różne właściwości:
### Kategoria
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Aktualny status
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Data utworzenia
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Opis
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Słowa kluczowe
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Ostatnia modyfikacja przez
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Kierownik
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Data modyfikacji
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Format prezentacji
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Ostatnia data wydruku
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Współdzielone między producentami
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Temat
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Tytuł
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Wniosek
W tym samouczku nauczyliśmy się, jak uzyskać dostęp do wbudowanych właściwości w prezentacjach PowerPoint za pomocą Aspose.Slides for Java. Postępując zgodnie z powyższymi krokami, możesz łatwo pobrać różne właściwości, takie jak autor, data utworzenia i tytuł, programowo.
## Najczęściej zadawane pytania
### Czy mogę modyfikować te wbudowane właściwości, używając Aspose.Slides dla Java?
Tak, możesz modyfikować te właściwości za pomocą Aspose.Slides. Po prostu użyj odpowiednich metod setter dostarczonych przez interfejs IDocumentProperties.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Aspose.Slides obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność na różnych platformach.
### Czy mogę również pobrać właściwości niestandardowe?
Tak, oprócz wbudowanych właściwości możesz również pobierać i modyfikować właściwości niestandardowe, korzystając z Aspose.Slides dla Java.
### Czy Aspose.Slides oferuje dokumentację i pomoc techniczną?
Tak, na stronie znajdziesz kompleksową dokumentację i dostęp do forów pomocy technicznej. [Strona internetowa Aspose](https://reference.aspose.com/slides/java/).
### Czy jest dostępna wersja próbna Aspose.Slides dla Java?
Tak, możesz pobrać bezpłatną wersję próbną ze strony [Tutaj](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}