---
"description": "Naučte se, jak krok za krokem převést jednotlivé snímky PowerPointu do HTML s ukázkami kódu pomocí Aspose.Slides pro Javu."
"linktitle": "Převod jednotlivých snímků v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Převod jednotlivých snímků v Javě"
"url": "/cs/java/presentation-conversion/convert-individual-slide-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod jednotlivých snímků v Javě


## Úvod do převodu jednotlivých snímků v Javě

V tomto tutoriálu si projdeme procesem převodu jednotlivých snímků z prezentace v PowerPointu do HTML pomocí Aspose.Slides pro Javu. Tato podrobná příručka vám poskytne zdrojový kód a vysvětlení, která vám s tímto úkolem pomohou.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- Nainstalována knihovna Aspose.Slides pro Javu.
- Soubor prezentace v PowerPointu (`Individual-Slide.pptx`), které chcete převést.
- Nastavení vývojového prostředí v Javě.

## Krok 1: Nastavení projektu

1. Vytvořte projekt v Javě ve vámi preferovaném vývojovém prostředí.
2. Přidejte do svého projektu knihovnu Aspose.Slides pro Javu.

## Krok 2: Importujte potřebné třídy

Ve vaší třídě Java importujte požadované třídy a nastavte počáteční konfiguraci.

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

## Krok 3: Definujte hlavní metodu převodu

Vytvořte metodu pro provedení převodu jednotlivých snímků. Nezapomeňte nahradit `"Your Document Directory"` se skutečnou cestou k adresáři dokumentů.

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

## Krok 4: Implementace CustomFormattingControlleru

Vytvořte `CustomFormattingController` třída pro zpracování vlastního formátování během převodu.

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

Nakonec zavolejte `convertIndividualSlides` metoda pro provedení procesu konverze.

```java
public static void main(String[] args) {
    convertIndividualSlides();
}
```

## Kompletní zdrojový kód pro převod jednotlivých snímků v Javě

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

Úspěšně jste převedli jednotlivé snímky z prezentace v PowerPointu do formátu HTML pomocí nástroje Aspose.Slides pro Javu. Tento tutoriál vám poskytl potřebný kód a kroky k dosažení tohoto úkolu. Neváhejte a přizpůsobte výstup a formátování podle svých specifických požadavků.

## Často kladené otázky

### Jak mohu dále přizpůsobit HTML výstup?

Výstup HTML můžete přizpůsobit úpravou `CustomFormattingController` třída. Upravte `writeSlideStart` a `writeSlideEnd` metody pro změnu struktury a stylu HTML slajdu.

### Mohu převést více prezentací v PowerPointu najednou?

Ano, kód můžete upravit tak, aby procházel více prezentačních souborů a převáděl je jednotlivě voláním metody `convertIndividualSlides` metoda pro každou prezentaci.

### Jak mám zvládnout dodatečné formátování tvarů a textu v rámci snímků?

Můžete prodloužit `CustomFormattingController` třída pro zpracování formátování specifického pro tvar implementací `writeShapeStart` a `writeShapeEnd` metody a aplikování vlastní logiky formátování v nich.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}