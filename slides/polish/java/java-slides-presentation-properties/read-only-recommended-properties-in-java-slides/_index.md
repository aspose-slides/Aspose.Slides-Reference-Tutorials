---
title: Zalecane właściwości tylko do odczytu w slajdach Java
linktitle: Zalecane właściwości tylko do odczytu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak włączyć właściwości zalecane tylko do odczytu w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Postępuj zgodnie z naszym przewodnikiem krok po kroku z przykładami kodu źródłowego, aby zwiększyć bezpieczeństwo prezentacji.
type: docs
weight: 17
url: /pl/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

## Wprowadzenie do włączania zalecanych właściwości tylko do odczytu w slajdach Java

tym samouczku przyjrzymy się, jak włączyć właściwości zalecane tylko do odczytu dla prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Właściwości zalecane tylko do odczytu mogą być przydatne, gdy chcesz zachęcić użytkowników do przeglądania prezentacji bez wprowadzania jakichkolwiek zmian. Te właściwości sugerują, że prezentację należy otworzyć w trybie tylko do odczytu. Dostarczymy Ci przewodnik krok po kroku wraz z kodem źródłowym Java, jak to osiągnąć.

## Warunki wstępne

 Zanim zaczniemy, upewnij się, że w swoim projekcie masz skonfigurowaną bibliotekę Aspose.Slides for Java. Można go pobrać z[Witryna internetowa Aspose.Slides dla języka Java](https://products.aspose.com/slides/java/).

## Krok 1: Utwórz nową prezentację programu PowerPoint

Zaczniemy od utworzenia nowej prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Jeśli masz już prezentację, możesz pominąć ten krok.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

W powyższym kodzie zdefiniowaliśmy ścieżkę do wyjściowego pliku PowerPoint i utworzyliśmy nowy obiekt prezentacji.

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

 W tym fragmencie kodu używamy`getProtectionManager().setReadOnlyRecommended(true)` metoda, aby ustawić właściwość Zalecane tylko do odczytu`true`. Dzięki temu, gdy ktoś otworzy prezentację, zostanie poproszony o otwarcie jej w trybie tylko do odczytu.

## Krok 3: Zapisz prezentację

Na koniec zapisujemy prezentację z włączoną właściwością Zalecane tylko do odczytu.

## Kompletny kod źródłowy zalecanych właściwości tylko do odczytu w slajdach Java

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

W tym samouczku nauczyłeś się, jak włączyć właściwość Zalecane tylko do odczytu dla prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Ta funkcja może być pomocna, gdy chcesz ograniczyć możliwość edycji i zachęcić widzów do korzystania z prezentacji w trybie tylko do odczytu. Możesz dodatkowo zwiększyć bezpieczeństwo, ustawiając hasło dla prezentacji.

## Często zadawane pytania

### Jak wyłączyć właściwość Zalecane tylko do odczytu?

Aby wyłączyć właściwość Zalecane tylko do odczytu, po prostu użyj następującego kodu:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Czy mogę ustawić hasło dla prezentacji polecanej tylko do odczytu?

Tak, możesz ustawić hasło dla prezentacji zalecanej tylko do odczytu, używając Aspose.Slides for Java. Możesz skorzystać z`setPassword` metoda ustawienia hasła do prezentacji. Jeśli ustawione jest hasło, użytkownicy będą musieli je wprowadzić, aby otworzyć prezentację, nawet w trybie tylko do odczytu.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Pamiętaj o wymianie`"YourPassword"` z żądanym hasłem.