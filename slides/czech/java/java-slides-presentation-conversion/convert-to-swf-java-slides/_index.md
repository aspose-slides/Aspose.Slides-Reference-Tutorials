---
title: Převést na SWF v Java Slides
linktitle: Převést na SWF v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Převeďte PowerPointové prezentace do formátu SWF v Javě pomocí Aspose.Slides. Postupujte podle našeho podrobného průvodce se zdrojovým kódem pro bezproblémový převod.
weight: 35
url: /cs/java/presentation-conversion/convert-to-swf-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převést na SWF v Java Slides


## Úvod do převodu PowerPointové prezentace na SWF v Javě pomocí Aspose.Slides

V tomto tutoriálu se naučíte, jak převést prezentaci v PowerPointu (PPTX) do formátu SWF (Shockwave Flash) pomocí Aspose.Slides for Java. Aspose.Slides je výkonná knihovna, která umožňuje programově pracovat s prezentacemi PowerPoint.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Java Development Kit (JDK) nainstalován.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://downloads.aspose.com/slides/java).

## Krok 1: Import knihovny Aspose.Slides

Nejprve musíte do svého projektu Java importovat knihovnu Aspose.Slides. Soubor JAR můžete přidat do cesty třídy svého projektu.

## Krok 2: Inicializujte objekt prezentace Aspose.Slides

 tomto kroku vytvoříte a`Presentation` objekt k načtení prezentace PowerPoint. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru PowerPoint.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```

## Krok 3: Nastavte možnosti převodu SWF

 Nyní nastavíte možnosti převodu SWF pomocí`SwfOptions` třída. Proces převodu můžete přizpůsobit zadáním různých možností. V tomto příkladu nastavíme`viewerIncluded` možnost`false`, což znamená, že prohlížeč nezahrneme do souboru SWF.

```java
SwfOptions swfOptions = new SwfOptions();
swfOptions.setViewerIncluded(false);
```

V případě potřeby můžete také nakonfigurovat možnosti týkající se rozvržení poznámek a komentářů. V tomto příkladu nastavíme pozici poznámek na „BottomFull“.

```java
INotesCommentsLayoutingOptions notesOptions = swfOptions.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 4: Převeďte na SWF

 Nyní můžete prezentaci PowerPoint převést do formátu SWF pomocí`save` metoda`Presentation` objekt.

```java
presentation.save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
```

Tento řádek kódu uloží prezentaci jako soubor SWF se zadanými volbami.

## Krok 5: Zahrnout prohlížeč (volitelné)

 Pokud chcete prohlížeč zahrnout do souboru SWF, můžete změnit`viewerIncluded` možnost`true` a prezentaci znovu uložte.

```java
swfOptions.setViewerIncluded(true);
presentation.save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
```

## Krok 6: Vyčistěte

 Nakonec se ujistěte, že jste je zlikvidovali`Presentation`vznést námitku proti uvolnění jakýchkoli zdrojů.

```java
if (presentation != null) presentation.dispose();
```

## Kompletní zdrojový kód pro převod do SWF v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci objektu Presentation, který představuje soubor prezentace
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
try
{
	SwfOptions swfOptions = new SwfOptions();
	swfOptions.setViewerIncluded(false);
	INotesCommentsLayoutingOptions notesOptions = swfOptions.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Ukládání stránek prezentace a poznámek
	presentation.save(dataDir + "SaveAsSwf_out.swf", SaveFormat.Swf, swfOptions);
	swfOptions.setViewerIncluded(true);
	presentation.save(dataDir + "SaveNotes_out.swf", SaveFormat.Swf, swfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

Úspěšně jste převedli prezentaci PowerPoint do formátu SWF pomocí Aspose.Slides for Java. Proces převodu můžete dále přizpůsobit prozkoumáním různých možností, které poskytuje Aspose.Slides.

## FAQ

### Jak nastavím různé možnosti převodu SWF?

 Možnosti převodu SWF můžete přizpůsobit úpravou souboru`SwfOptions` objekt. Seznam dostupných možností naleznete v dokumentaci Aspose.Slides.

### Mohu do souboru SWF zahrnout poznámky a komentáře?

 Ano, do souboru SWF můžete zahrnout poznámky a komentáře konfigurací`SwfOptions` podle toho. Použijte`setViewerIncluded` způsob kontroly, zda jsou zahrnuty poznámky a komentáře.

### Jaká je výchozí pozice poznámek v souboru SWF?

Výchozí pozice poznámek v souboru SWF je „Žádné“. Podle potřeby jej můžete změnit na „BottomFull“ nebo jiné pozice.

### Existují nějaké další výstupní formáty podporované Aspose.Slides?

Ano, Aspose.Slides podporuje různé výstupní formáty, včetně PDF, HTML, obrázků a dalších. Tyto možnosti můžete prozkoumat v dokumentaci.

### Jak mohu řešit chyby během převodu?

Bloky try-catch můžete použít ke zpracování výjimek, které mohou nastat během procesu převodu. Ujistěte se, že najdete v dokumentaci Aspose.Slides konkrétní doporučení pro řešení chyb.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
