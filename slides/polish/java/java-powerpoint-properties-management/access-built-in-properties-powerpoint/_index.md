---
title: Uzyskaj dostęp do wbudowanych właściwości w programie PowerPoint
linktitle: Uzyskaj dostęp do wbudowanych właściwości w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak uzyskać dostęp do wbudowanych właściwości programu PowerPoint przy użyciu Aspose.Slides dla języka Java. Ten samouczek przeprowadzi Cię przez proces pobierania autora, daty utworzenia i innych informacji.
weight: 10
url: /pl/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku omówimy, jak uzyskać dostęp do wbudowanych właściwości prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom Java programową pracę z prezentacjami programu PowerPoint, umożliwiając bezproblemowe wykonywanie takich zadań, jak czytanie i modyfikowanie właściwości.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK. Można go pobrać z[Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[ten link](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego projektu Java. Dodaj następującą instrukcję importu na początku pliku Java:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Krok 1: Skonfiguruj obiekt prezentacji
Zacznij od skonfigurowania obiektu Prezentacja reprezentującego prezentację programu PowerPoint, z którą chcesz pracować. Oto jak możesz to zrobić:
```java
// Ścieżka do katalogu zawierającego plik prezentacji
String dataDir = "path_to_your_presentation_directory/";
// Utwórz instancję klasy Prezentacja
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Krok 2: Uzyskaj dostęp do właściwości dokumentu
Po skonfigurowaniu obiektu Prezentacja można uzyskać dostęp do wbudowanych właściwości prezentacji za pomocą interfejsu IDocumentProperties. Oto jak możesz odzyskać różne właściwości:
### Kategoria
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Aktualny stan
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
### Zmieniona data
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Forma prezentacji
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Data ostatniego wydruku
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Udostępniane pomiędzy producentami
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
tym samouczku nauczyliśmy się, jak uzyskać dostęp do wbudowanych właściwości prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java. Wykonując kroki opisane powyżej, możesz łatwo programowo pobrać różne właściwości, takie jak autor, data utworzenia i tytuł.
## Często zadawane pytania
### Czy mogę modyfikować te wbudowane właściwości za pomocą Aspose.Slides dla Java?
Tak, możesz modyfikować te właściwości za pomocą Aspose.Slides. Wystarczy użyć odpowiednich metod ustawiających udostępnianych przez interfejs IDocumentProperties.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Aspose.Slides obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność na różnych platformach.
### Czy mogę również pobrać właściwości niestandardowe?
Tak, oprócz wbudowanych właściwości, możesz także pobierać i modyfikować właściwości niestandardowe za pomocą Aspose.Slides for Java.
### Czy Aspose.Slides oferuje dokumentację i wsparcie?
 Tak, obszerną dokumentację i fora pomocy technicznej można znaleźć na stronie[Strona Aspose](https://reference.aspose.com/slides/java/).
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
