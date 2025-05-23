---
"description": "Naučte se, jak převést prezentace PowerPointu do obrázků TIFF s vlastní velikostí pomocí Aspose.Slides pro Javu. Podrobný návod s příklady kódu pro vývojáře."
"linktitle": "Převod s vlastní velikostí v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Převod s vlastní velikostí v Java Slides"
"url": "/cs/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod s vlastní velikostí v Java Slides


## Úvod do převodu s vlastní velikostí v Javě Slides

tomto článku se podíváme na to, jak převést prezentace PowerPointu do obrázků TIFF s vlastní velikostí pomocí rozhraní API Aspose.Slides for Java. Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům programově pracovat se soubory PowerPointu. Projdeme si to krok za krokem a poskytneme vám potřebný kód Java k provedení tohoto úkolu.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Nainstalovaná vývojářská sada Java (JDK)
- Aspose.Slides pro knihovnu Java

Knihovnu Aspose.Slides pro Javu si můžete stáhnout z webových stránek: [Stáhněte si Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/)

## Krok 1: Import knihovny Aspose.Slides

Chcete-li začít, musíte importovat knihovnu Aspose.Slides do svého projektu v Javě. Zde je návod, jak to udělat:

```java
// Přidejte potřebný příkaz pro import
import com.aspose.slides.*;
```

## Krok 2: Načtěte prezentaci v PowerPointu

Dále budete muset načíst prezentaci PowerPoint, kterou chcete převést na obrázek TIFF. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru prezentace.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření instance objektu Presentation, který představuje soubor Presentation.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Krok 3: Nastavení možností převodu TIFF

Nyní nastavme možnosti pro převod TIFF. Určíme typ komprese, DPI (body na palec), velikost obrázku a umístění poznámek. Tyto možnosti si můžete přizpůsobit podle svých požadavků.

```java
// Vytvoření instance třídy TiffOptions
TiffOptions opts = new TiffOptions();

// Nastavení typu komprese
opts.setCompressionType(TiffCompressionTypes.Default);

// Nastavení DPI obrázku
opts.setDpiX(200);
opts.setDpiY(100);

// Nastavit velikost obrázku
opts.setImageSize(new Dimension(1728, 1078));

// Nastavení pozice not
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 4: Uložit jako TIFF

Po nastavení všech možností můžete nyní prezentaci uložit jako obrázek TIFF se zadaným nastavením.

```java
// Uložit prezentaci do formátu TIFF s danou velikostí obrázku
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Kompletní zdrojový kód pro převod s vlastní velikostí v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance objektu Presentation, který představuje soubor Presentation.
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Vytvoření instance třídy TiffOptions
	TiffOptions opts = new TiffOptions();
	// Nastavení typu komprese
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Typy komprese
	// Výchozí – Určuje výchozí schéma komprese (LZW).
	// Žádná – Určuje žádnou kompresi.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Hloubka závisí na typu komprese a nelze ji nastavit ručně.
	// Jednotka rozlišení je vždy rovna „2“ (body na palec)
	// Nastavení DPI obrázku
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Nastavit velikost obrázku
	opts.setImageSize(new Dimension(1728, 1078));
	// Uložit prezentaci do formátu TIFF s danou velikostí obrázku
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Gratulujeme! Úspěšně jste převedli prezentaci PowerPoint do formátu TIFF s vlastní velikostí pomocí nástroje Aspose.Slides pro Javu. Tato funkce může být cenná, když potřebujete z prezentací generovat vysoce kvalitní obrázky pro různé účely.

## Často kladené otázky

### Jak mohu změnit typ komprese pro obrázek TIFF?

Typ komprese můžete změnit úpravou `setCompressionType` metoda v `TiffOptions` třída. K dispozici jsou různé typy komprese, například Výchozí, Žádná, CCITT3, CCITT4, LZW a RLE.

### Mohu upravit DPI (body na palec) obrázku TIFF?

Ano, DPI můžete upravit pomocí `setDpiX` a `setDpiY` metody v `TiffOptions` třída. Jednoduše nastavte požadované hodnoty pro ovládání rozlišení obrazu.

### Jaké jsou dostupné možnosti pro umístění poznámek v obrázku TIFF?

Pozici poznámek v obrázku TIFF lze nakonfigurovat pomocí `setNotesPosition` s možnostmi jako BottomFull, BottomTruncated a SlideOnly. Vyberte si tu, která nejlépe vyhovuje vašim potřebám.

### Je možné zadat vlastní velikost obrázku pro konverzi TIFF?

Rozhodně! Vlastní velikost obrázku si můžete nastavit pomocí `setImageSize` metoda v `TiffOptions` třída. Zadejte požadované rozměry (šířku a výšku) výstupního obrázku.

### Kde najdu více informací o Aspose.Slides pro Javu?

Podrobnou dokumentaci a další informace o Aspose.Slides pro Javu naleznete v dokumentaci: [Referenční příručka k Aspose.Slides pro Java API](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}