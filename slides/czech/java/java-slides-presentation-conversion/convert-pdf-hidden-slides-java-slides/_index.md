---
"description": "Naučte se, jak převést prezentace PowerPointu do PDF se skrytými snímky pomocí Aspose.Slides pro Javu. Postupujte podle našeho podrobného návodu se zdrojovým kódem pro bezproblémové generování PDF."
"linktitle": "Převod do PDF se skrytými snímky v aplikaci Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Převod do PDF se skrytými snímky v aplikaci Java Slides"
"url": "/cs/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod do PDF se skrytými snímky v aplikaci Java Slides


## Úvod do převodu prezentací v PowerPointu do PDF se skrytými snímky pomocí Aspose.Slides pro Javu

tomto podrobném návodu se naučíte, jak převést prezentaci v PowerPointu do PDF a zároveň zachovat skryté snímky pomocí nástroje Aspose.Slides pro Javu. Skryté snímky jsou ty, které se nezobrazují během běžné prezentace, ale lze je zahrnout do výstupu PDF. Poskytneme vám zdrojový kód a podrobné pokyny k provedení tohoto úkolu.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Knihovna Aspose.Slides pro Java: Ujistěte se, že máte ve svém projektu Java nastavenou knihovnu Aspose.Slides pro Java. Můžete si ji stáhnout z [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

2. Vývojové prostředí Java: Na vašem systému byste měli mít nainstalované vývojové prostředí Java.

## Krok 1: Import Aspose.Slides pro Javu

Nejprve je třeba importovat knihovnu Aspose.Slides do vašeho projektu v Javě. Ujistěte se, že jste knihovnu přidali do cesty sestavení vašeho projektu.

```java
import com.aspose.slides.*;
```

## Krok 2: Načtěte prezentaci v PowerPointu

Začnete načtením prezentace PowerPoint, kterou chcete převést do formátu PDF. Nahraďte `"Your Document Directory"` a `"HiddingSlides.pptx"` s příslušnou cestou k souboru.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Krok 3: Konfigurace možností PDF

Nakonfigurujte možnosti PDF tak, aby do výstupu PDF zahrnovaly skryté snímky. Toho lze dosáhnout nastavením `setShowHiddenSlides` majetek `PdfOptions` třída do `true`.

```java
// Vytvořte instanci třídy PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Určete, že vygenerovaný dokument má obsahovat skryté snímky
pdfOptions.setShowHiddenSlides(true);
```

## Krok 4: Uložte prezentaci jako PDF

Nyní uložte prezentaci do souboru PDF se zadanými možnostmi. Nahraďte `"PDFWithHiddenSlides_out.pdf"` s požadovaným názvem výstupního souboru.

```java
// Uložit prezentaci do PDF s zadanými možnostmi
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Krok 5: Zdroje pro úklid

Po dokončení prezentace nezapomeňte uvolnit zdroje, které s ní pracuje.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Kompletní zdrojový kód pro převod do PDF se skrytými snímky v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Vytvořte instanci třídy PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Určete, že vygenerovaný dokument má obsahovat skryté snímky
	pdfOptions.setShowHiddenSlides(true);
	// Uložit prezentaci do PDF s zadanými možnostmi
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto komplexním průvodci jste se naučili, jak převést prezentaci v PowerPointu do PDF a zároveň zachovat skryté snímky pomocí Aspose.Slides pro Javu. Poskytli jsme vám podrobný návod spolu s potřebným zdrojovým kódem, abyste tento úkol bez problémů zvládli.

## Často kladené otázky

### Jak mohu skrýt snímky v prezentaci v PowerPointu?

Chcete-li skrýt snímek v prezentaci PowerPoint, postupujte takto:
1. V zobrazení Řazení snímků vyberte snímek, který chcete skrýt.
2. Klikněte pravým tlačítkem myši na vybraný snímek.
3. V kontextové nabídce vyberte možnost „Skrýt snímek“.

### Mohu programově zobrazit skryté snímky v Aspose.Slides pro Javu?

Ano, skryté snímky v Aspose.Slides pro Javu můžete programově zobrazit nastavením `Hidden` majetek `Slide` třída do `false`Zde je příklad:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Nahraďte slideIndex indexem skrytého snímku.
slide.setHidden(false);
```

### Jak si stáhnu Aspose.Slides pro Javu?

Aspose.Slides pro Javu si můžete stáhnout z webových stránek Aspose. Navštivte [Stránka ke stažení Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/) abyste získali nejnovější verzi.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}