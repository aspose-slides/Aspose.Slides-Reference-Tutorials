---
title: Hozzáférés a PowerPoint beépített tulajdonságaihoz
linktitle: Hozzáférés a PowerPoint beépített tulajdonságaihoz
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan érheti el a PowerPoint beépített tulajdonságait az Aspose.Slides for Java segítségével. Ez az oktatóanyag végigvezeti Önt a szerző visszakeresésén, a létrehozás dátumán és egyebeken.
weight: 10
url: /hu/java/java-powerpoint-properties-management/access-built-in-properties-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hozzáférés a PowerPoint beépített tulajdonságaihoz

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan érheti el a PowerPoint-prezentációk beépített tulajdonságait az Aspose.Slides for Java segítségével. Az Aspose.Slides egy hatékony könyvtár, amely lehetővé teszi a Java fejlesztők számára, hogy programozottan dolgozzanak PowerPoint prezentációkkal, és zökkenőmentesen végezzenek el olyan feladatokat, mint például a tulajdonságok olvasása és módosítása.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti innen[itt](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Töltse le és telepítse az Aspose.Slides for Java-t innen[ez a link](https://releases.aspose.com/slides/java/).

## Csomagok importálása
Először is importálnia kell a szükséges csomagokat a Java projektbe. Adja hozzá a következő importálási utasítást a Java fájl elejéhez:
```java
import com.aspose.slides.IDocumentProperties;
import com.aspose.slides.Presentation;

```
## 1. lépés: Állítsa be a prezentációs objektumot
Kezdje a Prezentáció objektum beállításával, amely azt a PowerPoint-prezentációt képviseli, amellyel dolgozni szeretne. A következőképpen teheti meg:
```java
// A bemutató fájlt tartalmazó könyvtár elérési útja
String dataDir = "path_to_your_presentation_directory/";
// Példányosítsa a Prezentáció osztályt
Presentation pres = new Presentation(dataDir + "your_presentation_file.pptx");
```
## 2. lépés: Nyissa meg a Dokumentum tulajdonságait
A Presentation objektum beállítása után az IDocumentProperties felület segítségével érheti el a bemutató beépített tulajdonságait. A következőképpen kérhet le különféle tulajdonságokat:
### Kategória
```java
System.out.println("Category : " + documentProperties.getCategory());
```
### Jelenlegi állapot
```java
System.out.println("Current Status : " + documentProperties.getContentStatus());
```
### Készítés ideje
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
### Utoljára módosította
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
#### Bemutató formátum
```java
System.out.println("Presentation Format : " + documentProperties.getPresentationFormat());
```
### Utolsó nyomtatás dátuma
```java
System.out.println("Last Print Date : " + documentProperties.getLastPrinted());
```
### Megosztva a gyártók között
```java
System.out.println("Is Shared between producers : " + documentProperties.getSharedDoc());
```
### Tantárgy
```java
System.out.println("Subject : " + documentProperties.getSubject());
```
### Cím
```java
System.out.println("Title : " + documentProperties.getTitle());
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan érheti el a PowerPoint prezentációk beépített tulajdonságait az Aspose.Slides for Java segítségével. A fent vázolt lépések követésével könnyedén lekérheti a különféle tulajdonságokat, például a szerzőt, a létrehozás dátumát és a címet programozottan.
## GYIK
### Módosíthatom ezeket a beépített tulajdonságokat az Aspose.Slides for Java segítségével?
Igen, módosíthatja ezeket a tulajdonságokat az Aspose.Slides segítségével. Egyszerűen használja az IDocumentProperties felület által biztosított megfelelő beállító metódusokat.
### Az Aspose.Slides kompatibilis a PowerPoint különböző verzióival?
Az Aspose.Slides a PowerPoint verziók széles skáláját támogatja, biztosítva a kompatibilitást a különböző platformokon.
### Lekérhetek egyéni tulajdonságokat is?
Igen, a beépített tulajdonságok mellett egyéni tulajdonságokat is lekérhet és módosíthat az Aspose.Slides for Java segítségével.
### Az Aspose.Slides kínál dokumentációt és támogatást?
 Igen, átfogó dokumentációt találhat, és elérheti a támogatási fórumokat a webhelyen[Aspose honlapja](https://reference.aspose.com/slides/java/).
### Elérhető az Aspose.Slides for Java próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
