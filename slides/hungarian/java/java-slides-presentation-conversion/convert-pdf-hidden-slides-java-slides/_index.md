---
title: Konvertálás PDF-be a Java Slides rejtett diákjaival
linktitle: Konvertálás PDF-be a Java Slides rejtett diákjaival
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan konvertálhat PowerPoint-prezentációkat PDF-formátumba rejtett diákkal az Aspose.Slides for Java segítségével. Kövesse lépésről lépésre útmutatónkat a forráskóddal a zökkenőmentes PDF generáláshoz.
weight: 27
url: /hu/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Konvertálás PDF-be a Java Slides rejtett diákjaival


## Bevezetés a PowerPoint-bemutató PDF-formátumba konvertálásához rejtett diákkal az Aspose.Slides for Java segítségével

Ebből a lépésenkénti útmutatóból megtudhatja, hogyan alakíthat át PowerPoint-prezentációt PDF-formátumba, miközben megőrzi a rejtett diákat az Aspose.Slides for Java használatával. A rejtett diák azok, amelyek nem jelennek meg a szokásos prezentáció során, de beilleszthetők a PDF kimenetbe. A feladat végrehajtásához megadjuk a forráskódot és a részletes utasításokat.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1.  Aspose.Slides for Java Library: Győződjön meg arról, hogy be van állítva az Aspose.Slides for Java könyvtár a Java projektben. Letöltheti a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).

2. Java fejlesztői környezet: Java fejlesztői környezetet kell telepíteni a rendszerére.

## 1. lépés: Importálja az Aspose.Slides-t Java-hoz

Először is importálnia kell az Aspose.Slides könyvtárat a Java projektbe. Győződjön meg arról, hogy hozzáadta a könyvtárat a projekt felépítési útvonalához.

```java
import com.aspose.slides.*;
```

## 2. lépés: Töltse be a PowerPoint-prezentációt

 Először töltse be a PDF-be konvertálni kívánt PowerPoint-prezentációt. Cserélje ki`"Your Document Directory"` és`"HiddingSlides.pptx"` a megfelelő fájl elérési úttal.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## 3. lépés: Konfigurálja a PDF-beállításokat

Konfigurálja a PDF-beállításokat, hogy a rejtett diák a PDF-kimenetben szerepeljen. Ezt úgy teheti meg, hogy beállítja a`setShowHiddenSlides` tulajdona a`PdfOptions` osztályba`true`.

```java
// Példányosítsa a PdfOptions osztályt
PdfOptions pdfOptions = new PdfOptions();
// Adja meg, hogy a létrehozott dokumentum rejtett diákat tartalmazzon
pdfOptions.setShowHiddenSlides(true);
```

## 4. lépés: Mentse el a prezentációt PDF formátumban

 Most mentse a prezentációt PDF-fájlba a megadott beállításokkal. Cserélje ki`"PDFWithHiddenSlides_out.pdf"` a kívánt kimeneti fájlnévvel.

```java
// Mentse a prezentációt PDF-be a megadott beállításokkal
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 5. lépés: Erőforrások tisztítása

Ügyeljen arra, hogy felszabadítsa a prezentáció által használt erőforrásokat, ha végzett vele.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Teljes forráskód PDF-be konvertálásához a Java Slides rejtett diákjaival

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Példányosítsa a PdfOptions osztályt
	PdfOptions pdfOptions = new PdfOptions();
	// Adja meg, hogy a létrehozott dokumentum rejtett diákat tartalmazzon
	pdfOptions.setShowHiddenSlides(true);
	// Mentse a prezentációt PDF-be a megadott beállításokkal
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebből az átfogó útmutatóból megtanulta, hogyan alakíthat át PowerPoint-prezentációt PDF-formátumba, miközben megőrzi a rejtett diákat az Aspose.Slides for Java segítségével. A feladat zökkenőmentes elvégzéséhez lépésről lépésre bemutatott oktatóanyagot adtunk a szükséges forráskóddal együtt.

## GYIK

### Hogyan rejthetek el diákat egy PowerPoint prezentációban?

Ha el szeretne rejteni egy diát egy PowerPoint-prezentációban, kövesse az alábbi lépéseket:
1. Válassza ki az elrejteni kívánt diát a Diarendező nézetben.
2. Kattintson a jobb gombbal a kiválasztott diára.
3. A helyi menüből válassza a "Dia elrejtése" lehetőséget.

### Programozottan megjeleníthetem a rejtett diák elrejtését az Aspose.Slides for Java alkalmazásban?

 Igen, programozottan felveheti a rejtett diák elrejtését az Aspose.Slides for Java alkalmazásban a következő beállításával`Hidden` tulajdona a`Slide` osztályba`false`. Íme egy példa:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Cserélje le a slideIndexet a rejtett dia indexére
slide.setHidden(false);
```

### Hogyan tölthetem le az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java letölthető az Aspose webhelyéről. Meglátogatni a[Aspose.Slides for Java letöltési oldal](https://releases.aspose.com/slides/java/) hogy megszerezze a legújabb verziót.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
