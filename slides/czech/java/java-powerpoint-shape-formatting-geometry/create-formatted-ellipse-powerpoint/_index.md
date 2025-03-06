---
title: Vytvořte formátovanou elipsu v PowerPointu
linktitle: Vytvořte formátovanou elipsu v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vytvořit formátovanou elipsu v PowerPointu pomocí Aspose.Slides for Java, s naším podrobným průvodcem krok za krokem.
weight: 17
url: /cs/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte formátovanou elipsu v PowerPointu

## Úvod
Vítejte v tomto komplexním tutoriálu o vytváření formátované elipsy v PowerPointu pomocí Aspose.Slides pro Java. Aspose.Slides je výkonná knihovna, která umožňuje vývojářům programově manipulovat se soubory PowerPoint. Ať už automatizujete generování snímků nebo vylepšujete prezentace pomocí vlastních tvarů, tento průvodce vás provede každým krokem a zajistí, že na snímky můžete snadno přidat dokonale naformátovanou elipsu. Pojďme se ponořit a uvidíme, jak toho můžeme dosáhnout!
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte nainstalovaný JDK 1.6 nebo vyšší.
2.  Aspose.Slides pro Javu: Stáhněte si nejnovější verzi z[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte IDE jako IntelliJ IDEA nebo Eclipse.
4. Základní znalost Javy: Vyžaduje se znalost programování v Javě.
## Importujte balíčky
Chcete-li začít používat Aspose.Slides, musíte importovat potřebné balíčky. Můžete to udělat takto:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Nastavte adresář projektu
Nejprve potřebujete adresář pro ukládání souborů PowerPoint.
### Vytvořit adresář
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Ujistěte se, že vyměníte`"Your Document Directory"` se skutečnou cestou, kam chcete soubory uložit.
## Krok 2: Inicializujte prezentaci
Nyní vytvořte instanci třídy Presentation, která představuje soubor PowerPoint.
```java
// Třída okamžité prezentace, která představuje PPTX
Presentation pres = new Presentation();
```
## Krok 3: Získejte první snímek
Dále získejte první snímek z prezentace, kam přidáte elipsu.
```java
// Získejte první snímek
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Přidejte tvar elipsy
Přidejte na snímek automatický tvar typu elipsa.
```java
// Přidejte automatický tvar typu elipsy
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Tady,`50, 150, 150, 50` jsou souřadnice a velikost elipsy (x pozice, y pozice, šířka, výška).
## Krok 5: Použijte formátování na elipsu
Nyní aplikujte na elipsu nějaké formátování. Nastavíme plnou barvu výplně a barvu čáry.
### Nastavte barvu výplně
```java
// Použijte určité formátování na tvar elipsy
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Nastavte barvu a šířku čáry
```java
// Použijte určité formátování na linii Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Krok 6: Uložte prezentaci
Nakonec prezentaci uložte do určeného adresáře.
```java
// Zapište soubor PPTX na disk
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Krok 7: Zlikvidujte předmět prezentace
Zlikvidujte objekt prezentace, abyste uvolnili zdroje.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Závěr
Gratulujeme! Úspěšně jste vytvořili formátovanou elipsu v prezentaci PowerPoint pomocí Aspose.Slides for Java. Tento výukový program vás provede nastavením projektu, přidáním elipsy, použitím formátování a uložením prezentace. Díky těmto dovednostem můžete nyní své PowerPointové snímky programově vylepšit, díky čemuž budou vaše prezentace dynamičtější a vizuálně přitažlivější.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům programově vytvářet, upravovat a spravovat prezentace PowerPoint.
### Mohu použít Aspose.Slides pro Javu s jakýmkoli IDE?
Ano, Aspose.Slides pro Javu můžete použít s jakýmkoli Java IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
### Potřebuji licenci pro Aspose.Slides?
Ano, Aspose.Slides je komerční produkt a pro plnou funkčnost potřebujete licenci. Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu další dokumentaci k Aspose.Slides for Java?
 Podrobnou dokumentaci najdete na Aspose.Slides for Java[dokumentační stránku](https://reference.aspose.com/slides/java/).
### Je k dispozici podpora pro Aspose.Slides?
 Ano, Aspose nabízí podporu prostřednictvím jejich[Fórum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
