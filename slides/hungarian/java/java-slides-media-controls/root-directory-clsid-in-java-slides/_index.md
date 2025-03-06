---
title: Root Directory ClsId a Java Slides-ben
linktitle: Root Directory ClsId a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthatja be a ClsId gyökérkönyvtárat az Aspose.Slides programban Java prezentációkhoz. Testreszabhatja a hiperhivatkozás viselkedését a CLSID segítségével.
weight: 10
url: /hu/java/media-controls/root-directory-clsid-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Root Directory ClsId a Java Slides-ben


## Bevezetés a ClsId gyökérkönyvtár beállításába az Aspose.Slides for Java programban

Az Aspose.Slides for Java programban beállíthatja a gyökérkönyvtár ClsId azonosítóját, amely a CLSID (osztályazonosító), amely az alkalmazás megadására szolgál, amelyet a prezentációban található hiperhivatkozások aktiválásakor gyökérkönyvtárként használnak. Ebben az útmutatóban lépésről lépésre végigvezetjük, hogyan kell ezt megtenni.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Slides for Java könyvtár hozzáadva a projekthez. Letöltheti innen[Aspose.Slides a Java dokumentációhoz](https://reference.aspose.com/slides/java/).
- Java fejlesztéshez beállított kódszerkesztő vagy integrált fejlesztési környezet (IDE).

## 1. lépés: Hozzon létre egy új prezentációt

Először is hozzunk létre egy új bemutatót az Aspose.Slides for Java segítségével. Ebben a példában egy üres prezentációt fogunk létrehozni.

```java
// Kimeneti fájl név
String resultPath = "your_output_path/pres.ppt"; // Cserélje ki a "saját_kimeneti_útvonal" értéket a kívánt kimeneti könyvtárra.
Presentation pres = new Presentation();
```

 fenti kódban meghatározzuk a kimeneti prezentációs fájl elérési útját, és létrehozunk egy újat`Presentation` tárgy.

## 2. lépés: Állítsa be a Root Directory ClsId

 A gyökérkönyvtár ClsId beállításához létre kell hoznia egy példányt`PptOptions` és állítsa be a kívánt CLSID-t. A CLSID azt az alkalmazást jelöli, amely a hiperhivatkozás aktiválásakor gyökérkönyvtárként lesz használva.

```java
PptOptions pptOptions = new PptOptions();
// Állítsa a CLSID-t "Microsoft Powerpoint.Show.8"-ra
pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
```

 A fenti kódban létrehozunk egy`PptOptions` objektumot, és állítsa be a CLSID-t a „Microsoft Powerpoint.Show.8” értékre. Lecserélheti a gyökérkönyvtárként használni kívánt alkalmazás CLSID azonosítójára.

## 3. lépés: Mentse el a prezentációt

Most mentsük el a prezentációt a Root Directory ClsId készlettel.

```java
// Prezentáció mentése
pres.save(resultPath, SaveFormat.Ppt, pptOptions);
```

 Ebben a lépésben elmentjük a prezentációt a megadottra`resultPath` a ... val`PptOptions` korábban hoztuk létre.

## 4. lépés: Tisztítás

 Ne felejtse el megsemmisíteni a`Presentation` tiltakozik az allokált erőforrások felszabadítása ellen.

```java
if (pres != null) {
    pres.dispose();
}
```

## A Java Slides gyökérkönyvtárának ClsIdjének teljes forráskódja

```java
// Kimeneti fájl név
String resultPath = "Your Output Directory" + "pres.ppt";
Presentation pres = new Presentation();
try {
	PptOptions pptOptions = new PptOptions();
	//állítsa be a CLSID-t "Microsoft Powerpoint.Show.8"-ra
	pptOptions.setRootDirectoryClsid(UUID.fromString("64818D10-4F9B-11CF-86EA-00AA00B929E8"));
	// Prezentáció mentése
	pres.save(resultPath, SaveFormat.Ppt, pptOptions);
} finally {
	if (pres != null) pres.dispose();
}
```

## Következtetés

Sikeresen beállította a ClsId gyökérkönyvtárat az Aspose.Slides for Java fájlban. Ez lehetővé teszi, hogy megadja azt az alkalmazást, amely gyökérkönyvtárként lesz használva, amikor a hiperhivatkozásokat aktiválják a prezentációban. A CLSID-t egyedi igényei szerint testreszabhatja.

## GYIK

### Hogyan találhatom meg a CLSID-t egy adott alkalmazáshoz?

Egy adott alkalmazás CLSID-jének megkereséséhez tekintse meg az alkalmazás fejlesztője által biztosított dokumentációt vagy forrásokat. A CLSID-k a COM-objektumokhoz rendelt egyedi azonosítók, és jellemzően az egyes alkalmazásokra jellemzőek.

### Beállíthatok egyéni CLSID-t a gyökérkönyvtárhoz?

 Igen, beállíthat egyéni CLSID-t a gyökérkönyvtárhoz, ha megadja a kívánt CLSID-értéket a segítségével`setRootDirectoryClsid` módszert, ahogy a kódpéldában is látható. Ez lehetővé teszi, hogy egy adott alkalmazást használjon gyökérkönyvtárként, amikor a hiperhivatkozások aktiválva vannak a prezentációban.

### Mi történik, ha nem állítom be a gyökérkönyvtár ClsId-jét?

Ha nem állítja be a Root Directory ClsId értéket, az alapértelmezett viselkedés a bemutató megnyitásához használt megjelenítőtől vagy alkalmazástól függ. A hiperhivatkozások aktiválásakor saját alapértelmezett alkalmazását használhatja gyökérkönyvtárként.

### Módosíthatom az egyes hiperhivatkozások gyökérkönyvtárának ClsIdjét?

Nem, a Root Directory ClsId jellemzően a prezentáció szintjén van beállítva, és a prezentáción belüli összes hivatkozásra vonatkozik. Ha különböző alkalmazásokat kell megadnia az egyes hiperhivatkozásokhoz, előfordulhat, hogy ezeket a hivatkozásokat külön kell kezelnie a kódban.

### Vannak-e korlátozások a használható CLSID-ekre vonatkozóan?

A használható CLSID-eket általában a rendszerre telepített alkalmazások határozzák meg. Olyan CLSID-eket kell használnia, amelyek megfelelnek a hiperhivatkozások kezelésére alkalmas érvényes alkalmazásoknak. Ne feledje, hogy érvénytelen CLSID használata váratlan viselkedést eredményezhet.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
