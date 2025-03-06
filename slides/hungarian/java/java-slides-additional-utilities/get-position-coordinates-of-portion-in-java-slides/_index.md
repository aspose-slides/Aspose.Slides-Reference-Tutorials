---
title: Szerezze meg a rész pozíciókoordinátáit a Java Slides-ben
linktitle: Szerezze meg a rész pozíciókoordinátáit a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg a szövegrész koordinátáinak lekérését Java diákban az Aspose.Slides for Java API segítségével. Pontosan szabályozhatja a szöveg elhelyezését a PowerPoint-prezentációkban.
weight: 12
url: /hu/java/additional-utilities/get-position-coordinates-of-portion-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés a rész pozíciókoordinátáinak lekéréséhez Java Slides-ben

Ebben az átfogó útmutatóban megvizsgáljuk, hogyan lehet lekérni a Java diákon belüli rész pozíciókoordinátáit az Aspose.Slides for Java API használatával. Megtanulja, hogyan érheti el és kezelheti a szövegrészeket egy diában, és hogyan bonthatja ki azok X és Y koordinátáit. Ez a lépésenkénti oktatóanyag forráskód-példákat és értékes információkat tartalmaz, amelyek segítenek elsajátítani ezt a feladatot.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java Development Kit (JDK) telepítve
- Aspose.Slides for Java könyvtár letöltve és konfigurálva
- Az Ön által választott Java Integrated Development Environment (IDE).

Most pedig kezdjük a megvalósítással.

## 1. lépés: A projekt beállítása

Mielőtt az Aspose.Slides for Java-val dolgozhatnánk, be kell állítanunk egy Java projektet, és konfigurálnunk kell a könyvtárat. Kövesse az alábbi lépéseket a projekt elkészítéséhez:

1. Hozzon létre egy új Java-projektet az IDE-ben.
2. Adja hozzá az Aspose.Slides for Java könyvtárat projektje függőségeihez.
3. Importálja a szükséges Aspose.Slides osztályokat a Java fájl elejére.

```java
import com.aspose.slides.*;
import java.awt.geom.Point2D;
```

## 2. lépés: A prezentáció betöltése

 Ebben a lépésben betöltjük azt a PowerPoint prezentációt, amely azt a diát tartalmazza, amellyel dolgozni szeretnénk. Cserélje ki`"Your Document Directory"` a PowerPoint-fájl tényleges elérési útjával.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
```

## 3. lépés: Szövegrészek és koordináták elérése

Most elérjük a dián belüli szövegrészeket, és lekérjük azok X és Y koordinátáit. Ennek elérése érdekében a bekezdéseken és részeken keresztül ismételgetjük. Íme a kódrészlet:

```java
try
{
    IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
    ITextFrame textFrame = shape.getTextFrame();
    for (IParagraph paragraph : textFrame.getParagraphs())
    {
        for (IPortion portion : paragraph.getPortions())
        {
            Point2D.Float point = portion.getCoordinates();
            System.out.println("Coordinates X =" + point.getX() + " Coordinates Y =" + point.getY());
        }
    }
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

Ez a kód lekéri az X és Y koordinátákat a megadott dián lévő minden egyes szövegrészhez. Módosíthatja saját igényei szerint.

## Teljes forráskód a rész pozíciókoordinátáinak lekéréséhez a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "Shapes.pptx");
try
{
	IAutoShape shape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
	ITextFrame textFrame = shape.getTextFrame();
	for (IParagraph paragraph : textFrame.getParagraphs())
	{
		for (IPortion portion : paragraph.getPortions())
		{
			Point2D.Float point = portion.getCoordinates();
			System.out.println("Corrdinates X =" + point.getX() + " Corrdinates Y =" + point.getY());
		}
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan szerezheti meg a Java diákon belüli szövegrészek pozíciókoordinátáit az Aspose.Slides for Java API használatával. Ez a tudás különösen akkor lehet hasznos, ha pontos szabályozásra van szüksége a szöveges elemek elhelyezése felett a PowerPoint-prezentációkban.

## GYIK

### Hogyan tölthetem le az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java letölthető a webhelyről a következő hivatkozás segítségével:[Az Aspose.Slides letöltése Java-hoz](https://releases.aspose.com/slides/java/)

### Hol találom az Aspose.Slides for Java dokumentációját?

 Az Aspose.Slides for Java dokumentációja a következő címen érhető el:[Aspose.Slides a Java dokumentációhoz](https://reference.aspose.com/slides/java/)

### Használhatom az Aspose.Slides for Java programot kereskedelmi projektjeimben?

Igen, az Aspose.Slides for Java használható kereskedelmi projektekben. Azonban feltétlenül tekintse át az Aspose által biztosított licencfeltételeket.

### Az Aspose.Slides for Java kompatibilis a különböző PowerPoint fájlformátumokkal?

Igen, az Aspose.Slides for Java különféle PowerPoint fájlformátumokat támogat, beleértve a PPTX, PPT és egyebeket.

### Hogyan kaphatok további támogatást vagy segítséget az Aspose.Slides for Java-hoz?

További támogatást és forrásokat érhet el az Aspose webhelyén. Fórumokat, dokumentációt és prémium támogatási lehetőségeket biztosítanak a felhasználók számára.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
