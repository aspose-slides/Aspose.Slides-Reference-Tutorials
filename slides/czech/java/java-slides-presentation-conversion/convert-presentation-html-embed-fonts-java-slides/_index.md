---
title: Převod prezentace do HTML s vložením všech písem do Java Slides
linktitle: Převod prezentace do HTML s vložením všech písem do Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se převádět prezentace do HTML pomocí vložených písem pomocí Aspose.Slides for Java. Tento podrobný průvodce zajišťuje konzistentní formátování pro bezproblémové sdílení.
weight: 13
url: /cs/java/presentation-conversion/convert-presentation-html-embed-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do převodu prezentace do HTML s vložením všech písem do Java Slides

dnešní digitální době se převod prezentací do HTML stal nezbytným pro bezproblémové sdílení informací napříč různými platformami. Při práci s Java Slides je důležité zajistit, aby všechna písma použitá ve vaší prezentaci byla vložena, aby bylo zachováno konzistentní formátování. V tomto podrobném průvodci vás provedeme procesem převodu prezentace do HTML při vkládání všech písem pomocí Aspose.Slides for Java. Začněme!

## Předpoklady

Než se ponoříme do kódu a procesu převodu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Slides for Java API, které si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).
-  Soubor prezentace (např.`presentation.pptx`), který chcete převést do HTML.

## Krok 1: Nastavení prostředí Java

Ujistěte se, že máte v systému správně nainstalované Java a Aspose.Slides for Java API. Pokyny k instalaci naleznete v dokumentaci.

## Krok 2: Načtení souboru prezentace

 kódu Java musíte načíst soubor prezentace, který chcete převést. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Krok 3: Vložení všech písem do prezentace

Chcete-li vložit všechna písma použitá v prezentaci, můžete použít následující fragment kódu. Tím je zajištěno, že výstup HTML bude obsahovat všechna potřebná písma pro konzistentní vykreslování.

```java
try
{
    // Vyloučit výchozí prezentační písma
    String[] fontNameExcludeList = {  };
    LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
    pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
    if (pres != null) pres.dispose();
}
```

## Krok 4: Převod prezentace do HTML

Nyní, když jsme vložili všechna písma, je čas převést prezentaci do HTML. Kód uvedený v kroku 3 tuto konverzi zvládne.

## Krok 5: Uložení souboru HTML

Posledním krokem je uložení souboru HTML s vloženými fonty. Soubor HTML bude uložen do určeného adresáře, což zajistí, že budou zahrnuta všechna písma.

A je to! Úspěšně jste převedli prezentaci do HTML při vkládání všech písem pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
try
{
	// vyloučit výchozí prezentační písma
	String[] fontNameExcludeList = {  };
	LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, "C:\\Windows\\Fonts\\");
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(linkcont));
	pres.save("Your Output Directory" + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Převod prezentací do HTML s vloženými fonty je zásadní pro zachování konzistentního formátování na různých platformách. S Aspose.Slides pro Java se tento proces stává přímočarým a efektivním. Nyní můžete sdílet své prezentace ve formátu HTML bez obav z chybějících písem.

## Nejčastější dotazy

### Jak mohu zkontrolovat, zda jsou ve výstupu HTML vložena všechna písma?

Můžete si prohlédnout zdrojový kód souboru HTML a vyhledat odkazy na písma. Všechna písma použitá v prezentaci by měla být uvedena v souboru HTML.

### Mohu dále upravit výstup HTML, jako je styl a rozvržení?

 Ano, výstup HTML můžete upravit úpravou souboru`HtmlOptions` a šablonu HTML používanou pro formátování. Aspose.Slides for Java poskytuje flexibilitu v tomto ohledu.

### Existují nějaká omezení při vkládání písem do HTML?

Zatímco vkládání písem zajišťuje konzistentní vykreslování, mějte na paměti, že může zvětšit velikost souboru výstupu HTML. Nezapomeňte optimalizovat prezentaci tak, aby byla vyvážena kvalita a velikost souboru.

### Mohu pomocí této metody převést prezentace se složitým obsahem do HTML?

Ano, tato metoda funguje pro prezentace se složitým obsahem, včetně obrázků, animací a multimediálních prvků. Aspose.Slides pro Java zvládá konverzi efektivně.

### Kde najdu další zdroje a dokumentaci k Aspose.Slides for Java?

 Máte přístup ke komplexní dokumentaci a zdrojům pro Aspose.Slides pro Java na[Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
