---
"date": "2025-04-23"
"description": "Tanuld meg, hogyan szabhatod testre a hivatkozások színeit PowerPoint-bemutatókban az Aspose.Slides for Python segítségével. Javítsd diákat személyre szabott hivatkozásstílusokkal hatékonyan."
"title": "Hogyan állítsunk be hiperhivatkozás színeit PowerPointban az Aspose.Slides for Python használatával"
"url": "/hu/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan állítsunk be hiperhivatkozás színeit PowerPointban az Aspose.Slides for Python használatával

## Bevezetés

A PowerPoint-bemutatóid vizuális megjelenésének javítása a hiperhivatkozások színeinek testreszabásával egyszerűen elvégezhető az Aspose.Slides Pythonhoz készült verziójával. Ez az útmutató végigvezet a hiperhivatkozások meghatározott színekkel történő beállításán a diákon Python használatával.

**Amit tanulni fogsz:**
- Hogyan állítsunk be egy hiperhivatkozás színét szöveges alakzatokban a PowerPointban.
- A vizuálisan vonzó prezentáció létrehozásának lépései.
- Az Aspose.Slides for Python főbb jellemzői, amelyek megkönnyítik ezt a testreszabást.

Mielőtt belekezdenénk, nézzük át a szükséges előfeltételeket.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a környezete a következőkkel felkészült:
- **Könyvtárak és verziók:** Telepítés `aspose.slides` könyvtár. Győződjön meg róla, hogy a Python telepítve van a gépén.
- **Környezeti beállítási követelmények:** Ez az oktatóanyag feltételezi a Python alapvető beállítását Windows, Mac vagy Linux rendszeren.
- **Előfeltételek a tudáshoz:** A Python programozásban való jártasság előnyt jelent.

## Az Aspose.Slides beállítása Pythonhoz

Az Aspose.Slides Pythonhoz való használatának megkezdéséhez telepítse a csomagot a pip segítségével:

```bash
pip install aspose.slides
```

**Licenc megszerzésének lépései:**
- **Ingyenes próbaverzió:** Tölts le egy próbaverziót innen [Az Aspose kiadási oldala](https://releases.aspose.com/slides/python-net/).
- **Ideiglenes engedély:** Kérjen ideiglenes engedélyt a [vásárlási oldal](https://purchase.aspose.com/temporary-license/) kiterjesztett hozzáféréshez.
- **Vásárlás:** A funkciók korlátozás nélküli feloldásához érdemes megfontolni a licenc megvásárlását a következő webhelyről: [Az Aspose vásárlási oldala](https://purchase.aspose.com/buy).

**Alapvető inicializálás:**
A telepítés és a licencelés után importáld az Aspose.Slides fájlt a szkriptedbe:

```python
import aspose.slides as slides
```

## Megvalósítási útmutató

Ez a szakasz végigvezet a hivatkozások színeinek beállításán egy PowerPoint-bemutatóban.

### Hivatkozás színének beállítása funkció

#### Áttekintés

A szöveges alakzatokba ágyazott hiperhivatkozások színét az Aspose.Slides for Python segítségével szabhatod testre. Ez javítja az olvashatóságot és a vizuális vonzerőt.

##### 1. lépés: Új prezentáció létrehozása

Hozz létre egy prezentációs példányt:

```python
with slides.Presentation() as presentation:
    # A kódod itt
```

##### 2. lépés: Alakzat hozzáadása szöveggel

Adjon hozzá egy téglalap alakzatot az első diához, és illesszen be egy hivatkozást tartalmazó szöveget.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### 3. lépés: Hiperhivatkozás tulajdonságainak beállítása

Rendeld hozzá a hiperhivatkozást és állítsd be a színét. `hyperlink_click` A tulajdonság meghatározza, hogy a hivatkozásnak hová kell navigálnia kattintáskor.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Állítsa be a színforrást a hiperhivatkozás részformátumához, és határozza meg a kitöltés típusát és színét.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### 4. lépés: Mentse el a prezentációt

Mentse el a prezentációt egy megadott könyvtárba:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}