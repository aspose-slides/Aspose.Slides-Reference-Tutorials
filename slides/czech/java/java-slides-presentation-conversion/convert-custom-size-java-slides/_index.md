---
title: Převod s vlastní velikostí v Java Slides
linktitle: Převod s vlastní velikostí v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se převádět prezentace PowerPoint na obrázky TIFF s vlastní velikostí pomocí Aspose.Slides for Java. Podrobný průvodce s příklady kódu pro vývojáře.
weight: 31
url: /cs/java/presentation-conversion/convert-custom-size-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převod s vlastní velikostí v Java Slides


## Úvod do převodu s vlastní velikostí v Java Slides

V tomto článku prozkoumáme, jak převést PowerPointové prezentace na obrázky TIFF s vlastní velikostí pomocí Aspose.Slides for Java API. Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům pracovat se soubory PowerPoint programově. Půjdeme krok za krokem a poskytneme vám potřebný kód Java, abyste mohli tento úkol splnit.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalován
- Aspose.Slides pro knihovnu Java

 Knihovnu Aspose.Slides for Java si můžete stáhnout z webu:[Stáhněte si Aspose.Slides pro Java](https://releases.aspose.com/slides/java/)

## Krok 1: Import knihovny Aspose.Slides

Chcete-li začít, musíte do svého projektu Java importovat knihovnu Aspose.Slides. Můžete to udělat takto:

```java
// Přidejte potřebné prohlášení o importu
import com.aspose.slides.*;
```

## Krok 2: Načtěte prezentaci PowerPoint

 Dále budete muset načíst prezentaci PowerPoint, kterou chcete převést na obrázek TIFF. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Vytvořte instanci objektu Presentation, který představuje soubor Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Krok 3: Nastavte možnosti převodu TIFF

Nyní nastavíme možnosti pro převod TIFF. Zadáme typ komprese, DPI (bodů na palec), velikost obrázku a polohu poznámek. Tyto možnosti si můžete přizpůsobit podle svých požadavků.

```java
// Vytvořte instanci třídy TiffOptions
TiffOptions opts = new TiffOptions();

// Nastavení typu komprese
opts.setCompressionType(TiffCompressionTypes.Default);

// Nastavení DPI obrazu
opts.setDpiX(200);
opts.setDpiY(100);

// Nastavte velikost obrázku
opts.setImageSize(new Dimension(1728, 1078));

// Nastavte polohu poznámek
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Krok 4: Uložte jako TIFF

Se všemi konfigurovanými možnostmi můžete nyní prezentaci uložit jako obrázek TIFF se zadaným nastavením.

```java
// Uložte prezentaci do formátu TIFF se zadanou velikostí obrázku
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Kompletní zdrojový kód pro převod s vlastní velikostí v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci objektu Presentation, který představuje soubor Presentation
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// Vytvořte instanci třídy TiffOptions
	TiffOptions opts = new TiffOptions();
	// Nastavení typu komprese
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Typy komprese
	// Výchozí – Určuje výchozí schéma komprese (LZW).
	// Žádná – neurčuje žádnou kompresi.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Hloubka závisí na typu komprese a nelze ji nastavit ručně.
	// Jednotka rozlišení je vždy rovna „2“ (body na palec)
	// Nastavení DPI obrazu
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Nastavte velikost obrázku
	opts.setImageSize(new Dimension(1728, 1078));
	// Uložte prezentaci do formátu TIFF se zadanou velikostí obrázku
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Gratulujeme! Úspěšně jste převedli prezentaci PowerPoint na obrázek TIFF s vlastní velikostí pomocí Aspose.Slides for Java. To může být cenná funkce, když potřebujete generovat vysoce kvalitní obrázky z vašich prezentací pro různé účely.

## FAQ

### Jak mohu změnit typ komprese pro obrázek TIFF?

 Typ komprese můžete změnit úpravou`setCompressionType` metoda v`TiffOptions` třída. K dispozici jsou různé typy komprese, například Výchozí, Žádná, CCITT3, CCITT4, LZW a RLE.

### Mohu upravit DPI (bodů na palec) obrázku TIFF?

Ano, můžete upravit DPI pomocí`setDpiX` a`setDpiY` metody v`TiffOptions` třída. Jednoduše nastavte požadované hodnoty pro ovládání rozlišení obrazu.

### Jaké jsou dostupné možnosti pro umístění poznámek v obrázku TIFF?

 Pozici poznámek v obrázku TIFF lze konfigurovat pomocí`setNotesPosition` metoda s možnostmi jako BottomFull, BottomTruncated a SlideOnly. Vyberte si ten, který nejlépe vyhovuje vašim potřebám.

### Je možné určit vlastní velikost obrázku pro převod TIFF?

 Absolutně! Vlastní velikost obrázku můžete nastavit pomocí`setImageSize` metoda v`TiffOptions` třída. Zadejte rozměry (šířku a výšku), které chcete pro výstupní obrázek.

### Kde najdu více informací o Aspose.Slides for Java?

 Podrobnou dokumentaci a další informace o Aspose.Slides pro Java naleznete v dokumentaci:[Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
