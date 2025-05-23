---
"description": "Ismerje meg, hogyan engedélyezheti az Írásvédett Ajánlott tulajdonságokat Java PowerPoint prezentációkban az Aspose.Slides for Java használatával. Kövesse lépésről lépésre szóló útmutatónkat forráskódpéldákkal a prezentációk fokozott biztonsága érdekében."
"linktitle": "Csak olvasható ajánlott tulajdonságok Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Csak olvasható ajánlott tulajdonságok Java diákban"
"url": "/hu/java/presentation-properties/read-only-recommended-properties-in-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Csak olvasható ajánlott tulajdonságok Java diákban


## Bevezetés a csak olvasható ajánlott tulajdonságok engedélyezésébe Java diákban

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan engedélyezhetők a „Csak olvasható” ajánlott tulajdonságok PowerPoint-bemutatókhoz az Aspose.Slides for Java használatával. A „Csak olvasható” ajánlott tulajdonságok hasznosak lehetnek, ha arra szeretné ösztönözni a felhasználókat, hogy a bemutatót változtatások nélkül tekintsék meg. Ezek a tulajdonságok azt javasolják, hogy a prezentációt írásvédett módban kell megnyitni. Lépésről lépésre útmutatót és Java forráskódot biztosítunk ennek eléréséhez.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár be van állítva a projektedben. Letöltheted innen: [Aspose.Slides Java-hoz weboldal](https://products.aspose.com/slides/java/).

## 1. lépés: Új PowerPoint-bemutató létrehozása

Először egy új PowerPoint prezentációt fogunk létrehozni az Aspose.Slides for Java segítségével. Ha már van prezentációd, kihagyhatod ezt a lépést.

```java
String outPptxPath = "Your Output Directory" + "ReadOnlyRecommended.pptx";
Presentation pres = new Presentation();
```

A fenti kódban definiáltuk a kimeneti PowerPoint fájl elérési útját, és létrehoztunk egy új prezentációs objektumot.

## 2. lépés: Csak olvasható ajánlott tulajdonság engedélyezése

Most engedélyezzük a Csak olvasható ajánlott tulajdonságot a prezentációhoz.

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

Ebben a kódrészletben a következőt használjuk: `getProtectionManager().setReadOnlyRecommended(true)` metódus a Csak olvasható ajánlott tulajdonság értékre állításához `true`Ez biztosítja, hogy amikor valaki megnyitja a prezentációt, a rendszer kérni fogja, hogy írásvédett módban nyissa meg.

## 3. lépés: Mentse el a prezentációt

Végül a prezentációt engedélyezve a Csak olvasható ajánlott tulajdonsággal mentjük el.

## Teljes forráskód a Java Slides csak olvasható ajánlott tulajdonságaihoz

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

Ebben az oktatóanyagban megtanultad, hogyan engedélyezheted a Csak olvasható ajánlott tulajdonságot egy PowerPoint-bemutatóhoz az Aspose.Slides for Java használatával. Ez a funkció akkor lehet hasznos, ha korlátozni szeretnéd a szerkesztést, és arra szeretnéd ösztönözni a nézőket, hogy csak olvasható módban használják a bemutatót. A biztonságot tovább fokozhatod, ha jelszót állítasz be a bemutatóhoz.

## GYIK

### Hogyan tilthatom le az Írásvédett ajánlott tulajdonságot?

A Csak olvasható ajánlott tulajdonság letiltásához egyszerűen használja a következő kódot:

```java
pres.getProtectionManager().setReadOnlyRecommended(false);
```

### Beállíthatok jelszót egy írásvédett, ajánlott prezentációhoz?

Igen, beállíthatsz jelszót egy írásvédett, ajánlott prezentációhoz az Aspose.Slides for Java használatával. Használhatod a `setPassword` módszer a prezentáció jelszavának beállítására. Ha be van állítva jelszó, a felhasználóknak meg kell adniuk azt a prezentáció megnyitásához, még írásvédett módban is.

```java
pres.getProtectionManager().setPassword("YourPassword");
```

Ne felejtsd el kicserélni `"YourPassword"` a kívánt jelszóval.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}