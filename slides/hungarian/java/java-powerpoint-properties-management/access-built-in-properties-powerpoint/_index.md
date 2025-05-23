---
"description": "Ismerje meg, hogyan érheti el a PowerPoint beépített tulajdonságait az Aspose.Slides for Java használatával. Ez az oktatóanyag végigvezeti Önt a szerző, a létrehozási dátum és egyebek lekérésén."
"linktitle": "Beépített tulajdonságok elérése a PowerPointban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Beépített tulajdonságok elérése a PowerPointban"
"url": "/hu/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Beépített tulajdonságok elérése a PowerPointban

## Bevezetés
Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan férhetünk hozzá a PowerPoint-bemutatók beépített tulajdonságaihoz az Aspose.Slides for Java segítségével. Az Aspose.Slides egy hatékony függvénytár, amely lehetővé teszi a Java-fejlesztők számára, hogy programozottan dolgozzanak PowerPoint-bemutatókkal, lehetővé téve az olyan feladatok zökkenőmentes olvasását és módosítását, mint a tulajdonságok módosítása.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:
1. Java fejlesztőkészlet (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszerén. Letöltheti innen: [itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides Java-hoz: Töltse le és telepítse az Aspose.Slides Java-hoz programot innen: [ez a link](https://releases.aspose.com/slides/java/).

## Csomagok importálása
Először importálnod kell a szükséges csomagokat a Java projektedbe. Add hozzá a következő import utasítást a Java fájlod elejéhez:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## 1. lépés: A prezentációs objektum beállítása
Kezd azzal, hogy beállítod a Presentation objektumot, hogy az a PowerPoint-bemutatót képviselje, amellyel dolgozni szeretnél. Így teheted meg:
```java
// prezentációs fájlt tartalmazó könyvtár elérési útja
String dataDir = "path_to_your_presentation_directory/";
// Hozz létre egy Presentation osztályt
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## 2. lépés: A dokumentum tulajdonságainak elérése
A Presentation objektum beállítása után az IDocumentProperties felület segítségével érheti el a prezentáció beépített tulajdonságait. A következőképpen kérheti le a különböző tulajdonságokat:
### Kategória
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Jelenlegi állapot
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Létrehozás dátuma
```java
System.out.println("Creation Date : " + documentProperties.getCreatedTime());
```
### Szerző
```java
System.out.println("Author : " + documentProperties.getAuthor());
```
### Leírás
```java
System.out.println("Description : " + documentProperties.getComments());
```
### Kulcsszavak
```java
System.out.println("KeyWords : " + documentProperties.getKeywords());
```
### Utolsó módosítás:
```java
System.out.println("Last Modified By : " + documentProperties.getLastSavedBy());
```
### Felügyelő
```java
System.out.println("Supervisor : " + documentProperties.getManager());
```
### Módosított dátum
```java
System.out.println("Modified Date : " + documentProperties.getLastSavedTime());
```
#### Prezentációs formátum
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Utolsó nyomtatás dátuma
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Megosztva a producerek között
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Téma
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Cím
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan érhetjük el a PowerPoint-bemutatók beépített tulajdonságait az Aspose.Slides for Java használatával. A fent vázolt lépéseket követve könnyedén lekérhetünk programozottan különféle tulajdonságokat, például a szerzőt, a létrehozási dátumot és a címet.
## GYIK
### Módosíthatom ezeket a beépített tulajdonságokat az Aspose.Slides for Java használatával?
Igen, módosíthatod ezeket a tulajdonságokat az Aspose.Slides segítségével. Egyszerűen használd a megfelelő setter metódusokat, amelyeket az IDocumentProperties felület biztosít.
### Kompatibilis az Aspose.Slides a PowerPoint különböző verzióival?
Az Aspose.Slides a PowerPoint verziók széles skáláját támogatja, biztosítva a kompatibilitást a különböző platformok között.
### Lekérhetek egyéni tulajdonságokat is?
Igen, a beépített tulajdonságok mellett egyéni tulajdonságokat is lekérhetsz és módosíthatsz az Aspose.Slides for Java segítségével.
### Az Aspose.Slides kínál dokumentációt és támogatást?
Igen, átfogó dokumentációt találhat, és hozzáférhet a támogatási fórumokhoz a következő címen: [Aspose weboldal](https://reference.aspose.com/slides/java/).
### Van elérhető próbaverzió az Aspose.Slides for Java-hoz?
Igen, letölthet egy ingyenes próbaverziót innen [itt](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}