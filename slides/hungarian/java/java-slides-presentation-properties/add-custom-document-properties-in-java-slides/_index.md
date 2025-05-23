---
"description": "Ismerd meg, hogyan teheted teljessé a PowerPoint-bemutatóidat egyéni dokumentumtulajdonságokkal a Java Slides-ban. Lépésről lépésre útmutató kódpéldákkal az Aspose.Slides for Java használatával."
"linktitle": "Egyéni dokumentumtulajdonságok hozzáadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Egyéni dokumentumtulajdonságok hozzáadása Java diákban"
"url": "/hu/java/presentation-properties/add-custom-document-properties-in-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni dokumentumtulajdonságok hozzáadása Java diákban


## Bevezetés az egyéni dokumentumtulajdonságok hozzáadásához Java Slides-ben

Ebben az oktatóanyagban végigvezetünk azon, hogyan adhatsz egyéni dokumentumtulajdonságokat egy PowerPoint-bemutatóhoz az Aspose.Slides for Java használatával. Az egyéni dokumentumtulajdonságok lehetővé teszik, hogy további információkat tárolj a bemutatóról referenciaként vagy kategorizálás céljából.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben.

## 1. lépés: Szükséges csomagok importálása

```java
import com.aspose.slides.*;
```

## 2. lépés: Új prezentáció létrehozása

Először létre kell hoznod egy új prezentációs objektumot. Ezt a következőképpen teheted meg:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Hozz létre egy Presentation osztályt
Presentation presentation = new Presentation();
```

## 3. lépés: Dokumentumtulajdonságok lekérése

Ezután lekérheti a prezentáció dokumentumtulajdonságait. Ezek a tulajdonságok beépített tulajdonságokat tartalmaznak, például a címet, a szerzőt és az egyéni tulajdonságokat, amelyeket hozzáadhat.

```java
// Dokumentumtulajdonságok lekérése
IDocumentProperties documentProperties = presentation.getDocumentProperties();
```

## 4. lépés: Egyéni tulajdonságok hozzáadása

Most adjunk hozzá egyéni tulajdonságokat a prezentációhoz. Az egyéni tulajdonságok egy névből és egy értékből állnak. Bármilyen információ tárolására használhatjuk őket.

```java
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
```

## 5. lépés: Tulajdonságnév lekérése egy adott indexben

Egy adott indexben található egyéni tulajdonság nevét is lekérheti. Ez akkor lehet hasznos, ha adott tulajdonságokkal kell dolgoznia.

```java
// Tulajdonságnév lekérése egy adott indexben
String getPropertyName = documentProperties.getCustomPropertyName(2);
```

## 6. lépés: Kijelölt tulajdonság eltávolítása

Ha el szeretne távolítani egy egyéni tulajdonságot, ezt megteheti a nevének megadásával. Itt az 5. lépésben megszerzett tulajdonságot távolítjuk el.

```java
// Kijelölt tulajdonság eltávolítása
documentProperties.removeCustomProperty(getPropertyName);
```

## 7. lépés: A prezentáció mentése

Végül mentse el a prezentációt a hozzáadott és eltávolított egyéni tulajdonságokkal egy fájlba.

```java
// Prezentáció mentése
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az Egyéni dokumentumtulajdonságok hozzáadásához Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy Presentation osztályt
Presentation presentation = new Presentation();
// Dokumentumtulajdonságok lekérése
IDocumentProperties documentProperties = presentation.getDocumentProperties();
// Egyéni tulajdonságok hozzáadása
documentProperties.set_Item("New Custom", 12);
documentProperties.set_Item("My Name", "Mudassir");
documentProperties.set_Item("Custom", 124);
// Tulajdonságnév lekérése adott indexben
String getPropertyName = documentProperties.getCustomPropertyName(2);
// Kijelölt tulajdonság eltávolítása
documentProperties.removeCustomProperty(getPropertyName);
// Prezentáció mentése
presentation.save(dataDir + "CustomDocumentProperties_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Megtanultad, hogyan adhatsz hozzá egyéni dokumentumtulajdonságokat egy PowerPoint-bemutatóhoz Java nyelven az Aspose.Slides használatával. Az egyéni tulajdonságok értékesek lehetnek a bemutatóiddal kapcsolatos további információk tárolására. Ezt a tudást kiterjesztheted további egyéni tulajdonságokkal, szükség szerint az adott felhasználási esetedben.

## GYIK

### Hogyan kérhetem le egy egyéni tulajdonság értékét?

Egyéni tulajdonság értékének lekéréséhez használhatja a `get_Item` módszer a `documentProperties` tárgy. Például:

```java
Object customPropertyValue = documentProperties.get_Item("New Custom");
```

### Hozzáadhatok különböző adattípusok egyéni tulajdonságait?

Igen, hozzáadhatsz egyéni tulajdonságokat különféle adattípusokhoz, beleértve a számokat, karakterláncokat, dátumokat és egyebeket, ahogy a példában is látható. Az Aspose.Slides Java-ban zökkenőmentesen kezeli a különböző adattípusokat.

### Van-e korlátozás a hozzáadható egyéni tulajdonságok számára?

Nincs szigorú korlátozás a hozzáadható egyéni tulajdonságok számára vonatkozóan. Ne feledje azonban, hogy a túlzott számú tulajdonság hozzáadása befolyásolhatja a prezentációs fájl teljesítményét és méretét.

### Hogyan listázhatom ki egy prezentáció összes egyéni tulajdonságát?

Az összes egyéni tulajdonságon végighaladva listázhatja őket. Íme egy példa erre:

```java
for (int i = 0; i < documentProperties.getCustomCount(); i++) {
    String propertyName = documentProperties.getCustomPropertyName(i);
    Object propertyValue = documentProperties.get_Item(propertyName);
    System.out.println("Property Name: " + propertyName);
    System.out.println("Property Value: " + propertyValue);
}
```

Ez a kód megjeleníti a prezentációban található összes egyéni tulajdonság nevét és értékét.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}