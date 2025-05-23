---
"description": "Dowiedz się, jak ulepszyć prezentacje PowerPoint za pomocą niestandardowych właściwości dokumentu w Java Slides. Przewodnik krok po kroku z przykładami kodu przy użyciu Aspose.Slides dla Java."
"linktitle": "Dodawanie niestandardowych właściwości dokumentu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodawanie niestandardowych właściwości dokumentu w slajdach Java"
"url": "/pl/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie niestandardowych właściwości dokumentu w slajdach Java


## Wprowadzenie do dodawania niestandardowych właściwości dokumentu w slajdach Java

W tym samouczku przeprowadzimy Cię przez proces dodawania niestandardowych właściwości dokumentu do prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Niestandardowe właściwości dokumentu pozwalają Ci przechowywać dodatkowe informacje o prezentacji w celach informacyjnych lub kategoryzacji.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że biblioteka Aspose.Slides for Java jest zainstalowana i skonfigurowana w projekcie Java.

## Krok 1: Importuj wymagane pakiety

```java
import com.aspose.slides.*;
```

## Krok 2: Utwórz nową prezentację

Najpierw musisz utworzyć nowy obiekt prezentacji. Możesz to zrobić w następujący sposób:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";

// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
```

## Krok 3: Pobieranie właściwości dokumentu

Następnie pobierzesz właściwości dokumentu prezentacji. Właściwości te obejmują wbudowane właściwości, takie jak tytuł, autor i właściwości niestandardowe, które możesz dodać.

```java
// Pobieranie właściwości dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## Krok 4: Dodawanie niestandardowych właściwości

Teraz dodajmy niestandardowe właściwości do prezentacji. Niestandardowe właściwości składają się z nazwy i wartości. Możesz ich użyć do przechowywania dowolnych informacji, które chcesz.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## Krok 5: Uzyskanie nazwy nieruchomości pod określonym indeksem

Możesz również pobrać nazwę niestandardowej właściwości pod określonym indeksem. Może to być przydatne, jeśli musisz pracować z określonymi właściwościami.

```java
// Pobieranie nazwy właściwości pod określonym indeksem
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## Krok 6: Usuwanie wybranej właściwości

Jeśli chcesz usunąć niestandardową właściwość, możesz to zrobić, podając jej nazwę. Tutaj usuwamy właściwość, którą uzyskaliśmy w kroku 5.

```java
// Usuwanie wybranej właściwości
documentProperties.removeCustomProperty(getPropertyName);
```

## Krok 7: Zapisywanie prezentacji

Na koniec zapisz prezentację z dodanymi i usuniętymi właściwościami niestandardowymi do pliku.

```java
// Zapisywanie prezentacji
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy do dodawania niestandardowych właściwości dokumentu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Presentation
Presentation presentation = new Presentation();
// Pobieranie właściwości dokumentu
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Dodawanie właściwości niestandardowych
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Pobieranie nazwy właściwości pod określonym indeksem
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Usuwanie wybranej właściwości
documentProperties.removeCustomProperty(getPropertyName);
// Zapisywanie prezentacji
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Wniosek

Nauczyłeś się, jak dodawać niestandardowe właściwości dokumentu do prezentacji PowerPoint w Javie za pomocą Aspose.Slides. Niestandardowe właściwości mogą być cenne do przechowywania dodatkowych informacji związanych z prezentacjami. Możesz rozszerzyć tę wiedzę, aby uwzględnić więcej niestandardowych właściwości, jeśli będzie to potrzebne w konkretnym przypadku użycia.

## Najczęściej zadawane pytania

### Jak pobrać wartość właściwości niestandardowej?

Aby pobrać wartość właściwości niestandardowej, możesz użyć `get_Item` metoda na `documentProperties` obiekt. Na przykład:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Czy mogę dodać niestandardowe właściwości różnych typów danych?

Tak, możesz dodawać niestandardowe właściwości różnych typów danych, w tym liczby, ciągi znaków, daty i inne, jak pokazano w przykładzie. Aspose.Slides for Java bezproblemowo obsługuje różne typy danych.

### Czy liczba niestandardowych właściwości, które mogę dodać, jest ograniczona?

Nie ma ścisłego limitu liczby niestandardowych właściwości, które możesz dodać. Pamiętaj jednak, że dodanie nadmiernej liczby właściwości może wpłynąć na wydajność i rozmiar pliku prezentacji.

### Jak mogę wyświetlić listę wszystkich właściwości niestandardowych w prezentacji?

Możesz przejść przez wszystkie niestandardowe właściwości, aby je wyświetlić. Oto przykład, jak to zrobić:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Ten kod wyświetli nazwy i wartości wszystkich niestandardowych właściwości w prezentacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}