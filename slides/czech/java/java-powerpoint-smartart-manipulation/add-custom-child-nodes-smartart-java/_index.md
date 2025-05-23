---
"description": "Naučte se, jak přidávat vlastní podřízené uzly do objektů SmartArt v prezentacích PowerPointu pomocí Javy s Aspose.Slides. Vylepšete své snímky profesionální grafikou bez námahy."
"linktitle": "Přidání vlastních podřízených uzlů do prvku SmartArt pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání vlastních podřízených uzlů do prvku SmartArt pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání vlastních podřízených uzlů do prvku SmartArt pomocí Javy

## Zavedení
SmartArt je výkonná funkce v PowerPointu, která uživatelům umožňuje rychle a snadno vytvářet profesionálně vypadající grafiku. V tomto tutoriálu se naučíme, jak přidávat vlastní podřízené uzly do SmartArt pomocí Javy s Aspose.Slides.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Vývojová sada pro Javu (JDK): Ujistěte se, že máte v systému nainstalovanou Javu.
2. Aspose.Slides pro Javu: Stáhněte a nainstalujte Aspose.Slides pro Javu z [zde](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Pro začátek importujte potřebné balíčky do vašeho projektu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Načtení prezentace
Načtěte prezentaci PowerPointu, kam chcete přidat vlastní podřízené uzly do prvku SmartArt:
```java
String dataDir = "Your Document Directory";
// Načtěte požadovanou prezentaci
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Krok 2: Přidání prvku SmartArt do snímku
Nyní přidejme na snímek SmartArt:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Krok 3: Přesunutí tvaru SmartArt
Přesunutí tvaru SmartArt na nové místo:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Krok 4: Změna šířky tvaru
Změna šířky tvaru SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Krok 5: Změna výšky tvaru
Změna výšky tvaru SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Krok 6: Otočte tvar
Otočení tvaru SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Krok 7: Uložte prezentaci
Nakonec uložte upravenou prezentaci:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Závěr
tomto tutoriálu jsme se naučili, jak přidávat vlastní podřízené uzly do SmartArt pomocí Javy s Aspose.Slides. Dodržováním těchto kroků můžete vylepšit své prezentace o vlastní grafiku, díky čemuž budou poutavější a profesionálnější.
## Často kladené otázky
### Mohu přidat různé typy rozvržení SmartArt pomocí Aspose.Slides pro Javu?
Ano, Aspose.Slides pro Javu podporuje různá rozvržení SmartArt, což vám umožňuje vybrat si to, které nejlépe vyhovuje vašim potřebám při prezentaci.
### Je Aspose.Slides pro Javu kompatibilní s různými verzemi PowerPointu?
Aspose.Slides pro Javu je navržen tak, aby bezproblémově fungoval s různými verzemi PowerPointu, a zajistil tak kompatibilitu a konzistenci napříč platformami.
### Mohu programově přizpůsobit vzhled tvarů SmartArt?
Rozhodně! S Aspose.Slides pro Javu si můžete programově přizpůsobit vzhled, velikost, barvu a rozvržení tvarů SmartArt tak, aby vyhovovaly vašim designovým preferencím.
### Poskytuje Aspose.Slides pro Javu dokumentaci a podporu?
Ano, na webových stránkách Aspose najdete komplexní dokumentaci a přístup k fórům podpory komunity.
### Je k dispozici zkušební verze Aspose.Slides pro Javu?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides pro Javu z webových stránek, abyste si před nákupem prohlédli její funkce a možnosti. [zde](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}