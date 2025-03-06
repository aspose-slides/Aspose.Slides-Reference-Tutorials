---
title: Odebrat segment z geometrického tvaru v PowerPointu
linktitle: Odebrat segment z geometrického tvaru v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak odstranit segmenty z geometrických tvarů v PowerPointu pomocí Aspose.Slides for Java, s naším podrobným průvodcem krok za krokem.
weight: 22
url: /cs/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
Chcete manipulovat s tvary v prezentacích PowerPoint pomocí Javy? Jste na správném místě! Aspose.Slides for Java je robustní API, které vám umožňuje snadno vytvářet, upravovat a spravovat snímky v prezentacích. V tomto kurzu vás provedeme procesem odebrání segmentu z geometrického tvaru v PowerPointu. Ať už jste zkušený vývojář nebo teprve začínáte, tento průvodce vám krok za krokem poskytne postup, jak tento úkol zvládnout. Jste připraveni se ponořit? Začněme!
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Stáhněte si knihovnu Aspose.Slides pro Java z[tady](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Pro psaní a spouštění kódu Java použijte IDE, jako je IntelliJ IDEA nebo Eclipse.
4. Základní znalost Javy: Základní znalost programování v Javě vám pomůže pokračovat v tomto tutoriálu.
## Importujte balíčky
Pro začátek musíme naimportovat potřebné balíčky z knihovny Aspose.Slides. Postup je následující:
```java
import com.aspose.slides.*;

```
Rozdělme proces odebrání segmentu z geometrického tvaru na snímku aplikace PowerPoint do několika kroků.
## Krok 1: Vytvořte novou prezentaci
Nejprve musíme vytvořit nový objekt prezentace. Tento objekt bude sloužit jako schránka pro naše diapozitivy a tvary.
```java
Presentation pres = new Presentation();
```
## Krok 2: Přidejte geometrický tvar do snímku
Dále přidejte na snímek tvar geometrie. Pro tento příklad použijeme tvar srdce.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## Krok 3: Načtěte geometrickou cestu tvaru
Jakmile je tvar přidán, musíme načíst jeho geometrickou cestu. Geometrická dráha obsahuje segmenty, které definují tvar.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## Krok 4: Odstraňte segment z geometrické cesty
Nyní odstraníme konkrétní segment z geometrické dráhy. V tomto příkladu odstraníme segment na indexu 2.
```java
path.removeAt(2);
```
## Krok 5: Nastavte novou geometrickou cestu
Po odstranění segmentu nastavte upravenou geometrickou cestu zpět na tvar.
```java
shape.setGeometryPath(path);
```
## Krok 6: Uložte prezentaci
Nakonec upravenou prezentaci uložte do souboru.
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Krok 7: Vyčistěte zdroje
Vždy zajistěte vyčištění prostředků, abyste zabránili úniku paměti.
```java
if (pres != null) pres.dispose();
```
## Závěr
tady to máte! S Aspose.Slides pro Java je manipulace s tvary v prezentacích PowerPoint přímočará a efektivní. Podle kroků uvedených v tomto kurzu můžete snadno odstranit segmenty z geometrických tvarů, což vám poskytne větší kontrolu nad návrhem a funkčností vašich snímků. Šťastné kódování!
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonné API pro vytváření, úpravy a správu prezentací v PowerPointu programově.
### Mohu použít Aspose.Slides pro Java s jinými tvary kromě tvaru srdce?
Absolutně! Aspose.Slides for Java podporuje širokou škálu tvarů, se kterými můžete manipulovat.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Potřebuji licenci k používání Aspose.Slides for Java?
 Ano, pro plnou funkčnost potřebujete licenci. Můžete si jeden zakoupit[tady](https://purchase.aspose.com/buy) nebo získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu další dokumentaci k Aspose.Slides for Java?
 K dispozici je obsáhlá dokumentace[tady](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
