---
"description": "Dowiedz się, jak włączyć właściwości Read-Only Recommended w prezentacjach Java PowerPoint przy użyciu Aspose.Slides for Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku z przykładami kodu źródłowego, aby zwiększyć bezpieczeństwo prezentacji."
"linktitle": "Właściwości zalecane tylko do odczytu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Właściwości zalecane tylko do odczytu w slajdach Java"
"url": "/pl/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Właściwości zalecane tylko do odczytu w slajdach Java


## Wprowadzenie do włączania właściwości zalecanych tylko do odczytu w slajdach Java

W tym samouczku pokażemy, jak włączyć właściwości Read-Only Recommended dla prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Właściwości Read-Only Recommended mogą być przydatne, gdy chcesz zachęcić użytkowników do obejrzenia prezentacji bez wprowadzania żadnych zmian. Te właściwości sugerują, że prezentacja powinna zostać otwarta w trybie read-only. Udostępnimy Ci przewodnik krok po kroku wraz z kodem źródłowym Java, aby to osiągnąć.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że w projekcie masz skonfigurowaną bibliotekę Aspose.Slides for Java. Możesz ją pobrać ze strony [Aspose.Slides dla witryny Java](https://products.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację programu PowerPoint

Zaczniemy od utworzenia nowej prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Jeśli masz już prezentację, możesz pominąć ten krok.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

W powyższym kodzie zdefiniowaliśmy ścieżkę do pliku wyjściowego programu PowerPoint i utworzyliśmy nowy obiekt prezentacji.

## Krok 2: Włącz zalecaną właściwość tylko do odczytu

Teraz włączmy dla prezentacji właściwość Zalecane tylko do odczytu.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

W tym fragmencie kodu używamy `getProtectionManager().setReadOnlyRecommended(true)` metoda ustawiania właściwości Zalecane tylko do odczytu na `true`. Dzięki temu po otwarciu prezentacji użytkownik zostanie poproszony o otwarcie jej w trybie tylko do odczytu.

## Krok 3: Zapisz prezentację

Na koniec zapisujemy prezentację z włączoną właściwością Zalecane tylko do odczytu.

## Kompletny kod źródłowy dla właściwości zalecanych tylko do odczytu w slajdach Java

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

W tym samouczku dowiedziałeś się, jak włączyć właściwość Read-Only Recommended dla prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Ta funkcja może być pomocna, gdy chcesz ograniczyć edycję i zachęcić widzów do korzystania z prezentacji w trybie tylko do odczytu. Możesz dodatkowo zwiększyć bezpieczeństwo, ustawiając hasło dla prezentacji.

## Najczęściej zadawane pytania

### Jak wyłączyć właściwość Zalecane tylko do odczytu?

Aby wyłączyć właściwość Zalecane tylko do odczytu, wystarczy użyć następującego kodu:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Czy mogę ustawić hasło dla prezentacji rekomendowanej tylko do odczytu?

Tak, możesz ustawić hasło dla prezentacji Read-Only Recommended przy użyciu Aspose.Slides dla Java. Możesz użyć `setPassword` metoda ustawiania hasła do prezentacji. Jeśli hasło jest ustawione, użytkownicy będą musieli je wpisać, aby otworzyć prezentację, nawet w trybie tylko do odczytu.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Pamiętaj o wymianie `"YourPassword"` z wybranym przez Ciebie hasłem.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}