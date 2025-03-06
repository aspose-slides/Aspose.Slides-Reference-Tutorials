---
title: Převeďte zobrazení snímku poznámek do formátu PDF v aplikaci Java Slides
linktitle: Převeďte zobrazení snímku poznámek do formátu PDF v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se převádět PowerPointové prezentace s poznámkami do PDF pomocí Aspose.Slides for Java. Postupujte podle našeho podrobného průvodce se zdrojovým kódem.
weight: 16
url: /cs/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do převodu zobrazení poznámek do formátu PDF v aplikaci Java Slides

V tomto tutoriálu vás provedeme procesem převodu prezentace PowerPoint se zobrazením snímku s poznámkami do formátu PDF pomocí knihovny Aspose.Slides for Java. Tato knihovna poskytuje výkonné funkce pro práci s PowerPointovými prezentacemi v Javě.

## Předpoklady
1. Java Development Kit (JDK) nainstalován.
2. Do vašeho projektu byla přidána knihovna Aspose.Slides for Java.

## Krok 1: Import nezbytných tříd
Chcete-li začít, budete muset importovat potřebné třídy z knihovny Aspose.Slides. Zde je kód, jak to udělat:

```java
import com.aspose.slides.*;
```

## Krok 2: Načtěte prezentaci PowerPoint
 Měli byste mít připravený soubor prezentace PowerPoint. Nahradit`"Your Document Directory"` s cestou k adresáři, kde je umístěn soubor vaší prezentace. Zde je kód pro načtení prezentace:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Krok 3: Nakonfigurujte možnosti PDF
Nyní nakonfigurujeme možnosti exportu PDF. Konkrétně nastavíme pozici poznámek na „BottomFull“, aby se poznámky zahrnuly pod snímky v PDF. Zde je kód:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Další možnosti PDF si můžete přizpůsobit podle svých požadavků.

## Krok 4: Uložte prezentaci jako PDF s poznámkami
 Nakonec prezentaci uložme jako soubor PDF včetně poznámek. Můžete zadat název výstupního souboru (např.`"Pdf_Notes_out.pdf"`) a zvolte formát (`SaveFormat.Pdf`). Zde je kód, jak to udělat:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Krok 5: Vyčistěte zdroje
Jakmile s prezentací skončíte, nezapomeňte uvolnit zdroje:

```java
if (presentation != null) presentation.dispose();
```

## Kompletní zdrojový kód pro převod Notes Slide View do PDF v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci objektu Presentation, který představuje soubor prezentace
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Uložení prezentace do PDF poznámek
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak převést PowerPointové prezentace se zobrazením snímků poznámek do PDF pomocí knihovny Aspose.Slides for Java. K dosažení této konverze jsme postupovali podle podrobného průvodce se zdrojovým kódem. Zde jsou hlavní poznatky:

## FAQ

### Jak změním pozici poznámek v PDF?

 Pozici poznámek v PDF můžete změnit úpravou souboru`setNotesPosition` argument metody. Můžete jej nastavit například na`NotesPositions.RightFull` pro umístění poznámek na pravou stranu snímků.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### Mohu export PDF dále upravit?

 Ano, export PDF si můžete přizpůsobit úpravou různých možností v`PdfOptions` objekt. Můžete si například nastavit kvalitu, kompresi a další parametry podle svých potřeb.

### Jak mohu získat Aspose.Slides pro Java?

 Aspose.Slides for Java si můžete stáhnout z webové stránky na adrese[tady](https://releases.aspose.com/slides/java/).

### Existují nějaké licenční požadavky pro používání Aspose.Slides?

Ano, Aspose.Slides vyžaduje platnou licenci pro komerční použití. Licenci můžete získat z webu Aspose.

### Kde najdu další dokumentaci a příklady?

 Komplexní dokumentaci a příklady pro Aspose.Slides pro Javu naleznete na adrese[tady](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
