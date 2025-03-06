---
title: Klonovat tvary v PowerPointu
linktitle: Klonovat tvary v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se klonovat tvary v prezentacích PowerPoint pomocí Aspose.Slides for Java. Zjednodušte svůj pracovní postup pomocí tohoto snadno sledovatelného výukového programu.
weight: 16
url: /cs/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Klonovat tvary v PowerPointu

## Úvod
V tomto tutoriálu prozkoumáme, jak klonovat tvary v prezentacích PowerPoint pomocí Aspose.Slides for Java. Klonování tvarů umožňuje duplikovat existující tvary v rámci prezentace, což může být užitečné zejména pro vytváření konzistentních rozvržení nebo opakování prvků na snímcích.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit. Nejnovější verzi si můžete stáhnout a nainstalovat z[webová stránka](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Knihovna Aspose.Slides for Java: Stáhněte si a zahrňte knihovnu Aspose.Slides for Java do svého projektu Java. Odkaz ke stažení najdete[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Chcete-li začít, budete muset importovat potřebné balíčky do svého projektu Java. Tyto balíčky poskytují funkce potřebné pro práci s prezentacemi PowerPoint pomocí Aspose.Slides for Java.
```java
import com.aspose.slides.*;

```
## Krok 1: Načtěte prezentaci
 Nejprve musíte načíst prezentaci PowerPoint obsahující tvary, které chcete klonovat. Použijte`Presentation` třídy k načtení zdrojové prezentace.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Krok 2: Klonujte tvary
Dále naklonujete tvary ze zdrojové prezentace a přidáte je na nový snímek ve stejné prezentaci. To zahrnuje přístup ke zdrojovým obrazcům, vytvoření nového snímku a následné přidání klonovaných obrazců do nového snímku.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Krok 3: Uložte prezentaci
Nakonec upravenou prezentaci s klonovanými tvary uložte do nového souboru.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Závěr
Klonování tvarů v prezentacích PowerPoint pomocí Aspose.Slides for Java je přímočarý proces, který vám může pomoci zjednodušit pracovní postup vytváření prezentací. Podle kroků uvedených v tomto kurzu můžete snadno duplikovat existující tvary a přizpůsobit je podle potřeby.

## FAQ
### Mohu klonovat tvary na různých snímcích?
Ano, můžete klonovat tvary z libovolného snímku v prezentaci a přidat je na jiný snímek pomocí Aspose.Slides for Java.
### Existují nějaká omezení pro klonování tvarů?
Zatímco Aspose.Slides for Java poskytuje robustní možnosti klonování, složité tvary nebo animace nemusí být dokonale replikovány.
### Mohu upravit klonované tvary po jejich přidání na snímek?
Rozhodně, jakmile jsou tvary naklonovány a přidány na snímek, můžete podle potřeby upravit jejich vlastnosti, styly a obsah.
### Podporuje Aspose.Slides for Java klonování dalších prvků kromě tvarů?
Ano, pomocí Aspose.Slides for Java můžete klonovat snímky, text, obrázky a další prvky v rámci prezentace PowerPoint.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides for Java z webu[webová stránka](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
