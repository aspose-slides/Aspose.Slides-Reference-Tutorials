---
"description": "Naučte se, jak odstranit segmenty z geometrických tvarů v PowerPointu pomocí Aspose.Slides pro Javu s naším podrobným návodem krok za krokem."
"linktitle": "Odebrání segmentu z geometrického tvaru v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Odebrání segmentu z geometrického tvaru v PowerPointu"
"url": "/cs/java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Odebrání segmentu z geometrického tvaru v PowerPointu

## Zavedení
Hledáte způsoby, jak manipulovat s tvary ve svých prezentacích v PowerPointu pomocí Javy? Jste na správném místě! Aspose.Slides pro Javu je robustní API, které vám umožňuje bez námahy vytvářet, upravovat a spravovat snímky ve vašich prezentacích. V tomto tutoriálu vás provedeme procesem odebrání segmentu z geometrického tvaru v PowerPointu. Ať už jste zkušený vývojář, nebo teprve začínáte, tato příručka vám poskytne podrobný návod, jak tento úkol zvládnout. Jste připraveni se do toho pustit? Pojďme na to!
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Vývojářská sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK. Můžete si ji stáhnout z [Webové stránky společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides pro Javu: Stáhněte si knihovnu Aspose.Slides pro Javu z [zde](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Pro psaní a spouštění kódu Java použijte IDE, jako je IntelliJ IDEA nebo Eclipse.
4. Základní znalost Javy: Základní znalost programování v Javě vám pomůže s tímto tutoriálem.
## Importovat balíčky
Pro začátek musíme importovat potřebné balíčky z knihovny Aspose.Slides. Postupujte takto:
```java
import com.aspose.slides.*;

```
Pojďme si rozebrat proces odebrání segmentu z geometrického tvaru na snímku aplikace PowerPoint do několika kroků.
## Krok 1: Vytvořte novou prezentaci
Nejprve musíme vytvořit nový objekt prezentace. Tento objekt bude sloužit jako kontejner pro naše snímky a tvary.
```java
Presentation pres = new Presentation();
```
## Krok 2: Přidání geometrického tvaru na snímek
Dále přidejte na snímek geometrický tvar. V tomto příkladu použijeme tvar srdce.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);
```
## Krok 3: Načtení geometrické cesty tvaru
Jakmile je tvar přidán, musíme načíst jeho geometrickou cestu. Geometrická cesta obsahuje segmenty, které definují tvar.
```java
IGeometryPath path = shape.getGeometryPaths()[0];
```
## Krok 4: Odebrání segmentu z geometrické cesty
Nyní odstraníme konkrétní segment z geometrické cesty. V tomto příkladu odstraníme segment na indexu 2.
```java
path.removeAt(2);
```
## Krok 5: Nastavení nové geometrické cesty
Po odstranění segmentu vraťte upravenou geometrickou cestu zpět do tvaru.
```java
shape.setGeometryPath(path);
```
## Krok 6: Uložte prezentaci
Nakonec upravenou prezentaci uložte do souboru.
```java
String resultPath = "Your Output Directory" + "GeometryShapeRemoveSegment.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
## Krok 7: Vyčištění zdrojů
Vždy se ujistěte, že jste vyčistili zdroje, abyste zabránili úniku paměti.
```java
if (pres != null) pres.dispose();
```
## Závěr
A tady to máte! S Aspose.Slides pro Javu je manipulace s tvary ve vašich prezentacích v PowerPointu jednoduchá a efektivní. Dodržováním kroků popsaných v tomto tutoriálu můžete snadno odebrat segmenty z geometrických tvarů, což vám poskytne větší kontrolu nad designem a funkčností vašich slajdů. Šťastné programování!
## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je výkonné API pro programovou tvorbu, úpravu a správu prezentací v PowerPointu.
### Mohu použít Aspose.Slides pro Javu s jinými tvary než tvarem srdce?
Rozhodně! Aspose.Slides pro Javu podporuje širokou škálu tvarů, se kterými můžete manipulovat.
### Je k dispozici bezplatná zkušební verze Aspose.Slides pro Javu?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).
### Potřebuji licenci k používání Aspose.Slides pro Javu?
Ano, pro plnou funkčnost potřebujete licenci. Můžete si ji zakoupit. [zde](https://purchase.aspose.com/buy) nebo si pořídit dočasný řidičský průkaz [zde](https://purchase.aspose.com/temporary-license/).
### Kde najdu další dokumentaci k Aspose.Slides pro Javu?
K dispozici je komplexní dokumentace [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}