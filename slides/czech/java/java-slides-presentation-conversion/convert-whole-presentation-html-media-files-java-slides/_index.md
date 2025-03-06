---
title: Převeďte celou prezentaci do HTML pomocí mediálních souborů v Java Slides
linktitle: Převeďte celou prezentaci do HTML pomocí mediálních souborů v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se převádět prezentace do HTML pomocí mediálních souborů pomocí Java Slides. Postupujte podle našeho podrobného průvodce s Aspose.Slides pro Java API.
weight: 30
url: /cs/java/presentation-conversion/convert-whole-presentation-html-media-files-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do převodu celé prezentace do HTML pomocí mediálních souborů v Java Slides

V dnešní digitální době je nutnost převádět prezentace do různých formátů včetně HTML běžným požadavkem. Vývojáři Javy se často ocitají v této výzvě. Naštěstí s Aspose.Slides for Java API lze tento úkol provést efektivně. V tomto podrobném průvodci prozkoumáme, jak převést celou prezentaci do HTML při zachování mediálních souborů pomocí Java Slides.

## Předpoklady

Než se ponoříme do aspektu kódování, ujistěte se, že máme vše správně nastaveno:

- Java Development Kit (JDK): Ujistěte se, že máte ve svém systému nainstalovanou sadu JDK.
-  Aspose.Slides for Java: Budete muset mít nainstalované Aspose.Slides for Java API. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Importujte potřebné balíčky

Chcete-li začít, musíte importovat potřebné balíčky. Tyto balíčky poskytnou třídy a metody potřebné pro náš úkol.

```java
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SlideImageFormat;
import com.aspose.slides.SVGOptions;
import com.aspose.slides.VideoPlayerHtmlController;
```

## Krok 2: Zadejte adresář dokumentů

 Definujte cestu k adresáři vašeho dokumentu, kde je umístěn soubor prezentace. Nahradit`"Your Document Directory"` se skutečnou cestou.

```java
String dataDir = "Your Document Directory";
```

## Krok 3: Inicializujte prezentaci

 Načtěte prezentaci, kterou chcete převést do HTML. Nezapomeňte vyměnit`"presentationWith.pptx"` s názvem souboru vaší prezentace.

```java
Presentation pres = new Presentation("presentationWith.pptx");
```

## Krok 4: Vytvořte HTML Controller

 Vytvoříme a`VideoPlayerHtmlController` zvládnout proces konverze. Nahraďte URL požadovanou webovou adresou.

```java
VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
    "", htmlDocumentFileName, "http://www.example.com/");
```

## Krok 5: Nakonfigurujte možnosti HTML a SVG

Nastavte možnosti HTML a SVG pro převod. Zde si můžete přizpůsobit formátování podle potřeby.

```java
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);
htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
```

## Krok 6: Uložte prezentaci jako HTML

Nyní je čas uložit prezentaci jako soubor HTML, včetně mediálních souborů.

```java
pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
```

## Kompletní zdrojový kód pro převod celé prezentace do HTML s mediálními soubory v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
String htmlDocumentFileName = "presentationWithVideo.html";
Presentation pres = new Presentation("presentationWith.pptx");
try
{
	VideoPlayerHtmlController controller = new VideoPlayerHtmlController(
			"", htmlDocumentFileName, "http://www.example.com/");
	HtmlOptions htmlOptions = new HtmlOptions(controller);
	SVGOptions svgOptions = new SVGOptions(controller);
	htmlOptions.setHtmlFormatter(HtmlFormatter.createCustomFormatter(controller));
	htmlOptions.setSlideImageFormat(SlideImageFormat.svg(svgOptions));
	pres.save(htmlDocumentFileName, SaveFormat.Html, htmlOptions);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prošli procesem převodu celé prezentace do HTML s mediálními soubory pomocí Java Slides a Aspose.Slides for Java API. Dodržením těchto kroků můžete efektivně převést své prezentace do formátu vhodného pro web, přičemž zachováte všechny základní mediální prvky.

## FAQ

### Jak mohu nainstalovat Aspose.Slides for Java?

 Chcete-li nainstalovat Aspose.Slides pro Java, navštivte stránku ke stažení na adrese[tady](https://releases.aspose.com/slides/java/) a postupujte podle dodaných pokynů k instalaci.

### Mohu dále upravit výstup HTML?

 Ano, výstup HTML si můžete přizpůsobit podle svých požadavků. The`HtmlOptions` class poskytuje různá nastavení pro řízení procesu převodu, včetně možností formátování a rozvržení.

### Podporuje Aspose.Slides for Java jiné výstupní formáty?

Ano, Aspose.Slides for Java podporuje různé výstupní formáty, včetně PDF, PPTX a dalších. Tyto možnosti můžete prozkoumat v dokumentaci.

### Je Aspose.Slides for Java vhodný pro komerční projekty?

Ano, Aspose.Slides for Java je robustní a komerčně životaschopné řešení pro zpracování úloh souvisejících s prezentacemi v aplikacích Java. Je široce používán v projektech na podnikové úrovni.

### Jak získám přístup k převedené HTML prezentaci?

 Po dokončení převodu můžete získat přístup k HTML prezentaci umístěním souboru uvedeného v`htmlDocumentFileName` variabilní.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
