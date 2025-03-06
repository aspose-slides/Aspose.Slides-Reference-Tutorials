---
title: Změňte styl tvaru SmartArt v PowerPointu pomocí Java
linktitle: Změňte styl tvaru SmartArt v PowerPointu pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak změnit styly SmartArt v prezentacích PowerPoint pomocí Javy s Aspose.Slides pro Javu. Vylepšete své prezentace.
type: docs
weight: 23
url: /cs/java/java-powerpoint-smartart-manipulation/change-smartart-shape-style-powerpoint-java/
---
## Úvod
Ve světě vývoje v Javě je vytváření výkonných prezentací často požadavkem. Prezentace v PowerPointu jsou běžným médiem, ať už jde o obchodní prezentace, vzdělávací účely nebo pouhé sdílení informací. Někdy však výchozí styly a formáty poskytované PowerPointem nemusí plně vyhovovat našim potřebám. Zde vstupuje do hry Aspose.Slides for Java.
Aspose.Slides for Java je robustní knihovna, která vývojářům v jazyce Java umožňuje programově pracovat s prezentacemi v PowerPointu. Poskytuje širokou škálu funkcí, včetně možnosti manipulovat s tvary, styly, animacemi a mnoha dalšími. V tomto tutoriálu se zaměříme na jeden konkrétní úkol: změna stylu tvaru SmartArt v prezentacích PowerPoint pomocí Javy.
## Předpoklady
Než se pustíte do výukového programu, musíte mít splněno několik předpokladů:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK. Nejnovější verzi si můžete stáhnout a nainstalovat z webu Oracle.
2. Knihovna Aspose.Slides for Java: Budete si muset stáhnout a zahrnout knihovnu Aspose.Slides for Java do svého projektu. Odkaz ke stažení najdete[tady](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE pro vývoj v Javě. Populární jsou IntelliJ IDEA, Eclipse nebo NetBeans.

## Importujte balíčky
Než začneme kódovat, naimportujme potřebné balíčky do našeho Java projektu. Tyto balíčky nám umožní bezproblémovou práci s funkcemi Aspose.Slides.
```java
import com.aspose.slides.*;
```
## Krok 1: Načtěte prezentaci
Nejprve musíme načíst prezentaci PowerPoint, kterou chceme upravit.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "AccessSmartArtShape.pptx");
```
## Krok 2: Procházejte tvary
Dále projdeme každý tvar v prvním snímku prezentace.
```java
for (IShape shape : presentation.getSlides().get_Item(0).getShapes())
```
## Krok 3: Zkontrolujte typ SmartArt
U každého tvaru zkontrolujeme, zda se jedná o tvar SmartArt.
```java
if (shape instanceof ISmartArt)
```
## Krok 4: Odeslání do SmartArt
 Pokud je tvarem SmartArt, přeneseme jej do`ISmartArt` rozhraní.
```java
ISmartArt smart = (ISmartArt) shape;
```
## Krok 5: Zkontrolujte a změňte styl
Poté zkontrolujeme aktuální styl SmartArt a v případě potřeby jej změníme.
```java
if (smart.getQuickStyle() == SmartArtQuickStyleType.SimpleFill)
{
    smart.setQuickStyle(SmartArtQuickStyleType.Cartoon);
}
```
## Krok 6: Uložte prezentaci
Nakonec upravenou prezentaci uložíme do nového souboru.
```java
presentation.save(dataDir + "ChangeSmartArtStyle_out.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak změnit styl tvaru SmartArt v prezentacích PowerPoint pomocí Java a knihovny Aspose.Slides for Java. Podle podrobného průvodce můžete snadno přizpůsobit vzhled tvarů SmartArt tak, aby lépe vyhovoval vašim potřebám prezentace.
## FAQ
### Mohu používat Aspose.Slides pro Javu s jinými Java knihovnami?
Ano, Aspose.Slides for Java lze bez problémů integrovat s jinými knihovnami Java, aby se zvýšila funkčnost vašich aplikací.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete využít bezplatnou zkušební verzi Aspose.Slides for Java od[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro Java?
 Podporu pro Aspose.Slides pro Java můžete získat na adrese[Fórum](https://forum.aspose.com/c/slides/11).
### Mohu si zakoupit dočasnou licenci pro Aspose.Slides for Java?
 Ano, můžete si zakoupit dočasnou licenci pro Aspose.Slides for Java od[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro Javu?
 Můžete najít podrobnou dokumentaci k Aspose.Slides pro Javu[tady](https://reference.aspose.com/slides/java/).