---
title: Spojte tvary pomocí konektorů v PowerPointu
linktitle: Spojte tvary pomocí konektorů v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se propojovat tvary pomocí konektorů v prezentacích PowerPoint s Aspose.Slides pro Java. Návod krok za krokem pro začátečníky.
weight: 18
url: /cs/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu prozkoumáme, jak spojovat tvary pomocí konektorů v prezentacích PowerPoint s pomocí Aspose.Slides for Java. Postupujte podle těchto podrobných pokynů, abyste efektivně spojili tvary a vytvořili vizuálně přitažlivé snímky.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka Java.
- Nainstalovaný Java Development Kit (JDK) ve vašem systému.
-  Staženo a nastaveno Aspose.Slides pro Javu. Pokud jste jej ještě nenainstalovali, můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Editor kódu, jako je Eclipse nebo IntelliJ IDEA.

## Importujte balíčky
Nejprve importujte potřebné balíčky pro práci s Aspose.Slides ve vašem projektu Java.
```java
import com.aspose.slides.*;

```
## Krok 1: Okamžitá prezentace
 Vytvořte instanci`Presentation`class, která představuje soubor PPTX, na kterém pracujete.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Krok 2: Přístup ke kolekci Shapes
Otevřete kolekci tvarů pro vybraný snímek, kam chcete přidat tvary a spojnice.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Krok 3: Přidejte tvary
Přidejte na snímek požadované tvary. V tomto příkladu přidáme elipsu a obdélník.
```java
// Přidejte automatický tvar Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Přidejte obdélník automatického tvaru
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Krok 4: Přidejte konektor
Přidejte tvar spojnice do kolekce obrazců snímku.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Krok 5: Připojte tvary ke konektorům
Připojte tvary ke konektoru.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 6: Přesměrujte konektor
Přesměrování hovoru pro nastavení automatické nejkratší cesty mezi tvary.
```java
connector.reroute();
```
## Krok 7: Uložte prezentaci
Po připojení tvarů pomocí spojek prezentaci uložte.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Nakonec nezapomeňte objekt prezentace zlikvidovat.
```java
if (input != null) input.dispose();
```
Nyní jste úspěšně propojili tvary pomocí konektorů v PowerPointu pomocí Aspose.Slides pro Java.

## Závěr
tomto tutoriálu jsme se naučili, jak spojovat tvary pomocí konektorů v prezentacích PowerPoint s Aspose.Slides pro Java. Pomocí těchto jednoduchých kroků můžete své prezentace vylepšit vizuálně přitažlivými diagramy a vývojovými diagramy.
## FAQ
### Mohu upravit vzhled konektorů v Aspose.Slides for Java?
Ano, můžete přizpůsobit různé vlastnosti konektorů, jako je barva, styl čáry a tloušťka, aby vyhovovaly vašim potřebám prezentace.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides for Java podporuje různé formáty PowerPoint, včetně PPTX, PPT a ODP.
### Mohu připojit více než dva tvary jedním konektorem?
Ano, můžete propojit více tvarů pomocí složitých konektorů poskytovaných Aspose.Slides pro Java.
### Nabízí Aspose.Slides for Java podporu pro přidávání textu do tvarů?
Rozhodně můžete snadno přidávat text do tvarů a konektorů programově pomocí Aspose.Slides pro Java.
### Je k dispozici komunitní fórum nebo kanál podpory pro Aspose.Slides pro uživatele Java?
 Ano, na fóru Aspose.Slides můžete najít užitečné zdroje, klást otázky a komunikovat s ostatními uživateli[tady](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
