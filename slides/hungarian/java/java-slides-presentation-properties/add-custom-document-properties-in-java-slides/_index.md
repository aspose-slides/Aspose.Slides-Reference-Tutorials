---
title: Adjon hozzá egyéni dokumentumtulajdonságokat a Java Slides-hez
linktitle: Adjon hozzá egyéni dokumentumtulajdonságokat a Java Slides-hez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan javíthatja a PowerPoint prezentációkat egyéni dokumentumtulajdonságokkal a Java Slides alkalmazásban. Lépésről lépésre, kódpéldákkal az Aspose.Slides for Java használatával.
weight: 13
url: /hu/java/presentation-properties/add-custom-document-properties-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adjon hozzá egyéni dokumentumtulajdonságokat a Java Slides-hez


## Bevezetés az egyéni dokumentumtulajdonságok hozzáadásához a Java Slides-ben

Ebben az oktatóanyagban végigvezetjük az Aspose.Slides for Java segítségével egyéni dokumentumtulajdonságok PowerPoint-prezentációhoz adásának folyamatán. Az egyéni dokumentum tulajdonságai lehetővé teszik, hogy további információkat tároljon a prezentációról referencia vagy kategorizálás céljából.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben.

## 1. lépés: Importálja a szükséges csomagokat

```java
import com.aspose.slides.*;
```

## 2. lépés: Hozzon létre egy új prezentációt

Először is létre kell hoznia egy új prezentációs objektumot. Ezt a következőképpen teheti meg:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Példányosítsa a Prezentáció osztályt
Presentation presentation = new Presentation();
```

## 3. lépés: A dokumentum tulajdonságainak lekérése

Ezután lekérheti a prezentáció dokumentumtulajdonságait. Ezek a tulajdonságok olyan beépített tulajdonságokat tartalmaznak, mint a cím, szerző és egyéni tulajdonságok, amelyeket hozzáadhat.

```java
// Dokumentumtulajdonságok lekérése
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## 4. lépés: Egyéni tulajdonságok hozzáadása

Most adjunk egyéni tulajdonságokat a prezentációhoz. Az egyéni tulajdonságok egy névből és egy értékből állnak. Használhatja őket bármilyen kívánt információ tárolására.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## 5. lépés: Ingatlannév beszerzése egy adott indexen

Egy egyedi tulajdonság nevét is lekérheti egy adott indexnél. Ez akkor lehet hasznos, ha meghatározott tulajdonságokkal kell dolgoznia.

```java
// Tulajdonnév lekérése egy adott indexnél
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## 6. lépés: A kiválasztott tulajdonság eltávolítása

Ha el szeretne távolítani egy egyéni tulajdonságot, ezt a nevének megadásával teheti meg. Itt eltávolítjuk az 5. lépésben megszerzett tulajdont.

```java
// A kiválasztott tulajdonság eltávolítása
documentProperties.removeCustomProperty(getPropertyName);
```

## 7. lépés: A prezentáció mentése

Végül mentse a prezentációt a hozzáadott és eltávolított egyéni tulajdonságokkal egy fájlba.

```java
// Prezentáció mentése
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az egyéni dokumentumtulajdonságok hozzáadásához a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítsa a Prezentáció osztályt
Presentation presentation = new Presentation();
// Dokumentumtulajdonságok lekérése
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Egyéni tulajdonságok hozzáadása
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Tulajdonnév beszerzése egy adott indexnél
String getPropertyName = documentProperties.getCustomPropertyName(2);
// A kiválasztott tulajdonság eltávolítása
documentProperties.removeCustomProperty(getPropertyName);
// Prezentáció mentése
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Megtanulta, hogyan adhat egyéni dokumentumtulajdonságokat egy PowerPoint prezentációhoz Java nyelven az Aspose.Slides segítségével. Az egyéni tulajdonságok értékesek lehetnek a prezentációkkal kapcsolatos további információk tárolására. Ezt a tudást kibővítheti további egyéni tulajdonságokkal, ha az adott használati esethez szükséges.

## GYIK

### Hogyan kérhetem le az egyéni tulajdonság értékét?

 Egy egyéni tulajdonság értékének lekéréséhez használhatja a`get_Item` módszer a`documentProperties` tárgy. Például:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Hozzáadhatok különböző adattípusok egyéni tulajdonságait?

Igen, a példában látható módon hozzáadhat különféle adattípusok egyéni tulajdonságait, beleértve a számokat, karakterláncokat, dátumokat és egyebeket. Az Aspose.Slides for Java zökkenőmentesen kezeli a különböző adattípusokat.

### Korlátozott a hozzáadható egyéni tulajdonságok száma?

hozzáadható egyéni tulajdonságok számának nincs szigorú korlátozása. Ne feledje azonban, hogy túl sok tulajdonság hozzáadása hatással lehet a bemutatófájl teljesítményére és méretére.

### Hogyan sorolhatom fel az összes egyéni tulajdonságot egy prezentációban?

Az összes egyéni tulajdonságot végignézve felsorolhatja őket. Íme egy példa, hogyan kell ezt megtenni:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Ez a kód megjeleníti a prezentáció összes egyéni tulajdonságának nevét és értékét.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
