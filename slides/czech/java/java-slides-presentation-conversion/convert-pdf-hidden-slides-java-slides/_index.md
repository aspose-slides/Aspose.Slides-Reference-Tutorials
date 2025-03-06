---
title: Převeďte do PDF pomocí skrytých snímků v Java Slides
linktitle: Převeďte do PDF pomocí skrytých snímků v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se převádět PowerPointové prezentace do PDF se skrytými snímky pomocí Aspose.Slides for Java. Postupujte podle našeho podrobného průvodce se zdrojovým kódem pro bezproblémové generování PDF.
weight: 27
url: /cs/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převeďte do PDF pomocí skrytých snímků v Java Slides


## Úvod do převodu PowerPointové prezentace do PDF se skrytými snímky pomocí Aspose.Slides pro Java

tomto podrobném průvodci se dozvíte, jak pomocí Aspose.Slides for Java převést prezentaci v PowerPointu do PDF při zachování skrytých snímků. Skryté snímky jsou snímky, které se při běžné prezentaci nezobrazují, ale lze je zahrnout do výstupu PDF. Poskytneme vám zdrojový kód a podrobné pokyny k dosažení tohoto úkolu.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1.  Knihovna Aspose.Slides for Java: Ujistěte se, že máte v projektu Java nastavenou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

2. Vývojové prostředí Java: V systému byste měli mít nainstalované vývojové prostředí Java.

## Krok 1: Import Aspose.Slides pro Java

Nejprve musíte do svého projektu Java importovat knihovnu Aspose.Slides. Ujistěte se, že jste knihovnu přidali do cesty sestavení vašeho projektu.

```java
import com.aspose.slides.*;
```

## Krok 2: Načtěte prezentaci PowerPoint

 Začnete načtením PowerPointové prezentace, kterou chcete převést do PDF. Nahradit`"Your Document Directory"` a`"HiddingSlides.pptx"` s příslušnou cestou k souboru.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Krok 3: Nakonfigurujte možnosti PDF

Nakonfigurujte možnosti PDF tak, aby zahrnovaly skryté snímky do výstupu PDF. Můžete to udělat nastavením`setShowHiddenSlides` vlastnictvím`PdfOptions` třídy do`true`.

```java
// Vytvořte instanci třídy PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Určete, že vygenerovaný dokument by měl obsahovat skryté snímky
pdfOptions.setShowHiddenSlides(true);
```

## Krok 4: Uložte prezentaci jako PDF

 Nyní uložte prezentaci do souboru PDF se zadanými možnostmi. Nahradit`"PDFWithHiddenSlides_out.pdf"` s požadovaným názvem výstupního souboru.

```java
// Uložte prezentaci do PDF se zadanými možnostmi
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Krok 5: Prostředky pro čištění

Po dokončení prezentace nezapomeňte uvolnit zdroje používané prezentací.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Kompletní zdrojový kód pro převod do PDF se skrytými snímky v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Vytvořte instanci třídy PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Určete, že vygenerovaný dokument by měl obsahovat skryté snímky
	pdfOptions.setShowHiddenSlides(true);
	// Uložte prezentaci do PDF se zadanými možnostmi
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto komplexním průvodci jste se naučili, jak převést prezentaci v PowerPointu do PDF při zachování skrytých snímků pomocí Aspose.Slides for Java. Poskytli jsme vám výukový program krok za krokem spolu s nezbytným zdrojovým kódem pro bezproblémové splnění tohoto úkolu.

## FAQ

### Jak mohu skrýt snímky v prezentaci PowerPoint?

Chcete-li skrýt snímek v prezentaci PowerPoint, postupujte takto:
1. V zobrazení Řazení snímků vyberte snímek, který chcete skrýt.
2. Klepněte pravým tlačítkem myši na vybraný snímek.
3. Z kontextové nabídky vyberte "Skrýt snímek".

### Mohu programově odkrýt skryté snímky v Aspose.Slides pro Java?

 Ano, můžete programově odkrýt skryté snímky v Aspose.Slides pro Java nastavením`Hidden` vlastnictvím`Slide` třídy do`false`. Zde je příklad:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Nahraďte slideIndex indexem skrytého snímku
slide.setHidden(false);
```

### Jak si stáhnu Aspose.Slides for Java?

 Aspose.Slides for Java si můžete stáhnout z webu Aspose. Navštivte[Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/) získat nejnovější verzi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
