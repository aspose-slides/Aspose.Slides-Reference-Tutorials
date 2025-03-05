---
title: Uložte PowerPoint s výchozím běžným písmem pomocí Java
linktitle: Uložte PowerPoint s výchozím běžným písmem pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak programově manipulovat s prezentacemi PowerPoint pomocí Aspose.Slides for Java. Osvojte si práci s Java PowerPoint pomocí výukových programů krok za krokem.
type: docs
weight: 12
url: /cs/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## Úvod
V oblasti vývoje Java může vytváření a manipulace s prezentacemi v PowerPointu programově výrazně zvýšit produktivitu a možnosti přizpůsobení. Aspose.Slides for Java je robustní knihovna, která umožňuje vývojářům efektivně zpracovávat soubory PowerPoint a nabízí komplexní sadu funkcí od jednoduchých úprav až po složité prezentace.
## Předpoklady
Než se pustíte do používání Aspose.Slides for Java, ujistěte se, že máte nastaveny následující předpoklady:
1. Java Development Kit (JDK): Aspose.Slides for Java vyžaduje ke správné funkci JDK 1.8 nebo vyšší.
2. Aspose.Slides for Java JAR: Stáhněte si nejnovější verzi Aspose.Slides pro Java z[tady](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte IntelliJ IDEA, Eclipse nebo jiné Java IDE dle vašeho výběru.
4. Základní porozumění Javě: Je nutná znalost základů programovacího jazyka Java.

## Importujte balíčky
Chcete-li začít používat Aspose.Slides for Java, importujte potřebné balíčky:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
To zajišťuje, že máte přístup ke všem třídám a metodám poskytovaným Aspose.Slides for Java.
## Krok 1: Nastavte svůj projekt
Nejprve vytvořte nový projekt Java ve svém IDE a zahrňte soubor JAR Aspose.Slides for Java do cesty sestavení vašeho projektu.
## Krok 2: Inicializujte objekt prezentace
 Instantovat a`Presentation` objekt načtením existujícího souboru PowerPoint (.pptx) z vašeho místního adresáře.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Načíst prezentaci
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Nahradit`"Your Document Directory"` a`"Your Output Directory"` s vašimi skutečnými cestami k souborům.
## Krok 3: Uložte prezentaci s výchozími běžnými písmy
 Určete výchozí běžné písmo pro výstupní formáty (HTML a PDF).`HtmlOptions` a`PdfOptions` respektive.
```java
try {
    // Možnosti uložení HTML
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Možnosti uložení PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Zajistěte výměnu`"Arial Black"` a`"Lucida Console"` s požadovanými výchozími běžnými fonty.

## Závěr
Pomocí těchto kroků jste se naučili, jak efektivně manipulovat s prezentacemi PowerPoint pomocí Aspose.Slides for Java. Tato schopnost vám umožňuje automatizovat úlohy, přizpůsobovat prezentace a vylepšovat vaše Java aplikace o pokročilé funkce pro manipulaci s PowerPointem.
## FAQ
### Může Aspose.Slides for Java pracovat se staršími verzemi JDK?
Aspose.Slides for Java vyžaduje kvůli kompatibilitě JDK 1.8 nebo vyšší.
### Jak mohu získat dočasné licencování pro Aspose.Slides pro Java?
 Dočasnou licenci můžete získat od[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu podrobnější dokumentaci k Aspose.Slides for Java?
 Prozkoumejte komplexní dokumentaci[tady](https://reference.aspose.com/slides/java/).
### Je pro Aspose.Slides pro Java k dispozici podpora komunity?
 Ano, můžete získat podporu komunity[tady](https://forum.aspose.com/c/slides/11).
### Mohu vyzkoušet Aspose.Slides for Java zdarma?
 Ano, stáhněte si bezplatnou zkušební verzi[tady](https://releases.aspose.com/).