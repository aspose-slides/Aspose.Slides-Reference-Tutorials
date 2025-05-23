---
"description": "Naučte se, jak propojovat tvary pomocí spojnic v prezentacích v PowerPointu s Aspose.Slides pro Javu. Podrobný návod pro začátečníky."
"linktitle": "Propojení tvarů pomocí spojnic v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Propojení tvarů pomocí spojnic v PowerPointu"
"url": "/cs/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Propojení tvarů pomocí spojnic v PowerPointu

## Zavedení
V tomto tutoriálu se podíváme na to, jak propojit tvary pomocí spojnic v prezentacích v PowerPointu s pomocí Aspose.Slides pro Javu. Postupujte podle těchto podrobných pokynů, abyste efektivně propojili tvary a vytvořili vizuálně atraktivní snímky.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka Java.
- Nainstalovaná sada pro vývojáře Java (JDK) ve vašem systému.
- Stáhl jsem a nastavil Aspose.Slides pro Javu. Pokud jste ho ještě nenainstalovali, můžete si ho stáhnout z [zde](https://releases.aspose.com/slides/java/).
- Editor kódu, jako například Eclipse nebo IntelliJ IDEA.

## Importovat balíčky
Nejprve importujte potřebné balíčky pro práci s Aspose.Slides do vašeho projektu v Javě.
```java
import com.aspose.slides.*;

```
## Krok 1: Vytvoření instance třídy prezentací
Vytvořte instanci `Presentation` třída, která představuje soubor PPTX, se kterým pracujete.
```java
// Cesta k adresáři s dokumenty.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Krok 2: Přístup ke kolekci tvarů
Otevřete kolekci tvarů pro vybraný snímek, kam chcete přidat tvary a spojnice.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Krok 3: Přidání tvarů
Přidejte na snímek požadované tvary. V tomto příkladu přidáme elipsu a obdélník.
```java
// Přidat elipsu automatického tvaru
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Přidat automatický tvar obdélníku
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Krok 4: Přidání konektoru
Přidejte tvar spojnice do kolekce tvarů snímků.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Krok 5: Spojte tvary se spojnicemi
Spojte tvary se spojnicí.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 6: Přesměrování konektoru
Voláním metody reroute nastavíte automatickou nejkratší cestu mezi tvary.
```java
connector.reroute();
```
## Krok 7: Uložení prezentace
Po propojení tvarů pomocí spojnic prezentaci uložte.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Nakonec nezapomeňte zlikvidovat objekt Presentation.
```java
if (input != null) input.dispose();
```
Nyní jste úspěšně propojili tvary pomocí spojnic v PowerPointu s využitím Aspose.Slides pro Javu.

## Závěr
V tomto tutoriálu jsme se naučili, jak propojovat tvary pomocí spojnic v prezentacích v PowerPointu s Aspose.Slides pro Javu. Dodržováním těchto jednoduchých kroků můžete vylepšit své prezentace vizuálně poutavými diagramy a vývojovými diagramy.
## Často kladené otázky
### Mohu si přizpůsobit vzhled konektorů v Aspose.Slides pro Javu?
Ano, můžete si přizpůsobit různé vlastnosti spojnic, jako je barva, styl čáry a tloušťka, aby vyhovovaly vašim potřebám prezentace.
### Je Aspose.Slides pro Javu kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides pro Javu podporuje různé formáty PowerPointu, včetně PPTX, PPT a ODP.
### Mohu propojit více než dva tvary jednou spojnicí?
Ano, můžete propojit více tvarů pomocí komplexních konektorů, které poskytuje Aspose.Slides pro Javu.
### Nabízí Aspose.Slides pro Javu podporu pro přidávání textu do tvarů?
Rozhodně můžete snadno programově přidávat text k tvarům a spojnicím pomocí Aspose.Slides pro Javu.
### Existuje nějaké komunitní fórum nebo kanál podpory pro uživatele Aspose.Slides pro Javu?
Ano, na fóru Aspose.Slides můžete najít užitečné zdroje, klást otázky a komunikovat s ostatními uživateli. [zde](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}