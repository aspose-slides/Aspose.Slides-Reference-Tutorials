---
title: Propojte tvary pomocí Webů připojení v PowerPointu
linktitle: Propojte tvary pomocí Webů připojení v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se propojovat tvary v PowerPointu pomocí Aspose.Slides for Java. Automatizujte své prezentace bez námahy.
type: docs
weight: 19
url: /cs/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak propojit tvary pomocí spojovacích webů v PowerPointu pomocí Aspose.Slides pro Java. Tato výkonná knihovna nám umožňuje programově manipulovat s prezentacemi PowerPoint, takže úkoly jako spojování tvarů jsou bezproblémové a efektivní.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu. Můžete si jej stáhnout a nainstalovat z[webová stránka](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Stáhněte a nainstalujte Aspose.Slides for Java z[stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Vyberte IDE pro vývoj v Javě, jako je IntelliJ IDEA, Eclipse nebo NetBeans.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Krok 1: Přístup ke kolekci Shapes
Přístup ke kolekci tvarů pro vybraný snímek:
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Třída Instantiate Presentation, která představuje soubor PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Krok 2: Přidání tvaru konektoru
Přidejte tvar spojnice do kolekce tvarů snímku:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Krok 3: Přidání automatických tvarů
Přidejte automatické tvary, jako je elipsa a obdélník:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Krok 4: Připojení tvarů ke konektorům
Spojte tvary do konektoru:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 5: Nastavení indexu webu připojení
Nastavte požadovaný index webu připojení pro tvary:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Závěr
tomto tutoriálu jsme se naučili, jak spojovat tvary pomocí spojovacích webů v PowerPointu pomocí Aspose.Slides pro Java. S těmito znalostmi nyní můžete snadno automatizovat a přizpůsobovat své prezentace v PowerPointu.
## FAQ
### Lze Aspose.Slides for Java použít pro jiné manipulační úlohy v PowerPointu?
Ano, Aspose.Slides for Java poskytuje širokou škálu funkcí pro vytváření, úpravy a převod prezentací PowerPoint.
### Je Aspose.Slides for Java zdarma k použití?
 Aspose.Slides for Java je komerční knihovna, ale její funkce můžete prozkoumat pomocí bezplatné zkušební verze. Návštěva[tady](https://releases.aspose.com/) začít.
### Mohu získat podporu, pokud při používání Aspose.Slides for Java narazím na nějaké problémy?
 Ano, můžete získat podporu z komunitních fór Aspose[tady](https://forum.aspose.com/c/slides/11).
### Jsou k dispozici dočasné licence pro Aspose.Slides for Java?
 Ano, dočasné licence jsou k dispozici pro účely testování a hodnocení. Můžete získat jeden[tady](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit licenci pro Aspose.Slides for Java?
Licenci si můžete zakoupit na webu Aspose[tady](https://purchase.aspose.com/buy).