---
title: Přístup k vestavěným vlastnostem v aplikaci PowerPoint
linktitle: Přístup k vestavěným vlastnostem v aplikaci PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Zjistěte, jak získat přístup k integrovaným vlastnostem v PowerPointu pomocí Aspose.Slides for Java. Tento výukový program vás provede vyhledáním autora, data vytvoření a dalšími.
weight: 10
url: /cs/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
V tomto tutoriálu prozkoumáme, jak získat přístup k vestavěným vlastnostem v prezentacích PowerPoint pomocí Aspose.Slides for Java. Aspose.Slides je výkonná knihovna, která vývojářům v jazyce Java umožňuje programově pracovat s prezentacemi aplikace PowerPoint a umožňuje bezproblémové provádění úkolů, jako je čtení a úprava vlastností.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[tady](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Stáhněte si a nainstalujte Aspose.Slides for Java z[tento odkaz](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Nejprve je třeba importovat potřebné balíčky do vašeho projektu Java. Na začátek souboru Java přidejte následující příkaz pro import:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Krok 1: Nastavte objekt prezentace
Začněte nastavením objektu Prezentace tak, aby představoval prezentaci PowerPoint, se kterou chcete pracovat. Můžete to udělat takto:
```java
// Cesta k adresáři obsahujícímu soubor prezentace
String dataDir = "path_to_your_presentation_directory/";
// Vytvořte instanci třídy Prezentace
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Krok 2: Otevřete vlastnosti dokumentu
Po nastavení objektu Presentation můžete přistupovat k vestavěným vlastnostem prezentace pomocí rozhraní IDocumentProperties. Zde je návod, jak můžete získat různé vlastnosti:
### Kategorie
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Aktuální stav
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Datum vzniku
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Autor
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Popis
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Klíčová slova
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Naposledy změněno
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Dozorce
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Upravené datum
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Formát prezentace
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Datum posledního tisku
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Sdíleno mezi producenty
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Předmět
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titul
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Závěr
tomto tutoriálu jsme se naučili, jak přistupovat k vestavěným vlastnostem v prezentacích PowerPoint pomocí Aspose.Slides for Java. Podle výše uvedených kroků můžete snadno programově načíst různé vlastnosti, jako je autor, datum vytvoření a název.
## FAQ
### Mohu upravit tyto vestavěné vlastnosti pomocí Aspose.Slides for Java?
Ano, tyto vlastnosti můžete upravit pomocí Aspose.Slides. Jednoduše použijte vhodné metody nastavení poskytované rozhraním IDocumentProperties.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Aspose.Slides podporuje širokou škálu verzí aplikace PowerPoint a zajišťuje kompatibilitu napříč různými platformami.
### Mohu také načíst vlastní vlastnosti?
Ano, kromě vestavěných vlastností můžete také načíst a upravit uživatelské vlastnosti pomocí Aspose.Slides for Java.
### Nabízí Aspose.Slides dokumentaci a podporu?
 Ano, na webu naleznete komplexní dokumentaci a přístup k fórům podpory[Aspose webové stránky](https://reference.aspose.com/slides/java/).
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
