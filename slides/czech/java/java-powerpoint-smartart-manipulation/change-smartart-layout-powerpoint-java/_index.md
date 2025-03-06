---
title: Změňte rozvržení SmartArt v PowerPointu pomocí Java
linktitle: Změňte rozvržení SmartArt v PowerPointu pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se manipulovat s rozvrženími SmartArt v prezentacích PowerPoint pomocí Java s Aspose.Slides for Java.
weight: 19
url: /cs/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Změňte rozvržení SmartArt v PowerPointu pomocí Java

## Úvod
V tomto kurzu prozkoumáme, jak manipulovat s rozvržením SmartArt v prezentacích PowerPoint pomocí Javy. SmartArt je výkonná funkce v PowerPointu, která uživatelům umožňuje vytvářet vizuálně přitažlivou grafiku pro různé účely, jako je ilustrování procesů, hierarchií, vztahů a další.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte následující:
1. Java Development Environment: Ujistěte se, že máte v systému nainstalovanou sadu Java Development Kit (JDK).
2.  Knihovna Aspose.Slides: Stáhněte si a nainstalujte knihovnu Aspose.Slides for Java z[tady](https://releases.aspose.com/slides/java/).
3. Základní porozumění Javě: Užitečná bude znalost základů programovacího jazyka Java.
4. Integrované vývojové prostředí (IDE): Vyberte si IDE podle svých preferencí, jako je Eclipse nebo IntelliJ IDEA.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Krok 1: Nastavte své projektové prostředí Java
Ujistěte se, že váš projekt Java je správně nastaven ve zvoleném IDE. Vytvořte nový projekt Java a zahrňte knihovnu Aspose.Slides do závislostí svého projektu.
## Krok 2: Vytvořte novou prezentaci
Vytvořte instanci nového objektu prezentace a vytvořte novou prezentaci PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Přidejte grafiku SmartArt
Přidejte do prezentace obrázek SmartArt. Určete polohu a rozměry grafického prvku SmartArt na snímku.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Krok 4: Změňte rozvržení SmartArt
Změňte rozvržení grafického prvku SmartArt na požadovaný typ rozvržení.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci do určeného adresáře ve vašem systému.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Závěr
Manipulace s rozvržením SmartArt v prezentacích PowerPoint pomocí Javy je jednoduchý proces s Aspose.Slides pro Javu. Podle tohoto kurzu můžete snadno upravit grafiku SmartArt tak, aby vyhovovala vašim potřebám prezentace.
## FAQ
### Mohu upravit vzhled grafiky SmartArt pomocí Aspose.Slides for Java?
Ano, můžete přizpůsobit různé aspekty grafiky SmartArt, jako jsou barvy, styly a efekty.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Aspose.Slides podporuje PowerPointové prezentace vytvořené v různých verzích PowerPointu, což zajišťuje kompatibilitu napříč různými platformami.
### Nabízí Aspose.Slides podporu pro další programovací jazyky?
Ano, Aspose.Slides je k dispozici pro více programovacích jazyků, včetně .NET, Pythonu a JavaScriptu.
### Mohu vytvořit grafiku SmartArt od začátku pomocí Aspose.Slides?
Grafiku SmartArt můžete samozřejmě vytvářet programově nebo upravovat stávající tak, aby vyhovovaly vašim požadavkům.
### Existuje komunitní fórum, kde mohu vyhledat pomoc ohledně Aspose.Slides?
 Ano, můžete navštívit fórum Aspose.Slides[tady](https://forum.aspose.com/c/slides/11) klást otázky a zapojit se do komunity.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
