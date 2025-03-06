---
title: Převést jednotlivé snímky v Java Slides
linktitle: Převést jednotlivé snímky v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak převést jednotlivé PowerPoint snímky do HTML krok za krokem pomocí příkladů kódu pomocí Aspose.Slides for Java.
type: docs
weight: 12
url: /cs/java/presentation-conversion/convert-individual-slide-java-slides/
---

## Úvod do převodu jednotlivých snímků v Java Slides

V tomto tutoriálu si projdeme procesem převodu jednotlivých snímků z PowerPointové prezentace do HTML pomocí Aspose.Slides for Java. Tento podrobný průvodce vám poskytne zdrojový kód a vysvětlení, která vám pomohou splnit tento úkol.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Nainstalovaná knihovna Aspose.Slides for Java.
- Soubor prezentace PowerPoint (`Individual-Slide.pptx`), které chcete převést.
- Nastavení vývojového prostředí Java.

## Krok 1: Nastavte projekt

1. Vytvořte projekt Java ve vámi preferovaném vývojovém prostředí.
2. Přidejte do projektu knihovnu Aspose.Slides for Java.

## Krok 2: Importujte potřebné třídy

Ve své třídě Java naimportujte požadované třídy a nastavte počáteční konfiguraci.

```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.INotesCommentsLayoutingOptions;
import com.aspose.slides.NotesPositions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.IHtmlFormattingController;
import com.aspose.slides.IHtmlGenerator;
import com.aspose.slides.ISlide;
import com.aspose.slides.IShape;
```

## Krok 3: Definujte hlavní metodu konverze

 Vytvořte metodu pro provedení převodu jednotlivých snímků. Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k vašemu adresáři dokumentů.

```java
public static void convertIndividualSlides() {
    String dataDir = "Your Document Directory";
    Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
    try {
        HtmlOptions htmlOptions = new HtmlOptions();
        htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
        INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
        notesOptions.setNotesPosition(NotesPositions.BottomFull);
        
        // Ukládání souboru
        for (int i = 0; i < presentation.getSlides().size(); i++) {
            presentation.save(dataDir + "Individual-Slide" + (i + 1) + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
        }
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Krok 4: Implementujte CustomFormattingController

 Vytvořte`CustomFormattingController` třída pro zpracování vlastního formátování během převodu.

```java
public static class CustomFormattingController implements IHtmlFormattingController {
    public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation) {
    }
    
    public void writeSlideStart(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
    }
    
    public void writeSlideEnd(IHtmlGenerator generator, ISlide slide) {
        generator.addHtml(SlideFooter);
    }
    
    public void writeShapeStart(IHtmlGenerator generator, IShape shape) {
    }
    
    public void writeShapeEnd(IHtmlGenerator generator, IShape shape) {
    }
    
    private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
    private static String SlideFooter = "</div>";
}
```

## Krok 5: Proveďte konverzi

 Nakonec zavolejte na`convertIndividualSlides` způsob provedení procesu převodu.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Kompletní zdrojový kód pro převod jednotlivých snímků v Java Slides

```java
	String dataDir = "Your Document Directory";
	Presentation presentation = new Presentation(dataDir + "Individual-Slide.pptx");
	try
	{
		HtmlOptions htmlOptions = new HtmlOptions();
		htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(new CustomFormattingController()));
		INotesCommentsLayoutingOptions notesOptions = htmlOptions.getNotesCommentsLayouting();
		notesOptions.setNotesPosition(NotesPositions.BottomFull);
		// Ukládání souboru
		for (int i = 0; i < presentation.getSlides().size(); i++)
			presentation.save(dataDir + "Individual Slide" + i + 1 + "_out.html", new int[]{i + 1}, SaveFormat.Html, htmlOptions);
	}
	finally
	{
		if (presentation != null) presentation.dispose();
	}
}
public static class CustomFormattingController implements IHtmlFormattingController
{
	public void writeDocumentStart(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeDocumentEnd(IHtmlGenerator generator, IPresentation presentation)
	{
	}
	public void writeSlideStart(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(String.format(SlideHeader, generator.getSlideIndex() + 1));
	}
	public void writeSlideEnd(IHtmlGenerator generator, ISlide slide)
	{
		generator.addHtml(SlideFooter);
	}
	public void writeShapeStart(IHtmlGenerator generator, IShape shape)
	{
	}
	public void writeShapeEnd(IHtmlGenerator generator, IShape shape)
	{
	}
	private static String SlideHeader = "<div class=\"slide\" name=\"slide\" id=\"slide{0}\">";
	private static String SlideFooter = "</div>";
```

## Závěr

Úspěšně jste převedli jednotlivé snímky z powerpointové prezentace do HTML pomocí Aspose.Slides for Java. Tento výukový program vám poskytl nezbytný kód a kroky k dosažení tohoto úkolu. Neváhejte a upravte výstup a formátování podle potřeby pro vaše specifické požadavky.

## FAQ

### Jak mohu dále upravit výstup HTML?

 Výstup HTML můžete upravit úpravou souboru`CustomFormattingController` třída. Upravte`writeSlideStart` a`writeSlideEnd` metody pro změnu struktury HTML a stylů snímku.

### Mohu převést více prezentací PowerPoint najednou?

 Ano, kód můžete upravit tak, aby procházel více prezentačními soubory a jednotlivě je převádět voláním`convertIndividualSlides` metoda pro každou prezentaci.

### Jak zvládnu další formátování tvarů a textu na snímcích?

 Můžete prodloužit`CustomFormattingController` třídy pro zpracování formátování specifického pro tvar implementací`writeShapeStart` a`writeShapeEnd` metody a v nich aplikovat vlastní logiku formátování.