---
title: Diák konvertálása PDF-be a Java Slides jegyzeteivel
linktitle: Diák konvertálása PDF-be a Java Slides jegyzeteivel
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan konvertálhat PowerPoint diákat PDF-be jegyzetekkel Java nyelven az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató Java fejlesztőknek. Javítsa a prezentáció megosztását.
weight: 19
url: /hu/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diák konvertálása PDF-be a Java Slides jegyzeteivel


## Bevezetés a diák PDF formátumba konvertálásához a jegyzetekkel Java nyelven

digitális prezentációk világában értékes szolgáltatás a diák PDF formátumba konvertálása a kísérő megjegyzésekkel. A Java-fejlesztők ezt az Aspose.Slides for Java könyvtár segítségével érhetik el, amely robusztus eszközkészletet biztosít a PowerPoint-prezentációk programozott használatához. Ebben a lépésenkénti útmutatóban megvizsgáljuk, hogyan konvertálhat diákat PDF formátumba jegyzetekkel a Java és az Aspose.Slides for Java használatával.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

Most, hogy megvan a vázlatunk, lépjünk bele a megvalósításba lépésről lépésre.
## 1. lépés: A projekt beállítása

Először hozzon létre egy Java-projektet, és adja hozzá az Aspose.Slides for Java könyvtárat a projekt függőségeihez.

## 2. lépés: A prezentáció betöltése

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 3. lépés: Új prezentáció létrehozása

```java
Presentation auxPresentation = new Presentation();
```

## 4. lépés: Diák másolása

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## 5. lépés: A dia méretének beállítása

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. lépés: A PDF-beállítások konfigurálása

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## 7. lépés: Mentés PDF-ként

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Teljes forráskód a diák PDF formátumba konvertálásához a Java Slides jegyzeteivel

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítson egy bemutató objektumot, amely egy prezentációs fájlt képvisel
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Dia típusának és méretének beállítása
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), bemutató.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan konvertálhat diákot PDF-formátumba jegyzetekkel Java nyelven az Aspose.Slides for Java segítségével. Kitértünk a projekt beállítására, a prezentáció betöltésére, új prezentáció létrehozására, diák másolására, a dia méretének beállítására, a PDF opciók konfigurálására, végül a prezentáció PDF formátumban történő mentésére, jegyzetekkel.

## GYIK

### Hogyan telepíthetem az Aspose.Slides for Java programot?

Az Aspose.Slides for Java telepítéséhez kövesse az alábbi lépéseket:
1.  Töltse le a könyvtárat innen[itt](https://releases.aspose.com/slides/java/).
2. Adja hozzá a JAR-fájlt a Java-projekt osztályútvonalához.

### Testreszabhatom a jegyzetek pozícióját a generált PDF-ben?

 Igen, testreszabhatja a jegyzetek pozícióját a`NotesPositions` enum a PDF beállítások között. Ebben az oktatóanyagban azt állítjuk be`BottomFull`, de felfedezhet más lehetőségeket is.

### Vannak-e licenckövetelmények az Aspose.Slides for Java használatához?

Igen, az Aspose.Slides for Java egy kereskedelmi célú könyvtár, és előfordulhat, hogy licencet kell szereznie az éles használathoz. Az engedélyezéssel kapcsolatos részletekért látogasson el az Aspose webhelyére.

### Konvertálhatok több diát egyszerre?

Biztosan! A prezentáció diákjait végigpörgetheti, és az új prezentációba klónozhatja, így egyszerre több diát konvertálhat PDF formátumba jegyzetekkel.

### Hol találok további dokumentációt az Aspose.Slides for Java-hoz?

 Az Aspose.Slides for Java részletes dokumentációját a következő oldalon találja:[Aspose.Slides for Java API Reference](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
