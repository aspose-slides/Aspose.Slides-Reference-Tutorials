---
"description": "Naučte se, jak manipulovat s rozvrženími SmartArt v prezentacích PowerPointu pomocí Javy s Aspose.Slides pro Javu."
"linktitle": "Změna rozvržení SmartArt v PowerPointu pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Změna rozvržení SmartArt v PowerPointu pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Změna rozvržení SmartArt v PowerPointu pomocí Javy

## Zavedení
V tomto tutoriálu se podíváme na to, jak manipulovat s rozvržením SmartArt v prezentacích PowerPointu pomocí Javy. SmartArt je výkonná funkce v PowerPointu, která uživatelům umožňuje vytvářet vizuálně přitažlivou grafiku pro různé účely, například pro ilustraci procesů, hierarchií, vztahů a dalších.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte následující:
1. Vývojové prostředí Java: Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK).
2. Knihovna Aspose.Slides: Stáhněte a nainstalujte knihovnu Aspose.Slides pro Javu z [zde](https://releases.aspose.com/slides/java/).
3. Základní znalost Javy: Znalost základů programovacího jazyka Java bude užitečná.
4. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE, například Eclipse nebo IntelliJ IDEA.

## Importovat balíčky
Pro začátek importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Krok 1: Nastavení prostředí projektu Java
Ujistěte se, že je váš projekt Java ve zvoleném IDE správně nastaven. Vytvořte nový projekt Java a do závislostí projektu přidejte knihovnu Aspose.Slides.
## Krok 2: Vytvořte novou prezentaci
Vytvořte instanci nového objektu Presentation pro vytvoření nové prezentace v PowerPointu.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Přidání obrázku SmartArt
Přidejte do prezentace obrázek SmartArt. Určete umístění a rozměry obrázku SmartArt na snímku.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Krok 4: Změna rozvržení prvku SmartArt
Změňte rozložení obrázku SmartArt na požadovaný typ rozložení.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Krok 5: Uložení prezentace
Uložte upravenou prezentaci do určeného adresáře ve vašem systému.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Závěr
Manipulace s rozvržením objektů SmartArt v prezentacích PowerPointu pomocí Javy je s Aspose.Slides pro Javu přímočarý proces. Pomocí tohoto tutoriálu můžete snadno upravovat grafiku SmartArt tak, aby vyhovovala potřebám vaší prezentace.
## Často kladené otázky
### Mohu si přizpůsobit vzhled obrázků SmartArt pomocí Aspose.Slides pro Javu?
Ano, můžete si přizpůsobit různé aspekty obrázků SmartArt, jako jsou barvy, styly a efekty.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Aspose.Slides podporuje prezentace v PowerPointu vytvořené v různých verzích PowerPointu, což zajišťuje kompatibilitu napříč různými platformami.
### Nabízí Aspose.Slides podporu pro jiné programovací jazyky?
Ano, Aspose.Slides je k dispozici pro více programovacích jazyků, včetně .NET, Pythonu a JavaScriptu.
### Mohu vytvářet grafiku SmartArt od nuly pomocí Aspose.Slides?
Grafiku SmartArt si samozřejmě můžete vytvářet programově nebo upravovat stávající grafiku tak, aby splňovala vaše požadavky.
### Existuje nějaké komunitní fórum, kde můžu vyhledat pomoc ohledně Aspose.Slides?
Ano, můžete navštívit fórum Aspose.Slides [zde](https://forum.aspose.com/c/slides/11) klást otázky a komunikovat s komunitou.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}