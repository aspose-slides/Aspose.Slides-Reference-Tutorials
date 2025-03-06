---
title: Csak olvasható, ajánlott tulajdonságok a Java Slides-ben
linktitle: Csak olvasható, ajánlott tulajdonságok a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan engedélyezheti a Java PowerPoint prezentációkban az Írásvédett tulajdonságokat az Aspose.Slides for Java segítségével. Kövesse lépésenkénti útmutatónkat a forráskód példáival a fokozott prezentációbiztonság érdekében.
weight: 17
url: /hu/java/presentation-properties/read-only-recommended-properties-in-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a Java Slides írásvédett tulajdonságainak engedélyezésébe

Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet engedélyezni az Írásvédett ajánlott tulajdonságokat PowerPoint-prezentációkhoz az Aspose.Slides for Java használatával. Az Írásvédett ajánlott tulajdonságok hasznosak lehetnek, ha arra szeretné ösztönözni a felhasználókat, hogy változtatások nélkül tekintsenek meg egy prezentációt. Ezek a tulajdonságok azt sugallják, hogy a prezentációt csak olvasható módban kell megnyitni. Ennek eléréséhez lépésről lépésre útmutatót adunk a Java forráskóddal együtt.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy a projektben be van állítva az Aspose.Slides for Java könyvtár. Letöltheti a[Aspose.Slides for Java webhely](https://products.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy új PowerPoint-bemutatót

Kezdjük egy új PowerPoint prezentáció létrehozásával az Aspose.Slides for Java használatával. Ha már van prezentációja, kihagyhatja ezt a lépést.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

A fenti kódban meghatároztuk a kimeneti PowerPoint-fájl elérési útját, és létrehoztunk egy új prezentációs objektumot.

## 2. lépés: Engedélyezze az Írásvédett ajánlott tulajdonságot

Most engedélyezzük a Csak olvasható tulajdonságot a prezentációhoz.

```java
try
{
    pres.getProtectionManager().setReadOnlyRecommended(true);
    pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

 Ebben a kódrészletben a`getProtectionManager().setReadOnlyRecommended(true)` metódussal állítsa be a Read-Recommended tulajdonságot`true`. Ez biztosítja, hogy amikor valaki megnyitja a prezentációt, a rendszer felkéri, hogy csak olvasható módban nyissa meg.

## 3. lépés: Mentse el a prezentációt

Végül a prezentációt úgy mentjük el, hogy engedélyezve van a Read-Only Recommended tulajdonság.

## Teljes forráskód a Java Slides csak olvasható, ajánlott tulajdonságaihoz

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
try
{
	pres.getProtectionManager().setReadOnlyRecommended(true);
	pres.save(outPptxPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan engedélyezheti a Csak olvasható tulajdonságot egy PowerPoint-prezentációhoz az Aspose.Slides for Java használatával. Ez a funkció akkor lehet hasznos, ha korlátozni szeretné a szerkesztést, és arra ösztönzi a nézőket, hogy a prezentációt csak olvasható módban használják. Tovább fokozhatja a biztonságot, ha jelszót állít be az előadáshoz.

## GYIK

### Hogyan tilthatom le a Csak olvasható tulajdonságot?

A Csak olvasható tulajdonság letiltásához egyszerűen használja a következő kódot:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Beállíthatok jelszót egy írásvédett, ajánlott prezentációhoz?

Igen, az Aspose.Slides for Java segítségével beállíthat jelszót a csak olvasható, ajánlott prezentációkhoz. Használhatja a`setPassword` módszer a prezentáció jelszavának beállítására. Ha be van állítva jelszó, a felhasználóknak meg kell adniuk azt a prezentáció megnyitásához, még csak olvasható módban is.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

 Ne felejtse el cserélni`"YourPassword"` a kívánt jelszóval.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
