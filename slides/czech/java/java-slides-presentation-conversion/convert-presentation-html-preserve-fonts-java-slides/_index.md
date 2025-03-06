---
title: Převod prezentace do HTML se zachováním původních písem v Java Slides
linktitle: Převod prezentace do HTML se zachováním původních písem v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Převeďte PowerPointové prezentace do HTML při zachování původních písem pomocí Aspose.Slides for Java.
type: docs
weight: 14
url: /cs/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

## Úvod do převodu prezentace do HTML se zachováním původních písem v Java Slides

V tomto tutoriálu prozkoumáme, jak převést prezentaci PowerPoint (PPTX) do HTML při zachování původních písem pomocí Aspose.Slides for Java. Tím zajistíte, že výsledný HTML bude co nejvíce odpovídat vzhledu původní prezentace.

## Krok 1: Nastavení projektu
Než se ponoříme do kódu, ujistěte se, že máte potřebné nastavení:

1. Stáhnout Aspose.Slides for Java: Pokud jste to ještě neudělali, stáhněte si a zahrňte knihovnu Aspose.Slides for Java do svého projektu.

2. Vytvoření projektu Java: Nastavte projekt Java ve svém oblíbeném IDE a ujistěte se, že máte složku „lib“, kam můžete umístit soubor JAR Aspose.Slides.

3. Import požadovaných tříd: Importujte potřebné třídy na začátek vašeho souboru Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Převod prezentace do HTML pomocí původních písem

Nyní převedeme PowerPointovou prezentaci do HTML při zachování původních písem:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Načtěte prezentaci
Presentation pres = new Presentation("input.pptx");

try {
    // Vyloučit výchozí prezentační písma jako Calibri a Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Vytvořte možnosti HTML a nastavte vlastní formátovač HTML
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Uložte prezentaci jako HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Zlikvidujte předmět prezentace
    if (pres != null) pres.dispose();
}
```

V tomto fragmentu kódu:

-  Vstupní PowerPointovou prezentaci načteme pomocí`Presentation`.

- Definujeme seznam písem (`fontNameExcludeList`), které chceme vyloučit z vkládání do HTML. To je užitečné pro vyloučení běžných písem, jako je Calibri a Arial, aby se zmenšila velikost souboru.

-  Vytvoříme instanci`EmbedAllFontsHtmlController` a předat mu seznam vyloučených písem.

-  tvoříme`HtmlOptions` a nastavte vlastní formátovač HTML pomocí`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Nakonec prezentaci uložíme jako HTML se zadanými možnostmi.

## Kompletní zdrojový kód pro převod prezentace do HTML se zachováním původních písem v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// vyloučit výchozí prezentační písma
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak převést prezentaci PowerPoint do HTML při zachování původních písem pomocí Aspose.Slides for Java. To je užitečné, když chcete zachovat vizuální věrnost vašich prezentací při jejich sdílení na webu.

## FAQ

### Jak si stáhnu Aspose.Slides for Java?

 Aspose.Slides for Java si můžete stáhnout z webu Aspose. Návštěva[tady](https://downloads.aspose.com/slides/java/) získat nejnovější verzi.

### Mohu přizpůsobit seznam vyloučených písem?

 Ano, můžete přizpůsobit`fontNameExcludeList` pole pro zahrnutí nebo vyloučení konkrétních písem podle vašich požadavků.

### Funguje tato metoda pro starší formáty PowerPoint, jako je PPT?

Tento příklad kódu je určen pro soubory PPTX. Pokud potřebujete převést starší soubory PPT, možná budete muset provést úpravy v kódu.

### Jak mohu dále upravit výstup HTML?

 Můžete prozkoumat`HtmlOptions` třídy k přizpůsobení různých aspektů výstupu HTML, jako je velikost snímku, kvalita obrazu a další.