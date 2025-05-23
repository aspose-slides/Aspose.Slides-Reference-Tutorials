---
"description": "Naučte se, jak přistupovat k vestavěným vlastnostem v PowerPointu pomocí Aspose.Slides pro Javu. Tento tutoriál vás provede načtením autora, data vytvoření a dalších informací."
"linktitle": "Přístup k předdefinovaným vlastnostem v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přístup k předdefinovaným vlastnostem v PowerPointu"
"url": "/cs/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přístup k předdefinovaným vlastnostem v PowerPointu

## Zavedení
tomto tutoriálu se podíváme na to, jak přistupovat k vestavěným vlastnostem v prezentacích PowerPointu pomocí knihovny Aspose.Slides pro Javu. Aspose.Slides je výkonná knihovna, která umožňuje vývojářům v Javě programově pracovat s prezentacemi PowerPointu a umožňuje bezproblémové provádění úkolů, jako je čtení a úprava vlastností.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Vývojářská sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK. Můžete si ji stáhnout z [zde](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides pro Javu: Stáhněte a nainstalujte Aspose.Slides pro Javu z [tento odkaz](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Nejprve je třeba importovat potřebné balíčky do vašeho projektu Java. Na začátek souboru Java přidejte následující příkaz import:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## Krok 1: Nastavení prezentačního objektu
Začněte nastavením objektu Presentation, který bude reprezentovat prezentaci PowerPointu, se kterou chcete pracovat. Zde je návod, jak to udělat:
```java
// Cesta k adresáři obsahujícímu soubor prezentace
String dataDir = "path_to_your_presentation_directory/";
// Vytvoření instance třídy Presentation
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## Krok 2: Otevření vlastností dokumentu
Po nastavení objektu Presentation můžete přistupovat k vestavěným vlastnostem prezentace pomocí rozhraní IDocumentProperties. Zde je návod, jak načíst různé vlastnosti:
### Kategorie
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Aktuální stav
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Datum vytvoření
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
### Naposledy upraveno uživatelem
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Vedoucí
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Datum úpravy
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
### Podrobit
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Titul
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Závěr
V tomto tutoriálu jsme se naučili, jak přistupovat k vestavěným vlastnostem v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. Dodržením výše uvedených kroků můžete snadno programově načíst různé vlastnosti, jako je autor, datum vytvoření a název.
## Často kladené otázky
### Mohu tyto vestavěné vlastnosti upravit pomocí Aspose.Slides pro Javu?
Ano, tyto vlastnosti můžete upravit pomocí Aspose.Slides. Jednoduše použijte příslušné metody nastavení poskytované rozhraním IDocumentProperties.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Aspose.Slides podporuje širokou škálu verzí PowerPointu, což zajišťuje kompatibilitu napříč různými platformami.
### Mohu také načíst vlastní vlastnosti?
Ano, kromě vestavěných vlastností můžete také načíst a upravit vlastní vlastnosti pomocí Aspose.Slides pro Javu.
### Nabízí Aspose.Slides dokumentaci a podporu?
Ano, komplexní dokumentaci a přístup k fórům podpory naleznete na [Webové stránky Aspose](https://reference.aspose.com/slides/java/).
### Je k dispozici zkušební verze Aspose.Slides pro Javu?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}