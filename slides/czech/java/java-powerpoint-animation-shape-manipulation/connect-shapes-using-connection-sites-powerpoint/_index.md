---
"description": "Naučte se, jak propojovat tvary v PowerPointu pomocí Aspose.Slides pro Javu. Automatizujte své prezentace bez námahy."
"linktitle": "Propojení tvarů pomocí webů připojení v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Propojení tvarů pomocí webů připojení v PowerPointu"
"url": "/cs/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propojení tvarů pomocí webů připojení v PowerPointu

## Zavedení
V tomto tutoriálu se podíváme na to, jak propojit tvary pomocí spojovacích míst v PowerPointu s využitím knihovny Aspose.Slides pro Javu. Tato výkonná knihovna nám umožňuje programově manipulovat s prezentacemi v PowerPointu, což usnadňuje a zefektivňuje úkoly, jako je propojování tvarů.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Vývojářská sada pro Javu (JDK): Ujistěte se, že máte v systému nainstalovanou Javu. Můžete si ji stáhnout a nainstalovat z [webové stránky](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides pro Javu: Stáhněte a nainstalujte Aspose.Slides pro Javu z [stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si IDE pro vývoj v Javě, například IntelliJ IDEA, Eclipse nebo NetBeans.

## Importovat balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;

```
## Krok 1: Přístup ke kolekci tvarů
Přístup ke kolekci tvarů pro vybraný snímek:
```java
// Cesta k adresáři s dokumenty.                    
String dataDir = "Your Document Directory";
// Vytvořit instanci třídy Presentation, která reprezentuje soubor PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Krok 2: Přidání tvaru spojnice
Přidejte tvar spojnice do kolekce tvarů snímků:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Krok 3: Přidání automatických tvarů
Přidejte automatické tvary, jako je elipsa a obdélník:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Krok 4: Spojování tvarů se spojnicemi
Spojte tvary se spojnicí:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 5: Nastavení indexu připojovacího webu
Nastavte požadovaný index místa připojení pro tvary:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak propojit tvary pomocí spojovacích míst v PowerPointu s využitím Aspose.Slides pro Javu. S těmito znalostmi nyní můžete snadno automatizovat a přizpůsobovat své prezentace v PowerPointu.
## Často kladené otázky
### Lze Aspose.Slides pro Javu použít pro jiné úkoly manipulace s PowerPointem?
Ano, Aspose.Slides pro Javu nabízí širokou škálu funkcí pro vytváření, úpravy a konverzi prezentací v PowerPointu.
### Je Aspose.Slides pro Javu zdarma?
Aspose.Slides pro Javu je komerční knihovna, ale její funkce si můžete prohlédnout s bezplatnou zkušební verzí. Navštivte [zde](https://releases.aspose.com/) začít.
### Mohu získat podporu, pokud narazím na nějaké problémy při používání Aspose.Slides pro Javu?
Ano, podporu můžete získat na komunitních fórech Aspose. [zde](https://forum.aspose.com/c/slides/11).
### Jsou k dispozici dočasné licence pro Aspose.Slides pro Javu?
Ano, dočasné licence jsou k dispozici pro účely testování a hodnocení. Můžete si jednu pořídit. [zde](https://purchase.aspose.com/temporary-license/).
### Kde si mohu zakoupit licenci pro Aspose.Slides pro Javu?
Licenci si můžete zakoupit na webových stránkách Aspose [zde](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}