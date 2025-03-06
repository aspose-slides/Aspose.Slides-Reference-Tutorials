---
title: Alkalmazza a külső árnyékot a PowerPointban Java segítségével
linktitle: Alkalmazza a külső árnyékot a PowerPointban Java segítségével
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan alkalmazhat külső árnyékhatást a PowerPointban Java és Aspose.Slides használatával. Növelje prezentációit mélységgel és vizuális vonzerővel.
weight: 13
url: /hu/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
A tetszetős PowerPoint-prezentációk létrehozása gyakran magában foglalja az alakzatokhoz és a szöveghez különböző effektusok hozzáadását. Az egyik ilyen hatás a külső árnyék, amely kiemelheti az elemeket, és mélységet adhat a diáknak. Ebből az oktatóanyagból megtudhatja, hogyan lehet külső árnyékhatást alkalmazni egy alakzatra PowerPointban Java és Aspose.Slides használatával.
## Előfeltételek

Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

1. Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren. A JDK legújabb verzióját letöltheti és telepítheti az Oracle webhelyéről.

2.  Aspose.Slides for Java: Töltse le és telepítse az Aspose.Slides for Java alkalmazást a[letöltési oldal](https://releases.aspose.com/slides/java/).

3. Integrált fejlesztői környezet (IDE): Válassza ki a kívánt Java IDE-t, például az Eclipse-t, az IntelliJ IDEA-t vagy a NetBeans-t a Java alkalmazások kódolásához és futtatásához.

4. Alapvető Java ismeretek: A Java programozási nyelv alapjainak és az objektumorientált fogalmak ismerete hasznos lesz a kódpéldák megértéséhez.

## Csomagok importálása

Először is importálja a szükséges csomagokat az Aspose.Slides és a kapcsolódó funkciók használatához a Java projektben:

```java
import com.aspose.slides.*;
```

Most bontsuk fel a példakódot több lépésre, hogy a külső árnyékhatást alkalmazzuk egy alakzatra PowerPointban Java és Aspose.Slides használatával:

## 1. lépés: A projektkörnyezet beállítása

Hozzon létre egy új Java-projektet az előnyben részesített IDE-ben, és adja hozzá az Aspose.Slides for Java könyvtárat a projekt felépítési útvonalához.

## 2. lépés: Inicializálja a bemutató objektumot

 Hozzon létre egy példányt a`Presentation` osztály, amely egy PowerPoint bemutató fájlt képvisel.

```java
Presentation presentation = new Presentation();
```

## 3. lépés: Adjon hozzá egy diát és formát

Szerezzen hivatkozást arra a diára, amelyhez hozzá szeretné adni az alakzatot, majd adjon hozzá egy automatikus alakzatot (pl. téglalapot) a diához.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## 4. lépés: Az alak testreszabása

Állítsa az alakzat kitöltési típusát „NoFill” értékre, és adjon hozzá szöveget az alakzathoz.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## 5. lépés: A szöveg testreszabása

Hozzáférés az alakzat szövegtulajdonságaihoz, és testreszabhatja a betűméretet.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## 6. lépés: Engedélyezze a külső árnyék effektust

Engedélyezze a külső árnyékhatást a szövegrészhez.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## 7. lépés: Állítsa be az árnyék paramétereit

Határozza meg a külső árnyékhatás paramétereit, például az elmosódás sugarát, irányát, távolságát és árnyékszínét.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## 8. lépés: Mentse el a bemutatót

Mentse el a módosított bemutatót az alakzatra alkalmazott külső árnyékeffektussal.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Következtetés

Gratulálunk! Sikeresen alkalmazott külső árnyékhatást egy alakzatra a PowerPointban Java és Aspose.Slides használatával. Kísérletezzen különböző paraméterekkel, hogy elérje a kívánt vizuális effektusokat prezentációiban.

## GYIK

### Alkalmazhatom a külső árnyékhatást a téglalapokon kívül más alakzatokra is?
Igen, alkalmazhatja a külső árnyékhatást az Aspose.Slides által támogatott különféle alakzatokra, például körökre, háromszögekre és egyéni alakzatokra.

### Testreszabható az árnyék színe és intenzitása?
Teljesen! Az árnyékparaméterek teljes ellenőrzése alatt áll, beleértve a színt, az elmosódási sugarat, az irányt és a távolságot.

### Alkalmazhatok több effektust ugyanarra a formára?
Igen, több effektust is kombinálhat, például a külső árnyékot, a belső árnyékot, a ragyogást és a tükröződést, hogy fokozza a formák és a szövegek vizuális vonzerejét bemutatóiban.

### Az Aspose.Slides támogatja az effektusok alkalmazását a szöveges elemekre?
Igen, nem csak az alakzatokra, hanem az alakzatokon belüli egyes szövegrészekre is alkalmazhat effektusokat, így széleskörű rugalmasságot biztosít a diák megtervezésében.

### Hol találok további forrásokat és támogatást az Aspose.Slides számára?
 Hivatkozhat a[dokumentáció](https://reference.aspose.com/slides/java/) részletes API-referenciákért és fedezze fel a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) közösségi támogatásra és beszélgetésekre.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
