---
title: Klonovat snímek do jiné prezentace s mistrem
linktitle: Klonovat snímek do jiné prezentace s mistrem
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se klonovat snímky mezi prezentacemi v Javě pomocí Aspose.Slides. Výukový program krok za krokem o údržbě hlavních snímků.
type: docs
weight: 14
url: /cs/java/java-powerpoint-slide-cloning-techniques/clone-slide-another-presentation-master-powerpoint/
---
## Úvod
Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům programově vytvářet, upravovat a manipulovat s prezentacemi PowerPoint. Tento článek poskytuje obsáhlý, podrobný návod, jak klonovat snímek z jedné prezentace do druhé při zachování jeho hlavního snímku pomocí Aspose.Slides for Java.
## Předpoklady
Než se ponoříte do kódovací části, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[webová stránka](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java Library: Stáhněte a nainstalujte Aspose.Slides for Java z[Aspose stránku vydání](https://releases.aspose.com/slides/java/).
3. IDE: Použijte integrované vývojové prostředí (IDE) jako IntelliJ IDEA, Eclipse nebo NetBeans pro psaní a spouštění kódu Java.
4. Zdrojový soubor prezentace: Ujistěte se, že máte zdrojový soubor PowerPoint, ze kterého budete klonovat snímek.
## Importujte balíčky
Chcete-li začít, musíte do svého projektu Java importovat potřebné balíčky Aspose.Slides. Postup je následující:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
Pojďme si proces klonování snímku do jiné prezentace s hlavním snímkem rozdělit do podrobných kroků.
## Krok 1: Načtěte zdrojovou prezentaci
Nejprve musíte načíst zdrojovou prezentaci obsahující snímek, který chcete klonovat. Zde je kód:
```java
// Cesta k adresáři dokumentů.
String dataDir = "path/to/your/documents/directory/";
// Instantiate Presentation class pro načtení zdrojového souboru prezentace
Presentation srcPres = new Presentation(dataDir + "CloneToAnotherPresentationWithMaster.pptx");
```
## Krok 2: Vytvořte prezentaci cíle
 Dále vytvořte instanci souboru`Presentation` třídy pro cílovou prezentaci, kde bude snímek naklonován.
```java
// Instantiate Prezentační třída pro cílovou prezentaci
Presentation destPres = new Presentation();
```
## Krok 3: Získejte zdrojový snímek a hlavní snímek
Načtěte snímek a jeho odpovídající hlavní snímek ze zdrojové prezentace.
```java
// Instanciujte ISlide z kolekce snímků ve zdrojové prezentaci spolu s Master slide
ISlide sourceSlide = srcPres.getSlides().get_Item(0);
IMasterSlide sourceMaster = sourceSlide.getLayoutSlide().getMasterSlide();
```
## Krok 4: Naklonujte hlavní snímek do cílové prezentace
Klonujte hlavní snímek ze zdrojové prezentace do kolekce předloh v cílové prezentaci.
```java
//Naklonujte požadovaný snímek předlohy ze zdrojové prezentace do kolekce předloh v prezentaci Cíl
IMasterSlideCollection masters = destPres.getMasters();
IMasterSlide destMaster = masters.addClone(sourceMaster);
```
## Krok 5: Naklonujte snímek do cílové prezentace
Nyní naklonujte snímek spolu s jeho hlavním snímkem do cílové prezentace.
```java
// Naklonujte požadovaný snímek ze zdrojové prezentace s požadovanou předlohou na konec kolekce snímků v cílové prezentaci
ISlideCollection slides = destPres.getSlides();
slides.addClone(sourceSlide, destMaster, true);
```
## Krok 6: Uložte prezentaci cíle
Nakonec uložte cílovou prezentaci na disk.
```java
// Uložte cílovou prezentaci na disk
destPres.save(dataDir + "CloneToAnotherPresentationWithMaster_out.pptx", SaveFormat.Pptx);
```
## Krok 7: Zlikvidujte prezentace
Chcete-li uvolnit zdroje, zlikvidujte zdrojovou i cílovou prezentaci.
```java
// Zlikvidujte prezentace
if (srcPres != null) srcPres.dispose();
if (destPres != null) destPres.dispose();
```
## Závěr
Pomocí Aspose.Slides for Java můžete efektivně klonovat snímky mezi prezentacemi při zachování integrity jejich hlavních snímků. Tento tutoriál poskytuje podrobného průvodce, který vám pomůže toho dosáhnout. S těmito dovednostmi můžete programově spravovat prezentace v PowerPointu, díky čemuž budou vaše úkoly jednodušší a efektivnější.
## FAQ
### Co je Aspose.Slides for Java?  
Aspose.Slides for Java je výkonné rozhraní API pro vytváření, manipulaci a převod prezentací PowerPoint programově pomocí jazyka Java.
### Mohu klonovat více snímků najednou?  
Ano, můžete iterovat kolekcí snímků a podle potřeby klonovat více snímků.
### Je Aspose.Slides for Java zdarma?  
Aspose.Slides for Java nabízí bezplatnou zkušební verzi. Pro plnou funkčnost je potřeba zakoupit licenci.
### Jak získám dočasnou licenci pro Aspose.Slides for Java?  
 Dočasnou licenci můžete získat od[Aspose nákupní stránku](https://purchase.aspose.com/temporary-license/).
### Kde najdu další příklady a dokumentaci?  
 Navštivte[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro další příklady a podrobné informace.