---
"date": "2025-04-18"
"description": "Ismerd meg, hogyan teheted még jobbá prezentációidat a SmartArt felsorolásjelek képekkel való testreszabásával az Aspose.Slides for Java segítségével. Kövesd ezt a lépésről lépésre szóló útmutatót a professzionális megjelenésért."
"title": "Hogyan testreszabhatjuk a SmartArt felsorolásjeleket képekkel az Aspose.Slides for Java használatával | Lépésről lépésre útmutató"
"url": "/hu/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan testreszabhatjuk a SmartArt felsorolásjeleket képekkel az Aspose.Slides for Java használatával

## Bevezetés

A vizuálisan vonzó prezentációk készítése kulcsfontosságú a közönség figyelmének felkeltéséhez és az üzenet hatékony közvetítéséhez. A diák tervezésének egyik gyakori kihívása a SmartArt grafikák felsorolásjeleinek kiemelése egyéni képek használatával. Ez az oktatóanyag végigvezeti Önt azon, hogyan állíthat be egy képet felsorolásjel-kitöltési formátumként a SmartArt csomópontokban az Aspose.Slides for Java segítségével, lehetővé téve prezentációi professzionális szintűvé tételét.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása és használata Java-ban
- Felsoroláspontok testreszabása képekkel SmartArt-grafikákban
- A testreszabás gyakorlati alkalmazásai
- Gyakori problémák elhárítása

Mielőtt belevágnánk a megvalósításba, győződjünk meg róla, hogy minden elő van készítve.

## Előfeltételek

A bemutató követéséhez győződjön meg arról, hogy megfelel a következő előfeltételeknek:

1. **Könyvtárak és függőségek**Szükséged lesz az Aspose.Slides Java könyvtár 25.4-es vagy újabb verziójára.
2. **Környezet beállítása**:
   - Kompatibilis IDE, például IntelliJ IDEA vagy Eclipse
   - JDK 16 telepítve a gépeden
3. **Előfeltételek a tudáshoz**Jártasság a Java programozásban és az alapvető PowerPoint prezentációk felépítésében.

## Az Aspose.Slides beállítása Java-hoz

Kezdésként az Aspose.Slides könyvtárat az alábbi módszerek egyikével kell beilleszteni a projektbe:

### Szakértő

Adja hozzá ezt a függőséget a `pom.xml` fájl:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Vedd bele ezt a `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés

Vagy töltse le közvetlenül a könyvtárat innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

**Licencbeszerzés lépései**Az Aspose ingyenes próbalicencet kínál, amely tökéletes a funkciók teszteléséhez. Ideiglenes licencet kérhet, vagy vásárolhat egyet az értékelési korlátozások feloldásához.

A környezet inicializálásához és beállításához hozzon létre egy példányt a következőből: `Presentation` osztály, ahogy az látható:

```java
Presentation presentation = new Presentation();
```

## Megvalósítási útmutató

Ez a szakasz kezelhető lépésekre bontja a folyamatot, és elmagyarázza, hogyan érhető el a kívánt funkció.

### SmartArt hozzáadása egyéni felsorolásjel kitöltéssel

#### Áttekintés

Először egy SmartArt alakzatot adunk a diához, és testreszabjuk a felsorolásjeleit egy képkitöltéssel.

#### Lépésről lépésre útmutató

**1. Prezentációs objektum inicializálása**

```java
Presentation presentation = new Presentation();
```

*Cél*: Inicializál egy új bemutatópéldányt, ahová a SmartArt grafikákat fel fogja venni.

**2. SmartArt alakzat hozzáadása**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Magyarázat*: Ez a sor egy új SmartArt alakzatot ad hozzá az első diához az (x=10, y=10) pozícióban, 500x400 képpont méretben. A `VerticalPictureList` Az elrendezést függőleges igazításhoz használják.

**3. Felsorolásjeles kitöltés elérése és testreszabása**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Cél*: Ellenőrzi, hogy a csomópont rendelkezik-e `BulletFillFormat` tulajdonság. Ha igen, akkor betölt egy képet, és beállítja azt a felsorolásjelek kitöltéseként.
*Paraméterek*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: A képfájl elérési útja.
  - `PictureFillMode.Stretch`: Biztosítja, hogy a kép teljesen kitöltse a felsorolásjeles területet.

**4. Mentse el a prezentációját**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}