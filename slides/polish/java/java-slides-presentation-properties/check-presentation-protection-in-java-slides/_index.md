---
"description": "Dowiedz się, jak sprawdzić ochronę prezentacji w slajdach Java przy użyciu Aspose.Slides for Java. Ten przewodnik krok po kroku zawiera przykłady kodu do sprawdzania ochrony przed zapisem i otwarciem."
"linktitle": "Sprawdź ochronę prezentacji w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Sprawdź ochronę prezentacji w slajdach Java"
"url": "/pl/java/presentation-properties/check-presentation-protection-in-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sprawdź ochronę prezentacji w slajdach Java


## Wprowadzenie do sprawdzania ochrony prezentacji w slajdach Java

W tym samouczku pokażemy, jak sprawdzić ochronę prezentacji za pomocą Aspose.Slides dla Java. Omówimy dwa scenariusze: sprawdzanie ochrony przed zapisem i sprawdzanie ochrony przed otwarciem prezentacji. Przedstawimy przykłady kodu krok po kroku dla każdego scenariusza.

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że biblioteka Aspose.Slides for Java jest skonfigurowana w projekcie Java. Możesz ją pobrać ze strony internetowej Aspose i dodać do zależności projektu.

### Zależność Maven

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

Zastępować `your_version_here` z wersją Aspose.Slides for Java, której używasz.

## Krok 1: Sprawdź ochronę przed zapisem

Aby sprawdzić, czy prezentacja jest chroniona hasłem przed zapisem, możesz użyć `IPresentationInfo` interfejs. Oto kod, który to umożliwia:

```java
// Ścieżka do prezentacji źródłowej
String pptxFile = "path_to_presentation.pptx";

// Sprawdź hasło zabezpieczające przed zapisem za pomocą interfejsu IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

Zastępować `"path_to_presentation.pptx"` z rzeczywistą ścieżką do pliku prezentacji i `"password_here"` z hasłem zabezpieczającym przed zapisem.

## Krok 2: Sprawdź otwartą ochronę

Aby sprawdzić, czy prezentacja jest chroniona hasłem do otwierania, możesz skorzystać z `IPresentationInfo` interfejs. Oto kod, który to umożliwia:

```java
// Ścieżka do prezentacji źródłowej
String pptFile = "path_to_presentation.ppt";

// Sprawdź ochronę otwarcia prezentacji za pomocą interfejsu IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

Zastępować `"path_to_presentation.ppt"` z rzeczywistą ścieżką do pliku prezentacji.

## Kompletny kod źródłowy do sprawdzania ochrony prezentacji w slajdach Java

```java
//Ścieżka do prezentacji źródłowej
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Sprawdź hasło zabezpieczające przed zapisem za pomocą interfejsu IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Sprawdź hasło ochrony przed zapisem za pomocą interfejsu IProtectionManager
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
// Sprawdź ochronę otwarcia prezentacji za pomocą interfejsu IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Wniosek

W tym samouczku nauczyliśmy się, jak sprawdzać ochronę prezentacji w slajdach Java przy użyciu Aspose.Slides for Java. Omówiliśmy dwa scenariusze: sprawdzanie ochrony przed zapisem i sprawdzanie ochrony przed otwarciem. Teraz możesz zintegrować te sprawdzenia ze swoimi aplikacjami Java, aby skutecznie obsługiwać chronione prezentacje.

## Najczęściej zadawane pytania

### Jak uzyskać Aspose.Slides dla Java?

Możesz pobrać Aspose.Slides dla języka Java ze strony internetowej Aspose lub dodać go jako zależność Maven w swoim projekcie, zgodnie z opisem w sekcji dotyczącej wymagań wstępnych.

### Czy mogę sprawdzić zarówno ochronę przed zapisem, jak i ochronę przed otwarciem prezentacji?

Tak, możesz sprawdzić zarówno ochronę przed zapisem, jak i ochronę przed otwieraniem prezentacji, korzystając z podanych przykładów kodu.

### Co zrobić, jeśli zapomnę hasła zabezpieczającego?

Jeśli zapomnisz hasła zabezpieczającego do prezentacji, nie ma wbudowanego sposobu na jego odzyskanie. Upewnij się, że zapisujesz swoje hasła, aby uniknąć takich sytuacji.

### Czy Aspose.Slides for Java jest kompatybilny z najnowszymi formatami plików PowerPoint?

Tak, Aspose.Slides for Java obsługuje najnowsze formaty plików PowerPoint, w tym pliki .pptx.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}