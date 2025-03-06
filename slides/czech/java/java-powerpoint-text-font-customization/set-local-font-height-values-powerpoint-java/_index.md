---
title: Nastavte místní hodnoty výšky písma v PowerPointu pomocí Java
linktitle: Nastavte místní hodnoty výšky písma v PowerPointu pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak upravit výšku písma v prezentacích PowerPoint pomocí Java s Aspose.Slides. Vylepšete formátování textu na svých snímcích bez námahy.
type: docs
weight: 17
url: /cs/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---
## Úvod
V tomto tutoriálu se naučíte manipulovat s výškami písma na různých úrovních v rámci prezentací PowerPoint pomocí Aspose.Slides for Java. Kontrola velikosti písma je zásadní pro vytváření vizuálně přitažlivých a strukturovaných prezentací. Projdeme si příklady krok za krokem, abychom ilustrovali, jak nastavit výšky písma pro různé textové prvky.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalovaný ve vašem systému
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/java/).
- Základní znalost programování v jazyce Java a prezentací v PowerPointu
## Importujte balíčky
Ujistěte se, že jste do svého souboru Java zahrnuli potřebné balíčky Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Inicializujte objekt prezentace
Nejprve vytvořte nový objekt prezentace PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 2: Přidejte tvar a textový rámeček
Přidejte na první snímek automatický tvar s textovým rámečkem:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Krok 3: Vytvořte části textu
Definujte části textu s různými výškami písma:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Krok 4: Nastavte výšky písma
Nastavte výšky písma na různých úrovních:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci do souboru:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Závěr
Tento výukový program demonstroval, jak upravit výšku písma v rámci snímků aplikace PowerPoint pomocí programu Aspose.Slides for Java. Manipulací s velikostmi písem na různých úrovních (v celé prezentaci, v odstavci a po části) můžete dosáhnout přesné kontroly nad formátováním textu v prezentacích.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonné API pro programovou manipulaci s prezentacemi v PowerPointu.
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
 Dokumentaci najdete[tady](https://reference.aspose.com/slides/java/).
### Mohu si Aspose.Slides for Java před nákupem vyzkoušet?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro Java?
 Pro podporu navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Kde si mohu zakoupit licenci pro Aspose.Slides for Java?
 Můžete si zakoupit licenci[tady](https://purchase.aspose.com/buy).