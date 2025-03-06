---
title: Změňte data objektu OLE v aplikaci PowerPoint
linktitle: Změňte data objektu OLE v aplikaci PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak změnit data objektu OLE v PowerPointu pomocí Aspose.Slides for Java. Průvodce krok za krokem pro efektivní a snadné aktualizace.
weight: 14
url: /cs/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte data objektu OLE v aplikaci PowerPoint

## Úvod
Změna dat objektu OLE v prezentacích PowerPoint může být zásadním úkolem, když potřebujete aktualizovat vložený obsah bez ruční úpravy každého snímku. Tento komplexní průvodce vás provede procesem pomocí Aspose.Slides for Java, výkonné knihovny určené pro práci s prezentacemi v PowerPointu. Ať už jste ostřílený vývojář nebo teprve začínáte, tento návod vám pomůže a snadno se budete řídit.
## Předpoklady
Než se ponoříme do kódu, ujistěte se, že máte vše, co potřebujete, abyste mohli začít.
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Stáhněte si nejnovější verzi z[Stránka ke stažení Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Můžete použít jakékoli Java IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
4.  Aspose.Cells for Java: Toto je vyžadováno pro úpravu vložených dat v objektu OLE. Stáhněte si jej z[Stránka ke stažení Aspose.Cells](https://releases.aspose.com/cells/java/).
5.  Soubor prezentace: Připravte si soubor PowerPoint s vloženým objektem OLE. Pro tento tutoriál si to pojmenujme`ChangeOLEObjectData.pptx`.
## Importujte balíčky
Nejprve importujme potřebné balíčky do vašeho projektu Java.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Nyní si tento proces rozdělíme do jednoduchých, zvládnutelných kroků.
## Krok 1: Načtěte prezentaci PowerPoint
Chcete-li začít, musíte načíst prezentaci PowerPoint obsahující objekt OLE.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## Krok 2: Přístup ke snímku obsahujícímu objekt OLE
Dále získejte snímek, kde je vložený objekt OLE.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Najděte objekt OLE na snímku
Procházejte tvary na snímku a vyhledejte objekt OLE.
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
## Krok 4: Extrahujte vložená data z objektu OLE
Pokud je objekt OLE nalezen, extrahujte jeho vložená data.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## Krok 5: Upravte vložená data pomocí Aspose.Cells
Nyní použijte Aspose.Cells ke čtení a úpravě vložených dat, což je v tomto případě pravděpodobně sešit aplikace Excel.
```java
    Workbook wb = new Workbook(msln);
    // Upravte data sešitu
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## Krok 6: Uložte změněná data zpět do objektu OLE
Po provedení nezbytných změn uložte upravený sešit zpět do objektu OLE.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## Krok 7: Uložte aktualizovanou prezentaci
Nakonec uložte aktualizovanou prezentaci PowerPoint.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Závěr
Aktualizace objektových dat OLE v prezentacích PowerPoint pomocí Aspose.Slides for Java je jednoduchý proces, jakmile jej rozdělíte do jednoduchých kroků. Tato příručka vás provede načtením prezentace, přístupem a úpravou vložených dat OLE a uložením aktualizované prezentace. Pomocí těchto kroků můžete efektivně spravovat a programově aktualizovat vložený obsah na snímcích PowerPoint.
## FAQ
### Co je objekt OLE v PowerPointu?
Objekt OLE (Object Linking and Embedding) umožňuje vkládání obsahu z jiných aplikací, jako jsou tabulky aplikace Excel, do snímků aplikace PowerPoint.
### Mohu používat Aspose.Slides s jinými programovacími jazyky?
Ano, Aspose.Slides podporuje několik jazyků včetně .NET, Python a C++.
### Potřebuji Aspose.Cells k úpravě objektů OLE v PowerPointu?
Ano, pokud je objektem OLE tabulka Excel, budete k jeho úpravě potřebovat Aspose.Cells.
### Existuje zkušební verze Aspose.Slides?
 Ano, můžete získat a[zkušební verze zdarma](https://releases.aspose.com/) k testování funkcí Aspose.Slides.
### Kde najdu dokumentaci k Aspose.Slides?
 Podrobnou dokumentaci najdete na[Dokumentační stránka Aspose.Slides](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
