---
"description": "Převeďte prezentace PowerPointu do HTML se zachováním původních písem pomocí Aspose.Slides pro Javu."
"linktitle": "Převod prezentace do HTML se zachováním původních písem v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Převod prezentace do HTML se zachováním původních písem v Java Slides"
"url": "/cs/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod prezentace do HTML se zachováním původních písem v Java Slides


## Úvod do převodu prezentací do HTML se zachováním původních písem v Javě Slides

V tomto tutoriálu se podíváme na to, jak převést prezentaci PowerPoint (PPTX) do HTML se zachováním původních písem pomocí Aspose.Slides pro Javu. Tím zajistíme, že výsledný HTML kód bude co nejvíce připomínat vzhled původní prezentace.

## Krok 1: Nastavení projektu
Než se pustíme do kódu, ujistěte se, že máte potřebná nastavení:

1. Stáhněte si knihovnu Aspose.Slides pro Javu: Pokud jste tak ještě neučinili, stáhněte si a zahrňte do svého projektu knihovnu Aspose.Slides pro Javu.

2. Vytvořte projekt Java: Nastavte si projekt Java ve svém oblíbeném IDE a ujistěte se, že máte složku „lib“, kam můžete umístit soubor JAR Aspose.Slides.

3. Importujte požadované třídy: Importujte potřebné třídy na začátek souboru Java:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Převod prezentace do HTML s původními fonty

Nyní si převeďme prezentaci v PowerPointu do HTML se zachováním původních písem:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Načíst prezentaci
Presentation pres = new Presentation("input.pptx");

try {
    // Vyloučit výchozí prezentační fonty, jako jsou Calibri a Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Vytvoření možností HTML a nastavení vlastního formátovače HTML
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Uložit prezentaci jako HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Zlikvidujte prezentační objekt
    if (pres != null) pres.dispose();
}
```

V tomto úryvku kódu:

- Vstupní prezentaci v PowerPointu načteme pomocí `Presentation`.

- Definujeme seznam fontů (`fontNameExcludeList`), které chceme vyloučit z vkládání do HTML. To je užitečné pro vyloučení běžných písem, jako jsou Calibri a Arial, a zmenšení velikosti souboru.

- Vytvoříme instanci `EmbedAllFontsHtmlController` a předat mu seznam vyloučených písem.

- Tvoříme `HtmlOptions` a nastavte vlastní formátovač HTML pomocí `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Nakonec uložíme prezentaci jako HTML se zadanými možnostmi.

## Kompletní zdrojový kód pro převod prezentace do HTML se zachováním původních písem v Java Slides

```java
// Cesta k adresáři s dokumenty.
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

V tomto tutoriálu jste se naučili, jak převést prezentaci v PowerPointu do HTML se zachováním původních písem pomocí Aspose.Slides pro Javu. To je užitečné, pokud chcete zachovat vizuální věrnost prezentací při jejich sdílení na webu.

## Často kladené otázky

### Jak si stáhnu Aspose.Slides pro Javu?

Aspose.Slides pro Javu si můžete stáhnout z webových stránek Aspose. Navštivte [zde](https://downloads.aspose.com/slides/java/) abyste získali nejnovější verzi.

### Mohu si přizpůsobit seznam vyloučených písem?

Ano, můžete si to přizpůsobit `fontNameExcludeList` pole pro zahrnutí nebo vyloučení konkrétních písem podle vašich požadavků.

### Funguje tato metoda i pro starší formáty PowerPointu, jako je PPT?

Tento příklad kódu je určen pro soubory PPTX. Pokud potřebujete převést starší soubory PPT, může být nutné provést úpravy kódu.

### Jak mohu dále přizpůsobit HTML výstup?

Můžete prozkoumat `HtmlOptions` třída pro úpravu různých aspektů HTML výstupu, jako je velikost snímku, kvalita obrázku a další.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}