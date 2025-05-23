---
"description": "Zjistěte, jak přidávat uzly na konkrétní pozice ve SmartArt pomocí Javy s Aspose.Slides. Vytvářejte dynamické prezentace bez námahy."
"linktitle": "Přidání uzlů na určitou pozici v SmartArt pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání uzlů na určitou pozici v SmartArt pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání uzlů na určitou pozici v SmartArt pomocí Javy

## Zavedení
V tomto tutoriálu vás provedeme procesem přidávání uzlů na konkrétní pozice ve SmartArt pomocí Javy s Aspose.Slides. SmartArt je funkce v PowerPointu, která umožňuje vytvářet vizuálně přitažlivé diagramy a grafy.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
2. Knihovna Aspose.Slides pro Javu byla stažena. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).
3. Základní znalost programovacího jazyka Java.

## Importovat balíčky
Nejprve si importujme potřebné balíčky do našeho kódu v Javě:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Krok 1: Vytvoření instance prezentace
Začněte vytvořením instance třídy Presentation:
```java
Presentation pres = new Presentation();
```
## Krok 2: Otevření prezentačního snímku
Přejděte ke snímku, kam chcete přidat objekt SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Přidání tvaru SmartArt
Přidání tvaru SmartArt na snímek:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Krok 4: Přístup k uzlu SmartArt
Přístup k uzlu SmartArt na požadovaném indexu:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 5: Přidání podřízeného uzlu na konkrétní pozici
Přidejte nový podřízený uzel na určitou pozici v nadřazeném uzlu:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Krok 6: Přidání textu do uzlu
Nastavte text pro nově přidaný uzel:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Krok 7: Uložte prezentaci
Uložte upravenou prezentaci:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jste se naučili, jak přidávat uzly na konkrétní pozice v grafice SmartArt pomocí jazyka Java s Aspose.Slides. Pomocí těchto kroků můžete programově manipulovat s tvary grafiky SmartArt a vytvářet tak dynamické prezentace.
## Často kladené otázky
### Mohu přidat více uzlů najednou?
Ano, můžete programově přidat více uzlů iterací přes požadované pozice.
### Je Aspose.Slides kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides podporuje různé formáty PowerPointu, což zajišťuje kompatibilitu s většinou verzí.
### Mohu si přizpůsobit vzhled uzlů SmartArt?
Ano, vzhled uzlů, včetně jejich velikosti, barvy a stylu, si můžete přizpůsobit.
### Nabízí Aspose.Slides podporu pro jiné programovací jazyky?
Ano, Aspose.Slides poskytuje knihovny pro více programovacích jazyků, včetně .NET a Pythonu.
### Je k dispozici zkušební verze pro Aspose.Slides?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}