---
title: Převeďte snímky do PDF pomocí poznámek v Java Slides
linktitle: Převeďte snímky do PDF pomocí poznámek v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak převést PowerPoint snímky do PDF s poznámkami v Javě pomocí Aspose.Slides for Java. Podrobný průvodce pro vývojáře Java. Vylepšete sdílení prezentací.
weight: 19
url: /cs/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převeďte snímky do PDF pomocí poznámek v Java Slides


## Úvod do převodu snímků do PDF pomocí poznámek v Javě

Ve světě digitálních prezentací je cennou funkcí schopnost převádět snímky do PDF s doprovodnými poznámkami. Vývojáři v jazyce Java toho mohou dosáhnout pomocí knihovny Aspose.Slides for Java, která poskytuje robustní sadu nástrojů pro programovou práci s prezentacemi PowerPoint. V tomto podrobném průvodci prozkoumáme, jak převést snímky do PDF s poznámkami pomocí Java a Aspose.Slides for Java.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

Nyní, když máme náš přehled, pojďme se ponořit do implementace krok za krokem.
## Krok 1: Nastavení projektu

Nejprve vytvořte projekt Java a přidejte knihovnu Aspose.Slides for Java do závislostí vašeho projektu.

## Krok 2: Načtení prezentace

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Krok 3: Vytvoření nové prezentace

```java
Presentation auxPresentation = new Presentation();
```

## Krok 4: Kopírování snímků

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Krok 5: Úprava velikosti snímku

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Krok 6: Konfigurace možností PDF

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 7: Uložení jako PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Kompletní zdrojový kód pro převod snímků do PDF s poznámkami v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci objektu Presentation, který představuje soubor prezentace
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Nastavení typu a velikosti snímku
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili převádět snímky do PDF s poznámkami v Javě pomocí Aspose.Slides for Java. Zabývali jsme se nastavením projektu, načtením prezentace, vytvořením nové prezentace, kopírováním snímků, úpravou velikosti snímku, konfigurací možností PDF a nakonec uložením prezentace jako PDF s poznámkami.

## FAQ

### Jak nainstaluji Aspose.Slides for Java?

Chcete-li nainstalovat Aspose.Slides for Java, postupujte takto:
1.  Stáhněte si knihovnu z[tady](https://releases.aspose.com/slides/java/).
2. Přidejte soubor JAR do cesty třídy svého projektu Java.

### Mohu upravit pozici poznámek ve vygenerovaném PDF?

 Ano, můžete upravit pozici poznámek úpravou`NotesPositions` enum v možnostech PDF. V tomto tutoriálu jsme to nastavili na`BottomFull`, ale můžete prozkoumat i další možnosti.

### Existují nějaké licenční požadavky pro používání Aspose.Slides pro Java?

Ano, Aspose.Slides for Java je komerční knihovna a možná budete muset získat licenci, abyste ji mohli používat v produkci. Podrobnosti o licencích najdete na webu Aspose.

### Mohu převést více snímků najednou?

Rozhodně! Můžete procházet snímky v prezentaci a klonovat je do nové prezentace, což vám umožní převést více snímků do PDF s poznámkami najednou.

### Kde najdu další dokumentaci k Aspose.Slides pro Java?

 Podrobnou dokumentaci k Aspose.Slides for Java můžete najít na webu:[Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
