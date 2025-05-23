---
"description": "Naučte se, jak změnit data objektů OLE v PowerPointu pomocí Aspose.Slides pro Javu. Podrobný návod pro efektivní a snadné aktualizace."
"linktitle": "Změna dat objektu OLE v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Změna dat objektu OLE v PowerPointu"
"url": "/cs/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Změna dat objektu OLE v PowerPointu

## Zavedení
Změna dat objektů OLE v prezentacích PowerPointu může být klíčovým úkolem, pokud potřebujete aktualizovat vložený obsah, aniž byste museli ručně upravovat každý snímek. Tato komplexní příručka vás provede procesem s využitím Aspose.Slides pro Javu, výkonné knihovny určené pro práci s prezentacemi PowerPointu. Ať už jste zkušený vývojář, nebo teprve začínáte, tento tutoriál vám bude užitečný a snadno se v něm orientovat.
## Předpoklady
Než se pustíme do kódu, ujistěme se, že máte vše, co potřebujete k zahájení.
1. Vývojářská sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK. Můžete si ji stáhnout z [Stránky společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides pro Javu: Stáhněte si nejnovější verzi z [Stránka pro stažení Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Můžete použít jakékoli vývojové prostředí Java, například IntelliJ IDEA, Eclipse nebo NetBeans.
4. Aspose.Cells pro Javu: Toto je nutné k úpravě vložených dat v objektu OLE. Stáhněte si jej z [Stránka ke stažení Aspose.Cells](https://releases.aspose.com/cells/java/).
5. Soubor prezentace: Připravte si soubor PowerPoint s vloženým objektem OLE. Pro tento tutoriál ho pojmenujeme `ChangeOLEObjectData.pptx`.
## Importovat balíčky
Nejprve si importujme potřebné balíčky do vašeho projektu v Javě.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Nyní si celý proces rozdělme na jednoduché a zvládnutelné kroky.
## Krok 1: Načtěte prezentaci v PowerPointu
Pro začátek je potřeba načíst prezentaci PowerPointu obsahující objekt OLE.
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Krok 2: Přístup ke snímku obsahujícímu objekt OLE
Dále získejte snímek, do kterého je vložený objekt OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Nalezení objektu OLE na snímku
Projděte si tvary na snímku a vyhledejte objekt OLE.
```java
OleObjectFrame ole = null;
// Procházení všech tvarů pro rám Ole
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## Krok 4: Extrahování vložených dat z objektu OLE
Pokud je objekt OLE nalezen, extrahujte jeho vložená data.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Krok 5: Úprava vložených dat pomocí Aspose.Cells
Nyní použijte Aspose.Cells k načtení a úpravě vložených dat, což je v tomto případě pravděpodobně sešit aplikace Excel.
```java
    Workbook wb = new Workbook(msln);
    // Úprava dat v sešitu
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Krok 6: Uložení upravených dat zpět do objektu OLE
Po provedení potřebných změn uložte upravený sešit zpět do objektu OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Krok 7: Uložte aktualizovanou prezentaci
Nakonec uložte aktualizovanou prezentaci PowerPointu.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Závěr
Aktualizace dat objektů OLE v prezentacích PowerPointu pomocí Aspose.Slides pro Javu je přímočarý proces, jakmile si ho rozdělíte na jednoduché kroky. Tato příručka vás provede načtením prezentace, přístupem k vloženým datům OLE a jejich úpravou a uložením aktualizované prezentace. Pomocí těchto kroků můžete efektivně spravovat a aktualizovat vložený obsah ve vašich slidech PowerPointu programově.
## Často kladené otázky
### Co je objekt OLE v PowerPointu?
Objekt OLE (Object Linking and Embedding) umožňuje vkládat obsah z jiných aplikací, jako jsou tabulky aplikace Excel, do snímků aplikace PowerPoint.
### Mohu používat Aspose.Slides s jinými programovacími jazyky?
Ano, Aspose.Slides podporuje několik programovacích jazyků včetně .NET, Pythonu a C++.
### Potřebuji Aspose.Cells k úpravě objektů OLE v PowerPointu?
Ano, pokud je objekt OLE tabulka aplikace Excel, budete k její úpravě potřebovat Aspose.Cells.
### Existuje zkušební verze Aspose.Slides?
Ano, můžete získat [bezplatná zkušební verze](https://releases.aspose.com/) otestovat funkce Aspose.Slides.
### Kde najdu dokumentaci k Aspose.Slides?
Podrobnou dokumentaci naleznete na [Stránka s dokumentací k Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}