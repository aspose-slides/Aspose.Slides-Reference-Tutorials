---
title: Dodaj niestandardowe właściwości dokumentu w slajdach Java
linktitle: Dodaj niestandardowe właściwości dokumentu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ulepszyć prezentacje programu PowerPoint za pomocą niestandardowych właściwości dokumentu w aplikacji Java Slides. Przewodnik krok po kroku z przykładami kodu przy użyciu Aspose.Slides dla Java.
weight: 13
url: /pl/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do dodawania niestandardowych właściwości dokumentu w slajdach Java

W tym samouczku przeprowadzimy Cię przez proces dodawania niestandardowych właściwości dokumentu do prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Niestandardowe właściwości dokumentu umożliwiają przechowywanie dodatkowych informacji o prezentacji w celach informacyjnych lub kategoryzacji.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowaną i skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java.

## Krok 1: Zaimportuj wymagane pakiety

```java
import com.aspose.slides.*;
```

## Krok 2: Utwórz nową prezentację

Najpierw musisz utworzyć nowy obiekt prezentacji. Możesz to zrobić w następujący sposób:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```

## Krok 3: Pobieranie właściwości dokumentu

Następnie pobierzesz właściwości dokumentu prezentacji. Właściwości te obejmują właściwości wbudowane, takie jak tytuł, autor i właściwości niestandardowe, które można dodać.

```java
// Uzyskiwanie właściwości dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Krok 4: Dodawanie właściwości niestandardowych

Teraz dodajmy niestandardowe właściwości do prezentacji. Właściwości niestandardowe składają się z nazwy i wartości. Możesz ich używać do przechowywania dowolnych informacji.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Krok 5: Uzyskanie nazwy właściwości według określonego indeksu

Można także pobrać nazwę właściwości niestandardowej w określonym indeksie. Może to być przydatne, jeśli musisz pracować z określonymi właściwościami.

```java
// Pobieranie nazwy właściwości w określonym indeksie
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Krok 6: Usuwanie wybranej właściwości

Jeśli chcesz usunąć właściwość niestandardową, możesz to zrobić, podając jej nazwę. Tutaj usuwamy właściwość, którą uzyskaliśmy w kroku 5.

```java
// Usuwanie wybranej właściwości
documentProperties.removeCustomProperty(getPropertyName);
```

## Krok 7: Zapisywanie prezentacji

Na koniec zapisz prezentację z dodanymi i usuniętymi właściwościami niestandardowymi w pliku.

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy umożliwiający dodawanie niestandardowych właściwości dokumentu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
// Uzyskiwanie właściwości dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Dodawanie właściwości niestandardowych
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Pobieranie nazwy właściwości w określonym indeksie
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Usuwanie wybranej właściwości
documentProperties.removeCustomProperty(getPropertyName);
// Zapisywanie prezentacji
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Wniosek

Nauczyłeś się, jak dodawać niestandardowe właściwości dokumentu do prezentacji programu PowerPoint w Javie przy użyciu Aspose.Slides. Właściwości niestandardowe mogą być przydatne do przechowywania dodatkowych informacji związanych z prezentacjami. Możesz rozszerzyć tę wiedzę, aby uwzględnić więcej niestandardowych właściwości, jeśli są potrzebne w konkretnym przypadku użycia.

## Często zadawane pytania

### Jak odzyskać wartość właściwości niestandardowej?

 Aby pobrać wartość właściwości niestandardowej, możesz użyć metody`get_Item` metoda na`documentProperties` obiekt. Na przykład:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Czy mogę dodać niestandardowe właściwości różnych typów danych?

Tak, możesz dodawać niestandardowe właściwości różnych typów danych, w tym liczb, ciągów znaków, dat i innych, jak pokazano w przykładzie. Aspose.Slides dla Java płynnie obsługuje różne typy danych.

### Czy istnieje ograniczenie liczby niestandardowych właściwości, które mogę dodać?

Nie ma ścisłego ograniczenia liczby niestandardowych właściwości, które można dodać. Należy jednak pamiętać, że dodanie nadmiernej liczby właściwości może mieć wpływ na wydajność i rozmiar pliku prezentacji.

### Jak wyświetlić listę wszystkich właściwości niestandardowych w prezentacji?

Możesz przeglądać wszystkie niestandardowe właściwości, aby je wyświetlić. Oto przykład, jak to zrobić:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Ten kod wyświetli nazwy i wartości wszystkich właściwości niestandardowych w prezentacji.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
