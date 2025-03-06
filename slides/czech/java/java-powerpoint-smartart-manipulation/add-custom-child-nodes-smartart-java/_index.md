---
title: Přidejte vlastní podřízené uzly do SmartArt pomocí Java
linktitle: Přidejte vlastní podřízené uzly do SmartArt pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat vlastní podřízené uzly do SmartArt v prezentacích PowerPoint pomocí Java s Aspose.Slides. Vylepšete své snímky profesionální grafikou bez námahy.
weight: 11
url: /cs/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
SmartArt je výkonná funkce v PowerPointu, která uživatelům umožňuje rychle a snadno vytvářet profesionálně vypadající grafiku. V tomto tutoriálu se naučíme, jak přidat vlastní podřízené uzly do SmartArt pomocí Java s Aspose.Slides.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
2.  Aspose.Slides for Java: Stáhněte si a nainstalujte Aspose.Slides for Java z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Načtěte prezentaci
Načtěte prezentaci PowerPoint, do které chcete přidat vlastní podřízené uzly k obrázku SmartArt:
```java
String dataDir = "Your Document Directory";
// Načtěte požadovanou prezentaci
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Krok 2: Přidejte SmartArt do snímku
Nyní přidejte SmartArt na snímek:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Krok 3: Přesuňte tvar SmartArt
Přesuňte obrazec SmartArt na novou pozici:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Krok 4: Změňte šířku tvaru
Změna šířky tvaru SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Krok 5: Změňte výšku tvaru
Změňte výšku tvaru SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Krok 6: Otočte tvar
Otočte tvar SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Krok 7: Uložte prezentaci
Nakonec upravenou prezentaci uložte:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak přidat vlastní podřízené uzly do SmartArt pomocí Java s Aspose.Slides. Pomocí těchto kroků můžete své prezentace vylepšit vlastní grafikou, aby byly poutavější a profesionálnější.
## FAQ
### Mohu přidat různé typy rozvržení SmartArt pomocí Aspose.Slides for Java?
Ano, Aspose.Slides for Java podporuje různá rozvržení SmartArt, což vám umožňuje vybrat si to, které nejlépe vyhovuje vašim potřebám prezentace.
### Je Aspose.Slides for Java kompatibilní s různými verzemi PowerPointu?
Aspose.Slides for Java je navržena tak, aby bezproblémově fungovala s různými verzemi PowerPointu a zajistila kompatibilitu a konzistenci napříč platformami.
### Mohu upravit vzhled obrazců SmartArt programově?
Absolutně! Pomocí Aspose.Slides for Java můžete programově upravit vzhled, velikost, barvu a rozvržení tvarů SmartArt tak, aby vyhovovaly vašim návrhovým preferencím.
### Poskytuje Aspose.Slides for Java dokumentaci a podporu?
Ano, na webu Aspose můžete najít komplexní dokumentaci a přístup k fórům podpory komunity.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, z webu si můžete stáhnout bezplatnou zkušební verzi Aspose.Slides for Java a prozkoumat jeho funkce a možnosti před nákupem[tady](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
