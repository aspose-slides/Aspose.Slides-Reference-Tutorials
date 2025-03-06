---
title: Aplikujte vnější stín v PowerPointu s Javou
linktitle: Aplikujte vnější stín v PowerPointu s Javou
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak aplikovat efekt vnějšího stínu v PowerPointu pomocí Java s Aspose.Slides. Vylepšete své prezentace hloubkou a vizuální přitažlivostí.
weight: 13
url: /cs/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aplikujte vnější stín v PowerPointu s Javou

## Úvod
Vytváření vizuálně atraktivních prezentací PowerPoint často zahrnuje přidávání různých efektů do tvarů a textu. Jedním z takových efektů je vnější stín, který může nechat prvky vyniknout a přidat hloubku snímkům. V tomto tutoriálu se naučíte, jak aplikovat efekt vnějšího stínu na tvar v PowerPointu pomocí Java s Aspose.Slides.
## Předpoklady

Než začnete s tímto výukovým programem, ujistěte se, že máte následující předpoklady:

1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovanou Javu. Nejnovější verzi JDK si můžete stáhnout a nainstalovat z webu Oracle.

2.  Aspose.Slides for Java: Stáhněte a nainstalujte Aspose.Slides for Java z[stránka ke stažení](https://releases.aspose.com/slides/java/).

3. Integrované vývojové prostředí (IDE): Vyberte si preferované Java IDE, jako je Eclipse, IntelliJ IDEA nebo NetBeans pro kódování a spouštění Java aplikací.

4. Základní znalosti jazyka Java: Pro pochopení příkladů kódu bude přínosem znalost základů programovacího jazyka Java a objektově orientovaných konceptů.

## Importujte balíčky

Nejprve importujte potřebné balíčky pro práci s Aspose.Slides a souvisejícími funkcemi ve vašem projektu Java:

```java
import com.aspose.slides.*;
```

Nyní si ukázkový kód rozdělíme do několika kroků, jak aplikovat efekt vnějšího stínu na tvar v PowerPointu pomocí Java s Aspose.Slides:

## Krok 1: Nastavte své projektové prostředí

Vytvořte nový projekt Java ve vašem preferovaném IDE a přidejte knihovnu Aspose.Slides for Java do cesty sestavení vašeho projektu.

## Krok 2: Inicializujte objekt prezentace

 Vytvořte instanci souboru`Presentation` třídy, která představuje soubor prezentace PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Krok 3: Přidejte snímek a tvar

Získejte odkaz na snímek, kam chcete přidat obrazec, a poté na snímek přidejte automatický tvar (např. obdélník).

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Krok 4: Přizpůsobte tvar

Nastavte typ výplně tvaru na „NoFill“ a přidejte do tvaru text.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Krok 5: Přizpůsobte text

Přístup k textovým vlastnostem tvaru a přizpůsobení velikosti písma.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Krok 6: Povolte efekt vnějšího stínu

Povolte efekt vnějšího stínu pro textovou část.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Krok 7: Nastavte parametry stínu

Definujte parametry pro efekt vnějšího stínu, jako je poloměr rozostření, směr, vzdálenost a barva stínu.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Krok 8: Uložte prezentaci

Uložte upravenou prezentaci s efektem vnějšího stínu aplikovaným na tvar.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Závěr

Gratulujeme! Úspěšně jste použili efekt vnějšího stínu na obrazec v PowerPointu pomocí Java s Aspose.Slides. Experimentujte s různými parametry, abyste dosáhli požadovaných vizuálních efektů ve svých prezentacích.

## FAQ

### Mohu použít efekt vnějšího stínu na jiné tvary kromě obdélníků?
Ano, efekt vnějšího stínu můžete použít na různé tvary podporované Aspose.Slides, jako jsou kruhy, trojúhelníky a vlastní tvary.

### Je možné přizpůsobit barvu a intenzitu stínu?
Absolutně! Máte plnou kontrolu nad parametry stínu, včetně barvy, poloměru rozostření, směru a vzdálenosti.

### Mohu použít více efektů na stejný tvar?
Ano, můžete kombinovat více efektů, jako je vnější stín, vnitřní stín, záře a odraz, abyste zvýšili vizuální přitažlivost tvarů a textu ve vašich prezentacích.

### Podporuje Aspose.Slides použití efektů na textové prvky?
Ano, efekty můžete aplikovat nejen na tvary, ale také na jednotlivé textové části v rámci obrazců, což vám poskytuje rozsáhlou flexibilitu při navrhování snímků.

### Kde najdu další zdroje a podporu pro Aspose.Slides?
 Můžete odkazovat na[dokumentace](https://reference.aspose.com/slides/java/) pro podrobné reference API a prozkoumejte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu komunity a diskuze.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
