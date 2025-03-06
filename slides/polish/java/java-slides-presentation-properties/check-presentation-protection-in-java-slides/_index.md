---
title: Sprawdź ochronę prezentacji w slajdach Java
linktitle: Sprawdź ochronę prezentacji w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak sprawdzić ochronę prezentacji na slajdach Java za pomocą Aspose.Slides for Java. Ten przewodnik krok po kroku zawiera przykłady kodu dotyczące kontroli ochrony przed zapisem i otwarciem.
weight: 15
url: /pl/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Sprawdź ochronę prezentacji w slajdach Java


## Wprowadzenie do sprawdzania ochrony prezentacji w slajdach Java

W tym samouczku przyjrzymy się, jak sprawdzić ochronę prezentacji za pomocą Aspose.Slides dla Java. Omówimy dwa scenariusze: sprawdzanie ochrony przed zapisem i sprawdzanie otwartej ochrony prezentacji. Dla każdego scenariusza przedstawimy przykłady kodu krok po kroku.

## Warunki wstępne

Zanim zaczniemy, upewnij się, że masz skonfigurowaną bibliotekę Aspose.Slides for Java w swoim projekcie Java. Możesz pobrać go ze strony Aspose i dodać do zależności swojego projektu.

### Zależność od Mavena

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Zastępować`your_version_here` z wersją Aspose.Slides dla Java, której używasz.

## Krok 1: Sprawdź ochronę przed zapisem

 Aby sprawdzić, czy prezentacja jest zabezpieczona hasłem przed zapisem, możesz użyć metody`IPresentationInfo` interfejs. Oto kod, aby to zrobić:

```java
// Ścieżka do prezentacji źródłowej
String pptxFile = "path_to_presentation.pptx";

// Sprawdź hasło ochrony przed zapisem za pośrednictwem interfejsu IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Zastępować`"path_to_presentation.pptx"` z rzeczywistą ścieżką do pliku prezentacji i`"password_here"` z hasłem zabezpieczającym przed zapisem.

## Krok 2: Sprawdź opcję Otwarta ochrona

 Aby sprawdzić, czy prezentacja jest zabezpieczona hasłem do otwarcia, możesz skorzystać z metody`IPresentationInfo` interfejs. Oto kod, aby to zrobić:

```java
// Ścieżka do prezentacji źródłowej
String pptFile = "path_to_presentation.ppt";

// Sprawdź ochronę otwartej prezentacji poprzez interfejs IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Zastępować`"path_to_presentation.ppt"` z rzeczywistą ścieżką do pliku prezentacji.

## Kompletny kod źródłowy do sprawdzania ochrony prezentacji w slajdach Java

```java
//Ścieżka prezentacji źródła
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Sprawdź hasło ochrony przed zapisem za pośrednictwem interfejsu IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Sprawdź hasło ochrony przed zapisem za pośrednictwem interfejsu IProtectionManager
Presentation presentation = new Presentation();
try
{
	boolean isWriteProtected = presentation.getProtectionManager().checkWriteProtection("pass2");
	System.out.println("Is presentation write protected = " + isWriteProtected);
}
finally
{
	if (presentation != null) presentation.dispose();
}
// Sprawdź ochronę otwartej prezentacji poprzez interfejs IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Wniosek

tym samouczku dowiedzieliśmy się, jak sprawdzić ochronę prezentacji na slajdach Java za pomocą Aspose.Slides for Java. Omówiliśmy dwa scenariusze: sprawdzanie ochrony przed zapisem i sprawdzanie ochrony przed otwarciem. Możesz teraz zintegrować te kontrole z aplikacjami Java, aby skutecznie obsługiwać chronione prezentacje.

## Często zadawane pytania

### Jak uzyskać Aspose.Slides dla Java?

Możesz pobrać Aspose.Slides dla Java ze strony internetowej Aspose lub dodać go jako zależność Maven w swoim projekcie, jak pokazano w sekcji wymagań wstępnych.

### Czy mogę sprawdzić zarówno ochronę przed zapisem, jak i ochronę przed otwarciem prezentacji?

Tak, możesz sprawdzić zarówno ochronę przed zapisem, jak i ochronę przed otwarciem prezentacji, korzystając z dostarczonych przykładów kodu.

### Co powinienem zrobić, jeśli zapomnę hasła zabezpieczającego?

Jeśli zapomnisz hasła zabezpieczającego prezentację, nie ma wbudowanej możliwości jego odzyskania. Aby uniknąć takich sytuacji, pamiętaj o zapisywaniu swoich haseł.

### Czy Aspose.Slides for Java jest kompatybilny z najnowszymi formatami plików programu PowerPoint?

Tak, Aspose.Slides for Java obsługuje najnowsze formaty plików programu PowerPoint, w tym pliki .pptx.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
