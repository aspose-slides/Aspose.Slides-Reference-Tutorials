---
"description": "Naučte se, jak programově manipulovat s prezentacemi v PowerPointu pomocí Aspose.Slides pro Javu. Zvládněte práci s PowerPointem v Javě pomocí podrobných tutoriálů."
"linktitle": "Uložení PowerPointu s výchozím běžným písmem pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Uložení PowerPointu s výchozím běžným písmem pomocí Javy"
"url": "/cs/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uložení PowerPointu s výchozím běžným písmem pomocí Javy

## Zavedení
oblasti vývoje v Javě může programově vytvářet a manipulovat s prezentacemi v PowerPointu výrazně zvýšit produktivitu a možnosti přizpůsobení. Aspose.Slides pro Javu je robustní knihovna, která vývojářům umožňuje efektivně pracovat se soubory PowerPoint a nabízí komplexní sadu funkcí od jednoduchých úprav až po složité prezentace.
## Předpoklady
Než se pustíte do používání Aspose.Slides pro Javu, ujistěte se, že máte nastaveny následující předpoklady:
1. Vývojová sada pro Javu (JDK): Aspose.Slides pro Javu vyžaduje pro správné fungování JDK 1.8 nebo vyšší.
2. Aspose.Slides pro Javu JAR: Stáhněte si nejnovější verzi Aspose.Slides pro Javu z [zde](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte IntelliJ IDEA, Eclipse nebo jiné vývojové prostředí Java dle vašeho výběru.
4. Základní znalost Javy: Znalost základů programovacího jazyka Java je nezbytná.

## Importovat balíčky
Chcete-li začít používat Aspose.Slides pro Javu, importujte potřebné balíčky:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Tím je zajištěno, že máte přístup ke všem třídám a metodám poskytovaným Aspose.Slides pro Javu.
## Krok 1: Nastavení projektu
Nejprve vytvořte nový projekt Java ve vašem IDE a do cesty sestavení projektu vložte soubor Aspose.Slides for Java JAR.
## Krok 2: Inicializace prezentačního objektu
Vytvořte instanci `Presentation` objekt načtením existujícího souboru PowerPoint (.pptx) z vašeho lokálního adresáře.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Načíst prezentaci
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Nahradit `"Your Document Directory"` a `"Your Output Directory"` s vašimi skutečnými cestami k souborům.
## Krok 3: Uložení prezentace s výchozími běžnými písmy
Zadejte výchozí běžné písmo pro výstupní formáty (HTML a PDF) pomocí `HtmlOptions` a `PdfOptions` respektive.
```java
try {
    // Možnosti ukládání HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Možnosti ukládání PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Ujistěte se, že vyměníte `"Arial Black"` a `"Lucida Console"` s požadovanými výchozími běžnými fonty.

## Závěr
Dodržováním těchto kroků jste se naučili, jak efektivně manipulovat s prezentacemi v PowerPointu pomocí Aspose.Slides pro Javu. Tato funkce vám umožňuje automatizovat úkoly, přizpůsobovat prezentace a vylepšovat vaše Java aplikace pomocí pokročilých funkcí pro práci s PowerPointem.
## Často kladené otázky
### Může Aspose.Slides pro Javu fungovat se staršími verzemi JDK?
Aspose.Slides pro Javu vyžaduje pro kompatibilitu JDK 1.8 nebo vyšší.
### Jak mohu získat dočasnou licenci pro Aspose.Slides pro Javu?
Dočasné povolení můžete získat od [zde](https://purchase.aspose.com/temporary-license/).
### Kde najdu podrobnější dokumentaci k Aspose.Slides pro Javu?
Prozkoumejte komplexní dokumentaci [zde](https://reference.aspose.com/slides/java/).
### Je pro Aspose.Slides pro Javu k dispozici komunitní podpora?
Ano, můžete získat podporu komunity [zde](https://forum.aspose.com/c/slides/11).
### Mohu si Aspose.Slides pro Javu vyzkoušet zdarma?
Ano, stáhněte si bezplatnou zkušební verzi [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}