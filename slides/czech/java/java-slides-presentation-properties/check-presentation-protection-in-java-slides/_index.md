---
title: Zkontrolujte ochranu prezentace v aplikaci Java Slides
linktitle: Zkontrolujte ochranu prezentace v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Zjistěte, jak zkontrolovat ochranu prezentace na snímcích Java pomocí Aspose.Slides for Java. Tento podrobný průvodce poskytuje příklady kódu pro kontrolu zápisu a ochrany proti otevření.
weight: 15
url: /cs/java/presentation-properties/check-presentation-protection-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zkontrolujte ochranu prezentace v aplikaci Java Slides


## Úvod do kontroly ochrany prezentace v Java Slides

V tomto tutoriálu prozkoumáme, jak zkontrolovat ochranu prezentace pomocí Aspose.Slides for Java. Pokryjeme dva scénáře: kontrola ochrany proti zápisu a kontrola otevřené ochrany prezentace. Pro každý scénář poskytneme podrobné příklady kódu.

## Předpoklady

Než začneme, ujistěte se, že máte v projektu Java nastavenou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z webu Aspose a přidat do závislostí svého projektu.

### Závislost na Mavenovi

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>your_version_here</version>
</dependency>
```

 Nahradit`your_version_here` s verzí Aspose.Slides for Java, kterou používáte.

## Krok 1: Zkontrolujte ochranu proti zápisu

 Chcete-li zkontrolovat, zda je prezentace chráněna proti zápisu heslem, můžete použít`IPresentationInfo` rozhraní. Zde je kód, jak to udělat:

```java
// Cesta ke zdrojové prezentaci
String pptxFile = "path_to_presentation.pptx";

// Zkontrolujte heslo ochrany proti zápisu prostřednictvím rozhraní IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True
        && presentationInfo.checkWriteProtection("password_here");

System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
```

 Nahradit`"path_to_presentation.pptx"` se skutečnou cestou k souboru prezentace a`"password_here"` s heslem ochrany proti zápisu.

## Krok 2: Zkontrolujte otevřenou ochranu

 Chcete-li zkontrolovat, zda je prezentace chráněna heslem pro otevření, můžete použít`IPresentationInfo` rozhraní. Zde je kód, jak to udělat:

```java
// Cesta ke zdrojové prezentaci
String pptFile = "path_to_presentation.ppt";

// Zkontrolujte ochranu otevřené prezentace prostřednictvím rozhraní IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected()) {
    System.out.println("The presentation is protected by password to open.");
}
```

 Nahradit`"path_to_presentation.ppt"` se skutečnou cestou k souboru vaší prezentace.

## Kompletní zdrojový kód pro kontrolu ochrany prezentace v Java Slides

```java
//Cesta k prezentaci zdroje
String pptxFile = "Your Document Directory";
String pptFile = "Your Document Directory";
// Zkontrolujte heslo ochrany proti zápisu prostřednictvím rozhraní IPresentationInfo
IPresentationInfo presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptxFile);
boolean isWriteProtectedByPassword = presentationInfo.isWriteProtected() == NullableBool.True && presentationInfo.checkWriteProtection("pass2");
System.out.println("Is presentation write protected by password = " + isWriteProtectedByPassword);
// Zkontrolujte heslo ochrany proti zápisu prostřednictvím rozhraní IProtectionManager
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
// Zkontrolujte ochranu otevřené prezentace prostřednictvím rozhraní IPresentationInfo
presentationInfo = PresentationFactory.getInstance().getPresentationInfo(pptFile);
if (presentationInfo.isPasswordProtected())
{
	System.out.println("The presentation '" + pptxFile + "' is protected by password to open.");
}
```

## Závěr

tomto tutoriálu jsme se naučili, jak zkontrolovat ochranu prezentace na snímcích Java pomocí Aspose.Slides for Java. Pokryli jsme dva scénáře: kontrola ochrany proti zápisu a kontrola otevřené ochrany. Nyní můžete tyto kontroly integrovat do svých aplikací Java a efektivně zpracovávat chráněné prezentace.

## FAQ

### Jak získám Aspose.Slides pro Java?

Aspose.Slides pro Javu si můžete stáhnout z webu Aspose nebo je přidat jako závislost Maven do vašeho projektu, jak je znázorněno v sekci předpoklady.

### Mohu u prezentace zkontrolovat ochranu proti zápisu i otevřenou ochranu?

Ano, pomocí poskytnutých příkladů kódu můžete zkontrolovat ochranu proti zápisu i otevřenou ochranu prezentace.

### Co mám dělat, když zapomenu ochranné heslo?

Pokud zapomenete heslo pro ochranu prezentace, neexistuje žádný vestavěný způsob, jak jej obnovit. Abyste předešli takovým situacím, nezapomeňte si svá hesla zaznamenat.

### Je Aspose.Slides for Java kompatibilní s nejnovějšími formáty souborů PowerPoint?

Ano, Aspose.Slides for Java podporuje nejnovější formáty souborů PowerPoint, včetně souborů .pptx.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
