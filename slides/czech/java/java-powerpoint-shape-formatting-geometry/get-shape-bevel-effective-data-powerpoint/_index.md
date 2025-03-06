---
title: Získejte efektivní data Shape Bevel v PowerPointu
linktitle: Získejte efektivní data Shape Bevel v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak načíst efektivní data tvaru zkosení v PowerPointu pomocí Aspose.Slides pro Java. Vylepšete své prezentace úžasnými vizuálními efekty.
weight: 26
url: /cs/java/java-powerpoint-shape-formatting-geometry/get-shape-bevel-effective-data-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V moderních obchodních prezentacích hraje vizuální přitažlivost zásadní roli při efektivním předávání informací. Jedním z prvků, které mohou zlepšit vizuální dopad tvarů v prezentacích PowerPoint, je efekt zkosení. Aspose.Slides for Java poskytuje výkonné nástroje pro přístup a manipulaci s různými vlastnostmi tvarů, včetně jejich efektů zkosení. V tomto tutoriálu vás provedeme procesem načítání efektivních dat tvaru zkosení pomocí Aspose.Slides pro Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Základní znalost programovacího jazyka Java.
2. Nainstalovaný Java Development Kit (JDK) ve vašem systému.
3.  Stažen a nainstalován Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java:
```java
import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;

```
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři dokumentů, kde je umístěna prezentace PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Načtěte prezentaci
Načtěte prezentaci PowerPoint pomocí knihovny Aspose.Slides:
```java
Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
```
## Krok 3: Načtěte efektivní data zkosení
Získejte přístup k efektivním datům úkosu tvaru:
```java
IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();
```
## Krok 4: Vlastnosti úkosu tisku
Vytiskněte vlastnosti horního reliéfu obličeje efektivního tvaru:
```java
System.out.println("= Effective shape's top face relief properties =");
System.out.println("Type: " + threeDEffectiveData.getBevelTop().getBevelType());
System.out.println("Width: " + threeDEffectiveData.getBevelTop().getWidth());
System.out.println("Height: " + threeDEffectiveData.getBevelTop().getHeight());
```

## Závěr
V tomto tutoriálu jsme ukázali, jak načíst efektivní data zkosení tvaru v PowerPointu pomocí Aspose.Slides pro Java. Pomocí těchto kroků můžete snadno přistupovat k různým vlastnostem tvarů a manipulovat s nimi, abyste zvýšili vizuální přitažlivost svých prezentací.
## FAQ
### Mohu použít efekty zkosení na více tvarů současně?
Ano, můžete procházet tvary na snímku a podle potřeby aplikovat efekty zkosení.
### Podporuje Aspose.Slides jiné 3D efekty kromě zkosení?
Ano, Aspose.Slides poskytuje širokou škálu 3D efektů, které můžete použít na tvary v prezentacích PowerPoint.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Aspose.Slides zajišťuje kompatibilitu s různými verzemi PowerPointu a umožňuje bezproblémovou práci v různých prostředích.
### Mohu dále upravit vlastnosti efektu zkosení?
Absolutně máte plnou kontrolu nad vlastnostmi efektu zkosení a můžete je upravit podle svých požadavků.
### Kde najdu další zdroje a podporu pro Aspose.Slides?
 Můžete navštívit[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) pro jakékoli dotazy, podporu nebo další zdroje.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
