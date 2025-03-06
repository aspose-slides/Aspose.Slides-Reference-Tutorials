---
title: Přidejte uzly na konkrétní pozici v prvku SmartArt pomocí Javy
linktitle: Přidejte uzly na konkrétní pozici v prvku SmartArt pomocí Javy
second_title: Aspose.Slides Java PowerPoint Processing API
description: Zjistěte, jak přidávat uzly na konkrétní pozice v prvku SmartArt pomocí Java s Aspose.Slides. Vytvářejte dynamické prezentace bez námahy.
weight: 16
url: /cs/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu vás provedeme procesem přidávání uzlů na konkrétní pozice v SmartArt pomocí Java s Aspose.Slides. SmartArt je funkce v PowerPointu, která umožňuje vytvářet vizuálně přitažlivé diagramy a grafy.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Stažena knihovna Aspose.Slides pro Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
3. Základní znalost programovacího jazyka Java.

## Importujte balíčky
Nejprve importujme potřebné balíčky do našeho kódu Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Krok 1: Vytvořte instanci prezentace
Začněte vytvořením instance třídy Presentation:
```java
Presentation pres = new Presentation();
```
## Krok 2: Otevřete Prezentační snímek
Otevřete snímek, kam chcete přidat SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Přidejte tvar SmartArt
Přidejte na snímek obrazec SmartArt:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Krok 4: Přístup k SmartArt Node
Přístup k uzlu SmartArt na požadovaném indexu:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 5: Přidejte podřízený uzel na konkrétní pozici
Přidejte nový podřízený uzel na konkrétní pozici v nadřazeném uzlu:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Krok 6: Přidejte text do uzlu
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
V tomto tutoriálu jste se naučili přidávat uzly na konkrétních pozicích v obrázku SmartArt pomocí Java s Aspose.Slides. Pomocí těchto kroků můžete programově manipulovat s obrazci SmartArt a vytvářet dynamické prezentace.
## FAQ
### Mohu přidat více uzlů najednou?
Ano, můžete přidat více uzlů programově iterací přes požadované pozice.
### Je Aspose.Slides kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides podporuje různé formáty PowerPoint, což zajišťuje kompatibilitu s většinou verzí.
### Mohu přizpůsobit vzhled uzlů SmartArt?
Ano, můžete upravit vzhled uzlů, včetně jejich velikosti, barvy a stylu.
### Nabízí Aspose.Slides podporu pro další programovací jazyky?
Ano, Aspose.Slides poskytuje knihovny pro více programovacích jazyků, včetně .NET a Pythonu.
### Je k dispozici zkušební verze pro Aspose.Slides?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
